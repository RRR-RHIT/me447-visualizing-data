### Set up an R project

-   Login with your usual user name.

-   Create a folder for the course in your preferred directory. For example, C:/Users/layton/Documents/courses/me447.

-   Open RStudio. Some error statements will probably appear. No worry. We’re about to take care of that.

-   Create a new RStudio Project using File menu &gt; New Project &gt; Existing Directory. Use the Browse button to find the course folder you just made. Select that folder &gt; Create Project.

### Create an .Renviron file

These steps are Windows-specific (I'm not sure if the problem needs solving in Linux or Mac platforms.)

The purpose of the .Renviron file is to establish a library for R packages that is independent of the R software. Then you can update R to the latest version and not have to re-install all the packages you use.

-   In RStudio, open a new text file using File menu &gt; New File &gt; Text File.

-   Write the following line in the text file

    `R_LIBS_USER="C:/R/library"`

-   Save the file using the filename .Renviron in your course folder (don’t forget the dot that starts the filename). For example, C:/Users/layton/Documents/courses/me447/.Renviron

-   Create a new directory C:/R/library. (That is, in C: create a folder named R. In R create a folder named library.) This is the directory pointed to by the .Renviron file.

### Testing

-   If you create a new RStudio Project, always paste a copy of the .Renviron file in the project root directory.