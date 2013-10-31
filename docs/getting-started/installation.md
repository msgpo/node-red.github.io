---
layout: default
title: Installation
---   

### Install node.js

You can get the latest version from <http://nodejs.org/download/>.

Or, you may want to use a version from your operating system's package manager:
 <https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager>

### Install Node-RED

There are **three** ways to get Node-RED:

#### Download a release

Download the latest release from the link on <http://nodered.org>. The zip
contains a top-level folder called `node-red-X.Y.Z` where `X.Y.Z` is the version
number. Once extracted, from within that top-level folder, run the following
command:

    $ npm install --production

#### Use npm

Installing via npm allows you to [embed Node-RED into an existing application](../embedding.html).

Run the following commands to install from the npm repository:

    $ mkdir node-red
    $ cd node-red
    $ npm install node-red

This installs the latest release, and its core dependencies, into the `node-red/node_modules`
directory.

#### From GitHub

If you want to run the very latest code, you can clone the source repository
directly from GitHub:

    $ git clone https://github.com/node-red/node-red.git

Once cloned, the core pre-requisite modules must be installed. From the top-level
directory of Node-RED, run:

    $ npm install --production

### Installing additional nodes

The Node-RED release comes with a core set of useful nodes, but there are a growing
number of additional nodes available for install from other sources.

The project maintains its own [repository of nodes](http://github.com/node-red/node-red-nodes)
that don't belong in the core set, or that have been contributed by members of
the community. To install these nodes, either:

 - download the latest release from [GitHub](https://github.com/node-red/node-red-nodes/releases)
  and extract it under the `nodes/` directory of the Node-RED install directory.

 - or, clone the repository directly from GitHub into the `nodes/` directory:

       $ git clone https://github.com/node-red/node-red-nodes.git

### Installing individual node dependencies

*Eventually, nodes will be npm-installable themselves. This will take care of
all of the dependency management. Until then, it is a bit more manual...*

When Node-RED starts, it attempts to load the nodes from the `nodes/` directory.
Each will have its own set of dependencies that will need to be installed before
the node is available in the palette.

To help identify the dependencies, Node-RED logs any modules it fails to find
for a particular node. You only need to install these dependencies if you want
to use that node. For example, you probably don't want to install the `firmata`
module unless you are running with an Arduino attached.

Alternatively, a node's `.js` file can be examined to identify the modules it
explicitly requires. For example, the MongoDB node is defined in
`nodes/storage/66-mongodb.js` and contains:

    var RED = require("../../red/red");
    var mongo = require('mongodb');

The missing module, `mongodb` can subsequently be installed by running:

    $ npm install mongodb
