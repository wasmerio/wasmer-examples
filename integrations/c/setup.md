# Setup your C/C++ environment

To build C applications that use the Wasmer runtime as a host for guest Wasm modules, you will need a C compiler installed \(`clang` or `gcc`, for example\).

Download our SDK for the C-API from [Wasmer releases page](https://github.com/wasmerio/wasmer/releases).  
Depending on your system, you will need to download:

* Linux: `wasmer-c-api-linux-amd64.tar.gz` 
* macOS: `wasmer-c-api-darwin-amd64.tar.gz` 
* Windows: `wasmer-c-api-windows.tar.gz` 

Once you have downloaded the c-api file, you can now extract its contents and set the `WASMER_C_API` environment variable to the path of the dir \(this will be very useful for the examples\):

```bash
# Extract the contents to a dir
mkdir wasmer-c-api
tar -C wasmer-c-api -zxvf wasmer-c-api*.tar.gz

export WASMER_C_API=`pwd`/wasmer-c-api
```

{% hint style="info" %}
Note: You can also [build the C-API from source](../../ecosystem/wasmer/building-from-source/#building-the-c-api-from-source).
{% endhint %}

## Installing Clang/GCC

First, you can test if make is installed already by running:

```text
gcc --version
```

If this command does not return the make version, then see the following:

### MacOS

`gcc` / `clang` is usually installed by default. However, if it is not, you can [install make by installing xcode-select](http://osxdaily.com/2014/02/12/install-command-line-tools-mac-os-x/) on your mac.

### Debian / Debian Based / Linux

To install make on a debian based, you will want to run the following:

```text
sudo apt-get install build-essential
```

Make should be installable on your favorite linux distro as well. Please search for the correct command for your desired distribution.

### Windows

To install Make on Windows, you will probably want to install a GNU environment on windows. We suggest using [MinGW](http://www.mingw.org/).

```bash
gcc --version

# This should output: "LICENSE   README.md include   lib"
ls $WASMER_C_API
```

{% hint style="success" %}
If these commands work, The compiler and the Wasmer C API are successfully installed!
{% endhint %}

Next, let's take a look at building a simple Hello World Example!
