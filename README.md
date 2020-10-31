
## Minimally viable unofficial Debian packaging for the AWS SDK for C

Taken as a complete snapshot on 2020-02-15 at sha1 15e64e4 from
https://github.com/awslabs/aws-c-common

Updated 2020-07-09 with release 0.4.48 sha1 48aafc6
Updated 2020-10-30 with release 0.4.59 sha1 70ed84b

### Changes

No changes made other than

- downloading / copying all files _as is_ into `pkg/`
- addition of `pkg/debian/` directory for unofficial / informal Debian packaging
- addition of this README.md to document the changes

### Usage

Create yourself a `.orig.tar.gz` and use it with `dpkg-buildpackage` as for example via 

```sh
tar cvz --exclude=.git --exclude=debian --file aws-c-common_0.4.59.orig.tar.gz pkg/
cd pkg && dpkg-buildpackage -rfakeroot -us -uc -tc
```

which will create the `.deb` package you can install, the related
changes, dsc, ... files (which you can ignore), not sign them and run
`make clean` at the end.

### Copyright

All the actual upstream code in the repository is copyrighted by
Amazon as stated in the their repository, and licensed under Apache-2.0.

The Debian packaging is copyright Dirk Eddelbuettel and GPL'ed as usual.
