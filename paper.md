Note: this is a working draft of what we’ll discuss at the MSDSE summit, please feel free to add edits, comments, suggestions, etc.


# Outline
## Why run education from the cloud?
    Pros:
      - Standardize student environments
      - Have more control over student content
      - Fewer moving parts for students (though more for instructors)
      - Remove hardware requirements (they only need internet)
      - Can tackle more complex data/analytics topics by not requiring setup.
      - Dive right into material.
    Cons:
      - What happens when students leave the JupyterHub?
      - Requires a bit more technical expertise for instructors
      - More knowledge of Docker / some kubernetes (if using zero 2 jupyterhub)
      - Extra cost to instructor since you’re paying for computation
      - Bits and pieces that go into spec'ing out a deployment

- Software dependencies (repo2docker / Dockerfile)
    Course material (nbgitpuller)
    Cloud infrastructure (z2jh)

- Data

## Budgetary considerations

## A few example deployments of varying kinds
  - Small-scale, short-term (NeuroHackWeek)
      Go over the bits and pieces
  - Large-scale / long-term (data 8)
  - Small-scale / long-term (connector courses & modules)

## Open questions
  - Creating semi-standardized learning materials that expect a JupyterHub
  - Opportunities for tool-building around the Jupyter (and web-based UI more
    generally) world to improve education
  - Best-practices for teaching a class that’s based in the cloud
  - When to move / teach how to move *off* the cloud
  - Opportunities to grow these practices/tech outside of the “data sciencey”
  universities (e.g. smaller school, community colleges, high schools)

## Notes from summit session:

- How to support multiple classes - same deployment? Separate deployments?
Separate images?

Cost: right now Data 8 costs 1$/student/week (about $10k/semester). The cost of
team is substantial, but might be a one-off cost for setup. As development
continues, less expert supervision will be required.

Eventually, the hope is that JHub will be deployed on academic-facing
computational resources. The minimal requirement is something that runs
Kubernetes. XSEDE doesn’t run it yet, but we might expect it to run there
eventually.

Cost constraints (or lack thereof) are driving development. Improvements to
scalability will start coming when cost becomes more of a concern (right now
there’s a lot of free credits out there)

Colaboratory.

Canada has a publicly consolidated jupyterhub system (socialism!).

The Big Data Hubs could be a thing to deploy resources, but person-power is
still needed.

https://z2jh.jupyter.org

Pedagogical issues:

Is watching someone go through a notebook like watching a video or like
replaying a computation step-by-step?

nbgitpuller: “hybrid interactive mode”: particular blocks are left out that
students are asked to fill in

An intermediate approach: breaking up -- at most 5 code cells, with a few lines
each -- and then a challenge where students are supposed to actively fill in
parts of the code often (every 10-15 minutes?).

Greg Wilson : http://third-bit.com/2017/10/16/exercise-types.html

connectortools : define what an answer is and remove it from notebooks given to
students (nbclean)

nbgrader : auto-grading
nbclean : Create student notebooks, remove parts of cells, etc

okpy : auto-grading

repo2docker

Instructors don’t (necessarily) want to become docker gurus, so repo2docker
rides on top of a working cognitive model of dependencies.

Tools are new and rapidly evolving! That poses a challenge for both users and
developers of the tools.

Different users have different needs: plug-and-play versus a deeper
understanding. A “recipe” is important for some, but some need a “chemistry of
cooking” book. Sensible defaults.  What is the role of helm and the helm chart
in this.

William Stein’s thing.
