# Running this example

Open the terminal and install the dependencies
``npm install``

Run server.js with node or nodemon (see below)

``node server.js``

or

``nodemon server.js``

Open multiple browser tabs and point them to 

``localhost:3000``

Click around.

# P5.js and Socket

The client application is in public/sketch.js.
It's made in **p5.js**, a friendly library for creative coding.

p5.js provides intuitive functions for drawing, sound, and real time interaction.
p5.js centers on the js canvas element, it is not great for typical html pages.
p5.js is structured around a setup function and a main draw loop.
p5.js is made in js so it can be integrated with any other js library like socket.
p5.js applications are commonly referred to as sketches
p5.js is a library that needs to be linked in the container html to work. Look at **public/index.html**

[more information and tutorials here.](https://p5js.org/)

[Always keep the p5 reference open.](https://p5js.org/reference/)

## P5.js and VS Code

The p5 commands are not recognized by VS Code so if you want some contextual code completion (Intellisense) you have to copy the folder TSDef in your project and reference it at the beginning of your sketch: 

`/// <reference path="TSDef/p5.global-mode.d.ts" />`

[More information about p5 and VS code here](https://breaksome.tech/p5js-editor-how-to-set-up-visual-studio-code/)

## .gitignore

When you make commits in a git repository, you choose which files to stage and commit by using git add FILENAME and then git commit. But what if there are some files that you never want to commit? 

That's where a .gitignore file comes in handy. It lets Git know that it should ignore certain files and not track them.
In this case I don't want to share the node_modules in my project because it's better to let the users install them on their system.
With ``npm install``

## Nodemon

Note that while the client (browser app) can be restarted with a refresh, the server keeps running until you shut it down. If you make changes you won't see them unless you restart the process.  

If you want to stop the server and go back to the terminal press **CTRL+C**

Let's try to use npm to install a utility called nodemon. Nodemon restarts the server every time a file in the folder changes. Exit the process and type:  
`npm install -g nodemon`

-g stands for global (I think). Nodemon will be now visible from everywhere in your system.

Now do:

`nodemon server.js`


## Publishing on Glitch

**Glitch** is a community and a series of friendly tools to develop node based applications.
Glitch provides free hosting for node projects, most web hosts don't give you that degree of access. Another popular platform is heroku.
Glitch offers a code editor, file storage, and an intergrated terminal. You can create node applications from scratch via browser.
Glitch allows you to browse and remix other people projects. Take a minute to explore it:  
[glitch.com](https://glitch.com/)

This project is already structured for glitch with a server.js on the root and a "public" folder. You can clone the github project or remix the project from glitch.

Make sure this line is present in package.json, this is equivalent to launching the server on the local terminal:  
`"scripts": { "start": "node server.js" },`


### Without going thought github
Unfortunately Glitch doesn't allow you to import whole folders unless you are using github but you can follow this process:

* Create a ZIP file of the project.
* Upload it to the assets folder in your project, click it and click **Copy Url**
* Navigate to **Settings > Advance Options > Open Console** in your project
* In the console, first you want to pull the zip file from the url  
`wget -O file.zip https:///url-to-your-zip`  

* Extract it to the current directory  
`unzip file.zip -d .`  

* Remove the zip file  
`rm file.zip`  

* Refresh our app so the new files are shown in the editor  
`refresh`  

