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
    - These would be stored on the `Job` class because these attributes are only relevant to the attributes related to jobs.

