Use var for JavaScript as long as you can to avoid violating global variables.

Name a model like "FooInfo" if it is not a representation. (eg. Foo will not be deleted even when FooInfo is deleted.)

Make it session-less and database-less as long as you can.

JavaScript ['foo','bar',] will cause troubles silencely for some browsers, be aware.

International website must have a URL scheme like "/en-US/User/Login". (Never use "/User/Login?culture=en-US", "/User/Login/en-US", "/en/User/Login".)

If Server and Client use the same data-scheme, then make it DLL and share it.

Redis is a nice server to cache but maybe you made a mistake to keep things scalable if you need it. (Properly designed, scalable web applications never need Redis.)
