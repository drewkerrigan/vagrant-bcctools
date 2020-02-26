# vagrant-bcctools

I created this repo because it turns out that playing with [bcctools](https://github.com/iovisor/bcc) on macOS is a PITA.

You can't use the following:

* the docker image mentioned in the bcc repo's [`QUICKSTART.md`](https://github.com/iovisor/bcc/blob/master/QUICKSTART.md) because that's expected a Linux Docker host.
* the [vagrant](https://github.com/iovisor/vagrant) repo is 4 years old and doesn't appear to play nice with a modern version of Vagrant.

## usage

* We'll assume you've installed VirtualBox and Vagrant.

Setup the vagrant session (this will take a while).

```sh
make setup
```

Once vagrant session is up, you can verify your install using the "hello world" python script:

```sh
vagrant ssh
sudo python3 /usr/share/doc/bpfcc-tools/examples/hello_world.py
```

In another terminal session

```sh
vagrant ssh
```

In the first terminal session you'll see something similar as the ssh session begins and [`clone`](https://linux.die.net/man/2/clone) syscall is triggered.

```sh
b'            sshd-4402  [000] ....  1828.790597: 0: Hello, World!'
b'   systemd-udevd-432   [001] ....  1828.836454: 0: Hello, World!'
...
b'            bash-4482  [000] ....  1829.552158: 0: Hello, World!'
```

to tear down

```sh
make clean
```

## examples

Finding examples:

```
ls /usr/share/doc/bpftrace/examples
ls /usr/share/doc/bpfcc-tools/examples
```

Finding additional tools:

```sh
$ ls /usr/sbin | grep bpf
argdist-bpfcc
bashreadline-bpfcc
biolatency-bpfcc
biosnoop-bpfcc
biotop-bpfcc
bitesize-bpfcc
...
zfsslower-bpfcc
$ 
$ which bpftrace
/usr/bin/bpftrace
```



## copyright

2019 &copy; Mark Sta Ana
