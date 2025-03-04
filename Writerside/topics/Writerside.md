# Writerside

Writerside is a technical writing tool by Jetbrains (the makers of IntelliJ) that is designed for technical
documentation writers.

## How it works

In a Writerside setup, you have your documentation files. Those can be written in either Markdown or XML-Topics.
The files are then processed by Writerside and converted into static HTML-files (or also alternatively a PDF-file) that
can then be hosted on any web server.

However, Writerside is pretty strict about how to structure your documentation.
Only adding a new file to the project will not work, you have to add it to the `.tree` file in the project root, which
is the table of all your documentation files. If you don't add your file here, it won't be compiled.

You can check out `6d@dhbw.tree` in our GitHub repository for an example for this structure. You should however not need
to edit this file manually, as Writerside will do this for you.

## The IDE

The Writerside IDE is made to work with Writerside projects. It has support for all files that all other Jetbrains
IDEAs knows, a preview window and a tree view of all topics in the Writerside project.

### Adding new files

To add new files to the project, simply open the `Writerside` tool window on the left side of the IDE. This should open
a window similar to this:

![Writerside-Tool-Window.png](Writerside-Tool-Window.png)

In the bottom half of this tool window, you see your Table of Contents, which is equal to the `.tree` file in your
project. You can add new topics here, either by right-clicking on a current topic or by using the `+` button in the top
right.

### Preview

After you added a file and wrote some content, you naturally want to see how it looks. You can do this by using the
`Writerside Preview` tool window on the right side of the IDE. This will show you a preview of the currently opened
file, with the option to open it in your browser instead of the IDE.

![Writerside-Preview-Window.png](Writerside-Preview-Window.png)

## Export

To generate an output of your documentation, you can use either the IDE directly (by adding a run configuration) or do
this task in a CI/CD pipeline. The output (for the HTML-based export) will be a zip-archive of the static HTML files
that you can host on any web server, for example on GitHub Pages.

Our setup uses a GitHub Actions workflow for this. You can check out the `.github/workflows` folder
in [our repository](https://github.com/6SemesterAtDHBW/dev-blog/) for an example of these workflows. If you decide to
use them as well, please make sure to change the instance ID to the one you chose during the creation of your Writerside
project in the environment variables `ARTIFACT` and `INSTANCE` (ours is `6d@dhbw`, so only change that part).

The CI/CD pipeline will automatically push the generated HTML-files to a branch called `deployment`, which you can then
use to host the documentation on for example GitHub Pages. You can setup this in a similar way to how we did it:

![Github-Pages.png](Github-Pages.png)
