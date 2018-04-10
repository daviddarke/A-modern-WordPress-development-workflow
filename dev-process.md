footer: A modern WordPress development workflow - David Darke | [atomicsmash.co.uk](https://www.atomicsmash.co.uk)
slidenumbers: true

# A modern WordPress development workflow

---

![fill](assets/atomicsmash-logo.png)

---

## September 2010

![original](assets/spike-island.jpg)

---

### Working with WordPress

![inline](assets/old-dev-process.pdf)

---

[.build-lists: true]
[.autoscale: true]

# [fit] What's wrong with this simple setup?

* It's almost impossible for two developer to work at the same time, (unless they are sat next to each other)
* Dropbox does have a revision system, but only on a per file basis
* Deployments were cumbersome and not traceable (FTP is the worst)
* No real control over servers and hosting (Shared hosting)
* Nothing was re-usable
* Hours wasted handling development environment differences and thing out of our control

---

## Today (April 2018)

![original](assets/atomic_now.jpg)


---

## Our challenges

* Shared development environment
* Find a reliable deployment method
* Improve hosting reliability, level of control and performance

---

### Laravel Homestead

![inline](assets/vagrant_homestead.pdf)

---

![inline](assets/computer_inside_computer.gif)

---

### Laravel Homestead

> **Laravel Homestead is an official, pre-packaged Vagrant box that provides you a wonderful development environment without requiring you to install PHP, a web server, and any other server software on your local machine.**
-- Homestead documentation

^ Vagrant boxes are completely disposable. If something goes wrong, you can destroy and re-create the box in minutes!

---

### The anatomy of 99.9999% of WordPress Websites

![inline](assets/anatomy_of_wordpress.pdf)

#### What makes any WordPress site unique?

^
* Think of your Wordpress website as a web application.
* It's just a dependancy

---

## Your theme and custom plugin code

### Get your code into GIT... NOW

![inline](assets/git.pdf)

---
[.autoscale: true]


### 'Please use git' - A blog by Amin Shah Gilani [^1]

* It’s too complicated
* I’m not too good with the command line.
* “Our project is too small”
* “Our team is too small”
* “We use Dropbox”

---

# Recap 2

#ASTODO Only show database part

![inline](assets/anatomy_of_wordpress.pdf)

---

## We started using shared remote databases
##  **mysql.mycompany.co.uk**

This means all our **development** databases are accessible from anywhere.

---

# Recap 3

#ASTODO only show uploads

![inline](assets/anatomy_of_wordpress.pdf)

---

## We store development asset on Amazon S3

An S3 bucket per site, which is only accessible to the development team

![inline 200%](assets/amazon-s3.pdf)

---

# Recap 4

#ASTODO Only show WordPress parts

![inline](assets/anatomy_of_wordpress.pdf)

---

![inline](assets/composer.pdf)

Composer pulls which even WordPress version is required (usually the latest) and all required plugins.
# [fit] https://www.atomicsmash.co.uk/blog/using-composer-wordpress-development/


---

![inline](assets/repo-files.png)

Git repository is clean of WordPress, plugins and uploads


---

# Premium plugins

We use an private composer storage solution called Release Belt.

https://github.com/Rarst/release-belt

---

![fit](assets/release-belt.png)

---

## Our challenges

* ~~Shared development environment~~ ✔
* Find a reliable deployment method
* Improve hosting reliability, level of control and performance

---

# Capistrano

![inline](assets/capistrano.pdf)

---

## A single deployment

1. **Developer** runs `cap production deploy`
1. **Capistrano** logs into your remote server
1. **Capistrano** grabs the latest code from Git
1. **Capistrano** runs composer and pulls down WordPress
1. If there are no errors in setup, **Capistrano** puts changes live

---

## `cap production deploy`
## `cap uat deploy`
## `cap staging deploy`

---

## `cap production deploy:rollback`

![inline](assets/mind-blown.gif)

---

## Our challenges

* ~~Shared development environment~~ ✔
* ~~Find a reliable deployment method~~ ✔
* Improve hosting reliability, level of control and performance


---

### Old dev process

![inline](assets/old-dev-process.pdf)

---

![inline](assets/delorean.gif)


---

### New dev process

![inline](assets/new-dev-process.pdf)


---

#[fit] Signup for logsmith

#[fit] We are looking for beta testers

#[fit] **http://eepurl.com/dkjmHb**

---

![fill](assets/logsmith-signup2.png)

---

![fill autoplay loop](assets/automation.mp4)

---

# THANKS!

Follow me:
@david_darke

Follow my studio:
@atomicsmash

Get presentation here:
https://github.com/daviddarke/A-modern-WordPress-development-workflow

---
[.autoscale: true]

### Tool list

- Capistrano | Used to deploy code from GIT to servers.
- Composer | Used to pulling PHP dependancies like Wordpress.
- Forge | Used for provisioning servers
- GIT | A version control system for storing and sharing code.
- Logflume | Gets uploads onto S3 so they are sharable with other developers
- Logsmith | The development framework made by Atomic Smash
- Release belt | Used for storing premium plugins and making them privately accessible to composer.

---

### Think of your Wordpress website as a web application.

You shouldn't need live content to build / test a website

---

# GDPR

If you are downloading content to a development machine from a live site, make sure you aren't pulling live user / customer data.

---


# [fit] Any questions? 🙋 🙋‍♂️


[^1]: https://hackernoon.com/please-use-git-da3bea7d1234
