---
layout: post
title: "What Is Equifax? What Could It Have Affected?"
categories: ['cybersecurity']
date: 2017-09-11T02:26:18-04:00
---

Someone asked me the following in an email:

> What is Equifax? What could it have affected?

Here is my response, so maybe a few more people can see it:

### What is Equifax?

Equifax is a credit reporting agency. They are one of the three (Experian and
TransUnion are the others). Credit reporting agencies track insanely detailed
financial information about every US citizen, and give them ratings that
determine what interest rates they pay on loans and credit cards. When a bank
checks you credit score, they check with one or more of the three agencies.

### What could it have effected?

**tldr;** Even though you don't know who Equifax is, they could have just
leaked your social security number, driver's license number and/or credit card number.

To collect their detailed information, all three credit reporting agencies
track your SSN, credit card numbers, bank account numbers, and other PII. Since
they need to be able to give a credit score for anyone, they have your
information even if you haven't heard of them before, because every bank and
credit card company reports to them (yeah, you read that right). So they have
everyone's information, and a lot of it -- they are a GOLDMINE for hackers.

Equifax had a huge security breach the other day, resulting in definitely
hundreds of thousands of leaks, and possibly 140 million leaks (the larger
figure is always quoted in media reports, but is the number of "maybe
affected").

### What should you do?

(You didn't ask but I'm guessing you want to know.) First, check your CapCom,
credit card, and whatever other accounts you have, to see if someone is using
them. If they are, call immediately and report it as fraud, so the company can
take action against it (credit card companies and banks do this frequently, and
should be able to remedy the situation quickly). Second, check out
[equifaxsecurity2017.com](equifaxsecurity2017.com) to determine if you are one of the affected people. If
you are "definitely not affected" you are lucky, around half of the US is in
the "maybe affected category, like me.

If you are in the "maybe" category, you probably want to put a credit freeze on
your account. It will only take 10-15 minutes of your time, but makes it harder
to open credit in your name. This will add an extra step the next time you take
out a loan (you will need to unfreeze your credit), but will make it much
harder for hackers to use the information to open a new account. I froze mine
with [Experian](https://www.experian.com/freeze/center.html). Make sure you
generate your own random PIN. According to this reddit
[post](https://www.reddit.com/r/security/comments/6z4mrp/equifaxs_security_pin_is_a_timestamp/),
Equifax, and possibly other credit reporting agencies are generating PINs with
timestamps, which provides virtually no security at all. To generate a 10-digit
pin (always go for the most digits possible) you can use this random number
[generator](https://www.random.org/integers/?num=10&min=1&max=9&col=10&base=10&format=html&rnd=new).

I hope this helps!

