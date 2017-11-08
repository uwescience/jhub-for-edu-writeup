# Jupyterhub for education: a survey of a shifting landscape

This paper provides a survey of the community of practice in using Jupyterhub
for teaching, with specific examples demonstrating case studies of differing
needs and different teaching practices, an explanation of the toolchain and
technical decisions that guided the architecture of this kind of application, an
explanation of the cost-structure, as well as a snapshot of current
alternatives.


## Dimensions of variance:

- Duration of the thing
- Number of students
- Complexity of the deployment (data, software)

## Explanation of the different moving parts

### Lifecycle of a course:  
Course material preparation

- Environment definition: pip, conda, docker

Teaching

Evaluation

What happens when it's done?

### The tool chain

Docker

The notebook

Kubernetes
 - helm and the helmchart

Authentication

nbgitpuller

## A diversity of needs and tools

Collect anecdotes and also tools that are "homebrew" hacks

nbgrader and okpy

Chris Hensch : data science modules

Notebook extensions: nbclean, hide solutions

Why do we think there is a multiplicity of tools in this space?

- One of the reasons has to do with the sheer complexity of the underlying machinery and a need to go around it to achieve even simple changes.

## Cost structure

## Alternatives and non-JH tech:
- Azure notebooks
- Colaboratory

One of the challenges in using these alternatives is that they are not
currently developed as open-source software, making it impossible to mix and
match individual features (e.g., live collaborative editing, Stack Overflow
search, etc.).
