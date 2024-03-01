# CP-Node
This repository contains the files to run [CodeParadise](https://github.com/ErikOnBike/CodeParadise) applications within Node.js.

Just clone this repo or copy the individual files to a directory and you're good to go. It's that simple. Well...almost. Don't forget to install [CodeParadise](https://github.com/ErikOnBike/CodeParadise) and have it running.

Run the following command to startup the example (calculating HTTP Server):
```bash
APP="http-server-example" SERVER_URL="ws://localhost:8080/io" node squeak_node_bundle.js client-environment.image
```

The above command will run the CodeParadise application "http-server-example" within Node.js. It is a calculating HTTP Server. You can send urls like `http://localhost:8181/add:42` or `http://localhost:8181/multiply:3.14` to it or combine them `http://localhost:8181/subtract:7/add:3`. It will update any existing calculation. You can 'snapshot' the image and restart it later. Snapshotting means the Smalltalk image gets 'sealed', it will no longer be connected to the CodeParadise server. Updates to the code will not be propagated to the image. Once sealed it can be run without needing the CodeParadise server running, so you can distribute the application to your friends. To start you can simply use `node squeak_node_bundle.js client-environment.image` and don't supply the server information.

There are two bundles, both are actually minified but the `.min` version has name mangling turned on which might make debugging a little more difficult.

Happy hacking!
