# Jupyterhub for education: a survey of a shifting landscape

This paper provides a survey of the community of practice in using Jupyterhub
for teaching, with specific examples demonstrating case studies of differing
needs and teaching practices, an explanation of the toolchain and
technical decisions that guided the architecture of this kind of application, an
explanation of the cost-structure, as well as a snapshot of current
alternatives.

## Differing flavors of education

### Commonalities in the lifecycle of teaching
- Preparation
  - Prepare course material
  - Figure out the environment needed
  - Prepare the environment
    - tell students to install w/ pip, conda
    - Use a tool like Docker
    - Use a joint environment like JHub
- Day of
  - Students arrive and get on the same page
  - Begin teaching course, students follow, maybe interactively
  - Breakout groups / discussion
- After class
  - Students leave w/ homework or other work outside of class
  - Students are evaluated by teacher
  - Students move on from class

### The tools involved / needs they meet
- Preparation
  - Managing an environment
    - Docker
      - Dockerfiles
      - repo2docker
    - Package managers
  - Preparing material
    - nbclean for student material
- Day of Teaching
  - Interacting w/ content
    - Jupyter Notebooks
    - Data science UIs (e.g., RStudio, JupyterLab)
  - Running code for the class
    - Individual computers
    - Shared server
      - JupyterHub
      - Kubernetes
        - helm and the helmchart
      - Authentication
  - Content sharing (nbgitpuller, git, Jupyter extensions, ipynb)
  - Enriching teaching
    - Interactive work (collaboratory, JupyterLab extension)
  - Grading and outside-of-class work
    - nbgrader / okpy
    - Feedback on answers (okpy)

### Axes along which educational events differ
- Duration of the event (day, week, semester)
- Number of students
- Background of students (intro vs. intermediate)
- Complexity of the deployment (data, software)

### Prototypical Classes
- The one-off domain bootcamp (e.g., NeuroHackWeek)
  - Description
    - 20-30 people
    - Participants have domain background but little training in the computational techniques
    - Motivated to learn
    - Material drawn from online resources / demos / etc
  - Technology
    - JupyterHub runs on Google Cloud
    - Docker image is prepared by the instructor (w/ a Dockerfile? repo2docker?)
    - Image is relatively hefty because all instructors have varying toolkits etc.
    - nbgitpuller to share each instructor's material
    - Hub is running on high-memory cloud instances for heavier computation (maybe connected to GPU or something?)
- The upper-division course (e.g., ???)
  - Description
    - Class of 30-50 students
    - From a few to many months
    - Students have background in the material, maybe in computing
    - More advanced techniques / concepts covered
    - Homework involves open-ended problem solving
    - Potentially more computation / disk / memory needed
  - Technology
    - JupyterHub running on university resources
    - Shared disk set up with large datasets to which students have read access
    - Datasets added to this disk as they are introduced
    - nbclean used to create "breakout" sections of code where students solve problems
    - Homework is given to students as a JupyterNotebook with a prompt at the beginning. It is filled in and students submit a path to their notebook for instructors to review / run.
- The introductory course (e.g., Data 8)
  - Description
    - Class of 50+ students
    - Spans several months
    - Material is not particularly advanced, but students have no background in this type of work.
    - Students may not be intrinsically motivated to learn
    - Goal is to give intuition / concepts, not expertise.
  - Technology
    - JupyterHub running an image with the "data science stack"
    - Notebooks utilized with heavy emphasis on interactive widgets
    - Packages used that have simpler APIs (e.g., pandas is avoided)
    - OKpy used to grade student homework, and to provide feedback to students for relatively simple homework questions.
- The data science teaching institute
  - Description
    - Collection of data science instructors
    - Variety of courses, topics, etc
    - High variance in usage of classes
    - Ongoing classes, bootcamps, etc throughout year
  - Technology
    - BinderHub with persistent storage running
    - Instructors asked to push course materials and requirements to GitHub
    - Links to interact are shared with students at the beginning of classes
    - Courses are also kept online as interactive material via the BinderHub
    - No grading or long-term persistent storage

### General best-practices learned
- Avoid the kitchen sink
- Build interactivity into lectures
- Use some degree of manually coding as instructor (AKA, don't go too fast)
- Use breakout sessions to let students catch up and assess if they're following
- Allow for instant group feedback (e.g. a google doc, form, etc)
- Use sticky notes + a floater to spot-check individual questions

### Alternatives and non-JH tech:
- Other cloud-based tech
  - Azure notebooks
  - Colaboratory
- Challenges to these approaches
  - Not open-source work, so future is uncertain
  - Not flexible, as using them requires using their platform
  - Less control over the environment (e.g., python only, even python 2 only)
  - Poorer integration with broader computational ecosystem of tools (e.g. nbgrader, jupyter extensions)
  - Differs more from non-cloud-based workflows (e.g., colaboratory has no persistent filesystem)

## Improvements to be made
### Technical and tooling improvements
- Still areas of pain in technical course deployments
- Why is there is a multiplicity of tools in this space?
- NEED: Simpler pathway to deploying technical solutions for teaching (e.g., push-button jupyterhub)
- NEED: More extensions and tooling around enhancing learning (e.g., interactivity and widgets)
- NEED: More composable / swappable environment images (e.g., R and Python)
- NEED: Academic-facing computational resources for teaching
- NEED: Technology to facilitate data transfer and access for students

### Community improvements
- NEED: Shared content for common course material (e.g. Chris Hensch + data science modules)
- NEED: tech training of individuals in universities (e.g., a person who can empower teachers to utilize tech in their teaching)
- NEED: Clearly-defined cost estimates and means of paying for technical infrastructure
- NEED: Method of sharing experiences and wisdom
- NEED: Personnel models at universities aimed that maximize impact of tech without requiring extensive new training.
- NEED: Materials / best-practices that assume students have worked in the cloud and now need to move to own computers.
- NEED: Efforts to reach smaller / teaching-focused universities, high-schools, etc.
