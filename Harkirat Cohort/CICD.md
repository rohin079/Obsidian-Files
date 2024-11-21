# What is CI and CD?

#### 

[](https://projects.100xdevs.com/tracks/CI-CD/cicd-1#8dcc536914ea4b33af86084e45f26ab7 "Continuous Integration")Continuous Integration

Continuous Integration (CI) is a development practice where developers frequently integrate their code changes into a shared repository, preferably several times a day. Each integration is automatically verified by

1. Building the project and

2. Running automated tests.

This process allows teams to detect problems early, improve software quality, and reduce the time it takes to validate and release new software updates.

#### 

[](https://projects.100xdevs.com/tracks/CI-CD/cicd-1#1b894e8c73894364a7193702cab18c29 "Continuous Deployment")Continuous Deployment

As the name suggests, deploying your code `continuously` to various environments (dev/stage/prod)

what a github actions workflow actually does is that it that it runs your code in a github virtual machine like ubuntu latest and then perform the steps you have given in the workflow in that code and if at any stage any step fails, the workflow will fail.

to make a github workflow, simply create a workflows folder inside a .github folder and then create your .yml file in it.

