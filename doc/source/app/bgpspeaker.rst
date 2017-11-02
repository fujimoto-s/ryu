************************************
ryu.service.protocol.bgp.application
************************************

This application provides a convenient way to speak BGP
protocol.

It reads a configuration file which specifies neighbors, routes and some other
settings.
ryu/service/protocols/bgp/bgp_sample_config.py is a sample
configuration file for this application.
Configurable items and descriptions are written in this sample.

Launch the speaker::

    ryu-manager ryu/service/protocols/bgp/application.py --bgp-app-config-file ryu/service/protocols/bgp/bgp_sample_config.py


It also provides an SSH interface. You can see the RIB and do some operations
via this. SSH port and username/password can be configured by the
configuration file.
You can check the help by hitting '?' key in this interface.


Example::

    $ ssh localhost -p 4990

    Hello, this is Ryu BGP speaker (version 4.19).

    bgpd> # Hit '?' key
     clear - allows to reset BGP connections
     help - show this help
     quit - exit this session
     set - set runtime settings
     show - shows runtime state information
    bgpd>
    bgpd> show rib all
    Status codes: * valid, > best
    Origin codes: i - IGP, e - EGP, ? - incomplete
         Network        Labels   Next Hop   Reason      Metric LocPrf Path
     *>  10.10.1.0/24   None     0.0.0.0    Only Path                 i
    bgpd>

