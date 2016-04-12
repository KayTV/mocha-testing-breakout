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

7. Add the following for each test file:

```
process.env.NODE_ENV = 'test';

var chai = require('chai');
var chaiHttp = require('chai-http');
var server = require('../../src/server/app');
var should = chai.should();

chai.use(chaiHttp);


describe('car routes', function() {


  // beforeEach(function(done) {
  //   done();
  // });

  // afterEach(function(done) {
  //   done();
  // });

  describe('', function() {

    it('', function(done) {
        done();
    });
  });

});
```
8. only show the logger if the NODE_ENV is not in test so add an if statement in the middleware

```
if (process.env.NODE_ENV !== 'test') {
  app.use(logger('dev'));
}
```
