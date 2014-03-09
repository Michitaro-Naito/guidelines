Use var for JavaScript as long as you can to avoid violating global variables.

Name a model like "FooInfo" if it is not a representation. (eg. Foo will not be deleted even when FooInfo is deleted.)

Make it session-less and database-less as long as you can.

JavaScript ['foo','bar',] will cause troubles silencely for some browsers, be aware.

International website must have a URL scheme like "/en-US/User/Login". (Never use "/User/Login?culture=en-US", "/User/Login/en-US", "/en/User/Login".)

If Server and Client use the same data-scheme, then make it DLL and share it. (Never change it oftenly, of course.)

Redis is a nice server to cache but maybe you made a mistake to keep things scalable if you need it. (Properly designed, scalable web applications never need Redis.)

To protect innocent Users from evil Users, User must be authenticated by at least one of these methods: Google+, CarrierEmail or CreditCard. IPAddress and DeviceID are not sufficient.

Server is naked if it has no DEP (Data Execution Preventation).

If you are willing to publish your library, make it Nuget and publish codes on GitHub.

Always test success and failure.

Talking about reponsibility among cooperaters wastes time. Just solve problems or discuss how to solve them instead.

Non-scalable business has no future. Just decline and never take your time for it.
