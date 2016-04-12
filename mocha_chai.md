# Mocha Chai Setup - for integration testing

Assumes you're using galvanize express

## Steps

1. Creates a "test" directory in project root

2. install dependencies (npm i chai chai-http mocha --save-dev)

3. Add a test script to *package.json* "test": "mocha"

4. add a new file in test called mocha.opts and add the following flag so that mocha
looks in all the directories within the test directory for tests: --recursive

5. create new folder called "integration" within test

6. Create a new file for each route resource that you are testing - i.e., AUTHORS-routes.js
within integration folder
