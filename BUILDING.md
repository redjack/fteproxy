fteproxy Build Instructions
===========================

Ubuntu/Debian
-------------

Install the following packages.
```
sudo apt-get install python-dev python-pip upx git
sudo pip install --upgrade fte pyptlib obfsproxy twisted pyinstaller
```

Note: If you are on Ubuntu 13.10, there is a bug with pyinstaller/pycrypto, such that binary packages do not build properly. Please install development version 52fa29ce of pyinstaller [3], instead of using pip. See [4] for more details.

Then, clone and build fteproxy.
```
git clone https://github.com/kpdyer/fteproxy.git
cd fteproxy
make
make test
make dist
```

OSX
---

Install homebrew [1], if you don't have it already.

```
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
```

Install the following packages.
```
brew install --build-from-source python gmp git upx
sudo pip install --upgrade fte pyptlib obfsproxy twisted pyinstaller
```

Then, clone and build fteproxy.
```
git clone https://github.com/kpdyer/fteproxy.git
cd fteproxy
make
make test
make dist
```

Note: if on OSX 10.9, you may experience a ```clang: warning: argument unused during compilation: '-mno-fused-madd'``` error. This can be resolved by setting the following evnironmental variables:

```
export CFLAGS=-Qunused-arguments
export CPPFLAGS=-Qunused-arguments
```

Windows
-------

If you must build fteproxy on Windows, please see [2] for guidance.


### References

* [1] http://brew.sh/
* [2] https://github.com/kpdyer/fteproxy-builder/blob/master/build/windows-i386/build_fteproxy.sh
* [3] https://github.com/pyinstaller/pyinstaller
* [4] https://github.com/kpdyer/fteproxy/issues/124
