---
layout: post
title: Why ProtonMail will not save you
author: jelle
---

I want to mention at the start of this post that I'm not saying that ProtonMail is less secure than other providers or that you should not use them. I used ProtonMail myself for a while and I believe they are a privacy friendly company. I also think it's good that they open sourced a bunch of their software.

That being said, I will argue in this post why ProtonMail will not "secure your communications", in the way you might think they will. The email system is quite old and needs to stay compatible for the most part, which means not everything can be totally secured.


## How email works

Most of the time when you send an email, it goes through two servers: your email provider and the recipients email provider. The email follows a path like this:

![Diagram showing how TLS only protects from server to server and not from end to end](/assets/img/protonmail/ProtonMailSend-2.png)

This is nothing special, ProtonMail works like any other email provider. This is because it has to, otherwise existing email users wouldn't be able to receive your email from ProtonMail! The way email servers communicate with each other is called the Simple Mail Transfer Protocol. This protocol was designed in 1982, and at that time the protocol was completely unencrypted. Everyone who was listening on the line between the two servers would be able to read the data coming through. Nowadays many servers support TLS (although it's not used totally everywhere), which means that data between the servers can only be read by the two servers.

So now let's look at receiving email. This is where ProtonMail claims their security lies. ProtonMail says all your email is stored encrypted on their server, which makes the last step in the line a bit different. Once the emails are stored on the ProtonMail server, they can only be decrypted by your keys (which is based on your password). That means if a hacker is able to steal the drives in the server, or if the secret service raids the datacenter and takes the server away, they will not be able to read your emails that are stored on them.

![Diagram showing how Protonmail creates a secure connection to the end user](/assets/img/protonmail/ProtonMailReceive-3.png)

When you request your emails from the server, you receive them encrypted and nobody that listens on that line is able to read them. Only when you receive them in your browser will your computer decrypt them so you can read them. 

I think this is a pretty interesting innovation, because it protects the data on the server against being stolen. This is basically the only thing ProtonMail protects your mail against though! The recipient's provider will still be able to read the emails that go through their server, and ProtonMail also has this ability. Only after ProtonMail has encrypted your email and thrown away the original is the data actually stored securely.

This also means that ProtonMail could be coerced into saving all email you receive **unencrypted**, alongside an encrypted version so you don't notice anything. 


## End to end encryption

ProtonMail claims to support "End-to-End Encryption". I think this is a dangerous claim to make because normally the "end-to-end" refers to the two users that are using the servers, and by default emails sent via ProtonMail are not encrypted end-to-end in this way. It's possible to use PGP encryption using ProtonMail, but this requires extra setup and your recipient knowing how to use it.

If we look at back at the previous diagrams, end-to-end encryption would mean that the data you send may still go through the servers to get to your recipient, but along the way nobody would be able to read it. You could think of this as a "tunnel" which runs along the servers of the mail providers, but does not allow them to look into it. 

This is not the case with ProtonMail, because as I said earlier, the existing email infrastructure does not support encryption this way. Newer communication systems, like the messaging app Signal, have created their own protocols to allow actual end-to-end encryption.

The claim that ProtonMail makes could lead you to believe their email service works the same way as an app like Signal does, but in actuality it works like described above. 


## What's the solution?
Probably not using email at all (for anything that's confidential). If you really care about encrypted secure communication you **should not** use email. 

The reality is that you probably need to use email, and in that case you should choose an email provider that you trust. If that's ProtonMail, go ahead. The encryption ProtonMail provides to your data at rest is a step up from other providers who store all data unencrypted. You still need to have trust in ProtonMail—you need to trust them to not store alternative copies, and have their access control well restricted—but if you trust them to do that correctly you can go with them. I still take issue with some of their marketing speak, and I find the price too high for the (for me) small benefit they provide. Personally I use mailbox.org, and I have an email server setup that I host myself (because well, I trust me!). 

Another thing that might help is using PGP, this helps somewhat because the body of the email will be end-to-end encrypted, given that the other user knows how to decrypt it. Here is a good support article you can follow if you want to try PGP with thunderbird: [https://support.mozilla.org/en-US/kb/digitally-signing-and-encrypting-messages](https://support.mozilla.org/en-US/kb/digitally-signing-and-encrypting-messages)
