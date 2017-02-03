---
layout: post
title: Working with Amazon AWS S3
---

As part of the process of migrating off a personal hosting service and onto Amazon AWS and Github, I am moving various configurations to S3. I plan to store configuration information for some small scripts and configuration that run in AWS Lambda. I am also piping emails to my personal domain to an S3 bucket. In summary, I would like to accomplish the following:

 1. Read files from my emails bucket
 2. Publish code to an S3 bucket (from CLI or npm)
 3. Publish configuration to a separate S3 bucket (from CLI or npm)
 4. Read configuration from S3 bucket in node-based lambda script

It was not immediately clear to me how I would read those emails. I could see the bucket, and the names of the files, but couldn't view the content through the AWS S3 web interface.

I started trying to do this in node, but soon feel back to the CLI as it seems better documented and easier to experiment with as I learn the S3 model. After following the [setup steps](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html), and having some initial success with `aws s3 ls`.

{% highlight bash %}
└─ $ ▶ aws s3 ls
2016-09-10 16:43:26 emails-bucket
2016-02-02 11:05:51 config-bucket
2016-07-23 11:27:30 code-bucket
{% endhighlight %}

After looking through the list of [S3 commands](http://docs.aws.amazon.com/cli/latest/reference/s3/) I realized S3 is incredibly simple. It's like a stripped down remote file share. You can create buckets, which contain files. You can copy files in and out of buckets, delete them, and move them, but that's it. There is no reading from S3, or piping the contents elsewhere. There is only copy in and copy out. I suppose the closest you get to directly interacting with S3 is the `presign` command, which gives you a time-limited URL from which the resource can be accessed.

### Reading files from an S3 bucket

Reading contents of my emails bucket looks like this.

{% highlight bash %}
└─ $ ▶ aws s3 sync s3://emails-bucket .
download: s3://emails-bucket/file1 to ./file1
download: s3://emails-bucket/file2 to ./file2
{% endhighlight %}

The `sync` command is like primitive `rsync` or sophisticated `cp`; it copies everything new from source to destination.

### Reading configuration from S3 bucket in a node-based lambda script

If I want to separate code and configuration into different S3 buckets and access configuration dynamically from the config bucket, I can either copy the files locally or make them temporarily accessible via a `presign` URL. Alternately, I could store config and code in the same S3 bucket. That is probably better. Ideally I'd like to keep canonical configuration outside of the code repository. Perhaps I could have a dedicated canonical S3 bucket for configuration, but merge that into the code during the build step.

My main goal of keeping config and code separate is to avoid having sensitve config (e.g. friends' email addresses) in my source repository, and to allow updates to configuration without needing to redeploy code. The easiest solution that gets most of those things is to have a separate bucket for configuration, and a deploy script that fetches config from S3 and replaces the fake config included in the repo.

Bummer. Lambda requires zips from S3, and it still seems to require manual upload every time it needs to be updated. Ah well.
