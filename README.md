# aiocian
[![MIT license](https://img.shields.io/badge/license-MIT-blue.svg)](
https://github.com/OlegYurchik/aiocian/blob/master/LICENSE)
[![built with Python3](https://img.shields.io/badge/built%20with-Python3-red.svg)](
https://www.python.org/)
## Description
Unofficial library for interaction with [Cian](https://cian.ru)

Contents
=================
* [Release Notes](#release-notes)
  * [0.0.1](#version-0-0-1)
* [Getting Started](#getting-started)
  * [Installation from pip](#installation-from-pip)
  * [Installation from GitHub](#installation-from-github)
  * [Quick Start](#quick-start)
## Release Notes
### Version 0.0.1
* Created library
* Add simple search
## Getting Started
### Installation from pip
For installation botovod library from pip you should have pip with python (prefer python3.6 or
later)
```bash
pip install aiocian
```
### Installation from GitHub
To basic installation from GitHub repository you should have git, python3 (prefer python3.6 or
later), pip (optionally) in your system
```bash
git clone https://github.com/OlegYurchik/aiocian.git
cd aiocian
pip install .
```
or
```bash
git clone https://github.com/OlegYurchik/aiocian.git
cd aiocian
python setup.py install
```
### Quick Start
After installation, you can use the library in your code. Below is a sneak example of using the
library
```python3
from aiocian import BUY, CianClient, FLAT, SPB
import asyncio


async def main():
    async with CianClient() as client:
        search = client.search(region=SPB, action=BUY, places=(FLAT,))

        async for result in search:
            print(result.url)


loop = asyncio.get_event_loop()
loop.run_until_complete(main)
loop.close()
```
