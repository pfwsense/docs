![alt text](https://pfwsense.org/wp-content/themes/PFWsense/assets/img/pfwsense.png "Logo Title Text 1")

# PFWsense documentation

Welcome to the PFWsense documentation & wiki.   
The purpose of this project is to provide PFWsense users with quality documentation.

## Contribute

You can contribute to the project in many ways, e.g. testing
functionality, sending in bug reports or creating pull requests
directly via GitHub.  Any help is always very welcome!

## License

PFWsense documentation is available under the 2-Clause BSD license:

http://opensource.org/licenses/BSD-2-Clause

Every contribution made to the project must be licensed under the
same conditions in order to keep PFWsense truly free and accessible
for everybody.

Some pictures are licensed under the Creative Commons Zero (CC0) license:

https://creativecommons.org/publicdomain/zero/1.0/

Logos may be subject to additional copyrights, property
rights, trademarks etc. and may require the consent of a third party or the
license of these rights. Shanghai Sciinfo Technology Co., Ltd. does not represent or make any warranties
that it owns or licenses any of the mentioned, nor does it grant them.

#### Prepare build

On FreeBSD the following packages are required:

```
pkg install py39-pip jpeg-turbo gmake
```

Install Sphinx, our default theme and contrib packages:

```
pip[3] install -r requirements.txt --upgrade
```

### Update API endpoints

A script is provided to update the api endpoint documentation, this can be
executed using:

```
./collect_api_endpoints.py --repo core /path/to/core/repository
./collect_api_endpoints.py --repo plugins /path/to/plugins/repository
```

#### Generate HTML documents

```
make html
```

(```make clean``` to flush)
