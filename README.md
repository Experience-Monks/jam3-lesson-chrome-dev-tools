# Dev Tools
This is a lesson on how we use Chrome Dev Tools in Jam3. Dev Tools provide a nice way of debugging your code and make things happen easier.

##How to work with Dev Tools?
To open dev tools you have to click Cmd + Alt + I (on OSX) or F12, Ctrl + Shift + I (on Windows), or if you want to open with the data of an special element just right click on it and select 'Inspect Element'

###Elements
Elemets panel allow you to inspect and live edition in the HTML and CSS of a web page.
This is how this panel looks:
![alt tag](./images/elements-panel.png?raw=true "Elements Panel")  


On the left side we have the HTML and on the right side we have the CSS, here we can check all the styles that are applied to the elements and we can change it and see it lively.

###Console
Here is the awesome!  

![alt tag](./images/console-panel-hello.png?raw=true "Console Panel")

In the console you can run whatever you want in Javascript! You can run simple commands and multiple line commands, you can even define functions and use theres later... trust me, here you can do all kind of stuff!  
The accessible variables in the console are all the ones defined in the current scope, this means that you can't access a variable only by calling it in the console. However you have globals variables like 'document' or 'window' that can be access in all places... and by quering document you can reach to any document element!  
For example: 
  
document.getElementById("theElementIwantToQuery");



###Sources
###Network
###Resources
###Timeline
###Profiles

###Audits

##Nice Tips!

##Useful links

If you one to learn more tips and tricks -> https://developer.chrome.com/devtools/docs/tips-and-tricks

To end... Always is good to challenge yourself at Code School ;) -> http://discover-devtools.codeschool.com/
