---
layout: post
title: Instagram Information Flow
keywords: ['cybersecurity','information flow','leak']
categories: ['cybersecurity']
date: 2017-04-13 00:38:32 -0500
excerpt_separator: <!-- EXCERPT -->
---

Services like Twitter and Instagram offer private accounts. Labeled with
a comforting digital padlock, these accounts claim to protect your data from
the public -- only people you approve can see your information. The digital
lock is comforting, but how much does it mean? How private is the data in
a private account? Less private than you may think.

<!-- EXCERPT -->

The weakness of private profiles became apparent to me a couple of weeks ago
when I received an email from Instagram with a photo from a private account
that I had not even requested to follow. To clarify: Instagram *sent me*
a photo of someone's family from a private account, whose owner had never
approved me to see it.

*What???*

Your first reaction might be something like "What are those idiots at Instagram
up to!" But I assure you, they are not incompetent, nor are they nefarious.
They are simply neglecting the importance of *information flow* (explained
below) in privacy.

Using this bug as a motivating example<sup><a href="#f1">1</a></sup>, I will
explain why information flow control is so important in guaranteeing user
privacy, why it is ignored, and what we can do about it.

## The Bug

Recently, I deleted the Instagram app from my phone. Only a few days later,
Instagram sent me an email trying to get me to return to using their service by
sending me an email with photos from my friends. The email also included photos
from suggested friends, one of whom had a private account. We'll call him Bob.

Here are the important things about how the email dealt with Bob's information:

* The email itself included Bob's profile picture and one image from his
    account, in the same format as accounts that I followed.
* When I clicked on his account name, I was brought to a page that said "This
    account is private." This page showed his profile picture and account name,
    but not any of his photos.
* When I clicked on the image itself, I was led to a "Sorry, this page isn't
    available" page.

Instagram did a good job hiding Bob's private images when I tried to directly
request them but the email itself still contained the image. Why is Instagram
able to block me from seeing such an image, but not able to stop it from being
emailed to me?

The answer lies in the difference between *access control* and *information
flow control*.

## Access Control and Information Flow Control

Both access control and information flow control describe mechanisms for
protecting "private" information, information that should be visible to some
parties but invisible to others.

## What makes information flow tough?

All of these social media services do a good job with access control - if
I click on private profile in the app, I won't be able to see any of its posts.
But, that is only one way to see those posts. When companies start adding on
extra services - friend recommendations, email digests, top stories - they
often fail to maintain the expected level of privacy.

## How do we fix it?

Relying on one programmer, let alone all of them, to write bug-free code is
unreasonable. We need a more systematic solution that will reduce the small
human errors that create unintended information flows. One way to do this is to
use the type system of a programming language to provide strong guarantees
about the flow of sensitive data.

[JIF](http://www.cs.cornell.edu/jif/) by Andrew Myers is an example of
a language extension that uses "labels" to restrict where sensitive data can
flow. [Jeeves](https://projects.csail.mit.edu/jeeves/) by Jean Yang<sup><a
href="#f2">2</a></sup> is another solution that makes it easier to enforce
information flow policies, through a technique called "policy-agnostic
programming."


## Footnotes

1. <span id="f1"></span>Only a couple of weeks later, another [information flow
   bug](https://jxyzabc.blogspot.com/2017/03/five-research-ideas-instagram-could.html)
   led a reporter to finding FBI Director Comey's Instagram account.
2. <span id="f2"></span>Disclaimer: Jean is the reason I am interested in
   information flow and encouraged me to write this post :)
