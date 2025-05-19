# Gofile-dl [![python](https://img.shields.io/badge/Python-3.11-3776AB.svg?style=flat&logo=python&logoColor=white)](https://www.python.org) 

## About ##
A CLI (Command Line Interface) tool to download all directories and files from a gofile.io link as a batch  

## Setup ##
1. Download repository  
```console
git clone https://github.com/rkwyu/gofile-dl
```
2. Install dependencies
```console
cd ./gofile-dl
python -m pip install -r requirements.txt
```

## Usage (CLI) ##
```console
usage: run.py [-h] [-d DIR] [-p PASSWORD] [-t THREAD] [-e EXCLUDES ...] url

positional arguments:
  url

options:
  -h, --help   show this help message and exit
  -d DIR       output directory
  -p PASSWORD  password
  -t THREAD    number of threads (default: 1)
  -e EXCLUDES  excluded files (supporting wildcard *)
```
Default output directory is `./output` 

#### Example 1: Download files from https://gofile.io/d/foobar ####
```console
python run.py https://gofile.io/d/foobar
```

#### Example 2: Download files from https://gofile.io/d/foobar to directory /baz/qux ####
```console
python run.py -d /baz/qux https://gofile.io/d/foobar
```

#### Example 3: Download files from https://gofile.io/d/foobar with password "1234" protected ####
```console
python run.py -p 1234 https://gofile.io/d/foobar
```

#### Example 4: Download files from https://gofile.io/d/foobar with 4 threads ####
```console
python run.py -t 4 https://gofile.io/d/foobar
```

#### Example 5: Download files from https://gofile.io/d/foobar except *.jpg, foo.bar files ####
```console
python run.py -e "*.jpg" -e "foo.bar" https://gofile.io/d/foobar
```
#### Example 4: Download files from https://gofile.io/d/foobar with 4 threads to directory /baz/qux with proxy ####
```console
python run.py -t 4 -d /baz/qux --proxy http:127.0.0.1:3128 https://gofile.io/d/foobar
```
## License ##
This project is licensed under the [MIT License](LICENSE.md)
