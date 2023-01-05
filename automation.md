# automation / scripting


## data sources

- [Querying the GitHub archive with the ClickHouse playground](https://til.simonwillison.net/clickhouse/github-explorer) `article`
- [Running OCR against a PDF file with AWS Textract](https://til.simonwillison.net/aws/ocr-pdf-textract) `article`
- [CallMeBot.com](https://www.callmebot.com/blog/free-api-whatsapp-messages/) - Free API to Send Whatsapp Messages `tool`
- [Google image resizing api](https://news.ycombinator.com/item?id=29747388) `hn comment`
- [Google search api](https://news.ycombinator.com/item?id=29747526) `hn comment`


## bash patterns

parse cli arguments:
```sh
while test $# -gt 0; do  
  case "$1" in  
    -a|--argument) shift; ARG="$1";;  
    -s|--switch) SWITCH=1;;
  esac  
  shift  
done
```

get script directory:
```sh
dir=$(cd -P -- "$(dirname -- "$0")" && pwd -P)
```