<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 0; WARNINGs: 0; ALERTS: 7.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>

<p style="color: red; font-weight: bold">Links to alert messages:</p><a href="#gdcalert1">alert1</a>
<a href="#gdcalert2">alert2</a>
<a href="#gdcalert3">alert3</a>
<a href="#gdcalert4">alert4</a>
<a href="#gdcalert5">alert5</a>
<a href="#gdcalert6">alert6</a>
<a href="#gdcalert7">alert7</a>

<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>


_"Ahorn is a visual level maker and editor for the game Celeste. It allows editing map binaries, creating new ones, adding rooms, and filling the rooms with anything your heart desires (as long as what your heart desires is possible within the realms of the game). The generated map binaries can be loaded in the stock game or using Everest." - Ahorn Developers_



<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/Ahorn-Tutorial0.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/Ahorn-Tutorial0.png "image_tooltip")


_Core displayed in Ahorn, using Broadway_


### Installation

There are two different methods of installing Ahorn. One works on all systems, while one is easier and only works on Windows.


#### Windows Installation (NSIS/Easy Installer)

Simply download and run the installer from [here](https://thoas.feralhosting.com/oddstr13/sharex/file/setup-Ahorn-0.0.3.exe). Ahorn will be in your start menu. However, because the installer is quite old, once Ahorn is installed, you'll have to update to the latest version of Ahorn, else you'll have a lot of features unavailable. While this is typically faster, it isn't reliable every time. That being said, if you have any issues, head over to [the Discord server](https://discord.gg/Vg2cnB5) if you have any questions, comments, or issues.


#### Install_ahorn.jl (All platforms)

This method works on all systems, however it will be much faster on Unix-like systems, such as Linux and macOS. Thus, the Easy Installer is recommended over it on Windows. You must have Julia 0.6 installed for this method. Julia 1.0, 1.1, and 0.7 will **not** work. Get it from [the Julia old releases page](https://julialang.org/downloads/oldreleases.html), or your distribution's package manager. Download the installer from [here](https://raw.githubusercontent.com/CelestialCartographers/Ahorn/master/install_ahorn.jl), and run it from the terminal/command prompt by moving to the directory you downloaded the installer to, and run `julia install_ahorn.jl`.


### Basic Usage



<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/Ahorn-Tutorial1.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/Ahorn-Tutorial1.png "image_tooltip")


_Chapter 1 C-Side, displayed inside Ahorn (GTK theme: [Lavender](https://github.com/vinceliuice/Lavender-theme))_

At first glance, the program might look confusing, so let's take a look at it one element by one:


#### Top Menubar



<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/Ahorn-Tutorial2.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/Ahorn-Tutorial2.png "image_tooltip")


The Menubar of Ahorn is pretty simple, as it's just a few buttons.


##### File

The File menu has 5 buttons, and they're pretty self-explanatory. 



*   <span style="text-decoration:underline;">Open</span> (Ctrl+O) opens a compatible .bin map file; 
*   <span style="text-decoration:underline;">New</span> makes a new .bin file that you're able to edit and then save inside Ahorn; 
*   <span style="text-decoration:underline;">Save</span> (Ctrl+S) and <span style="text-decoration:underline;">Save as</span> export the map as a map .bin file (that you can then play with Everest, replacing one of the game's levels, or some other ways); 
*   <span style="text-decoration:underline;">Exit</span> exits Ahorn, prompting the user to save if their map is unsaved.


##### Edit

The Edit menu simply has the Undo and Redo buttons. The <span style="text-decoration:underline;">Undo</span> (Ctrl+Z) button undoes the last action the user has done, and multiple if used multiple times, and the <span style="text-decoration:underline;">Redo</span> (Ctrl+Shift+Z) button redoes the last action the user has undone, and multiple if used multiple times.


##### Map

The Map menu has 3 buttons. Save Map Image is self explanatory, while the others are more complicated. They'll be covered in later chapters.


##### Room

The Room menu allows the user to create a new room inside the opened map, or configure the currently selected one. Rooms will be covered in later chapters.


##### Help

The Help menu has the <span style="text-decoration:underline;">Check for Updates</span> button, which checks the Ahorn GitHub repo for new updates, and the <span style="text-decoration:underline;">About</span> button:



<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/Ahorn-Tutorial3.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/Ahorn-Tutorial3.png "image_tooltip")


_This menu also contains the Git commit the user is using, and a link to the GitHub repo, but they're not shown in this screenshot._


#### Main Display

Everything below the menubar will be called the Main Display throughout this guide.

<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/Ahorn-Tutorial4.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/Ahorn-Tutorial4.png "image_tooltip")



##### Room Table

The Room table shows all the rooms in the current opened map. These are controlled via multiple hotkeys and the Room menu in the Top Menubar:



*   Move rooms with Alt+Arrow Keys.
*   Select a room in the room display and press Alt+Delete to delete one.
*   Select a room in the room display and select Room > Configure to change the room's properties
*   Select Room > Add to add a new room to the map
*   Ctrl+Alt+LMB on a room to teleport to that one in Celeste (Everest in Debug Mode + HTTP.jl only)

The table is sorted alphanumerically, by room name - the same way that Celeste does it. It's recommended to organize your rooms in a manner alike to Celeste's official rooms, so that strawberry and cassette position in the pause menu and the chapter select screen is less tedious and automatic. The 'lvl_' at the start of each room is a glitch in the official (private) map editor, and isn't necessary.

The minimum width and height for rooms are width=40, height=23. You can go below that, but it isn't recommended, as 40x23 is the size of the screen in tiles (the height is actually 22.5, but you can't make half-tiles in Celeste, so it takes up the whole screen having half a tile cut off at the bottom). If you do, however, transitions will glitch a little and entities in rooms other than that rooms won't render in Celeste, causing really weird visuals.


##### Tools

Ahorn's tools consist of everything you need to actually make maps:



*   Brushes allows you to paint bgTiles and fgTiles and have 3 modes: Pencil, which draws 1 tile at a time normally, Dither which creates a tiled pattern out of the tiles you draw and Ahorn which makes a seed pattern out of the selected tileset;
*   Bucket flood-fills a region of the same tile (including air) with a new tile. This is the same as the paint bucket or flood fill tool in most photo editing programs.
*   Lines makes a line out of a tile which can be either a straight line or an angled line;
*   Rectangles creates either a hollow or filled rectangle out of the selected tile;
*   Placements places entities, triggers, and decals. This will be looked into in further in later chapters;
*   Selection selects tiles, entities, triggers and decals to edit them: delete them or move them.

You can also toggle an element's visibility in the room display by double-clicking its name in the menu:



<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/Ahorn-Tutorial5.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/Ahorn-Tutorial5.png "image_tooltip")


<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/Ahorn-Tutorial6.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/Ahorn-Tutorial6.png "image_tooltip")


_In this example, bgTiles, triggers and bgDecals are toggled off, making them invisible in the room display._


##### Room Display

The room display is pretty self-explanatory: it displays the map's rooms, their tiles, entities, triggers and decals and allows you to edit them or change them. In order to select a room, you have to click on it with the left mouse button.

Navigating the room display is pretty easy:



*   Hold the right mouse button and move the mouse to move the map display;
*   Use the scroll wheel to zoom in or out.

Do keep in mind filler rooms in vanilla Celeste maps don't appear, but are still there: using debug mode's map edit display you can most likely notice them right away (named "FILLER"). There is no way to remove them or edit them other than to use Maple.
