reapi
=====

ReGameDLL API natives for Counter-Strike, from the ReGameDLL project.

    Type        AMXX module
    Game        Counter-Strike
    ABIs        arm64, armv7a
    Requires    ReGameDLL

Install
-------

Copy both .so files into <xash>/custom_modules/amxx/, open CS16Fresh, go to
the Modules tab, set the target game to Counter-Strike, and tap Install.

reapi exposes natives that talk to ReGameDLL internals, so it only works when
the server is running ReGameDLL. On a stock Half-Life game dll the natives are
present but have nothing to talk to.
