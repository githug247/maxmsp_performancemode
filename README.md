# maxmsp_performancemode


what performancemode does:

1. it changes displaying your patch from edit to presentation mode (no cables, no unneeded objects)
2. it hides all screen eating taskbars, unnecessary stuff, just your patch fullscreen in presentation mode
3. it sends a terminal command (via shell) using 'caffeinate -d' (macOS only! + check your OS version... apple might have done some changes; there are tons of forum reports about this). this disables your lockscreen and your screensaver until performance mode is undone and you've returned to edit mode (without having anything to change in your energy settings). so, imagine you're on stage with 10 minutes of nothing to do and then comes your important part... suddenly locking screens and type in password requests won't happen anymore :)


dependencies & usage:

this patch works with MAX on macOS only! it is possible to adapt it to windows, but you'll have to change some lines, esp. ref. to the shell object use.

TO MAKE PERFORMANCEMODE RUN YOU'LL NEED TO INSTALL JEREMY BERNSTEIN'S SHELL OBJECT (INTO YOUR MAX LIBRARY FOLDER) FIRST:
https://cycling74.com/forums/shell/ , https://github.com/jeremybernstein/shell , e.g. https://github.com/jeremybernstein/shell/releases/tag/1.0b2 

next you'll need the 'performancemode.maxpat' file from this repository here!
use it as subpatcher or as object from your MAX library. 'performancemode.maxpat' basically controls MAX's internal thispatcher object, which refers to the patcher window you've placed it in. so, performancemode's right outlet always needs to be connected to the inlet of thispatcher (see 'performancemode_integration.png'). you may use send and receive objects between performancemode and thispatcher to make another subpatcher window than the one your working in fullscreen. the file 'performancemode_integration_example.maxpat' contains an optional further explaination.


ATTENTION!: check the 'integration'-files for the correct connection of the message box, which also needs to be included in MAX's presentation mode (-> Inspector)! you can also replace that message box with a textbutton object etc. there are many ways to use the performancemode code. but be sure you have a way back to edit mode in your patch once you've switched to performancemode.
