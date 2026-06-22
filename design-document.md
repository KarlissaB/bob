# Design Document - Karlissa Brown

1. When the app starts, the main menu appears where the user can choose to enter details about their current job or job offers. It will also offer the ability adjust the comparison settings, and compare job offers.
    - I created the `Job Comparing App` class to represent the entry point of the system.
    - This will also be where key operations and functionality will be stored.
    
2. The current job details that may be entered should be stored, so I beleived that it would be best to store them as attributes.
    - **Text Atrributes:** `Title`, `Company`, `Location`
    - **Float Attributes:** `Cost of Living`, `Yearly Salary`, `Yearly Bonus`, `Gym Reimbursement`, `Pet Insurance`, `Adjusted Yearly Salary (Derived)`, `Adjusted Yearly Bonus (Derived)`, `Adjusted Pet Insurance (Derived)`
      - I wanted any form of monetary value to be stored as a float/decimal to be more accurate in calculations.
    - **Integer Attributes:** `Parental Leave`, `Personal Choice Holidays`
      - Instead of having both maternal and paternity leave attibutes, I decided to consolidate and call it parental leave.
      - These are integers because days cannot be fractioned.
    
    - It is important to note that `Pet Insurance` is calculated with the Yearly Salary Adjusted for cost of living (AYS). Therefore, I realized that multiple derived methods will need to be created as these are attributes that would only be used during calculations and not stored (derived).
    - `calculateAYS()` and `calculateAYB()` are methods that will need calculations to normalize the attributes. Then `calculatePet()` will call `calculateAYB()` to get the correct `Pet Insurance` amount.
    - These would be stored on the `Job` class because these attributes are only relevant to the attributes related to jobs.

3. It was noted that the job offers hold the same attributes as the current job, so it made the most sense for me to create a `Job` class to hold all of that information.
    - Originally, I wanted to use a boolean to distinguish between whether a job object represents the current job, or a job offer.
    
    - The app needs to have the ability to compare jobs, and for that to happen, the system needs to be able to find both quickly. While it would work for smaller sytems, iterating over multiple jobs to find the only true boolean would be inefficent. So, having the system torse the separately on the `Job Comparing App` would be helpful.
    
    - Depending on whether the user is entering a current job or job offer, they will be stored in their respective places based on the task.
   
    - The enter and edit task maybe consolidated in future refinements. I have two separate methods for creating and editing different types of jobs because for editing, it needs context of the job already stored. I might be able to implement logic to make the parameters optional.

    - The `saveJob` and `cancelJob` are only relevant to the `Job` class, so they do not need to be stored with the entering and editing job tasks on `Job Comparing App`.

4. I understood the comparison weights as how much a user prioritize certain job charateristics (attributes). I do not think that each job should have their own priority settings, so I created a `Comparison setting` class to hold this information. Also, it has it's own class because I believe that it will be working independetly of the job and the system.
    - The `saveSettings()` and the `cancelSettings()` tasks will be stored here with the method to set each of the integer attributes. This is because they are only relevant to this class, and the `Job Comparing App` class could reference this information.
    
5. As previously stated, by having the current job and job offers (stored as a list) on the `Job Comparing App` class, it will be able to look through all jobs, instead of operating on the context of one at a time.
   
6. The `Job` class will calculate the individual score of each job, and then the `Job Comparing App` will read those values and sort the jobs in a ranked order. `calculateJobScore` will run the calculation provided by the assignment to find the weighted average.
     - **Formula:** `JS = AYS + AYB + (MPL * AYS / 260) + (PCH * AYS / 260) + GR + (PET + (AYS *.02))`

8. The user interface will be planned out in a future wireframe, but for responsiveness, I tried to consider performance when making the UML class diagram.
     - Removing the boolean may help to eliminate time to identify the current job.
       
     - I also tried to ensure that there were no major dependencies, and that every class has their own responsibility.
        -   The `Job Comparing App` class should be tasked with determining whether a job is an offer or current. It will need to reference the `Comparison Settings` and `Job` class to determine the ranks for the jobs. This could be considered a dependency.
          
        -   The `Job` class will make sure that all the attributes pertaining to it are stored and calculated correctly. This will be where the score is derived. Saving and canceling created/edited jobs methods will also be stored here. It does not have any dependencies from other classes, but some of the derived attributes in its own class are dependent on each other. This should not be an issue because it has access to everything it needs to derive them.

        -   `Comparison Settings` will only hold the user's valued preference and does not have any dependecies from other classes or itself.

9. `The Job Comparing App` represents the entry point to the overall system.
       
