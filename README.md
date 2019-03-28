# fatalpra_doxygen

github pages for fatalpra doxygen output.

# quick start

If you do not need to build the latest API manual, then access [Code Documentation](https://soga-denken.github.io/fatalpra_doxygen/).

or you can git clone this repository.

```
git clone --depth 1 https://github.com/soga-denken/fatalpra_doxygen.git
```

If you want to build the latest API manul, follow the following directions.

# How to generate doxygen output

1. Build a Docker Container with doxygen

If you are not required to use proxy, then

```
git clone https://github.com/soga-denken/dockerfiles.git
cd dockerfiles/doxygen
docker build . -t doxygen
```

If you are required to use proxy, then replace the last line with

```
docker build --build-arg http_proxy="http://address:port"  --build-arg https_proxy="https://address:port"  --build-arg ftp_proxy="ftp://address:port"  --build-arg no_proxy="" . -t doxygen
```

2. Build Doxygen files

To build the API manual, run the following command.

```
docker run --rm "/path/to/doc/folder/":/output/ doxygen 
```

Open /path/to/doc/folder/index.html