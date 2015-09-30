# Project Journal


## Time Review

I would estimate that I spent around 40 hours on this project in total including the time spent planning together. We had our first team meeting to plan our initial design on September 11th, and we turned in our completed project on September 26th. I would estimate that we met for around 3-5 hours every week in order to make sure that we were all on the same page as far as how each feature was implemented in relation to each other. I then allocated about half my time coding new features, and the remaining half between refactoring, testing and debugging. The tasks that were easiest for me was communicating with our xml data files when we need to read or write data to them. It took me some time to read up on implementing xml files in java, but once I had the background knowledge I found that java’s xml handling capabilities to be quite convenient. The hardest part was how to structure the UI components and the logic they accessed in a neat manner.
## Teamwork
We would have two design meetings a week, one at the start of the week and one at the end of the week, and these meetings really helped with ensuring the implementation of our design went smoothly. We would communicate clearly when one of us required accessing the data or methods contained in another class that was under the responsibility of someone else. We divided the project into four parts: 1. Simulations , 2 . The grid, 3. The UI, 4. Handling the xml data. Brenna Milligan was responsible for the simulations, Collin Bacchi handled the grid, and I was responsible for the UI and handling all the XML data. 

I felt like we did a great job of communicating. Even when we did not have a meeting scheduled, if we ever needed to communicate something we would just use a group chat and my group members would respond quickly. We also required another group member to look over any pull request that was made to the master fork before it was merged, which helped keep us updated on what changes were made to the project.

We also did a great job of planning out each person’s responsibilities, each of us was able to work independently on our features for the most part, and connecting them together went very smoothly whenever a feature was ready to be added. 

Our prescribed roles held up very well to the project’s extensions, each of the extensions fell directly under one of our responsibilities. Collin was to handle the new variations of the grid, Brenna was to handle the new simulations, and I was to handle the new UI components and XML features. I felt like our original design held up very well against the new specifications, I personally didn’t have to change anything I had already implemented and my group members changed minimal amounts if any. 

## Commits
I tried my best to make a commit every time I completed implementing a new feature on my local fork. I would implement it and ensure it worked without bugs by testing it on my local fork before making a pull request to the master fork.
My commit messages always explained the new feature I was adding, the bug I just fixed, or the data file I had added/changed unless it was to just resolve a merge conflict that I received when pulling from the master fork.

79d45baf5db9ccfe4137f3a9c53c786acfee74f3

Added Functionalities to each of the UI Buttons:

The purpose of this commit was adding new buttons to the UI that would start, stop and increment the simulation. This commit did not create merge conflicts. This commit helped in testing the grid and simulations, as both my team members could now carefully look at the display on the grid in order to ensure it was working correctly

2269280fdcb20ec1756ee732fcde0b2502e32bb1

Dynamic cell configuration based on states:
The purpose of this commit was to create input fields for the user to set an arbritrary distribution of states on the grid based on the simulation that was loaded. This did not create any merge conflicts, and was helpful to Brenna in creating scenarios where the correctness of the simulation could be checked.

## Conclusions

My group did a good job of estimating the size of the project and allocating individual responsibilities. I felt busy but not overburdened with my responsibilities, and as far as I can tell my group members felt the same way. 

I had a good amount of responsibility, as I was involved in both the back and front end of the project between creating and parsing simulation-specific and grid-style specific xml data and creating the UI. Each time I finished a feature and made a pull request I would notify my group members in our group chat.

To be honest the layout of my UI components took a good amount of editing to get them just right. It was a bit of a learning process with how to layout components in multiple gridpanes within a borderpane, but I felt much more comfortable towards the end of the process. 
To be a better designer I would extract more methods as I implement new features rather than after I test and debug them. This would make my code more readable and easier to debug.

To be a better teammate I would like to maintain a good amount of communication about specific goals to ensure everyone is on the same page as to how different parts of the project are connected. Discussing different options together as a group to get each person’s point of view also proved to be very beneficial. If I could work on one part of my project it would be to refactor my UI code, as adding new features up until the deadline meant that I did not have as much time as I would have liked to refactor my code.

# Design Review
We all loaded Duvall’s code style preferences into our Eclipse, which allowed our code to be formatted quite consistently across all our classes. We also communicated on naming conventions, deciding to call local class variables with the convention myVariableName  to make it easily understandable to people viewing classes that they did not code themselves. All our class names are quite descriptive, for instance Brenna named her simulation classes after the simulations they implemented, Collin named his different grid shape classes according to the shape (e.g HexagonView, SquareView), and I named my Simulation reader class SimReader and my style reader class StyleReader. Methods are also named very descriptively. Methods are also generally readable, and do not require comments to understand as their names do a good job of explaining their purpose. For instance my SimReader class contains a method to read a XML file selected by the user, and its name is parseFile(). But I would say that my initialize method for the UI is too large, and has to initialize too many components over too many lines to be easily readable at a glance. I am currently planning to refactor my UI class as my code masterpiece to address this issue.

For my part of the project, which was the bulk of the GUI and the Configuration, the other parts of the project certainly a lot of dependency on my GUI buttons and parsed data. We discussed how to implement these dependencies through clear and concise methods that would be attached to each button. The only global variables that existed were static and final constants, so there was no issue of inconsistency within this dependency. 
Parsing data from new XML files for new simulations was especially easy to extend, and the SimulationReader class did not have to be adjusted at all to support the extensions. For each simulation, each of its specific parameters were always put into a Map, so even though the newer simulations were more complicated with many more specific parameters, the parameters were parsed and handled by the appropriate classes in the same way. Another feature that was easy to extend were the new grid shapes, as our grid display in the GUI was initially designed to be able to support grids of different shapes being added to it in exactly the same way. 

Simulation Class:
This class is the superclass for all the simulations we implemented in our project, and so it contains methods that show the similarities between the classes. This is a very well designed class, with short and descriptive methods, with appropriate method signatures. I would perhaps suggest that perhaps some of its abstract methods that help initialized the object could be called from its constructor to reduce the number of times its methods would have to be manually called. What I learnt from reading this code is that it was important to put thought into choosing method signatures, and to identify which methods would be best as protected or private in order to keep the class closed. 

In order to make this code reusable in a completely different project one option would be to make some of the more specific methods such as checking or returning cell neighbors to be abstract. The abstract methods take in lists and maps as arguments, which could have been used to implement the spawning of projectiles or enemies in my game. The method names would also have to be adjusted to not refer to just cells on a grid. 

GridView Class:
This code is interesting because it makes good use of extending the group class, which allows it to access all the cells associated with it quite easily, it is also very concise yet is extended to produce each of the grid shapes required. This is a very well written class, so the only thing I would suggest is that the assigning of a mouse listener to each cell be done in a separate method instead of within the updateCells() method. What I learnt is that it can be a very good idea to think of libraries and classes already specified by Java that can be extended, as the group class was used here. It was an excellent design choice that made things much simpler to code.

Since this class extends Group, implementing it in another project would be quite easy. It would only really require making the updateCells() method abstract for other projects to implement in their own way.

## Design

Configuration  


There is a writer class for each XML file used by the project, meaning that there is one writer class for each Simulation, hence the large number of writer classes. This utilizes a hierarchy of SimulationWriters, where each subclass only has the responsibility of specifying the specific parameters used by each simulation. There is also a writer class to write grid style XML files. These writer classes make producing new files and adjusting current files a simple matter.


There are two classes that read the configuration data: SimReader and StyleReader. SimReader takes in any simulation XML file and uses it to populate the fields of a SimReader object. StyleReader does the same thing but with a grid style XML file. Objects of both these classes are called from the UI buttons when the user wants to load something, and the values that are parsed from files are transferred to a grid object in the UI class. The grid takes the fields it needs, and passes other fields to the simulation associated with the grid. This means that the configuration is passed to the simulation through the grid object, so the simulation does not have to be accessible from the UI to keep it more closed. 
Visualization


The grid is the most significant part of the GUI, and it implemented with a combination of the Grid and GridView classes, where Grid works with the logic of the cells and GridView is only concerned about the display of the cells, this keeps things tidy and separate. The rest of the UI are all the ways the user interacts with the system, with buttons that control the animation attached to the gridview and load files into the grid. There is also a side panel that allows users to adjust simulation specific parameters and cell distributions that changes according to the loaded simulation. There is a hierarchy for the GridView to facilitate the different cell shapes supported.


Simulation
There is a cell and a simulation class for each simulation that we implemented in our project (e.g Fire, FireCell) and these are accessed only by the Grid when a simulation is loaded. There is a hierarchy for the Cells and for the Simulations, and each of these hierarchies have classes that utilize the factory design pattern to make selecting the appropriate simulation and cell simple. 

Adding a New Simulation:


Our design was such that adding a new simulation does not require changing any existing code. The simulation’s rules would need to be written up in a new simulation class, and the specifics of the simulation’s cell behavior would need to be written up in a new cell class. A new XML file specifying the values of the simulation’s specific parameters along with generic data would then be created and loaded to produce the simulation on the grid.


My Code in more Detail:


For creating the many simulation XML files that we needed I created sub classes that produced generic data common to all simulations in a super constructor which also automatically called an abstract method that would populate the file with all the simulation specific data that was needed. 


I then had a simulation reader and a style reader class to parse all the data from any xml file that was selected, which was very extensible as my xml files were written to have the same structure and common XML tags as specified through the data in my XMLTags and StyleTags classes. These reader classes did have many getter methods, but this was hard to avoid as their whole purpose was to return parsed data to other classes.


I was responsible for the whole GUI except for the grid, and I produced a variety of buttons through which users could interact with the system. These would open up file browsers, and control the progression of the simulation. For the extension I implemented dynamic parameter setting and cell distributions. This involved having dynamically produced input fields based on the loaded simulation that would allow the user to change the values of simulation specific parameters and cell distributions, this required passing data into the grid which would then either use it itself or pass it onto the simulation that was currently loaded. This was handled by a separate class that was used within the UI class.


I designed each of the XML files to be similar enough such that I would only need one reader class to properly parse all the data for any simulation, this made adding new simulations easy on the configuration end. I think the main GUI class grew too large during the extension stage as I did not put enough time into refactoring and extracting separate functions into their own classes, and as a result the code got less readable over time. My partners selected the XML file name as a reference to which simulation to create, so at the moment the current design requires that the XML files are named after the simulation. Addressing this would require a simple change to make other classes refer to a data field stored within the file rather than the filename itself. 
Exporting and saving the current states of the grid into an XML file was something that I implemented by myself. Its implementation is largely carried encapsulated out within the ExportingStates class, although it is accessed by a button press in the main UIViewer class. It requires access to the XMLReader object that was created when the XML file was loaded in order to have a pointer to the same destination file name, and access to the Grid object in order to access the current states of the grid. Each of these resources are passed in as parameters, and this implementation is closed except for which objects are passed into it.  It does assume that the destination file structure is the same as the one which was initially loaded, but this is not an issue as the pointer to the destination file does not change unless a new simulation file is loaded.  The design for this feature is extensible to other applications where positions and states of the objects in the grid need to be saved to a file. 


## Alternate Designs
Our original design proved to be robust in the face of the project extensions, as the only changes that were made were implementing additional features on top of the core structure. 
When we were discussing the best way to implement the grid, we decided on having the display of the grid and the logic behind the grid to be contained into separate classes. The alternate design was to have them implemented together in a single class, which would have worked fine for the core project. The positive of this alternative design would have been that handling the grid in the GUI would have been simpler as only one class would need to be accessed, but this would reduce the flexibility we had if we wanted to support multiple grids. I certainly preferred our design choice as it proved to be very flexible with implementing multiple grid shapes and borders.


When it came to how to pass the parsed data from the XML files into the grid and simulation, we discussed having both the Simulation and the Grid accessible from the UIView class as opposed to just the Grid. This would have the benefit of the data being passed directly to the simulation, rather than through methods in the Grid, but it would have the downside of making the Simulation more visible to the rest of our classes. While our choice did mean we had to have a few methods to carry data from the XMLReader object made in the UI class to the Simulation and back, it made the Simulations more closed off, which I think was worthwhile. 


One great feature of the projects current design is that extensions can be made to the grid quite freely without interfering the core methods of the grid such as iterating through all its cells due to the separation of the core grid and the visual grid view. This made it quite easy to apply extensions to the grid.


Another great feature is that all the simulations can be run from data files with the same structure, making it easy to parse and load simulations, and to support new simulations that need to be implemented. This made our project very extensible to support multiple simulations quite easily.


One important issue that remains with the project’s current design is that as of now simulations are selected based on the file name of the XML file, which limits having multiple configurations of the same simulation. Fortunately this can be changed quite easily.


Another important issue with the design is that the class that handles the UI does not enjoy the benefits of separating the display and the logic as the grid classes. It became overburdened with responsibilities as extensions were added to the program. This class needs to be refactored.






