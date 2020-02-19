
## Minimally viable unofficial Debian packaging for the AWS SDK for C

Taken as a complete snapshot on 2020-02-15 at sha1 15e64e4 from
https://github.com/awslabs/aws-c-common

### Changes

No changes made other than

- addition of debian/ directory for unofficial / informal Debian packaging
- addition of this README.md to document the changes
- renaming README.md to orig.README.md to make room for this file

### Usage

Create yourself a `.orig.tar.gz` and use it with `dpkg-buildpackage` as for example via 

```sh
cd ..
tar cvz --exclude=.git --exclude=debian --exclude=build \
	--file aws-c-common_0.4.30.orig.tar.gz pkg-aws-c-common
cd -
dpkg-buildpackage -rfakeroot -us -uc -tc
```

which will create the `.deb` package you can install, the related
changes, dsc, ... files (which you can ignore), not sign them and run
`make clean` at the end.

### Copyright

All the actual upstream code in the repository is copyrighted by
Amazon as stated in the their repository, and licensed under Apache-2.0.

The Debian packaging is copyright Dirk Eddelbuettel and GPL'ed as usual.
