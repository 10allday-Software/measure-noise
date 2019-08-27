# measure-noise
Measure how our data deviates from normal distribution


|Branch      |Status   | Coverage |
|------------|---------|----------|
|master      | [![Build Status](https://travis-ci.org/mozilla/measure-noise.svg?branch=master)](https://travis-ci.org/mozilla/measure-noise) | |
|dev         | [![Build Status](https://travis-ci.org/mozilla/measure-noise.svg?branch=dev)](https://travis-ci.org/mozilla/measure-noise)    | [![Coverage Status](https://coveralls.io/repos/github/mozilla/measure-noise/badge.svg)](https://coveralls.io/github/mozilla/measure-noise) |


## Install

    pip install measure-noise

## Usage

The `deviance()` method will return a `(description, score)` pair describing how the samples deviate from a normal distribution, and by how much.  This is intended to screen samples for use in the t-test, and other statistics, that assume a normal distribution.

* `SKEWED` - samples are heavily to one side of the mean
* `OUTLIERS` - there are more outliers than would be expected from normal distribution
* `MODAL` - few samples are near the mean (probably bimodal)
* `OK` - no egregious deviation from normal
* `N/A` - not enough data to make a conclusion (aka `OK`)

#### Example

    from measure_noise import deviance

	>>> desc, score = deviance([1,2,3,4,5,6,7,8])
    >>> desc
    'OK'

## Development

    git clone https://github.com/mozilla/measure-noise.git
    cd measure-noise
    pip install -r requirements.txt
    pip install or tests/requirements.txt
    python -m unittest discover tests 

## Windows

You must download the `scipy` and `numpy` binary packages. 
