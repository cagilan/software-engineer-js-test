Albumprinter test
This repository contains a basic setup for a JavaScript project. You will have the luxury of having a fully configured environment that can build a web application. See "System requirements" below to get up and running! The "Project outline" section walks you through a basic rundown of the structure.

The test
You will be working in an company where our customers will purchase a printed product. As such your expertise should not be restricted to developing applications, but also extend to understand the requirements of print and how to translate between the app and the print world and vice versa.

Goal
You should write a very simple application where there are two scenarios:

Scenario 1.
The user can select a photo file from his/her device and import it into the application
The user can position and scale this photo on a canvas (note: photo must always cover full canvas size)
Hit a submit button which will generate the print description as described below (these instructions can be displayed on screen in a text area).
Scenario 2.
The user can hit an import button which loads a previously saved description
Upon loading, the application should show a canvas that contains the photo
Photo is scaled and positioned as expected according to the loaded print instructions
Deliverables
Out of the box, the application already provides you some code to load and validate image files from your computer. You can take some inspiration here, or if you don't like the design approach of that code, feel free to show what you think is the "right approach" to code this application. Don't write code that just "get's the job done", write it as if was an application that you would have to maintain for years to come ;)

It is by no means necessary to make this application look attractive or to spend a lot of time in providing the best interaction with the photo. If you need to add buttons to “move photo left”, "move photo right" or “scale photo 50%", "scale photo 200%” that is enough. It is about the design of your code, NOT the design of the application interface!

It is more important to show how you write (in your eyes) a maintainable application. It is not important to finish all deliverables described above, as long as you can show how you would approach reaching that state. As such you can use pseudo code where desirable. Be prepared to explain the steps you took in a review of this test.

Product canvas properties
At Albelli, we define the dimensions of our printed products in inches. For this application we will name the product “Canvas” (a single printable surface). This Canvas is a rectangle of 15” x 10” in size.

A photo must always fill the full surface of the canvas (in other words: a photo must cover an area equal to or larger than 15” in width or 10” in height).

A photo has the following properties: width, height, x and y (once more all in inches). X and Y describe the coordinates of the photo relative to the top-left position of its canvas.

Print description
The print description you will generate (in scenario #1 of your application) can be in any format of your liking, as an example you could consider the following output in JSON format:

{
    "canvas": {
        "width": 15
        "height": 10,
        "photo" : {
            "id": “fileName”,
            "width": 20,
            "height": 20,
            "x": -2.5,
            "y": -5
        }
    }
}
Rules
Once you receive this test by e-mail you must fork this repository to your own GitHub account in which you will write your test.

You are free to use any libraries that make your life easier. However be sure to write your own logic for the part that is "Albelli unique" code. You can use a framework, but we are more interested in seeing how you would structure things if you didn't have a framework that defines the design pattern for you.

Your application should run on the latest public version of Google Chrome. You don't have to worry about making your code work on any other browser, as such you are free to use anything that is supported by Chrome and not worry about cross-browser implementations.

Project outline
The entry point for your JavaScript application is ./js/main.js. You can use the CommonJS require/exports pattern to include dependencies. The build script will ensure these get automatically built for use in your browser.

The project uses SASS as a preprocessor for writing your styles (though you can write regular CSS inside a .scss file if you would like to). If you choose to use CSS, you can use ./css/main.scss as your entry point SASS file.

All build output will be stored in the ./dist folder, this is automatically generated by the build script and its contents can be ignored.

System requirements
In order to build the project you will need Node.js.

Once you have Node, you will also have NPM available to you. NPM is Node's package manager which will resolve dependencies for you.

In the root of this repository, you can resolve all these dependencies via the command line using:

npm install
You can now start developing the application using Gulp (build system/task runner). by typing:

gulp dev
The following will happen:

All JavaScript is included and built for the browser
All SASS styles are converted into CSS
Your browser will open and run the application
File watchers are started: If you add/remove/change HTML, SCSS or JS files the appropriate rebuild tasks are automatically run and your browser will be refreshed automatically. This allows you to instantly view the results of your changes.
You can add / remove / change files to in the source folder and your browser will automatically update to reflect the changes.

You can use your favourite editor to edit your files.