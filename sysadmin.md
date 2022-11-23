# sysadmin/devops

## processes

- [A practical way to upgrade Postgres major versions with near-zero downtime](https://www.listennotes.com/blog/a-practical-way-to-upgrade-postgres-major-49/) `article`
- [Atomic Versioned Deploys in S3](https://samswanke.com/2019/10/03/atomic-versioned-deploys-in-s3.html) `article`
- [Zero downtime migration from AWS to Google](https://news.ycombinator.com/item?id=30945448) `hn comment`
- [BlueGreenDeployment - Martin Fowler](https://martinfowler.com/bliki/BlueGreenDeployment.html) `article`
- [Blue/Green Deployments on AWS](https://d1.awsstatic.com/whitepapers/AWS_Blue_Green_Deployments.pdf) `whitepaper`
- [Fine-tuning blue/green deployments on application load balancer](https://aws.amazon.com/blogs/devops/blue-green-deployments-with-application-load-balancer/) `article`
- [Use Application Load Balancers for Blue-Green and Canary Deployments](https://developer.hashicorp.com/terraform/tutorials/aws/blue-green-canary-tests-deployments) `article`
- [AWS Email Forwarder for almost free](https://nealalan.github.io/AWS-Email-Forwarder/)


## scripting

- [wait for port to be up](https://github.com/vishnubob/wait-for-it)

parse cli arguments:
```sh
while test $# -gt 0; do  
  case "$1" in  
    -f|--flag) shift; FLAG="$1";;  
  esac  
  shift  
done
```

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

reduce video file size

```sh
$ ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4
```

## learning

- [The HTTP crash course nobody asked for](https://fasterthanli.me/articles/the-http-crash-course-nobody-asked-for) `article`


## zfs

- [ZFS High-Availability NAS](https://github.com/ewwhite/zfs-ha/wiki) `article`

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


## terraform

- [GitLab as a Terraform state backend](https://balaskas.gr/blog/2022/11/11/gitlab-as-a-terraform-state-backend/)