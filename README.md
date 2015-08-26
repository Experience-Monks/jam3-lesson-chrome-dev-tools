#Chrome Dev Tools
This is a lesson on how we use Chrome Dev Tools at Jam3. Dev Tools provide a nice way of debugging your code and to quickly try different things in js/html/css.

##How to start working with Chrome Dev Tools?
To open dev tools, click on the menu in the top right, go to "more tools" and then click "Developer Tools" you can also use the shortcuts:

OSX - Cmd + Alt + i
Linux/Windows - F12 or Ctrl + Shift + I

or, if you want to jump right into inspecting an element. Right click an element, and select "inspect element" this will open the Developer Tools with that element selected. You can also use the shortcuts:

OSX - Cmd + Shift + C
Linux/Windows - Ctrl + Alt + C

##Anatomy
###Elements
Elements panel allows you to inspect and live edit the HTML and CSS of a web page.
![alt tag](./images/elements-panel.png?raw=true "Elements Panel")  

On the left side we have the HTML document and on the right side we have the CSS rules, computed CSS values, Event Listeners and other information for the currently selected node.

###Network
The network tab gives you information about all the request made by the page.

####Overview and Filtering
Many filters are available for the network requests in the top bar of the tab.
You can search for keywords, or select a type (to the right of the search field)

another option is to filter by when the request happend. in the top bar the icon (![alt tag](./images/overview.png?raw=true "Overview")) will toggle the overview on and off. The overview is a visual representation of the requests on a time line. you can quickly filter the requests by when they happened by clicking and dragging for the time span you want.

####Requests
the main part of this page will be the list of requests with basic information. Clicking on a request will open the details pane that breaks the information into different tabs.

######Headers
Shows the request and response headers of the request. It also shoes basic information about the request like URL, method and status.

######Preview and Response
these panes will show you the contents of the response or file.

######Cookies
lists all cookies sent with request, or received with the response.

######Timing
shows when events happened and how long they took for the request.

###Sources
The sources tab is one of your most important tools when it comes to debugging your javascript in the browser. It allows you to set breakpoints, view breakpoints, view all source files, step through code, view the callstack modify source files and even write and run javascript directly in the browser.

there are three panes to the sources tab. 

####Pane 1: source files
this pane shows you all the files loaded for the page. It's broken down into 3 groups.

* Sources - The websites source files.
* Content scripts - Chrome Extension scripts that have been loaded on the site. (you likely wont use this tab very often).
* Snippets - Scripts that you wrote in chrome and can run manually.

####Pane 2: Editor
this pane allows you to view/modify the contents of a file and set breakpoints.

If the source file is minified, then it makes it extremely hard to debug. If you need to debug a minified file (e.g live site or third party script) then there is a pretty print button in the bottom left (an icon that looks like an opening and closing curly braces) right beside the line number. This will format the code to make it much easier to read.

####Pane 3: debugging menu
the two main things in the debugging menu are the Call Stack and Breakpoints.

The callstack will be empty until the code hits a breakpoint or you pause the code. At this point you can view the callstack clicking on a call will take you to that file and show you the line.

The breakpoints are broken into categories, Breakpoints, DOM Breakpoints, XHR Breakpoints and Event Listener Breakpoints. In the menues you can toggle any of them on or off with the checkbox.

this menu also includes the debugger controls at the top.

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

###Timeline
[[coming soon]]
###Profiles
[[coming soon]]
###Resources

######Cookies

clicking on your domain in the cookies category will show all cookies that have been set. from here you can right click on any cookie to delete it, or clear all cookies.

######Local Storage

Clicking on your domain under the local storage category will show you all local storage that has been set. You can right click on the key or value to edit them, or add a new entry by right clicking on the first empty row. 

###Audits
[[coming soon]]

###Console
Here is the awesome!  

![alt tag](./images/console-panel-hello.png?raw=true "Console Panel")

In the console you can run whatever you want in Javascript! You can run any javascript expression, including multiple line expressions. You can even define functions and variables and reference them in future expressions... trust me, here you can do all kinds of stuff!
You can access any variable or function defined in the current scope, by default it's the global scope. Later we will learn how to change the scope.

###Emulation
![alt tag](./images/top-bar.png?raw=true "Top Bar")  
You can enable emulation by clicking the phone icon in the top left, right beside the search icon. This will surround the web view with rulers and a top bar that allows you to set internet speed, device, screen size and user-agent.
more options can be found by opening the drawer (click the icon that looks like a greater than symbol followed by an underscore) and selecting the Emulation.

















##In Practice
####Snippets

Snippets are js files that you can edit and run in the browser on any page. This can be useful for quickly testing code out or for writing simple utilities.

To get started, click on Snippets then right click on the tab and select "new" this will open a new script that you can start editing. (command+Enter or ctrl+Enter will run the script)

####Setting Breakpoints

Clicking on the line number in a js file will toggle a break point. You can then refresh your browser to debug your program.

####working with breakpoints

Once the browser stops on one of your breakpoints, it will jump to the sources tab and highlight the line that triggered it. 
From here you can view the callstack, step through the code, modify variables and call functions.
the scope that the debugger line is in will be in scope on the console.


##Nice Tips!

#####Selecting Nodes
When you click on a node in the element pane, chrome stores that in a variable. You can access it from the console by typing $n, where n is how far back in the history to go. 
$0 would be the last one you clicked on, $1 would be the second last one.

for example, to find all divs in the last node you clicked you could write
```js
$0.getElementsByTagName('div');
```

#####Auto Clear Cache
When testing changes in the browser you will need to make sure your cache is cleared. You can do this manual by using the shortcut
Mac OS - command + shfit + R
Windows - ctrl + shift + R
Linux - ctrl + shift + R

you can also disable the cache for a site when the dev tools are open.
go to the network tab and in the top bar select the "Disable cache" checkbox.

#####Open the drawer
[[coming soon]]
#####Preserve Log
[[coming soon]]

##Useful links

If you one to learn more tips and tricks -> https://developer.chrome.com/devtools/docs/tips-and-tricks

To end... Always is good to challenge yourself at Code School ;) -> http://discover-devtools.codeschool.com/
