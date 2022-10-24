Sope framework for Debian

This is a fork of the official [SOPE Framework](https://github.com/Alinto/sope) used by SOGo.

We forked this to get an easier way to create debian packages for these libraries.

# How To Build The Debian Package

This Debian package can be built easily as follow (on a standard debian bullseye) :

```
# this installs the build-dependencies:
apt install debhelper gnustep-make libgnustep-base-dev gobjc \
  libxml2-dev libldap2-dev libssl-dev zlib1g-dev \
  libpq-dev libmariadb-dev-compat
# this create the debian/control files for this 'Version' of Sope
debian/rules debian/control
# this compiles the debian package.
# adds --username=you@yourmachine to pgp-sign it
# this signs using debian/changelog last maintainer email.
debuild -d -- binary
```

You'll normally get all the sope packages in the parent folder.

You can then use dput to send your packages to a debian repository



