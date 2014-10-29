MyProxy Web Service Package
===========================
Provides a simple web service interface to MyProxyCA.  MyProxy is a Service for
managing and issuing PKI based credentials which is part of the Globus Toolkit.
MyProxyWebService provides a HTTP based wrapper interface to MyProxy enabling
HTTP based clients to connect to a MyProxy server and retrieve credentials.

The interface is implemented as a WSGI application which fronts a normal
MyProxyCA server.  ``myproxy-logon`` and ``myproxy-get-trustroots`` are
expressed as web service calls.  The WSGI application forwards the requests on
to the MyProxy server over the usual MyProxy protocol.  The web service
interface is RESTful using GET and POST operations and the logon interface makes
uses of HTTP Basic Auth to pass username and pass-phrase credentials.  The
service is hosted over HTTPS.

The unit tests include a test application served using paster.  Client scripts
are also available which need no specialised installation or applications, only
openssl and wget or curl which are typically available on Linux/UNIX based
systems.

Tests
-----
Unit test module with test files is in ``myproxy/ws/test/`` and 
``myproxy/ws/client/test``.  

Documentation
-------------
Epydoc generated documentation is available in ``documentation/``.  run the 
Makefile to regenerate if required.  Also see ``setup.py`` for a summary.
