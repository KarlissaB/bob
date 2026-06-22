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
    - Orignally, I wanted to use a boolean to distinguish between whether a job object represents the current job, or a job offer.
    
    - The app needs to have the ability to compare jobs, and for that to happen, the system needs to be able to find both quickly. While it would work for smaller sytems, iterating over multiple jobs to find the only true boolean would be inefficent. So, having the system torse the separately on the `Job Comparing App` would be helpful.
    
    - Depending on whether the user is entering a current job or job offer, they will be stored in their respective places based on the task.
   
    - The enter and edit task maybe consolidated in future refinements. I have two separate methods for creating and editing different types of jobs because for editing, it needs context of the job already stored. I might be able to implement logic to make the parameters optional.

4. 
