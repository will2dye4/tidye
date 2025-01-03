# tidye - Tidal simulation with multiple moons in Python

[![PyPI Version](https://img.shields.io/pypi/v/tidye)](https://pypi.org/project/tidye/) [![Python Version](https://img.shields.io/pypi/pyversions/tidye)](https://www.python.org/downloads/) [![PyPI Downloads](https://img.shields.io/pypi/dm/tidye)](https://pypi.org/project/tidye/) [![MIT License](https://img.shields.io/github/license/will2dye4/tidye)](https://github.com/will2dye4/tidye/blob/master/LICENSE)

The `tidye` simulator calculates tidal interactions between a planet and one or more moons.

## Installation

The easiest way to install the package is to download it from [PyPI](https://pypi.org) using `pip`.
Note that `tidye` depends on [Python](https://www.python.org/downloads/) 3.9 or newer; please
ensure that you have a semi-recent version of Python installed before proceeding.

Run the following command in a shell (a UNIX-like environment is assumed):

```
$ pip install tidye
```

The package has a few external dependencies besides Python itself. If you wish to
sandbox your installation inside a virtual environment, you may choose to use
[virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/en/latest/) or a similar
utility to do so.

When successfully installed, a program called `tidye` will be placed on your `PATH`.
See the Usage section below for details about how to use  this program.

## Usage

The `tidye` program is a command-line interface for simulating tidal forces.

At any time, you can use the `-h` or `--help` flags to see a summary of options that
the program accepts.

```
$ tidye -h
usage: tidye [-h] [-d DURATION] file

Simulate lunar tides from a provided configuration file.

positional arguments:
  file                  Path to config file (e.g., config.json)

optional arguments:
  -h, --help            show this help message and exit
  -d DURATION, --duration DURATION
                        Simulation duration (defaults to two full orbits)
```

Typical usage is `tidye <config_file>`, where `<config_file>` is the path to a file
describing the configuration of the planet and moons that you wish to simulate. For an
example config file, see the `sample_config.json` included in the repository, or check
the example below:

```json
{
  "planet": {
    "mass": 1000
  },
  "moons": [
    {
      "mass": 100,
      "orbital_radius": 300,
      "orbital_period": 1
    },
    {
      "mass": 200,
      "orbital_radius": 500,
      "orbital_period": 2,
      "orbital_phase": 0.5
    },
    {
      "mass": 150,
      "orbital_radius": 400,
      "geostationary": true
    }
  ]
}
```
