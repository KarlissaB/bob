# Project Plan

**Author**: Team 185

## 1 Introduction
Our product is a single-user app to help users make informed career decsions by comparing job offers with weighted factors such as benfits, salary, and cost of living.

## 2 Process Description
Our project development activities are as follows:

### Requirment Refinement
We will review all requirements and design documents prior to development. This ensures that we will have a sufficient understanding of what the program must do functionally. This will also give us an opportunity to resolve any open questions and inconstencies that may have been missed. We will also review what is required of each role, to ensure that we are ready to begin development.
- **Entrance Criteria:** All documents from `Group Project Deliverable 1`
- **Exit Criteria:** Every team member is aligned on interpretation of requirements, any consistencies across documents are resolved, and we have shared understanding of our workflow before implementation begins.

### UI Design
A wireframe will be created to show a full walkthrough of the app, and how the user is expected to interact with it. During this activity, we will consider ease of use, accessibility, and aesthetic appeal. This will enable us to have good understandings of the navigational flow, and be used as a reference for implementation.
- **Entrance Criteria:** An adequate understanding of the project requirments from each member.
- **Exit Criteria:** A wireframe showing the full navigational flow of the app, which must be intuitive, easy to use, and be reviewed and approved by the team.

### Environment Setup
Since all team members completed prior coursework activities, it is assumed that individual software setup (Andriod Studio, Java, Gradle, Git) has been completed. During this activity, one member will create the project, and make the inital commit to our repository, so that we all have access to it. We will also decide on development tracking tools to be used throguhout implementation in this stage. Methods to persist the data like database configuration must also be discussed.
- **Entrance Criteria:** Every team member's development enviroments setup from previous assignments.
- **Exit Criteria:** An intial commit with the app has been made to our Repo, and development tracking methods have been agreed upon. Data persistance methodology will also be understood.

### Object Model Implementation
The team will setup all of the classes and thier attributes, so that progress is not hindered by class dependencies during later activities. It will be broken down into 3 sections: the top-level class (point of entry) class, `Job` relevant classes, and the `Comparison Settings` class. Essentially, we will be implementing our UML diagram so that we have access to all objects needs to work on the later parts of the program without as many dependencies.
- **Entrance Criteria:** A completed, agreed upon UML diagram, completed environmental setup, and an intial commit
- **Exit Criteria:** All classes, attributes, and relationships from the UML diagram, must be implemeneted in the project correctly, and pushed to the team repository. These changes must be verfied as correct by the team before moving forward.

### Basic UI Implemenation
To prevent team members from being blocked when functionally testing later, we will create a simple home page, comparison settings, and job entry screens. During this step, we do not need to worry about the overall appearance, but focus on functionality instead. We will ensure that input fields and buttons are present on their designated pages so that the team can focus more on the coding elements in later activites.
- **Entrance Criteria:** A completed, agreed upon wireframe, completed environmental setup, and OM changes
- **Exit Criteria:** The necessary pages must be created and navigable with the required input fields and buttons present on each page. This must be reviewed by another team member to confirm all of the needed fields are there with reference to the the wireframe.

### Input Validation
When entering comparison setting values, the fields can only hold integers between 0 and 9. When entering job details, parental leave, personal holidays, gym reimbursement, and pet insurance also have numeric input constraints. Logic must be written to ensure that out of range values cannot be inputed into the system. Testing will need to be completed to make sure that validation logic was implemented correctly. This will follow the guidance provided in the testing plan document.
- **Entrance Criteria:** Basic UI implementation, OM implementation, and data persistance must be completed.
- **Exit Criteria:** The job entry and comparsion setting input fields prevent non-valid numbers from being allowed, and there should be unit tests to verify this.

### Derived Value Calculations
We need to derive values for the adjusted yearly salary (AYS) and adjusted yearly bonus (AYB) based off of cost of living. Then, the adjusted yearly salary will be used to help calculate pet insurance. One team member will build these methods to produce accurate values, and the ensure that these methods are tested with reference to the testing plan.
- **Entrance Criteria:** The OM implementation must be completed.
- **Exit Criteria:** The AYS, AYB, and pet insurance values will be accurately calculated with verification from unit tests.

### Job Ranking UI and Logic
Using the values from the comparison setting the jobs provided, a ranked list of all jobs should be provided. This will rely on calculating the job score using the formula provided in `Assignment 5`. While this can be verified in a unit test, and terminal area, we will also implement a basic UI. This UI will show the what the rankings will look like to the user. It is not expected to fully be completed in this activity.
- **Entrance Criteria:** The wireframe, OM changes, derived value calculations, comparison setting logic, and job entry logic must be completed.
- **Exit Criteria:** A basic view of a list of jobs, desceding, will be accurately show on the UI. The logic to calculate these scores will also be unit tested based on the testing plan.

### Job Comparison UI and Logic
W
### UI Refinement
### End to End Testing

## 3 Team

*Describe the team and their roles (include at least 4 roles, there may be more roles than there are team members)*

- Team: Aditya Shiroya, Aneta Obrochta, Christian Molina, Karlissa Brown
- *Roles, with a short description of each role*
- UI Developer
- Backend Developer
- 
- *Table showing which team member(s) has which role(s)*
