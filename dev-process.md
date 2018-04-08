footer: A modern WordPress development workflow - David Darke | [atomicsmash.co.uk](https://www.atomicsmash.co.uk)
slidenumbers: true

# A modern WordPress development workflow

---

![fill](assets/atomicsmash-logo.png)

---

## 8 years ago

![original](assets/spike-island.jpg)

---

## Today

![original](assets/unit-1-15.jpg)

---

### Working with WordPress

![inline](assets/old-dev-process.pdf)

---

[.build-lists: true]

# [fit] What's wrong with this?

* Almost impossible for two developer to work at the same time, (unless they are sat next to each other)
* Dropbox does have a revision system, but only on a per file basis
* Deployments were cumbersome and not traceable
* No real control over servers and hosting
* Nothing was re-usable
* Hours wasted handling development environment differences

---

[.build-lists: true]

## X challenges

* Shared development environment
* Get a reliable deployment method
* Improve hosting

---

![inline](assets/delorean.gif)

---

# [fit] Our shared development environment

---

### Laravel Homestead

![inline](assets/vagrant_homestead.pdf)

---

### Laravel Homestead

> **Laravel Homestead is an official, pre-packaged Vagrant box that provides you a wonderful development environment without requiring you to install PHP, a web server, and any other server software on your local machine.**

&

> **No more worrying about messing up your operating system! Vagrant boxes are completely disposable. If something goes wrong, you can destroy and re-create the box in minutes!**
-- Homestead documentation

---

### The anatomy of 99.9999% of WordPress Websites

![inline](assets/anatomy_of_wordpress.pdf)

#### What makes any WordPress site unique?

---

### Think of your Wordpress website as a web application.
### It's just a dependancy

![inline](assets/anatomy_of_wordpress.pdf)

---

## Your theme and custom plugin code

### Get your code into GIT... NOW

![inline](assets/git.pdf)

---

### 'Please use git' - A blog by Amin Shah Gilani [^1]

* It’s too complicated
* I’m not too good with the command line.
* “Our project is too small”
* “Our team is too small”
* “We use Dropbox”

---

# Recap 3

#ASTODO Only show database part

![inline](assets/anatomy_of_wordpress.pdf)

---

## We started using shared remote databases
##  **mysql.mycompany.co.uk**

This means all our **development** databases are accessible from anywhere.

---

### Think of your Wordpress website as a web application.

You shouldn't need live content to build / test a website

---

# GDPR

If you are downloading content to a development machine from a live site, make sure you aren't pulling live user / customer data.

---

# Recap 2

#ASTODO make this the second version of the diagram

![inline](assets/anatomy_of_wordpress.pdf)

---

## We store development asset on Amazon S3

An S3 bucket per site, which is only accessible to the development team

![inline 200%](assets/amazon-s3.pdf)

---

# Recap 3

#ASTODO Only show WordPress parts

![inline](assets/anatomy_of_wordpress.pdf)

---

![inline](assets/repo-files.png)

We need a way of getting WordPress

---

![inline](assets/composer.pdf)

Composer pulls which even WordPress version is required (usually the latest) and all required plugins.
# [fit] https://www.atomicsmash.co.uk/blog/using-composer-wordpress-development/

---

# Premium plugins

We use an private composer storage solution called Release Belt.

https://github.com/Rarst/release-belt

---

![fit](assets/release-belt.png)


---

# Signup for logsmith

We are looking for beta testers

http://eepurl.com/dkjmHb

---

![fill](assets/logsmith-signup2.png)

---

![fill autoplay loop](assets/automation.mp4)

---

# [fit] THANKS! ☺️

Follow me:
@david_darke

Follow my studio:
@atomicsmash

Get presentation here:
https://github.com/daviddarke/A-modern-WordPress-development-workflow

---

# Tools list

* GIT | A version control system for storing and sharing code.
* Composer | Used to pulling PHP dependancies like Wordpress.
* Release belt | Used for storing premium plugins and making them privately accessible to composer.
* Forge | Used for provisioning servers
* Logflume | Gets uploads onto S3 so they are sharable with other developers
* Logsmith | The development framework made by Atomic Smash

---


# [fit] Any questions? 🙋 🙋‍♂️


[^1]: https://hackernoon.com/please-use-git-da3bea7d1234
