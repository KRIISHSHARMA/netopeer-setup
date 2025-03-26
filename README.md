# INSTALLTION 
### Prerequisites

- install important libraries 
```
sudo apt-get install build-essential cmake git pkg-config libssl-dev libpcre3-dev libxml2-dev libxslt1-dev libprotobuf-dev protobuf-compiler libpcre2-8-0 libpcre2-dev libcurl4-openssl-dev libmbedtls-dev
```

**1. Building and Installing libyang**

- Clone the libyang repository:

```
git clone https://github.com/CESNET/libyang.git
cd libyang
mkdir build
cd build
cmake ..
make
sudo make install
```

**2. Building and Installing sysrepo**

- Clone the sysrepo repository:

```
git clone https://github.com/sysrepo/sysrepo.git
cd sysrepo
mkdir build
cd build
cmake ..
make
sudo make install
```

**3. Building and Installing libnetopeer**

- Clone the libnetopeer repository:

```
git clone https://github.com/CESNET/libnetconf2.git
cd libnetconf2
mkdir build
cd build
cmake ..
make
sudo make install
```

### Building and Installing netopeer

- Clone the libnetopeer repository:

```
git clone https://github.com/CESNET/netopeer2.git
cd netopeer2
mkdir build
cd build
cmake ..
make
sudo make install
```

### Errors Faced 

`libsysrepo.so.7: cannot open shared object file`
- This error occurs when libsysrepo.so.7 is not found by the dynamic loader.

**Solution:**

**make sure you have built sysrepo correctly , if  built correctly , create a symlink to the library in a standard location:**
```
locate libsysrepo.so.7
sudo ln -s /path/to/libsysrepo.so.7 /usr/lib/libsysrepo.so.7
```

### Verifying Installation

- `netopeer2-server -V`
- Above command should return something like this `netopeer2-server 2.2.35`
