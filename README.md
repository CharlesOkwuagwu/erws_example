## Example ##

This example shows how to use Websockets and Erlang Web server using binary
[Erlang External Term Format](http://www.erlang.org/doc/apps/erts/erl_ext_dist.html#id85682).
All messages are exchanged between client/server
using a *binary* (end-to-end)
[Javascript implementation of the Erlang External Term format]
(https://github.com/saleyn/erlb.js).


### Getting ###

    $ git clone https://github.com/saleyn/erws_example.git

### Building ###

Initial build:

    $ make deps

Successive build:

    $ make

### Running ###

    $ make run

Open a Web browser (tested with Chrome and Firefox) and point
to your server's address, port 40000. The click on the link
"Open a websocket demo" and you should see a popup window that looks like this:

![Example](https://raw.github.com/saleyn/erws_example/master/priv/example.png)

Clicking on the 'Ping' hyperlink will initiate a message sent back and forth
between client browser and server 10000 times.

The green and purple time-series represent random values sent from the server
in the form ``{TickerX, Value::integer(), Dummy::binary()}`` where TickerX is
either ``ticker1`` or ``ticker2``, Value is a random value used to plot in the
corresponding time-series, and the Dummy is dummy payload of size 1Kb.

The red time-series is the messages per secord rate of ``ticker1`` and ``ticker2``
respectively. Yellow time-series is the total inbound messages per second rate,
and orange time-series is the messages per second rate of incoming replies to
the ping requests initiated by user.

### License ###

Copyright (c) 2013 Serge Aleynikov

See attached LICENSE file
