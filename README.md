# golang 

[![Build Status](https://travis-ci.org/scotty-c/puppet-golang.svg?branch=master)](https://travis-ci.org/scotty-c/puppet-golang)

#### Table of Contents

1. [Overview](#overview)
2. [Module Description](#module-description)
3. [Usage](#usage)
4. [Dependencies](#dependencies) 
5. [Development](#development)

## Overview

This is a module that will install Google's Go language for all users.

## Module Description

This module installs GO from source, making it compatbale with any OS that listed on Google's site https://golang.org/doc/install

## Usage
For basic usage:
```
include golang
```
To customise the install please see the below examples. The deafult param is now to install from package !!!! 

To install from source:

```puppet
class {'golang':
  base_dir    => '/usr/local/go',
  from_source => true,
  version     => 'go1.4.1',
  goroot      => "$GOPATH/bin:/usr/local/go/bin:$PATH",
  workdir     => '/usr/local/',
  }
```

To install from the OS repos (yum ot apt)

```puppet
class {'golang':
  base_dir        => '/usr/local/go',
  from_source     => false,
  package_version => 'present',
  goroot          => "$GOPATH/bin:/usr/local/go/bin:$PATH",
  workdir         => '/usr/local/',
  }
```

Or all data can be set in Hiera ie ```golang::base_dir: /usr/local/go ```

##Dependencies

This module needs puppetlabs/vcsrepo

## Development

Pull request welcome. Just hit me up.
