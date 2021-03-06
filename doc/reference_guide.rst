GeoEasy 3.1
===========
Reference Guide
===============

GeoEasy is a complex tool for land surveyors 

* to calculate coordinates from observations,
* to convert surveyors' data set into different formats,
* to generate TINs and DEMs and calculate volumes,
* to adjust 1D/2D/3D networks,
* to calculate parameters of regression shape over points

The program supports several input and
output formats, so it can easily be inserted into user’s work-flow.

GeoEasy main window
-------------------

Starting the program the main window appears at upper left corner of the 
display. This window has menus only. If the globe is not rotating the 
program is busy, the user have to wait.

File menu
~~~~~~~~~

In the file menu the besides the file and project handling functions the
communicaton program (ComEasy) and settings are available.
projects, the third group 

New
...

A new geo data set is created, in the **Save As** dialog of the operating system
the user can set the location and the name of the new file.

.. image:: rg_images/new.png
	:align: center

Load
....

Open one or more data set. There are several data types you can select from
(e.g. .geo, .csv, .gsi, etc). You can select more files to load, use Shift or
Ctrl key to select more files. Only the 
memory of the computer limits the number of loaded data sets.

.. image:: rg_images/load.png
	:align: center

If the observations were made in face left and face right, from the readings on
the horizontal and vertical circle and the distances an average is calculated.
GeoEasy stores and uses these average values.

.. note::
	The name of the loaded data sets must be different even if they are
	loaded from different folders.

Close
.....

Close a loaded data set. Beside this menu option a cascading list of the
loaded data sets pops up. The user can select a data set name from the list.
If the data set to close have been changed, the user has an option to save it.

Save
....

Save a changed data set. Beside this menu option a cascading list of the
loaded data sets pops up. The user can select a data set name from the list.
The data set is saved to GeoEasy geo format even if the type of opened data
set is different. The name and the folder of the
files is the same as the loaded data set.

Save all
........

Save all changed data set to GeoEasy format.

Save as
.......

Save the selected data set into a different folder/name or type.
Beside this menu option a cascading list of the
loaded data sets pops up.
After selecting a file, in the Save As dialog box you can choose location, name
and type for the output file. After saving the original data set left opened.

Merge
.....

Merge all loaded data sets into a single GeoEasy data set.
After merging the original data sets left opened and the merged data set is not
loaded. If the same point has coordinates in more than one data set the first
coordinates found are saved to the merged data set.

GNU Gama export
...............

Export observations and coordinates into a GNU Gama XML file. 
First the network dimension (type of file 1D/2D/3D) and output file name is 
selected. Then you can 
select fixed and adjusted points. Only the observation belonging to the 
selected points are written to the output file.
If no fixed points are selected a free network adjustment is solved.

Load project
............

Load a previously saved project. Data set and windows are opened a saved to
the project.

Save project
............

Save the actual state of GeoEasy. The list of  opened datasets and windows are 
saved into the project file (.gpr). The project file is a simple text file.
to the project

Close project
.............

Close all data sets and windows except **Calculation results** and main window.

ComEasy
.......

ComEasy is the communication module which can communicate with the instruments
through serial (RS-232) line.

.. image:: rg_images/comeasy.png
	:align: center

Before starting download or upload to/from the instrument, the parameters of
the serial line have to be set (e.g. speed, data bits, parity, stop bits) using
**Commands/Settings** from the menu.

.. image:: rg_images/compars.png
	:align: center

Select **Commands/Download** from the menu to start downloading data from the
instrument. Set the output file in the displayed dialog box and start
data transmission on the instrument.

Statistics
..........

Summary information are shown in a popup windows, number of loaded data sets,
number of points, number of unknown points, number of detail points,
number of stations, number of known stations, number of occupied points,
number of oriented stations.

Calculation parameters
......................

.. image:: rg_images/calcpar.png
	:align: center

Reduction for projection [mm/km]:
	the change of the distances caused by the projection

Average height above MSL [m]:
	used to reduce distances to MSL

Standard deviation for directions ["]:
	mean error for directions and zenith angles in arc seconds

Standard deviation for distances [mm]:
	additive item for the mean error of distances

Standard deviation for distances [mm/km]:
	multiplier item for the mean error of distances

Standard deviation of levelling [mm/km]:
	relative mean error for levelling

Calculate refraction and Earth curve:
	turn on to consider the affect of refraction and Earth curve for
	distances longer than 400 meters

Decimals in results:
	number of figures after the decimal point in the Calculation results
	window, field-books and coordinate lists

Adjustment parameters
.....................

.. image:: rg_images/adjpar.png
	:align: center

Confidence level (0-1):
	Confidence level for detecting blunder, usual value 0.95 or 0.99.

Angle units:
	Angle units in the output of adjustment (360 for DMS, 400 for GON)

Tolerance [mm]:
	Maximal linear difference between observations and preliminary 
	coordinates. Observations over limit are not considered in the adjustment.

Distance limit [m]:
	Mean error for directions are enlarged linearly below this distance limit.
	For example if the distance limit is 200 meters and the mean error for
	directions is 3", the mean error for a 50 meters long direction will be
	200 / 50 * 3" = 12".

SVG error ellipses:
	An SVG will be generated with the network and error ellipses.

Colors
......

.. image:: rg_images/colpar.png
	:align: center

The colours used by the program can be set here. Click on the coloured
button toselect another colour.

Other parameters
................

.. image:: rg_images/otherpar.png
	:align: center

Language:
	Language of the user interface. You have to save parameters and restart
	the program to take affect.

Separator in exported lists:
	Separator character used in CSV export.

Separators in imported lists:
	List of separator characters in text import.

Skip repetead separators:
	MUltiple neighboring separators are considered as single separator.

Autorefresh windows:
	Refresh all opened windows if something changed.

Use detail points in orientation and adjustment:
	GeoEasy consider a point as detail point if its ID is number, it was not
	a station and only a polar observation is in the field-book for that
	point. These points are not selectable in orientation and network 
	adjustment.

Default fieldbook mask:
	The name of the default fieldbook mask. You can select from the loaded
	masks.

Default coordinate mask:
	The name of the default fieldbook mask. You can select from the loaded
	masks.

Number of rows in masks:
	The default number of rows in the fieldbooks and coordinate lists.

Browser:
	The path to the browser program used to open HTML files.
	It is a Linux only parameter.

RTF viewer:
	The path to the dociment viewer program for RTF files.
	It is a Linux only parameter.

Save parameters
...............

Save settings to *geo\_easy.msk* file.
This file is used to set the parameters after starting the program.

Exit
....

Close the application. If unsaved data exists you have a chance to save it.

Edit menu
~~~~~~~~~

The menu options in the edit menu can be used to display and edit GeoEasy
data set. A GeoEasy data set consists of three parts:

* observations (field-book)
* coordinates
* observation parameters

Observations
............

This menu option has a cascading menu with the name of the loaded GeoEasy data 
sets. After selecting a data set it is opened in the default mask. A mask is a
windows with tabular data, the *mask* name comes from the old Leica total 
stations.

.. image:: rg_images/fb.png
	:align: center

The field-book contains two type of rows, station and obeservation records.
In the station records the station number is editablei but the target point 
number not. The column headers may contain more labels, for example *target
height* and *instrument height*. The colour of the value defines the type of 
data.

The observations window contains a menu bar and pop up menus.

Coordinates
...........

This menu option has a cascading menu with the name of the loaded GeoEasy data 
sets. After selecting a data set it is opened in the default mask. A mask is a
windows with tabular data, the *mask* name comes from the old Leica total 
stations.

.. image:: rg_images/fb.png
	:align: center

The field-book contains two type of rows, station and obeservation records.
In the station records the station number is editablei but the target point 
number not. The column headers may contain more labels, for example *target
height* and *instrument height*. The colour of the value defines the type of 
data.

The observations window contains a menu bar and pop up menus.

Observation parameters
......................

The observation parameters are metadata about the observations and 
coordinates, id/name of observer, date, instrument type and standard
deviations. All fields are optional. If no standard deviations are given, the
values defined in the  **Calculation parameters** are used.

.. image:: obsparam.png
	:align: center

Load mask definitions
.....................

Starting GeoEasy the mask definitions are loaded from the geo_easy.msk file.
Using this menu option mask definitions can be loaded from user created
file.

Calculate menu
~~~~~~~~~~~~~~

Orientations
............

This menu option calculates orientations for all unoriented known stations.
The results are listed in the **Calculation results** window and the orientation
angles are stored in the field-books.

Preliminary orientations
........................

This menu option calculates orientations for all unoriented stations which 
have preliminary or final coordinates.
The results are listed in the **Calculation results** window and the orientation
angles are stored in the field-books.
This is useful before 2D or 3D network adjustment, to get preliminary
orientations.

Delete orientations
...................

This menu option removes all orientation angles from the loaded data sets.

Traversing
..........

Different type of traversing lines can be solved. Before starting the 
traversing calculation the orientations have to be made at the start and
end point if possible.
The points in the travesing line are selected from the list of possible points.
The type of traversing line (closed line, loop, free, ...) is detected by
the program.

The calculation results are sent to **Calculation results** window.

Traversing node
...............

A travesing node is an unknown point at which three or more free
travessing lines meet. First the coordinates of the node are calculated from
free travese lines as a weighted average. Finally the traversing lines
are solved as closed loop traversing.

Trigonomerical line
...................

This menu option calculates the elevations in a traverse line using
triginometric height calculation. Zenith angles have to be measured
between tranversing points. The points in thetrigonometric line are
selected from the list of possible points.

The calculation results are sent to **Calculation results** window.

Trigonometrical node
....................

Similiar to the traversing node, three or more free traversing lines
having the same endpoint are calculated.


Intersection of two lines
.........................

Two lines are given by two-two points and the intersection of the two lines
is calculated. The id/name of the intersection point canalso be given if
so the intersection point is stored in the opened data sets. This calculation 
is made in 2D.

Point on line
.............



Length
......

Area
....

Arc setting out
...............

Preliminary coordinates
.......................

Recalculate preliminary coordinates
...................................

3D network adjustment
.....................

Horizoltal network adjustment
.............................

Levelling network adjustment
............................

Coordinate transformation
.........................

Elevation transformation
........................

New detail points
.................

All detail point
................

3D intersections
................

Windows menu
~~~~~~~~~~~~

New graphic window
..................

Log window
..........

Console window
..............

Window list
...........

Refresh all window
..................

Help menu
~~~~~~~~~

GeoEasy field-book window
-------------------------

Commands menu
~~~~~~~~~~~~~

Calculate menu
~~~~~~~~~~~~~~

Help menu
~~~~~~~~~

Popup menu
~~~~~~~~~~

GeoEasy coordinate list
-----------------------

Commands menu
~~~~~~~~~~~~~

Calculate menu
~~~~~~~~~~~~~~

Help menu
~~~~~~~~~

Popup menu
~~~~~~~~~~

GeoEasy graphic window
----------------------

Commands menu
~~~~~~~~~~~~~

Calculate menu
~~~~~~~~~~~~~~

DTM menu
~~~~~~~~

Help menu
~~~~~~~~~

Popup menu
~~~~~~~~~~

GeoEasy calculation results
---------------------------

File menu
~~~~~~~~~

GeoEasy consol window
---------------------

File menu
~~~~~~~~~
