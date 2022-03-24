# Description
Creating a central repo where reusable workflows are being served in parameterised manner.Keeping all of them in `.github/workflows` folder/path. And to access those, we can call it as below. 

`uses: CondeNast/vb-github-actions/.github/workflows/e2e-test.yaml@main`

# Workflow types
We have following workflows:
  ## end to end test
  this workflow builds the application, starts the mock server and runs the cypress as per parameterised command.
  * name: e2e-test.yaml
  *   input params: 
       1.      NPM_TOKEN: npm token
       1.      CYPRESS_RUN: a cypress command that needs to be executed to run the cypress test cases
  ## unit test
  this workflow installs dependencies, checks for audit and runs the unit tests.
  * name: unit-test.yaml
  * input params: 
      1.      NPM_TOKEN: npm token

  ## docker build
  docker workflow builds the docker image by logging into quay
  * name: docker.yaml
  * input params: 
     1.      NPM_TOKEN: npm token
     1.      QUAY_USER: User name to login in quay
     1.      QUAY_TOKEN: quay password/token
