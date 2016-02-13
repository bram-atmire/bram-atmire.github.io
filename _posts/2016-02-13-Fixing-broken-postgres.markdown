---
layout: post
title:  "DSpace database broken after brew upgrade"
date:   2016-02-13 11:11:00
categories: Postgresql
---

The deployment of my DSpace 6 XMLUI webapp is currently broken. After recently upgrading my OS to El Capitan, I executed brew upgrade instead of brew update and modified all the dependencies I had installed with homebrew. The big difference between brew update and upgrade is that update just gets the best suited flavor of the same major version that you have installed of a specific dependency. Upgrade however, can upgrade to new major versions of your dependencies.

This had a negative effect on my homebrew installed version of postgres, as brew upgrade effectively took it from 9.4 to 9.5. I had no experience with postgresql upgrades until I now found out that your 9.4 initialized cluster effectively won't start with 9.5 binaries. Even though the manual suggests a "handy" pg_upgrade command, the instructions were a bit daunting:

http://www.postgresql.org/docs/9.5/static/pgupgrade.html

Because I wasn't waiting for any specific 9.5 features, I wanted an easier road by just rolling back to postgresql 9.4. Turns out homebrew has very elegant functionality for this. When upgrading a specific homebrew formula (like postgres), it actually keeps your older versions. All it takes is the simple brew switch command and postgres was back in action with my databases.

Thank you [Debilski](http://stackoverflow.com/users/200266/debilski) for the great answer 

http://stackoverflow.com/questions/3987683/homebrew-install-specific-version-of-formula


