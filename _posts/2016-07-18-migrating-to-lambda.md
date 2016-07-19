---
layout: post
title: Migrating to AWS Lambda
---

For a number of years I've had my own hosted website which I use to serve a wordpress site, host files and private git repos, and run cron jobs. My hosting provider (hostmonster) isn't awesome, but is adequate. I can ssh into my box and do stuff. I have to set up cron stuff through the web-portal, which is painful. I just successfully migrated from wordpress to Jekyll / Github pages. I've moved my domain hosting to a different provider. The only remaining functionality I need to replicate is a regular reminder email containing the sermon passage for the upcoming week.

I've already proved that AWS SES can send the email more securely than my private hosting (encrypted). However, I need to run some small code to generate the email and send it to a recipient list every morning. It looks like I can use AWS Lambda for this. Lambda supports NodeJS, Java, and Python natively. Sadly, no love for Ruby (although people have made it work). Since I'm trying to up my JS chops, it's probably a worthwhile exercise to rewrite my Ruby program in JS anyway.

One concern is whether my Lambda function will have access to a few static files (list of upcoming passages, list of recipients) in addition to the code. It appears you can give Lambda a ZIP file or an S3 location, so I should be able to access a few static files. You can trigger Lambda events as scheduled cron-style jobs. It should have everything I need!

I'll probably use nodemailer to send the email. It looks like it [shouldn't be a problem](https://aws.amazon.com/blogs/compute/nodejs-packages-in-lambda/) to pull in that npm package as well.
