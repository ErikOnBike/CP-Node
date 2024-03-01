# CP-Node
This repository contains the files to run [CodeParadise](https://github.com/ErikOnBike/CodeParadise) applications within Node.js.

Just clone this repo or copy the individual files to a directory and you're good to go. It's that simple. Well...almost. Don't forget to install [CodeParadise](https://github.com/ErikOnBike/CodeParadise) and have it running.

Run the following command to startup the example (calculating HTTP Server):
```bash
APP="http-server-example" SERVER_URL="ws://localhost:8080/io" node cp-node.js client-environment.image
```

The above command will run the CodeParadise application "http-server-example" within Node.js. It is a calculating HTTP Server. You can send urls like `http://localhost:8181/add:42` or `http://localhost:8181/multiply:3.14` to it or combine them `http://localhost:8181/subtract:7/add:3`. The server will perform the calculations and keep track of the current value. To see the calculations and value send `http://localhost:8181/value`. You can also `http://localhost:8181/undo` or `http://localhost:8181/reset` the calculations.

Finally, you can 'snapshot' the image and restart it later. The current application (in this case server) state is kept. So any calculations present are storing in the image. To snapshot use the url `http://localhost:8181/snapshot`. Snapshotting means the Smalltalk image gets 'sealed', it will no longer be connected to the CodeParadise server. Updates to the code will not be propagated to the image. Once sealed it can be run without needing the CodeParadise server running, so you can distribute the application to your friends. To start you can simply use `node cp-node.js client-environment.image` and don't supply the server information. You can change the name of the image file to better match your application's name of course.

There are two bundles, both are actually minified but the `.min` version has name mangling turned on which might make debugging a little more difficult.

Happy hacking!
