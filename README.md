CS16Fresh Custom Modules
========================

A catalog of custom native modules (`.so`) for CS16Fresh. Every module here
is optional: browse this repo, pick the ones you want, and install them with
the Modules screen in the CS16Fresh app. Nothing here is installed unless you
choose to install it.

This is a catalog only. The app does not download from here automatically -
you download a module's files, drop them in, and install from the Modules tab.


Layout
------

Each game has its own folder. Inside a game folder, every module lives in its
own named subfolder, and that subfolder holds the `.so` files for it:

    Counter-Strike/          modules that only work in Counter-Strike
        reapi/
            libamxx_reapi_arm64.so
            libamxx_reapi_armv7a.so
    Half-Life/               modules that only work in Half-Life (valve)
        weaponmod/
            libamxx_weaponmod_arm64.so
            libamxx_weaponmod_armv7a.so


File naming
-----------

The app reads the module name and CPU type (ABI) straight from the file name,
so keep this exact scheme:

    AMXX module      libamxx_<name>_arm64.so
                     libamxx_<name>_armv7a.so

    Metamod plugin   lib<name>_arm64.so
                     lib<name>_armv7a.so

Ship both ABIs when you can (arm64 and armv7a). The app picks the right one
for the device on its own.


How to install a module
-----------------------

1. Download the `.so` files for the module you want.
2. Copy them into the drop-in folder on your device:

       AMXX module     <xash>/custom_modules/amxx/
       Metamod plugin  <xash>/custom_modules/mod/

   (<xash> is your game folder, usually /sdcard/xash.)
3. Open CS16Fresh, go to the Modules tab, and pick the target game
   (Counter-Strike or Half-Life).
4. Tap Install on the module. The app places the file and writes the config
   line for you.
5. Restart the game so the module loads.

You can also skip the drop-in folder entirely and use the in-app file picker
to choose a `.so` directly.

Pick the matching game. A Counter-Strike module installed under Half-Life (or
the other way round) will simply not load.


Available modules
-----------------

Counter-Strike
    reapi        ReGameDLL API natives (requires ReGameDLL)

Half-Life
    weaponmod    Half-Life weapon-mod framework (Half-Life only)


Adding a module
---------------

To contribute a module, open a pull request that adds a new subfolder under
the right game folder, named after the module, containing the `.so` files and
a short README describing what it does and any requirements.
