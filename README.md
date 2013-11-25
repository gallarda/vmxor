vmxor
=====

vmxor creates virtual machines on Mac OS X with VMWare Fusion. vmxor has no
other dependencies. `vmxor-make` and `vmxor-dhcp` are just simple Perl scripts,
roughly 100 lines each.

As of this writing I am using vmxor with VMWare Fusion Professional 5.0.3 on
Mac OS X 10.8.5 to create openSUSE, SUSE Linux Enterprise, Fedora and CentOS
virtual machines.


Example Usage
-------------

### Run these commands once to setup your Mac for this example

```
ln -s /where/you/have/DVD/iso/files/ ~/.vmxor-dvds
cd ~/.vmxor-dvds
curl -C - -L -O http://download.opensuse.org/distribution/13.1/iso/openSUSE-13.1-DVD-i586.iso
cd location/of/vmxor/clone
./vmxor-dhcp myvm 10-99
sudo stage/commit.sh
```

### To create a VM named `myvm10` just do

```
cd vmxor/examples
./vmxor-make-opensuse myvm10
```

You will be instructed to enter `autoyast=floppy` with the openSUSE
Installation menu option.

That's it! You will have a minimal openSUSE 13.1 virtual server created and
running. From Terminal do `ssh root@myvm` with password `changeme`.


History
-------

I wrote vmxor before [Vagrant](http://www.vagrantup.com) worked with VMWare
Fusion. If you want to work on anything other than VMWare on Mac OS X then you
should consider Vagrant or other alternatives. I have not used Vagrant but I'm
sure it has way more features. On the other hand, it will probably be easier to
understand and customize vmxor.

A private earlier version of vmxor ran on Fusion 3 on Mac OS X 10.6 and
probably still works with this earlier version with possibly only one minor
tweak.



Enjoy,

Castedo Ellerman <castedo@castedo.com>

