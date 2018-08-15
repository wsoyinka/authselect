authselect-rpm
====================

Create RPM package for [authselect](http://www.gnu.org/software/authselect/).

This spec is based on sources from [Fedora](https://apps.fedoraproject.org/packages/authselect/sources/).

## Build steps

* Install dependencies
```
$ sudo yum install rpm-build rpmdevtools yum-utils make
```
* Clone this repository
* Build the RPM:
```
$ cd autoconf-archive-rpm
$ mkdir SOURCES
$ spectool -g -R -C SOURCES authselect.spec
$ rpmbuild --define "_topdir `pwd`" -bs authselect.spec
$ sudo yum-builddep SRPMS/authselect-<version>.src.rpm

dnf builddep SRPMS/authselect-1.0-20180813.1540.fc28.src.rpm

$ rpmbuild --define "_topdir `pwd`" --rebuild SRPMS/autoconf-archive-<version>.src.rpm

```
* The RPM should be written to RPMS/noarch
