CompSci 308: Game Analysis
===================

> This is the link to the Analysis Description: [Analysis - Game](http://www.cs.duke.edu/courses/compsci308/fall15/assign/01_game/part3.php)

Project Journal
=======

###Time Review
Planning and research about how I would go about implementing my initial design began on the 28th of August, starting with searching up online resources about introductions to implementing simple games with Java FX. I found an excellent step by step resource in this website here :http://gamedevelopment.tutsplus.com/tutorials/introduction-to-javafx-for-game-development--cms-23835, which really helped wrapping my head around the fundamental concepts in designing my game, such as managing my nodes on whatever scene I was using, and how to manage these node throughout my game. 


This period of time also included going over Professor Duvall’s in-class java fx example, which proved to be invaluable in showing a very clear implementation of many important basic mechanics that I would also implement in my own game. I also began making my first choices regarding the design of my project by thinking about how I would divide up the stages in my game into individual smaller classes. I would estimate that I spent approximately 5 hours during this preliminary stage. 
The implementation of my project began after this, and I found that I would need to refer to online resources quite often at this early stage before I grew more familiar with implementing generic features. I would say that I spent roughly 50% of my time implementing and testing new features, 20% of it refactoring, 20% of it debugging, and the final 10% on reading documentation to learn more about implementing features. 


As this was an individual project and my first project using github, I developed and tested the bulk of my code before pushing it to github in one large chunk. I understand that this would be highly sub-optimal when working with other people though, and I would certainly not do it the same way for my next project. 


The tasks that were easiest was completing the final levels and screens for my game, as at that point I was able to utilize the hierarchies and classes that I had previously wrote to make the process a lot more efficient than it was for my first level. The hardest task was to do my best to ensure that all my classes were as discrete and specific as possible, as it took effort to make sure that I wasn’t duplicating code and that things were organized clearly. Although this was challenging, it proved to be a very good use of time, as it made adding additional levels or objects into the game vastly easier, as it was simple to utilize and build upon what I had already made in making something similar earlier on in the project.
 A bad use of my time was certainly making sure all my images were suitably sized in order to prevent a memory overload occurring from too many objects being produced on the screen. I also spent a large amount of time trying to correct a  bug associated with this, as excessive memory allocation and garbage removal was the most problematic bug I had to correct, and it required me spending a lot of time trying to find a solution so that my game would not crash after a period of time. I believe I need to better understand how Java manages its memory allocation towards newly created objects, even after they are meant to be removed from the game, as a lack of understanding in this area slowed me down quite considerably. 




###Commits

You can put links to commits like this: [My favorite commit](https://github.com/duke-compsci308-fall2015/example_bins/commit/7be1fe10327f20a14293ef39fddd9f75b7359e43)

My  commits were certainly an area I could improve in, as my style of commits for this project would be highly inappropriate for a project where I worked with other people. I coded and tested almost the entirety of my project on my own machine, only pushing it when I had an almost fully working game. I only made a few commits in total, the first was for my entire game, one for adding a cheat code, and another for refactoring. Thus, my average commit size was unfortunately quite huge


At least my commit messages did represent what I committed quite accurately, but once again I am not proud of how I used github with this project, and will certainly keep better code management practices in mind for my next project. 


My first commit was essentially my entire project (message: Completed Game) , and it contained all the java files and images that my project needed to run. I had coded the entire thing on my own machine before pushing it onto my git repository, and it included all the main features of the game. This was a huge commit, and it certainly would not be a reasonable commit to make if other people were involved in this project, and it is not one I would make again. 


Another commit I made was one where I did my best to tidy up my code and make it more readable, it is labelled as “Refactoring via extracting methods”, and here I identified places where extracting methods would be useful in making my code more discrete and presentable. This was a more reasonably sized commit, as it was neither very large nor did it involve adding new features, it only rearranged what was already present. 

###Conclusions
I was able to meet the deadline for this project quite well as I felt I was quite conservative with my initial design, and as a result estimated my ability to accomplish this project quite well. I was hoping to err on the side of caution as I had never coded a game before, and I wanted to ensure my project wasn’t rushed and of poor quality. I believe that I now am more cognizant of my capabilities, and would be more comfortable spending more time on refactoring as implement new features, rather than leaving it to the end. I would much rather allocate time for this for while the bulk of coding is being done, rather than leaving it to the end. 


The part of my code that required the most editing was implementing dynamic data structures to store the enemies and projectiles that were produced during the game, as I had issues with excessive memory allocation in my game loop, and I had to spend some time to find a suitable solution.


In order to be a better designer, I ought to be more mindful of good design principles during my implementation of new features, and try to avoid leaving refactoring to the end. I will do my best to practice and include design principles during my initial design. 


One thing I certainly would have liked to improve on would have been the smoothness of my game control. Unfortunately by following the examples that Professor Duvall gave us I was only able to achieve motion that was quite jerky, making the game more difficult to play than it should have been. 




Design Review
=======

###Status

* Bullets are made with asterisks

1. You can order things with numbers.

###Design

You can put blocks of code in here like this:
```java
    /**
     * Returns sum of all values in given list.
     */
    public int getTotal (Collection<Integer> data) {
        int total = 0;
        for (int d : data) {
            total += d;
        }
        return total;
    }
```

###Alternate Designs

Code Masterpiece
================

