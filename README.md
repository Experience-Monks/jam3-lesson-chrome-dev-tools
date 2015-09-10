# Chrome Developer Tools
This is an overview of the Chrome Dev Tools and how we use them. The Chrome Dev Tools provide a nice way of debugging your code and to quickly try different js/html/css directly in the browser.

### How to start working with Chrome Developer Tools?
To open the developer tools, click on the menu in the top right, go to "more tools" and then click "Developer Tools". You will want to start using the shortcuts soon though:

OSX - <kbd>Cmd</kbd> + <kbd>Alt</kbd> + <kbd>I</kbd>  
Linux/Windows - <kbd>F12</kbd> or <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>I</kbd>

Or, if you want to jump right into inspecting an element. Right click an element, and select "inspect element" this will open the Developer Tools with that element selected. You can also use the shortcuts and hover over the element:

OSX - <kbd>Cmd</kbd> + <kbd>Shift</kbd> + <kbd>C</kbd>  
Linux/Windows - <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>C</kbd>

## Anatomy
This section will go over the basic features of the dev tools, organized by tab.

### Elements
The elements panel allows you to inspect and live edit the HTML and CSS of a web page.
![alt tag](./images/elements-panel.png?raw=true "Elements Panel")  

On the left side we have the HTML document and on the right side we have the CSS rules, computed CSS values, Event Listeners and other information for the currently selected node.

### Network
The network tab gives you information about all the request made by the page.

#### Overview and Filtering
Many filters are available for the network requests in the top bar of the tab.
You can search for keywords, or select a type (to the right of the search field)

Another option is to filter requests by when they happened. In the top bar, the icon (![alt tag](./images/overview.png?raw=true "Overview")) will toggle the overview on and off. The overview is a visual representation of the requests on a time line. You can quickly filter the requests by when they happened by clicking and dragging for the time span you want.

#### Requests
The main part of this tab is the list of requests and their basic information. Clicking on a request will open the details pane that breaks the information into different tabs.

###### Headers
Shows the request and response headers for the request. It also shows basic information about the request like URL, method and status.

###### Preview and Response
These panes will show you the contents of the response or file.

###### Cookies
Lists all cookies sent with request, or received with the response.

###### Timing
Shows when events occurred and how long they took for the request.

### Sources
The sources tab is one of your most important tools when it comes to debugging Javascript in the browser. It allows you to set breakpoints, view breakpoints, view source files, step through code, view the callstack, modify source files and even write and run javascript directly in the browser.

There are three panes to the sources tab. 

#### Pane 1: source files
This pane shows you all the files the page loaded. It's broken down into 3 groups.

* Sources - The websites source files.
* Content scripts - Chrome Extension scripts that have been loaded on the site. (you likely won't use this tab very often).
* Snippets - Scripts that you wrote in Chrome and can run manually.

#### Pane 2: Editor
This pane allows you to view and modify the contents of a file and set breakpoints.

If the source file is minified, then it makes it extremely hard to debug. If you need to debug a minified file (e.g live site or third party script) you can use the "pretty print" button in the bottom left (an icon that looks like an opening and closing curly braces) right beside the line number. This will format the code to make it much easier to read.

You can also make edits and save the file, this doesn't save it back to your original file but it will use this version when you refresh.

#### Pane 3: debugging menu
The two main elements in the debugging menu are the Call Stack and Breakpoints.

The callstack will be empty until execution is paused. At that point you can view the callstack. Clicking on a call will take you to that file and show you the line.

The breakpoints are broken into categories, Breakpoints, DOM Breakpoints, XHR Breakpoints and Event Listener Breakpoints. You can toggle any of them on or off in the menus.  

This menu also includes the debugger controls at the top.

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
continues execution on the line until the current function returns.

![alt tag](./images/turn_off_breakpoints.png?raw=true "Enable Or Disable Breakpoints")
Activate/Deactivate breakpoints  
If deactivated then all break points will be ignored.

![alt tag](./images/pause_on_exception.png?raw=true "Pause On Exception")
Pause on exceptions

### Timeline
The timeline tab is an overview of the operations of the website. You can see "when" and "how long" different things took. The main things you can see are loading, scripting, rendering and painting.

The top portion of this tab will be the main timeline, it shows all events color coded.

The second part shows a more default timeline and a description for each operation. 

The last part is a summary of the currently selected item. Either the current section of the timeline or a single operation.

### Profiles
Here, you can record/debug CPU and memory usage. You can also save them to a file to archive/share.

### Resources
###### Cookies
Clicking on a domain in the cookies category will show all cookies that have been set for that domain. From here you can right click on any cookie to delete it, or clear all cookies.

###### Local Storage
Clicking on a domain under the local storage category will show you all local storage that has been set for that domain. You can right click on the key or value to edit them, or add a new entry by right clicking on the first empty row. 

### Audits
Audits can be used to point out performance issues that could be slowing down load times like unused css rules or caching problems.

### Console
Here is the awesome!  

![alt tag](./images/console-panel-hello.png?raw=true "Console Panel")

In the console you can run whatever you want in Javascript! You can run any javascript expression, including multiple line expressions. You can even define functions and variables and reference them in future expressions... trust me, here you can do all kinds of stuff!
You can access any variable or function defined in the current scope, by default it's the global scope. Later we will learn how to change the scope.

### Emulation
![alt tag](./images/top-bar.png?raw=true "Top Bar")  
You can enable emulation by clicking the phone icon in the top left, right beside the search icon. This will surround the web view with rulers and a top bar that allows you to set internet speed, device, screen size and user-agent.
more options can be found by opening the drawer (click the icon that looks like a greater than symbol followed by an underscore) and selecting the Emulation tab.

## In Practice
#### Dom Manipulation
Sometimes you will want to change the dom to test something without having to refresh the browser with every change.

* reorder nodes by simply clicking and dragging it to the new location. 

* edit any attribute by double clicking(or right clicking and select "edit attribute") or add an attribute by right clicking and selecting "Add Attribute"

* do more in depth edits, by right clicking and selecting "Edit as HTML". This will allow you to write and HTML you want, adding nodes and text.

#### Style Manipulation
Testing styles by saving files and refreshing the browser can be tedious, especially if you just want to do something like increment a number by 1 until it looks right. The right panel of the Elements tab solves this problem.
This panel will show the styles for the currently selected node broken down the the css rules that assigned them.

If you click on these rules you can change the value to be anything you want.  
For numerical values, pressing <kbd>up</kbd> or <kbd>down</kbd> will increment or decrement the value by 1;  
Pressing <kbd>Shift</kbd> and <kbd>up</kbd>/<kbd>down</kbd> will increment or decrement the value by 10;
Pressing <kbd>Option</kbd> (<kbd>Ctrl</kbd> on Windows) and <kbd>up</kbd>/<kbd>down</kbd> will increment or decrement the value by 0.1;

If you need to add a new rule, just click underneath the last rule in a section and type in property name and then enter or tab to enter the value.

Crossed-out rules have been overwritten by another rule.

#### Setting Breakpoints
Clicking on the line number in a javascript file will toggle a break point. you can do this for as many lines as you want and then refresh your browser to debug the code.

#### Working with breakpoints
Once javascript execution halts at one of your breakpoints, the browser will jump to the sources tab and highlight the line in the file that triggered it. 
From here you can view the callstack, step through code, or modify variables and call functions.
The scope that the debugger line is in will be in scope on the console.

#### Writing/running scripts in the browser
Snippets are javascript files that you can edit and run in the browser on any page. This can be useful for quickly testing code out or for writing simple utilities.

To get started, click on Snippets then right click on the tab and select "new" this will open a new script that you can start editing. (command+Enter or ctrl+Enter will run the script)

## Nice Tips!
##### Selecting Nodes
When you click on a node in the element pane, chrome stores that in a variable. You can access it from the console by typing $n, where n is how far back in the history to go. 
$0 would be the last one you clicked on, $1 would be the second last one.

For example, to find all divs in the last node you clicked, you could write
```js
$0.getElementsByTagName('div');
```

##### Auto Clear Cache
When testing changes in the browser you will need to make sure your cache is cleared. You can do this manual by using the shortcut
Mac OS - command + shfit + R
Windows - ctrl + shift + R
Linux - ctrl + shift + R

you can also disable the cache for a site when the dev tools are open.
go to the network tab and in the top bar select the "Disable cache" checkbox.

##### Open the drawer
When you are any tab other then the console, it can still be useful to have the console available to run commands. You can have a console at the bottom of the console by opening the drawer.
in the top right of the console, this 
![alt tag](./images/open_drawer.png?raw=true "Open Drawer")
button will toggle the drawer open and closed.

##### Preserve Log
If you are debugging something that ends in a redirect of the browser, this will normally clear the console which makes it very difficult to debug. At the top of the console there is a checkbox for "Preserve log" this means that the console will not be cleared on refresh or redirect and you can see what happened.

##### Change Chrome Dev Tools Position
There are 3 positions for the chrome dev tools, and you will want each one at different times. You can change it by clicking the icon beside the 'x'. Or clicking and holding to reveal another option. 

![alt tag](./images/attached_side.png?raw=true "Attached Side") Attached to the side of the window.

![alt tag](./images/attached_bottom.png?raw=true "Attached Bottom") Attached to the bottom of the window.

![alt tag](./images/detached.png?raw=true "Detached") Detached and in it's own window.

##### Force Element State
If you are testing a button and want to change the style of the hover state, you don't want to have to hover over it every time you make a change. By right clicking on the node in the element page you can select "Force element state" > "hover" and it will always be it will stay in the hover state. 
of course, you can do this for active, focus and visited states as well.

## Useful links
If you one to learn more tips and tricks -> https://developer.chrome.com/devtools/docs/tips-and-tricks

To end... Always is good to challenge yourself at Code School ;) -> http://discover-devtools.codeschool.com/
