# 8.  Build you own app

## Overview

The purpose of this assignment is to provide you with the opportunity
to practice building a shiny application.  These are client-server
type web applications where all the tedious technical tasks of both
frontend and backend are transparently created by shiny, the user has
just to provide code for the content and layout.
Shiny has a few concepts
you have to understand to get going, but once you are comfortable
with the general skeleton of these applications, transforming your
analyses into interactive experiences goes fairly fast.


## The Data

![UFO](ufo.jpg)

For this assignment, you'll use UFO sightings data.  The data
originates from National UFO Research Center and is
downloaded from
[Timothy Renners page](https://data.world/timothyrenner/ufo-sightings).
It contains 5177 UFO sightings in the US and Canada in 2016.  It
contains the following variables:

* _Date_: date as mm/dd/yyyy
* _Time_: time as hh:mm:ss (12 hr format)
* _AM/PM_: am/pm indicator (AM, PM)
* _Country_: USA/CANADA
* _City_: name of the city where (or near of which) the ufo was seen
* _State_: US state or CA province, 2-letter acronym
* _Shape_: shape of the ufo (Light/Circle/Sphere/...)
* _lat_, _lng_: geocoded latitude, longitude; based on the city.
* _Summary_: brief description of sighting

 
## Assignment Structure

As with previous assignments, follow the link to create
your own private repository for this assignment (well, if you are
reading this readme you probably already did it).  This will
automatically create a private repository which you will submit to
Canvas as your assignment.  Note this is an individual assigment, so
you have to create your own repo.


### Complete the following steps:

Your task is to build your own shiny application.  The
application should provide users with the ability to interactively
explore the UFO dataset. What the application
looks like is up to you (but see below for a few ideas),
as long as it meets the following
requirements:

* There is a side panel in which you've created at least two widgets
  that change the visual output in your application, such as type of
  the plot, data
  displayed on the x or y axis of a scatterplot.  Note: I mean _side
  panel_ but it does not have to be _sidebarLayout_.
* There is a main panel where the data is presented (as a plot or table).
* You must create at least one visual representation of a dataset (a
  plot) that reacts to
  the widgets in the sidepanel
* You must also add some textual output that reacts to a widget, such as
  the number of non-missing observations.
* One of your widgets must change the data that is being
  displayed.  For instance, the user may be able to choose between
  distribution of date and distribution of shape.  In contrary, if the widget only
  changes the color of the plot, it will not count.
* Your plots, tables, maps and whatever you come up with must be
  appropriately labeled and use appropriate colors.
* You must push your application up to the
  [shinyapps.io](http://www.shinyapps.io) server (or
  another server if you like), making
  it publicly available
*  For this application, use the multiple-file setup (i.e both ui.R and
   server.R):
	* A ui.R file, that drives the structure of the user interface
	* A server.R file, that provides instructions to the R server
	* You should also create a readme.md file (feel free to delete
	  this one) that contains a brief "user
	  documentation" of your project: a brief description of the data, and
	  explanation what are the widgets and panels doing.  This
	  file should contain a link to your project on the
	  [shinyapps](http://www.shinyapps.io) server.

We hope that when you finish this project, you will good enough to go
and start your own shiny applications!

### Sidepanel

In your sidepanel, you should create at least two widgets of your choice. As
stated above in the requirements, at least one of these widgets should
change the data being displayed.  What the other widget does is
completely up to you (as long as it changes the visual representation
somehow).  Feel free to use whichever types of
widgets you want.


### Main panel

The main panel of your application should contain a visual
representation of the UFO dataset. The visualization can be made
with base R graphics, ggplot2, [plotly](https://plot.ly/r/),
[leaflet for maps](https://rstudio.github.io/leaflet/) or
something [more interesting](https://github.com/juba/scatterD3).
While we don't expect you to create anything ground-breaking, we do
expect you to create a clear visualization with proper labels and
titles. And of course, the graphic needs to react to changing values
in the widgets.

The main panel must also have at least one summary text, such as
number of observations, the name of the most common UFO
shape, etc, embedded in an
appropriate sentence.  The summary text must be calculated from the
data.  For instance "Selected subset contains 1234 observations" is
such a sentence, given _1234_ is derived from the actual (subset of) the data.

You may also opt to present some of your visualizations as tables (but
at least one must be a figure).


## Submission

As with the previous assignment, you should add and commit your
changes using git, and push your assignment to GitHub. In your
readme file, please include a link to your shiny hosted
application. You have to submit the URL of your repository to
canvas--this is your submission.


## Expectations

At this point in the quarter, we expect you to be following the best
practices we've incorporated into the class. This means:

* Proper use of libraries such as _dplyr_ for data manipulation
* Structuring your code so that if the data changes, you can easily
  update your entire application
* Clearly commenting and properly organizing your code
* Writing functions to encapsulate chunks of code that you use more
  than once
* Avoiding variables that are unnecessary for your analysis/report
* Creating appropriate labels for your visualizations


## Ideas:

While simple distributions or maps of the data is sufficient, here are
a few more advanced ideas you may consider:

* Are UFO-s just low-flying airplanes?  If so, you should see a
  correlation between UFO sightings and airports.  Hint: package
  _nycflights13_ contains airport location data.  
  (Or who knows? perhaps aliens are just more interested in airports?)
* Perhaps alcohol plays a role with UFO sightings?  If so, is there a
  relationship between drinking and UFO sightings?  Hint: use the
  drinking data from A4.
* Are there regional/seasonal differences in UFO species (shapes)?


## Grading:

In total **100 points**

* widget #1 (controls data): **30**
    * minor layout/explanation issues **-3**
	* various layout/explanation issues **-6**
    * widget does not control data: **-15**
* widget #2:  **20**
    * minor layout/explanation issues **-3**
	* various layout/explanation issues **-6**
    * widget does not affect visualization: **-15**
* plot(s)/table(s): **30**
    * minor syntax/layout issues: **-3**
	* various syntax/layout issues: **-6**
	* plot/table does not respond to widgets: **-15**
* summary text: **4**
    * a number (or a piece of text) computed from data **2**
	* the above number embedded in a sentence **1**
* published and works at [shinyapps.io](http://www.shinyapps.io): **8**
* appropriate readme **8**
    * no link to [shinyapps.io](http://www.shinyapps.io) version: **-2**
	* data description unclear **-2**
	* explanation of widgets/plots unclear **-2**
