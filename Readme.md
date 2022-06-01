# npmdomainchecker

This tool checks every maintainer from every package in the NPM registry for unregistered domains or unregistered MX records on those domains. If a domain is unregistered you can grab the domain and initiate a password reset on the account if it has no 2 factor auth enabled. This enables you to hijack a package and do whatever you want with it.

**Please do not use it for illegal purposes, only use it to check packages and submit them to bug bounty programs.**

I contacted the NPM security team about this but they are not interested in this kind of vulnerability.

## Usage

Download the package index first! This can take a long time as the server is extremely slow (takes more than 30 mins):

```
wget https://skimdb.npmjs.com/registry/_all_docs
```

After this simply run the tool. To see all options use the `--help` switch. The output is automatically saved to `output.txt` too. This tool will most probably run multiple days due to the high number of packages.

To easily find hits in the output, grep for `HIT`. The coloring is based on the number of downloads during the last year of the package.

The tool does a lot of DNS and whois requests so I suggest running this tool from a dedicated server to not risk having your private ip blocked.