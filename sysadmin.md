# sysadmin

## processes

devops:

- [A practical way to upgrade Postgres major versions with near-zero downtime](https://www.listennotes.com/blog/a-practical-way-to-upgrade-postgres-major-49/) `article`
- [Atomic Versioned Deploys in S3](https://samswanke.com/2019/10/03/atomic-versioned-deploys-in-s3.html) `article`
- [Zero downtime migration from AWS to Google](https://news.ycombinator.com/item?id=30945448) `hn comment`
- [BlueGreenDeployment - Martin Fowler](https://martinfowler.com/bliki/BlueGreenDeployment.html) `article`
- [Blue/Green Deployments on AWS](https://d1.awsstatic.com/whitepapers/AWS_Blue_Green_Deployments.pdf) `whitepaper`
- [Fine-tuning blue/green deployments on application load balancer](https://aws.amazon.com/blogs/devops/blue-green-deployments-with-application-load-balancer/) `article`
- [Use Application Load Balancers for Blue-Green and Canary Deployments](https://developer.hashicorp.com/terraform/tutorials/aws/blue-green-canary-tests-deployments) `article`
- [CloudFront vs Cloudflare, and how to reduce response times for both by ~35%+](https://www.foxy.io/blog/cloudfront-vs-cloudflare-and-how-to-reduce-response-times-for-both-by-35/) - origin shield `article`
- [Authenticating to AWS the right way for (almost) every use-case](https://leebriggs.co.uk/blog/2022/09/05/authenticating-to-aws-the-right-way) `article`
- [URL redirection with AWS Lambda@Edge](https://blog.cavelab.dev/2021/06/aws-lambda-edge-redirect/) `article`
- [Wildcard subdomains point to appropriate S3/CloudFront subdirectories](https://stackoverflow.com/questions/37634821/wildcard-subdomains-point-to-appropriate-s3-cloudfront-subdirectories/48745986#48745986) `so answer`
- [Strategies for deploying database migrations](https://www.prisma.io/dataguide/types/relational/migration-strategies) `article`
- [Using the expand and contract pattern for schema changes](https://www.prisma.io/dataguide/types/relational/expand-and-contract-pattern) `article`
- [High level overview of devops processes](https://web.archive.org/web/20200114165727/https://cs.gmu.edu/%7Etlatoza/teaching/swe432f19/Lecture-13-Deployment.pdf) `slides`
- [Automated blue/green database deployments](https://octopus.com/blog/databases-with-blue-green-deployments) `article`

sysadmin:

- [AWS Email Forwarder for almost free](https://nealalan.github.io/AWS-Email-Forwarder/) `article`
- [Increasing Battery Life on an Arch Linux Laptop (ThinkPad T14s)](https://austingwalters.com/increasing-battery-life-on-an-arch-linux-laptop-thinkpad-t14s/) `article`
- [Why I usually run 'w' first when troubleshooting unknown machines](https://rachelbythebay.com/w/2018/03/26/w/) `article`
- [Three Envelopes That taught me a Life Lesson in IT](https://community.spiceworks.com/topic/284059-three-envelopes-that-taught-me-a-life-lesson-in-it) `article`
- [How to configure a PostgreSQL database on RDS](https://www.prisma.io/dataguide/postgresql/setting-up-postgresql-on-rds) `article`
- [CDN guide](https://github.com/leandromoreira/cdn-up-and-running)
- [How RAID-6 dual parity calculation works](https://igoro.com/archive/how-raid-6-dual-parity-calculation-works/)
- [Have Postgresql accept 1 and 0 as true and false for boolean](https://dba.stackexchange.com/questions/46140/have-postgresql-accept-1-and-0-as-true-and-false-for-boolean)

unknown server investigation:
```
$ w
$ last
$ systemctl | grep running
$ ps auxwf
$ lsof -i -P
$ docker ps
```

man search for command:
```
man -k cmd
```

man search for command and open all pages:
```
man -K cmd
```

fastest way to transfer files in local network ([src](https://old.reddit.com/r/linuxadmin/comments/zu09e7/speed_up_rsync_or_use_tar_for_server/j1gl3i3/)):

source:
```
tar -cvf - /SOURCEDIR | nc TARGETIP 10240
```

target:
```
nc -l 10240 | tar -xvf -
```

analyzing logs ([src](https://news.ycombinator.com/item?id=33977143)):
```sh
$ cat file.log | sed 's/[0-9]//g' | sort | uniq -c | sort -nr
```

grep view context ([src](https://news.ycombinator.com/item?id=33976503)):
```sh
$ grep regex /var/log/logfile -A5    # view next 5 lines
$ grep regex /var/log/logfile -B5    # view previous 5 lines
$ grep regex /var/log/logfile -C5    # view 5 lines before and after the match
```

grep for multiple values ([src](https://news.ycombinator.com/item?id=33981124)):
```sh
$ grep -vE "THING1|THING2|THING3|THING4" file 
```

- [How (and Why) to Log Your Entire Bash History](https://spin.atomicobject.com/2016/05/28/log-bash-history/) `article`

find to which package file belongs 
```
rhel$ rpm -qf <file>
deb$ dpkg-query -S <file>
```

search man pages
```
man -k <query>
```

right way to shut down system:
```
halt -p
```

## rss

- [Kill the Newsletter](https://kill-the-newsletter.com/) `tool`
- [Feed Creator](https://createfeed.fivefilters.org/index.php) `tool`


## scripting

- [Now that's what I call a Hacker](https://www.jitbit.com/alexblog/249-now-thats-what-i-call-a-hacker/) `article`
- [wait for port to be up](https://github.com/vishnubob/wait-for-it) `tool`
- [Bash keyboard shortcuts](https://www.masteringemacs.org/article/keyboard-shortcuts-every-command-line-hacker-should-know-about-gnu-readline) `article`
- [Writing Robust Bash Shell Scripts](https://www.davidpashley.com/articles/writing-robust-shell-scripts/) `article`
- [Shell Script Best Practices](https://sharats.me/posts/shell-script-best-practices/) `article`
- [Httpbun](https://httpbun.com/) - http echo `tool`
- [serverless pastebin](https://topaz.github.io/paste/) - all data stored in url `tool`
- [localtunnel](https://github.com/localtunnel/localtunnel) - expose port to public internet `tool`
- [hishtory](https://github.com/ddworken/hishtory) - better shell history
- [Measure drive speed](https://askubuntu.com/questions/87035/how-to-check-hard-disk-performance/991311#991311) `so answer`
- [Better Bash History](https://www.thomaslaurenson.com/blog/2018-07-02/better-bash-history/) `article`
- [fix ssh in kitty terminal](https://sw.kovidgoyal.net/kitty/faq/#i-get-errors-about-the-terminal-being-unknown-or-opening-the-terminal-failing-when-sshing-into-a-different-computer)
- [Unix as IDE](https://blog.sanctum.geek.nz/series/unix-as-ide/) `article series`
- [Cron best practices](https://blog.sanctum.geek.nz/cron-best-practices/) `article`
- [Let that rsync in](https://sanctum.geek.nz/presentations/let-that-rsync-in.pdf) `slides`
- [Bring AWS Notifications Into Your Slack Channel](https://dev.to/aws-builders/bring-aws-notifications-into-your-slack-channel-gd4)
- [Prompt directory shortening](https://blog.sanctum.geek.nz/prompt-directory-shortening/)
- [Flameshot](https://flameshot.org/) `tool`


find tcp ports device is listening on
```sh
$ sudo ss --listen --tcp --process --numeric
# or more compact version:
$ sudo ss -ltpn
```

find out which servers and devices are up and running
```sh
$ nmap -sP 192.168.<subnet>.0/24
```

ping device on specific tcp port
```sh
$ nc -vz <ip> <port>
# add -u for udp port
```

load environment variables in shell:
```sh
export $(grep -v '^#' .env | xargs)
```

diff env files:
```sh
diff <(cat .env.example | sed 's/=.*//g' | grep '^[A-Z]' | sort) <(cat .env | sed 's/=.*//g' | grep '^[A-Z]' | sort)
```

about script naming:

without `.sh` extension when script is in some directory that is in `$PATH`
(like `/usr/bin`) and with `.sh` extension when in any directory not in `$PATH`

---

style guides

- [Unix shell script tactics](https://github.com/SixArm/unix-shell-script-tactics) `style guide`
- [Google Shell Style Guide](https://google.github.io/styleguide/shellguide.html) `style guide`
- [pure sh bible](https://github.com/dylanaraps/pure-sh-bible) `handbook`

---

web tools:
- [shellcheck](https://www.shellcheck.net/) `tool`
- [Crontab guru](https://crontab.guru/) `tool`

---


data parsing cmds:

- [jq](https://github.com/stedolan/jq) `json`
- [pup](https://github.com/EricChiang/pup) `html`
- [jqplay](https://jqplay.org/) - playground for `jq`


### ffmpeg multimedia stuff

- [Remove silence from video files](https://github.com/bambax/Remsi)

reduce video file size

```sh
$ ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4
```

## photography

- [Exposure Triangle simulator](https://dima.fi/exposure/) `tool`

## http

- [The HTTP crash course nobody asked for](https://fasterthanli.me/articles/the-http-crash-course-nobody-asked-for) `article`

## docker

- [Running Docker Containers as a Non-root User with a Custom UID / GID](https://nickjanetakis.com/blog/running-docker-containers-as-a-non-root-user-with-a-custom-uid-and-gid) `article`
- [Fast-Docker](https://github.com/omerbsezer/Fast-Docker)

## ansible

- [Fast-Ansible](https://github.com/omerbsezer/Fast-Ansible)


## zfs

- [ZFS High-Availability NAS](https://github.com/ewwhite/zfs-ha/wiki) `article`
- [Install and Setup ZFS on Debian 11](https://tweenpath.net/install-setup-zfs-debian-11/) `article`
- [What Is ZFS?: A Brief Primer](https://www.youtube.com/watch?v=lsFDp-W1Ks0) `YT video` `32 minutes`
- [Forbidden Arts of ZFS | Episode 3 | ZFS and mixed size drives](https://www.youtube.com/watch?v=JiVGOpMr87w) `YT video` `14 minutes`
- [So How Hard Is It To Crash and Kill a FreeNAS 11 ZFS Raid Z1 Array?](https://www.youtube.com/watch?v=vxFNBZIAClc) `YT video` `10 minutes`
- [ZFS 101 - Understanding ZFS storage and performance - Ars Technica](https://arstechnica.com/information-technology/2020/05/zfs-101-understanding-zfs-storage-and-performance/) `Article` `8 minutes`
- [Using ZFS Replication for Incremental Backups Over SSH on Linux](https://www.youtube.com/watch?v=NHM2T0uxkUM) `YT video` `53 minutes`
- [RAID-Z Expansion Feature for ZFS In the Home Stretch - FreeBSD Foundation](https://freebsdfoundation.org/blog/raid-z-expansion-feature-for-zfs/) `Article` `4 minutes`
- [How to upgrade a ZFS RAID-Z array to larger disks on OpenSolaris? - Server Fault](https://serverfault.com/a/15330) `SO answer`
- [ZFS Capacity Calculator - WintelGuy.com](https://wintelguy.com/zfs-calc.pl) `Web tool`
- [ZFS alert to avoid nasty surprises](https://thesmarthomejourney.com/2022/02/07/zfs-alert-via-pushover/)

## wireguard

Log connections
```sh
*/3 * * * * wg show all dump | grep 192.168.44 | awk 'BEGIN {}; {if (systime()-$6 <180 ) print strftime("\%m-\%d-\%Y \%H:\%M:\%S", systime()),$5, $4, (systime()-$6) "sec" } ; END {}' >> /var/log/wg.log
```

replace `192.168.44` with wireguard network prefix

## ssh

- [A Visual Guide to SSH Tunnels](https://iximiuz.com/en/posts/ssh-tunnels/) `article`

remote session management

- [tmux](https://github.com/tmux/tmux)
- [dtach](https://github.com/crigler/dtach)

kill session

"Enter" then ~ then . will kill a hung SSH connection, instead of having to close the terminal tab. 

Force password auth
```sh
$ ssh -o PreferredAuthentications=password -o PubkeyAuthentication=no <user>@<host>
```



## random

- [Guest WiFi using a QR code](https://blog.jgc.org/2022/07/guest-wifi-using-qr-code.html) `article`
- [Fake Windows Update Screens](https://fakeupdate.net/) `tool`


- [OpenTelemetry NodeJS: All you need to know](https://lightstep.com/blog/opentelemetry-nodejs)
- [Casio F-91W cheat sheet](https://menga.net/casio-f91w-cheat-sheet)
= [Choose Boring Technology](https://boringtechnology.club/)

vim sum selected numbers:

```
!awk '{print; sum+=$1}END{print sum}'
```