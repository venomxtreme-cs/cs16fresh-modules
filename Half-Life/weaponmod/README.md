weaponmod
=========

Half-Life weapon-mod framework (lets plugins add and manage custom weapons).

    Type        AMXX module
    Game        Half-Life (valve) only
    ABIs        arm64, armv7a

Install
-------

Copy both .so files into <xash>/custom_modules/amxx/, open CS16Fresh, go to
the Modules tab, set the target game to Half-Life, and tap Install.

Status on Android (read this)
-----------------------------

weaponmod locates the game functions it wants to hook by looking them up in
the game dll's exported symbols. The Half-Life game dll shipped with the
engine is built optimized, which inlines most of those functions away, so on
Android weaponmod loads and stays resident but its hooks do not activate. It
reports this in the log and disables itself cleanly - it will not crash the
server.

So on the current engine build this module is safe to install but does not
yet add working custom weapons. It will start working once the game dll
exports the symbols it needs.
