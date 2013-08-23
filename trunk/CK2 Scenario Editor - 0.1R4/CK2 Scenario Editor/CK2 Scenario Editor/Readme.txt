/============================\
|=== EU3 Scenario Editor ====|
|= Version 0.5 (Sept 17 07) =|
|======= By MichaelM ========|
\============================/


=== What is it? ===

This program loads data from either a saved game or history files and shows
the world map based on it. It lets you click on a province to edit its history
(if you are viewing history) or save game entry (if you are viewing a saved
game). There are also a number of other views to help you visualize the game
data. If you are in the political view, you can click on a country to edit its
history file. The history editors have some syntax highlighting and validation.


=== System Requirements ===

Java 1.5 or later (tested on Java 1.6)
EU3 (tested on regular and Napoleon's Ambition)


=== Instructions ===

1. Unzip somewhere.
2. Edit config.txt so that maindir points to your EU3 installation (should also
   work with the demo). If you're using a mod, edit the moddir entry also.
   Or you can double-click config.bat to get a graphical editor, if you have
   Java 1.6.
3. Double-click scen-ed.bat. A dialog will appear asking whether you want to
   load a saved game. Note that using a moddir with a saved game from another
   mod or vanilla will usually cause strange things to happen.

Click on a province, and its name should be shown at the bottom of the window.
Click "Show province history" to display the province's history file (Note: As
of version 0.2, simply double-clicking the province will display the history).
If you make any changes, you will get a dialog asking whether to save the
changes. If you click "Yes", a backup of the old file will be saved (with a '~'
prepended to its name). Note that at most one backup file exists at a time; if
you already had a backup file, it will be automatically overwritten.

In the menu titled "Views" are quite a few different ways to view the map. Play
around with them for a while to get a feel for what you can and can't do.

In most views, if a province history file is not found, the province will
appear bright red on the country map, and the message "Province has no history
file" will appear next to the "Show country history" button. A warning message
will be printed to the console whenever the mouse touches such a province, so
there may be a lot of output.

The current date is shown in the toolbar. Change the spinners to whatever you
want, and click "Set date" to apply the changes. The date has no effect when
in province mode.

There is also a bookmark list. If you loaded a saved game, there should be two
"bookmarks" in the list: one at 1.1.1, before any history, and the other at
the date of the saved game.

Use Ctrl +/- to zoom in and out. Note that zooming too far in may cause the
program to run out of memory; thus, I have capped the zoom at 5x. If you
get a stack trace that starts with something like "java.lang.OutOfMemoryException"
then edit the .bat file to look like:

java -jar EU3_Scenario_Editor.jar -Xmx512m

The 512 is the maximum number of megabytes of memory that can be used for the
program; you can set this to whatever you think is best.


=== Troubleshooting ===

If the program hangs, check the console window; hopefully, there will be a
stack trace there. If it just opens and shuts immediately, add the line
pause
to scen-ed.bat. This will make the console window stay up after the program
exits.


=== Known Bugs ===

* When you close an editor window, a large amount of text (three stack traces)
  is printed to standard output. This does not cause any other problems, so
  don't worry about it. (I do intend to fix it, but it's hard to track down.)
* In saved games, provinces that were colonized during the game appear as if
  they were controlled by no one. This is because the scenario editor uses the
  history to determine the controller, and for some reason, the game does not
  record in the history that the colonizing country also controlls the province.
  There is currently no workaround.


=== To do ===

    * Add a view mode for discoveries.
    * Improve the find capability in the editor.
    * I don't know what else; what do you think? Post your suggestions on the
        thread!


=== Credits ===

EUG-file handling (lib/eugFile.jar) is based partly on Kinniken's
VictoriaEditor (http://www.kstudio.net/vedit/). All else is entirely my own
work.
Big thanks go to seboden. He has been most helpful in not just finding bugs,
but also suggesting fixes.

-- MichaelM

