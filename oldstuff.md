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

short-hand for checking for required env vars:

```
: "${GIT_HASH:?Environment variable empty or not defined.}"
: "${GITHUB_RUN_ID:?Environment variable empty or not defined.}"
: "${GITHUB_RUN_ATTEMPT:?Environment variable empty or not defined.}"
```

<https://github.com/sigstore/cosign/blob/be0e054045beb7f8d5de2019db0a7e707f56f33a/scripts/sign-images-ci.sh#L21-L23>

- [Why your house is a terrible investment](https://jlcollinsnh.com/2013/05/29/why-your-house-is-a-terrible-investment/)

# programming

- [How to Use Google Spreadsheet as a Backend for Your App](https://betterprogramming.pub/google-spreadsheet-as-a-backend-b6b51541f1e1) `article`
- [google-spreadsheet js lib](https://theoephraim.github.io/node-google-spreadsheet/#/)

## code review

- [How to do a code review](https://google.github.io/eng-practices/review/reviewer/) `handbook`

## slicing

- [Scratch-made SVG Donut & Pie Charts in HTML5](https://heyoka.medium.com/scratch-made-svg-donut-pie-charts-in-html5-2c587e935d72) `article`
- [Inside the mind of a frontend developer: Hero section](https://ishadeed.com/article/inside-frontend-developer-mind-hero-section/) `article`
- [getElementsBySelector() (2003)](https://simonwillison.net/2003/Mar/25/getElementsBySelector/) `article`
- [Tree views in CSS](https://iamkate.com/code/tree-views/) `article`
- [A star rating widget in CSS](https://iamkate.com/code/star-rating-widget/) `article`
- [Flexbox Froggy](https://flexboxfroggy.com/) `interactive tutorial`
- [Grid Garden](https://cssgridgarden.com/) `interactive tutorial`
- [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) `article`
- [A Complete Guide to CSS Grid](https://css-tricks.com/snippets/css/complete-guide-grid/) `article`
- [An Interactive Guide to Flexbox](https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/) `article`
- [Lazy loading images in HTML](https://til.simonwillison.net/html/lazy-loading-images) `article`
- [Color Formats in CSS](https://www.joshwcomeau.com/css/color-formats/) `article`
- [React Wrap Balancer](https://react-wrap-balancer.vercel.app/) `react component`
- [Google SEO General Guidelines](https://static.googleusercontent.com/media/guidelines.raterhub.com/en//searchqualityevaluatorguidelines.pdf) `handbook`
- [System font stack](https://systemfontstack.com/)
- [CSS Easing functions](https://easings.net/)
- [Filter Blend - CSS blend modes and filters playground](https://ilyashubin.github.io/FilterBlend/)
- [SVG Path Visualizer](https://svg-path-visualizer.netlify.app)
- [SVG Sprites generator](https://svgsprit.es/)
- [CSS-animated hamburgers](https://jonsuh.com/hamburgers/)
- [react-zoom-pan-pinch](https://github.com/prc5/react-zoom-pan-pinch)
- [I’m harvesting credit card numbers and passwords from your site. Here’s how.](https://david-gilbertson.medium.com/im-harvesting-credit-card-numbers-and-passwords-from-your-site-here-s-how-9a8cb347c5b5)

```
.spinner {
  border-radius: 50%;
  width: 16px;
  height: 16px;
  border: 4px solid rgba(0, 0, 0, 0.2);
  border-left: 4px solid #000000;
  animation: spinner-animation 1.2s infinite linear;
}

@keyframes spinner-animation {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
```

## sql

- [SQL Formatter](https://sql-formatter-org.github.io/sql-formatter/)

## functional programming

- [An introduction to functional programming](https://codewords.recurse.com/issues/one/an-introduction-to-functional-programming) `article`

## go

- [Go by Example](https://gobyexample.com/) `handbook`
- [Go wiki - SliceTricks](https://github.com/golang/go/wiki/SliceTricks) `article`
- [Functional programming in Go](https://bitfieldconsulting.com/golang/functional) `article`

## python

- [Build Portable Binaries of Python Applications](https://hynek.me/til/python-portable-binaries/)

## Excel

- [You Suck at Excel with Joel Spolsky](https://www.youtube.com/watch?v=0nbkaYsR94c) `talk`

docker prune everything:

```
docker system prune --all
```

# git

- [Git from the inside out](https://codewords.recurse.com/issues/two/git-from-the-inside-out) `article`
- [Git For Ages 4 And Up](https://www.youtube.com/watch?v=1ffBJ4sVUb4) `yt video`
- [Curing A Case Of Git-UX](https://peppe.rs/posts/curing_a_case_of_git-UX/) `article`
- [Learn Git Branching](https://learngitbranching.js.org/) `interactive tutorial`
- [Git Explorer](https://gitexplorer.com/) `interactive tutorial`
- [Git Alias Open Pull Request on GitHub](https://salferrarello.com/git-alias-open-pull-request-github/) `article`

complex logs

```
$ git log --graph --all --decorate --stat --date=iso
```

## search

search repository code changes (for regex search use `-G` instead of `-S`)

```
$ git log -S "query" -p --all
```

search specific files for changes

```
$ git log -S "query" -p --all -- **/models/user*.py
```

search commit messages

```
$ git log --grep "query" --all
```

## stats

leaderboards

```
$ git shortlog -sn --all --no-merges
```

today's work

```
$ git log --since=00:00:00 --all --no-merges --oneline --author=<email>
```

# automation / scripting

- [Do-nothing scripting: the key to gradual automation](https://blog.danslimmon.com/2019/07/15/do-nothing-scripting-the-key-to-gradual-automation/) `article`

## data sources

- [Querying the GitHub archive with the ClickHouse playground](https://til.simonwillison.net/clickhouse/github-explorer) `article`
- [Running OCR against a PDF file with AWS Textract](https://til.simonwillison.net/aws/ocr-pdf-textract) `article`
- [CallMeBot.com](https://www.callmebot.com/blog/free-api-whatsapp-messages/) - Free API to Send Whatsapp Messages `tool`
- [Google image resizing api](https://news.ycombinator.com/item?id=29747388) `hn comment`
- [Google search api](https://news.ycombinator.com/item?id=29747526) `hn comment`
- [So you want to Scrape like the Big Boys?](https://incolumitas.com/2021/11/03/so-you-want-to-scrape-like-the-big-boys/)
- [currency exchange api](https://www.ecb.europa.eu/stats/eurofxref/eurofxref-daily.xml)
- [stock price api](https://query1.finance.yahoo.com/v10/finance/quoteSummary/AAPL?modules=price)

# business

- [CS50 Lecture by Mark Zuckerberg - 7 December 2005](https://www.youtube.com/watch?v=xFFs9UgOAlE) `yt video` `65 min`
- [Good enough engineering to start an Internet company](https://www.listennotes.com/blog/good-enough-engineering-to-start-an-internet-27/) `article`
- [The boring technology behind a one-person Internet company](https://www.listennotes.com/blog/the-boring-technology-behind-a-one-person-23/) `article`

## crypto

- [What Crypto Founders Can Learn from Blur’s Token Airdrop](https://archive.is/Bnvnu)

# deployment

- [Deploying Python web apps as AWS Lambda functions](https://til.simonwillison.net/awslambda/asgi-mangum)
- [Simple, zero-downtime deploys with nginx and docker-compose](https://www.tines.com/blog/simple-zero-downtime-deploys-with-nginx-and-docker-compose)

## nginx

- [Nginx - Shell Script CGI](https://techexpert.tips/nginx/nginx-shell-script-cgi/)
- [Nginx - WebSocket proxying](http://nginx.org/en/docs/http/websocket.html)
- [Why I recommend CGI instead of web frameworks](https://halestrom.net/darksleep/blog/046_cgi/)

## terraform

- [Best practices for using Terraform](https://cloud.google.com/docs/terraform/best-practices-for-terraform)
- [GitLab as a Terraform state backend](https://balaskas.gr/blog/2022/11/11/gitlab-as-a-terraform-state-backend/)
- [AWS IAM JSON to Terraform HCL](https://flosell.github.io/iam-policy-json-to-terraform/)
- [Host Multiple Websites with One S3 Bucket](https://opsdocks.com/posts/multiple-websites-one-s3/)

## ansible

- [Automatically configuring EC2 instance using Ansible in pull mode during bootstrap](https://hangarau.space/automatically-configuring-ec2-instance-from-cloudformation-using-ansible-in-pull-mode/)
- [Ansible Let's Encrypt Nginx setup](https://gist.github.com/mattiaslundberg/ba214a35060d3c8603e9b1ec8627d349)
- [Automate HTTPS Certificates with Ansible Roles ft. Let's Encrypt & CloudFlare](https://santoshk.dev/posts/2022/automate-https-certificates-with-ansible-roles/)

## github actions

- [Adding a workflow status badge](https://docs.github.com/en/actions/monitoring-and-troubleshooting-workflows/adding-a-workflow-status-badge)
- [action-tmate](https://github.com/mxschmitt/action-tmate) - ssh into github action runner `gh action`
- [setup-terraform](https://github.com/hashicorp/setup-terraform) `gh action`
- [Simulating ternary operator in GitHub Actions Workflows](https://knutle.dev/simulating-ternary-operator-in-github-actions-workflows/)
- [Automate Terraform with GitHub Actions](https://developer.hashicorp.com/terraform/tutorials/automation/github-actions)
- [How to use an SSH key inside GitHub actions](https://maxschmitt.me/posts/github-actions-ssh-key/)

## scaling

- [Scaling to 100k Users](https://alexpareto.com/scalability/systems/2020/02/03/scaling-100k.html)
- [A Beginner's Guide to Scaling to 11 Million+ Users on Amazon's AWS](http://highscalability.com/blog/2016/1/11/a-beginners-guide-to-scaling-to-11-million-users-on-amazons.html)
- [Building a Billion User Load Balancer Patrick Shuff USENIX LISA December 2016](https://www.youtube.com/watch?v=bxhYNfFeVF4)
