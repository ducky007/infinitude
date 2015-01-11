#Infinitude
###Documentation and information on protocol available on the [Wiki](https://github.com/nebulous/infinitude/wiki). Please contribute!

#### Infinitude is an alternative web service for [Carrier Infinity Touch*](https://github.com/nebulous/infinitude/wiki/Infinity-touch) thermostats.

*and presumably other Carrier/Bryant network thermostats as well

#### Requirements

 * Perl
   * Mojolicious
   * DateTime
   * [WWW::Wunderground::API](https://metacpan.org/module/WWW::Wunderground::API)
   * [IO::Termios](https://metacpan.org/module/IO::Termios) for RS485 serial monitoring
   * Try::Tiny

####Usage
 * Set your proxy server/port in the advanced wireless settings on the thermostat to point to your infinitude host/port. 
 * Start Infinitude. This traffic is _not encrypted_, so only run on a trusted network.
 *   The author runs Infinitude on a [Pogoplug v4](http://www.amazon.com/Pogoplug-Series-4-Backup-Device/dp/B006I5MKZY/ref=sr_1_1?ie=UTF8&tag=sbhq-20&qid=1415825203&sr=8-1&keywords=pogoplug) which sits on top of the air handler.

 <a href="http://imgur.com/IESJCCw"><img src="http://i.imgur.com/IESJCCw.jpg" title="source: imgur.com" /></a>

Edit the $conf section of infinitude.pl to set your optional Wunderground API key and RS485 serial device.

Infinitude is a Mojolicious application, so the simplest way to run it is via:

   ./infinitude daemon

which starts a server in development mode on port 3000.

Or to listen on port 80:

   ./infinitude daemon -l http://:80

See ./infinitude <command> --help for additional options

With any luck, Carrier will allow the owners of these devices and data direct access rather
than this ridiculous work around. If you have one of these thermostats, tell
Carrier you'd like direct network access to your thermostat, or at the very
least, access to a public API!
