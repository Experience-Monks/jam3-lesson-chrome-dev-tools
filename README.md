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


![alt tag](./images/continue.png?raw=true "continue")
resume execution until next breakpoint. (click and hold and release over second icon will not stop for 500ms)

![alt tag](./images/skip.png?raw=true "Step Over Next Function")
Step over next function

![alt tag](./images/into_function.png?raw=true "Step Into Next Function")
Step into next function 

![alt tag](./images/out_of_function.png?raw=true "Step Out Of Next Function")
step out of next function

![alt tag](./images/turn_off_breakpoints.png?raw=true "Enable Or Disable Breakpoints")
Enable or disable breakpoints

![alt tag](./images/pause_on_exception.png?raw=true "Pause On Exception")
Pause on exceptions



###Network
###Resources
###Timeline
###Profiles
###Audits
###Emulation



##Nice Tips!

##Useful links

If you one to learn more tips and tricks -> https://developer.chrome.com/devtools/docs/tips-and-tricks

To end... Always is good to challenge yourself at Code School ;) -> http://discover-devtools.codeschool.com/
