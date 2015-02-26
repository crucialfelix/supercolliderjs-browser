supercollider.js for web browsers
=================================

Tools for communicating between remote javascript clients (primarily web browsers) and supercollider.js

Work in progress.

Initially this just supports websockets and the API quark. This was part of supercollider.js but I'm moving it into its own package.
This reduces the dependencies and responsibilities of supercollider.js and will let this package focus on the browser and other remote javascript clients.

SuperCollider is an environment and programming language for real time audio synthesis and algorithmic composition. It provides an interpreted object-oriented language which functions as a network client to a state of the art, realtime sound synthesis server.

https://supercollider.github.io/


Documentation
-------------

http://supercolliderjs.readthedocs.org/en/latest/


Features
--------

- Call API endpoints in SuperCollider from a browser using JavaScript and a websocket/OSC bridge


Example
-------

    // the webserver has routes defined to serve these:
    <script src="/socket.io/socket.io.js"></script>
    <script src="/static/js/scapi.js"></script>
    <script>
      var sc = new SCApi("localhost", 4040);
      sc.call("server.boot", ["default"], function() {
        // server is booted now
        sc.call("group.new", [], function(groupID) {
          // spawn synths into this group
          sc.call("synth.new", ["scarysound", 100.0, 666.0, 7], function(synthID) {
            // enable things on the page to send control changes to the scarysound
          });
        });
      });
    </script>


Contribute
----------

- Issue Tracker: https://github.com/crucialfelix/supercolliderjs-browser/issues
- Source Code: https://github.com/crucialfelix/supercolliderjs-browser


License
-------

The project is licensed under the MIT license.
