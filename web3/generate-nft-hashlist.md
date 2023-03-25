# Generate NFT hashlist

Install [metaboss](https://github.com/samuelvanderwaal/metaboss#installation).

Generate hashlist from candy machine:

```
$ metaboss snapshot mints --v3 --creator [candy machine id] --rpc [rpc url]
```

Or generate hashlist of all nfts with update authority:

```
$ metaboss snapshot mints --update-authority [update authority public key] --rpc [rpc url]
```

Read more in [docs](https://metaboss.rs/snapshot.html#snapshot-mints).
