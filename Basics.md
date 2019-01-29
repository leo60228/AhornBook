**PLEASE DM YOUR EMAIL TO thefox#1337 OR PenguinOwl#3931 FOR EDITING RIGHTS.**

<h2>Celeste Mapping Guide</h2>


<p>Written by leo60228, thefox, Hyperfenix, and PenguinOwl

<h2>Table of Contents</h2>



[TOC]


<h2 id="chapter-1-basics">Chapter 1: Basics</h2>


_"Ahorn is a visual level maker and editor for the game Celeste. It allows editing map binaries, creating new ones, adding rooms, and filling the rooms with anything your heart desires (as long as what your heart desires is possible within the realms of the game). The generated map binaries can be loaded in the stock game or using Everest." - Ahorn Developers_

![alt_text](https://i.imgur.com/kwr69AK.png)


_Core displayed in Ahorn, using Broadway_

<h3 id="installation">Installation</h3>


There are two different methods of installing Ahorn. One works on all systems, while one is easier and only works on Windows.

<h4 id="windows-installation-nsis-easy-installer">Windows Installation (NSIS/Easy Installer)</h4>


Simply download and run the installer from [here](https://thoas.feralhosting.com/oddstr13/sharex/file/setup-Ahorn-0.0.3.exe). Ahorn will be in your start menu. However, because the installer is quite old, once Ahorn is installed, you'll have to update to the latest version of Ahorn, else you'll have a lot of features unavailable. While this is typically faster, it isn't reliable every time. That being said, if you have any issues, head over to [the Discord server](https://discord.gg/Vg2cnB5) if you have any questions, comments, or issues.

<h4 id="install_ahorn-jl-all-platforms">Install_ahorn.jl (All platforms)</h4>


This method works on all systems, however it will be much faster on Unix-like systems, such as Linux and macOS. Thus, the Easy Installer is recommended over it on Windows. You must have Julia 0.6 installed for this method. Julia 1.0, 1.1, and 0.7 will **not** work. Get it from [the Julia old releases page](https://julialang.org/downloads/oldreleases.html), or your distribution's package manager. Download the installer from [here](https://raw.githubusercontent.com/CelestialCartographers/Ahorn/master/install_ahorn.jl), and run it from the terminal/command prompt by moving to the directory you downloaded the installer to, and run `julia install_ahorn.jl`.

<h3 id="basic-usage">Basic Usage</h3>





![alt_text](https://i.imgur.com/k5BIPkr.png "image_tooltip")


_Chapter 1 C-Side, displayed inside Ahorn (GTK theme: [Lavender](https://github.com/vinceliuice/Lavender-theme))_

At first glance, the program might look confusing, so let's take a look at it one element by one:

<h4 id="top-menubar">Top Menubar</h4>





![alt_text](https://i.imgur.com/TQcVQOz.png)


The Menubar of Ahorn is pretty simple, as it's just a few buttons.

<h5 id="file">File</h5>


The File menu has 5 buttons, and they're pretty self-explanatory. 



*   <span style="text-decoration:underline;">Open</span> (Ctrl+O) opens a compatible .bin map file; 
*   <span style="text-decoration:underline;">New</span> makes a new .bin file that you're able to edit and then save inside Ahorn; 
*   <span style="text-decoration:underline;">Save</span> (Ctrl+S) and <span style="text-decoration:underline;">Save as</span> export the map as a map .bin file (that you can then play with Everest, replacing one of the game's levels, or some other ways); 
*   <span style="text-decoration:underline;">Exit</span> exits Ahorn, prompting the user to save if their map is unsaved.

<h5 id="edit">Edit</h5>


The Edit menu simply has the Undo and Redo buttons. The <span style="text-decoration:underline;">Undo</span> (Ctrl+Z) button undoes the last action the user has done, and multiple if used multiple times, and the <span style="text-decoration:underline;">Redo</span> (Ctrl+Shift+Z) button redoes the last action the user has undone, and multiple if used multiple times.

<h5 id="map">Map</h5>


The Map menu has 3 buttons. Save Map Image is self explanatory, while the others are more complicated. They'll be covered in later chapters.

<h5 id="room">Room</h5>


The Room menu allows the user to create a new room inside the opened map, or configure the currently selected one. Rooms will be covered in later chapters.

<h5 id="help">Help</h5>


The Help menu has the <span style="text-decoration:underline;">Check for Updates</span> button, which checks the Ahorn GitHub repo for new updates, and the <span style="text-decoration:underline;">About</span> button:




![alt_text](https://i.imgur.com/PXekVXT.png?1 "image_tooltip")


_This menu also contains the Git commit the user is using, and a link to the GitHub repo, but they're not shown in this screenshot._

<h4 id="main-display">Main Display</h4>


Everything below the menubar will be called the Main Display throughout this guide.


![alt_text](https://i.imgur.com/El0m9zk.png "image_tooltip")


<h5 id="room-table">Room Table</h5>

<img align="right" src="https://i.imgur.com/eQinAar.png?1">


The Room table shows all the rooms in the current opened map. These are controlled via multiple hotkeys and the Room menu in the Top Menubar:



*   Move rooms with Alt+Arrow Keys.
*   Select a room in the room display and press Alt+Delete to delete one.
*   Select a room in the room display and select Room > Configure to change the room's properties
*   Select Room > Add to add a new room to the map
*   Ctrl+Alt+LMB on a room to teleport to that one in Celeste (Everest in Debug Mode + HTTP.jl only)

The table is sorted alphanumerically, by room name - the same way that Celeste does it. It's recommended to organize your rooms in a manner alike to Celeste's official rooms, so that strawberry and cassette position in the pause menu and the chapter select screen is less tedious and automatic. The 'lvl_' at the start of each room is a glitch in the official (private) map editor, and isn't necessary.

The minimum width and height for rooms are width=40, height=23. You can go below that, but it isn't recommended, as 40x23 is the size of the screen in tiles (the height is actually 22.5, but you can't make half-tiles in Celeste, so it takes up the whole screen having half a tile cut off at the bottom). If you do, however, transitions will glitch a little and entities in rooms other than that rooms won't render in Celeste, causing really weird visuals.

<h5 id="tools">Tools</h5>
<img align="right" src="https://i.imgur.com/NqxakQV.png?1">


Ahorn's tools consist of everything you need to actually make maps:



*   Brushes allows you to paint bgTiles and fgTiles and have 3 modes: Pencil, which draws 1 tile at a time normally, Dither which creates a tiled pattern out of the tiles you draw and Ahorn which makes a seed pattern out of the selected tileset;
*   Bucket flood-fills a region of the same tile (including air) with a new tile. This is the same as the paint bucket or flood fill tool in most photo editing programs.
*   Lines makes a line out of a tile which can be either a straight line or an angled line;
*   Rectangles creates either a hollow or filled rectangle out of the selected tile;
*   Placements places entities, triggers, and decals. This will be looked into in further in later chapters;
*   Selection selects tiles, entities, triggers and decals to edit them: delete them or move them.

You can also toggle an element's visibility in the room display by double-clicking its name in the menu:



_In this example, bgTiles, triggers and bgDecals are toggled off, making them invisible in the room display._

<h5 id="room-display">Room Display</h5>


The room display is pretty self-explanatory: it displays the map's rooms, their tiles, entities, triggers and decals and allows you to edit them or change them. In order to select a room, you have to click on it with the left mouse button.

Navigating the room display is pretty easy:



*   Hold the right mouse button and move the mouse to move the map display;
*   Use the scroll wheel to zoom in or out.

Do keep in mind filler rooms in vanilla Celeste maps don't appear, but are still there: using debug mode's map edit display you can most likely notice them right away (named "FILLER"). There is no way to remove them or edit them other than to use Maple.

Clicking on an element with the middle mouse button while having the element type selected in the Tools Placements menu selects that element inside the Placements menu.

<h2 id="chapter-2-entities-triggers-and-decals">Chapter 2: Entities, Triggers and Decals</h2>


In this chapter, we will be going over how to place, edit and use entities, triggers and decals.

<h3>Entities</h3>


The entities list in Ahorn consists of [() entities](https://github.com/CelestialCartographers/Ahorn/tree/master/src/entities) (not all Celeste entities are implemented). Most of them have their own quirks and little notes to them, so we will be dedicating this chapter to looking over to most of these.




<img align="right" src="https://i.imgur.com/YWx1otX.png">


First, let's actually take a look at what an entity consists of:

An entity is an object in a room, with X and Y coordinates (some have width and height properties aswell). In order to edit those, you have to either use the property menu (available via right-clicking an entity), or use one of the shortcuts (arrow keys to move an entity, q/w/a/s to make it wider, higher, skinnier, or lower respectively, n to add a node, delete key to delete). Some entities also contain their own properties. For this example, we'll be using the Bonfire entity, as it's simple to understand and only has 1 of its own property:


![img](https://i.imgur.com/wrrWVcD.png)


Upon opening the properties menu, you'll see 3 properties: X, Y, and Mode. The X and Y are its' coordinates, but the Mode is a little bit more interesting. It has 3 options: Lit, Unlit, and Smoking. In order to change these, use the dropdown menu (or enter it manually), then press the Update button. Here are all 3 of them in action:




<img align="center" src="https://i.imgur.com/jm25ZBx.png">


<img align="center" src="https://i.imgur.com/o6VbLxy.png">


<img align="center" src="https://i.imgur.com/BxclTT5.png">


_Lit, Unlit and Smoking campfires in Celeste (not Ahorn!)_

_Note that the way they look might change depending on if you have the Dreaming checkbox in Metadata on or off._

This was a simple dropdown property with 3 choices, now let's take a look at an entity that has nodes. For this example, we'll be using the Badeline Boss entity.



![alt_text](https://i.imgur.com/rKHaT8E.png)


This might look confusing at first, with all the checkboxes and properties, but don't worry, we'll be only focusing on the node property this time.

When you add a node by pressing the 'Add row' key, a new entry in the table will show up:


![alt_text](https://i.imgur.com/GMraCnl.png)


This is the node that we have just created. In order to save this node, press Update, and it'll render in the Room Display, and if you want to edit this node's location, click on the field you want to edit and change it to whatever you like.

However, this isn't the best method to make nodes. The better way is to select the node in Room Display, then press the 'n' key. This will immediately create a new node close to the entity, and select it.

Whichever way you make the new node, they will always render in the Room Display like this:


![alt_text](https://i.imgur.com/Z6kzHhv.png)


When you unselect the node/source entity, the node will disappear and will only appear back if you select the source entity.

For the Badeline Boss, you can have unlimited nodes and they define where Badeline will move in the room once you hit her. Keep in mind, though, that the last node is meant to be out-of-bounds, because if you touch it, it'll crash the game.

There's no properties other than regular textfield/dropdown/checkmark/number fields and node tables, so from here on out, we'll be looking at the specific entity quirks and notes.

<h4>Entity Quirks</h4>
