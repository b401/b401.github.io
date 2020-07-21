---
layout: post
title: "Using CSS to hide evil things"
style: csshack
date: 2020-07-21
---


## Topic


Good evening neighbors,  
<br />
Quickie:  
Today I'd like to talk to you about a thing everyone does but no one pays a lot of 
attention to it.  
> __Copy/Pasting things from the internet into your terminal__

One would think what could possibly happen if I just copy this code from some
website I've found to fix my issue on the server.  
Well lets see...


## What you see isn't what you get

Let's take the following example:
<br />
Please use the textarea to paste the content into.  

{% include csshack.html %}

<img src="/assets/images/pikachu.jpg" style="max-width:40%">

<br />

While this attack isn't highly sophisticated I can think of multiple sysadmins off the top of my head who
would own their own server if they would be targeted by this attack.


## Craft
__HTML__
```
<span id="select">
    Copy/Paste to fix your
    <p id="danger">
        <br />
            rm -rf / # all your base are belong to us
        <br />
    </p>
    server
</span>
```

__CSS__
```
span#select{
    color: blue;
    user-select: all;
}
p#danger{
    display: inline-block;
    font-size:0px;
}
```

"display:inline-block" is used that the <br/> tags don't create a newline in html but act
as newline in a bash terminal which is equivalent as hitting the enter key. (doesn't work with zsh)  

"font-site:0px" is used to hide the text.

"user-select: all" was just added for convenience and could even be
suspicious to the trained eye.

## Why not JS/HTML5?
Of course it would be easier to copy any content to the user clipboard with
HTML5/JS. But I've wanted to share some CSS tricks with you guys. There's also
the CSS keylogger which I may share somewhere down the line.

## Conclusion
I've just wanted to share this piece of unlikely tech which could prevent you
from executing malicious code on your servers. :)

Also don't run around and just copy/paste stuff in your terminal.


### Likelihood
Highly unlikely ヽ(ﾟ_ﾟ)ノ

<br />

Thanks for reading. 
