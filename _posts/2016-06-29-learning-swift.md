---
layout: post
title: First Impressions of Swift
---

This morning I began working through the [swift tutorial](https://developer.apple.com/library/ios/referencelibrary/GettingStarted/DevelopiOSAppsSwift/Lesson1.html).

The playground is neat.

The synatx is familiar. The `let` and `var` keywords are comfortable coming from ES6. Built in optionals are nice. The weirdest thing so far is the optional binding in if statements. For example:

{% highlight swift %}
if let name = optionalName {
    greeting = "Hello, \(name)"
}
{% endhighlight %}

I guess it saves you the unboxing shuffle you'd otherwise do, e.g in Java:

{% highlight java %}
if (optionalName.isPresent()) {
  String name = optionalName.get();
  greeting = "Hello, " + name;
}
{% endhighlight %}

It's interesting how Swift differentiates between structs and classes by how they are passed as arguments. Structs are
pass by value and classes/objects are pass by value. Structs can have functions and initializers, just like normal
classes. However, structs aren't compatible with inheritance or type casting. Here's an example struct in Swift.

{% highlight swift %}
struct Card {
    var rank: Rank
    var suit: Suit
    func simpleDescription() -> String {
        return "The \(rank.simpleDescription()) of \(suit.simpleDescription())"
    }
}
let threeOfSpades = Card(rank: .Three, suit: .Spades)
let threeOfSpadesDescription = threeOfSpades.simpleDescription()
{% endhighlight %}



