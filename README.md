# Dev Tools
This is a lesson on how we use Chrome Dev Tools in Jam3. Dev Tools provide a nice way of debugging your code and make things happen easier.

##How to work with Dev Tools?
To open dev tools you have to click Cmd + Alt + I (on OSX) or F12, Ctrl + Shift + I (on Windows), or if you want to open with the data of an special element just right click on it and select 'Inspect Element'

###Elements
Elements panel allow you to inspect and live edition in the HTML and CSS of a web page.
This is how this panel looks:
![alt tag](./images/elements-panel.png?raw=true "Elements Panel")  


On the left side we have the HTML and on the right side we have the CSS, here we can check all the styles that are applied to the elements and we can change it and see it lively.

###Console
Here is the awesome!  

![alt tag](./images/console-panel-hello.png?raw=true "Console Panel")

In the console you can run whatever you want in Javascript! You can run simple commands and multiple line commands, you can even define functions and use theres later... trust me, here you can do all kind of stuff!  
The accessible variables in the console are all the ones defined in the current scope, this means that you can't access any variable in the console. However you have globals variables like 'document' or 'window' that can be access in all places... and by querying document you can reach to any document element!  
For example: 
  
document.getElementById("theElementIwantToQuery");



###Sources
The sources tab is one of your most important tools when it comes to debugging your javascript in the browser. It allows you set breakpoints, view breakpoints, view all source files, step through code, view callstack and even write and run javascript directly in the browser.

####source files

the first part of the sources tab shows you all the files loaded for the page. It's broken down into 3 groups.

* Sources - The websites source files.
* Content scripts - Chrome Extension scripts that have been loaded on the site. (you likely wont use this tab very often).
* Snippets - Scripts that you wrote in chrome and can run manually.

***

The second part of the sources tab shows the source of the file that is selected.

If the source file is minified, then it makes it extremely hard to debug. If not minifying the code is not an option (e.g live site or third party script) then there is a pretty print button in the bottom left (opening and closing curly braces) right beside the line number. This will format the code to make it much easier to read. 

***

The last part of the sources tab have lots of useful information.
* Lists all the break points on the page, broken into categories.
  * it also allows you to disable/enable the breakpoints
* the callstack
* watched variables



####Snippets

Snippets are js files that you can edit and run in the browser on any page. This can be useful for quickly testing code out or for writing simple utilities.

To get started, click on Snippets then right click on the tab and select "new" this will open a new script that you can start editing. (command+Enter or ctrl+Enter will run the script)

####Setting Breakpoints

Clicking on the line number in a js file will toggle a break point. You can then refresh your browser to debug your program.

####working with breakpoints

Once the browser stops on one of your breakpoints, it will jump to the sources tab and highlight the line that triggered it. 
From here you can view the callstack, step through the code, modify variables and call functions.
the scope that the debugger line is in will be in scope on the console.

![alt tag](./images/continue.png?raw=true "continue")
resume script execution  
will continue until next breakpoint. (click and hold release over second icon will not stop for 500ms)

![alt tag](./images/skip.png?raw=true "Step Over Next Function")
Step over next function call  
If the current line is a function call, it will run the function and stop on the next line.

![alt tag](./images/into_function.png?raw=true "Step Into Next Function")
Step into next function call  
If the current line is a function call, it will go to the first line in the function

![alt tag](./images/out_of_function.png?raw=true "Step Out Of Next Function")
step out of current function call  
continues execution on the line after the current function returns.


![alt tag](./images/turn_off_breakpoints.png?raw=true "Enable Or Disable Breakpoints")
Activate/Deactivate breakpoints  
If deactivated then all break points will be ignored.

![alt tag](./images/pause_on_exception.png?raw=true "Pause On Exception")
Pause on exceptions

###Network

The network tab will give information about all the request made by the page. 

####Files

There will be a list of all resource requests. Clicking on one will open up the another pane with more details. This section can also be filtered by type, keyword, or where it falls on the timeline. 

####Details
######Headers

shows basic information about the request like URL, method and status. It also shows Request and Response headers.

######Preview and Response

these panes will show you the contents of the response and files.

######Cookies

lists all cookies sent with request, or received with the response.

######Timing

shows the when events happened and how long they took for the request.

###Resources
###Timeline
###Profiles
###Audits
###Emulation

![alt tag](./images/top-bar.png?raw=true "Top Bar")  
You can enable emulation by clicking the phone icon in the top left, right beside the search icon. This will surround the web view with rulers and a top bar that allows you to set internet speed, device, screen size and user-agent.
more options can be found by opening the drawer (click the icon that looks like a greater than symbol followed by an underscore) and selecting the Emulation.

##Nice Tips!

##Useful links

If you one to learn more tips and tricks -> https://developer.chrome.com/devtools/docs/tips-and-tricks

To end... Always is good to challenge yourself at Code School ;) -> http://discover-devtools.codeschool.com/
