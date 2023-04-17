---
layout: post
title: Using Jekyll in 2021
category: Productivity
date: 2021-06-16
---

![avatar](/images/avatar.jpg) I've always been drawn to blogging/writing as a way to share my ideas and a document how life is changing in the new normal but never got round to it. One of my main problems is that all the CMS solutions I've tried always left me with the impression that they were slow, ugly and expensive.

It was either browsing reddit or reading Hacker news a few years back but I stumbled across Jekyll - the static site generator back in 2016. I was immediately drawn to it because:

* It felt lightweight for a blogging tool and I had a general grasp of how it's all put together with Ruby.

* The [html5up](https://html5up.net/) static pages I'd used in the past on other projects had been converted into themes that I could repurpose

* If you hosted it on [Github pages](https://pages.github.com/), it was free and I'd be able to keep this up on the internet forever.

## How to update Jekyll to run your on your MacBook in 2021

Whilst I'd used it on past projects, I wasn't expecting to be hit with so many errors and needing to read documentation. So if you try this:

``` ruby
  gem install bundler jekyll
  jekyll new my-awesome-site
  cd my-awesome-site
  bundle exec jekyll serve
# => Now browse to http://localhost:4000
```

You just end up being met errors in the terminal. It got pretty stressful towards the end where I considered just buying a new laptop in order to just 'start again' but with the help of Reddit, Github and Stack Overflow, I've found a way to update my machine so that I can run jekyll on a localhost.

>  ***Disclaimer, I'm not exactly technical so if anyone knows how to do this properly, let me know***

1. Make sure you're working on BigSur (I'm working on 11.4)

2. Update xcode on your machine to 12.5 via the appstore. The update froze a few times so force quitting and restaring the machine seemed to work.

3. **Open xcode to accept the terms and conditions**. Something I kept forgetting to do.

4. Open terminal and install Homebrew and Ruby (aiming to get v3.0.1 or higher) like so:

   ```ruby
   # Install Homebrew
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   
   # Install Ruby
   brew install ruby
   ```

5. Add the brew ruby and gems path to your shell configuration. Terminal has moved from bash to a zsh terminal. I have no idea what that means but I copied this:

   ```ruby
   echo 'export PATH="/usr/local/opt/ruby/bin:/usr/local/lib/ruby/gems/3.0.0/bin:$PATH"' >> ~/.zshrc
   ```

6. Install Jekyll:

   ```ruby
   gem install bundler jekyll
   ```

7. Install the webricks dependancy. I think this is to get your localhost up and running

   ``` 
   gem install webrick
   ```

8. Restart just to be safe 🤷🏽‍♂️

9. Update gems:

   ```
   gem update system
   ```

8. Change directory and run jekyll serve so that you can check any errors so that you can google how to resolve from there.
9. If you're like me using an older theme, then go back into it and pray that it works

## Key things to remember:

- Check the config and the gem file for any syntax issues
- Trying not to cry over how slow the process is.
- Pray that you never have to do this process again.

## Final thoughts

This definately isn't the best way approach but it worked for me. I'm sure that I'll be able to revisit this with the exact instructions to make it easier for people to use the platform.