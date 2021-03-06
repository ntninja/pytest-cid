# pytest-cid

![Made by the IPFS Community](https://img.shields.io/badge/made%20by-IPFS%20Community-blue.svg?style=flat-square)
[![](https://img.shields.io/badge/project-IPFS-blue.svg?style=flat-square)](http://ipfs.io/)
[![IRC #py-ipfs on chat.freenode.net](https://img.shields.io/badge/freenode%20IRC-%23py--ipfs-blue.svg?style=flat-square)](http://webchat.freenode.net/?channels=%23py-ipfs)
[![Matrix #py-ipfs:ninetailed.ninja](https://img.shields.io/matrix/py-ipfs:ninetailed.ninja?color=blue&label=matrix+chat&style=flat-square)](https://matrix.to/#/#py-ipfs:ninetailed.ninja?via=ninetailed.ninja&via=librem.one)
[![Standard README Compliant](https://img.shields.io/badge/standard--readme-OK-green.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

> Compare data structures containing matching CIDs of different versions and encodings

A simple wrapper around [`py-cid`](https://github.com/ipld/py-cid) for easily writing tests
involving CIDs in datastructures.

## Table of Contents

- [Install](#install)
- [Usage](#usage)
- [Documentation](#documentation)
- [Featured Projects](#featured-projects)
- [Contribute](#contribute)
  - [IRC/Matrix](#irc-matrix)
  - [Bug reports](#bug-reports)
  - [Pull requests](#pull-requests)
- [License](#license)

## Install

Install with pip:

```sh
pip install pytest-cid
```

## Usage

Basic usage example:

```py
>>> import pytest_cid
>>> cid_1 = "zb2rhfE3SX3q7Ha6UErfMqQReKsmLn73BvdDRagHDM6X1eRFN"
>>> cid_2 = "bafkreid7qoywk77r7rj3slobqfekdvs57qwuwh5d2z3sqsw52iabe3mqne"
>>> assert pytest_cid.match(cid_1) == cid_2
>>> assert pytest_cid.normalize(cid_1) == pytest_cid.normalize(cid_2)
>>> cid_struct_1 = {
... 	"Hash": "QmQcCtMgLVwvMQGu6mvsRYLjwqrZJcYtH4mboM9urWW9vX",
... 	"Name": "fsdfgh", "Size": "16"
... }
>>> cid_struct_2 = {
... 	"Hash": "f0170122021b377e527deaa9698a451fa07232d7cd9494f6553252f325559d9053b565b38",
... 	"Name": "fsdfgh", "Size": "16"
... }
>>> assert pytest_cid.match(cid_struct_1) == cid_struct_2
>>> assert pytest_cid.match(cid_struct_1) != cid_1
```

## Documentation

FIXME (Usage example covers the whole API as of 1.0.0)

## Contribute

### IRC/Matrix

Join us on [Matrix](https://matrix.to/#/#py-ipfs:ninetailed.ninja?via=ninetailed.ninja&via=librem.one) or on IRC on [#py-ipfs on chat.freenode.org](http://webchat.freenode.net/?channels=%23py-ipfs) if you have any suggestions, questions or just want to chat about IPFS and/or Python with us.

  * Please note however that, at the time of writing, the default `matrix.org` server is severely overloaded and your messages may only arrive with extreme delay; using a different homeserver is hence highly recommended.

### Bug reports

You can submit bug reports using the [GitHub issue tracker](https://github.com/alexander255/pytest-cid/issues).

### Pull requests

Pull requests are welcome.  Before submitting a new pull request, please
make sure that your code passes both the [code formatting](https://www.python.org/dev/peps/pep-0008/) check:

    $ tox -e styleck

And the unit tests:

    $ tox

Please make sure to include new unit tests for new features or changes in
behavior.

## License

Distributed under the terms of the *Mozilla Public License 2.0* license, “pytest-cid” is free and open source software.
Details may be found in the [LICENSE](LICENSE) file in this repository.
