# stylus-test-runner

DSL for testing your stylus source code

### Install

```
npm install stylus-test-runner
```


### Api

In your stylus repo, add the following ```.js``` file

```
var testRunnerConfig = {
  testDirPath: '{{path to testing directory}}',
  stylus: {
    use: require('{{path to stylus.js include}}')(),
    import: '{{path to stylus.styl include}}'
  }
}

require('stylus-test-runner')(testRunnerConfig)
```

In a ```.styl```, include the following.

```
// @describe This is a description
// @it This is the stylus being tested
// @expect This is the outputs css expected
// @throws Expect the test to throw an error
```

### Preview
```
// @describe clearfix()

// @it should output a clearfix styles to an element
.class
  clearfix()

// @expect
.class:after,
.class:before {
  content: "";
  display: table;
}
.class:after {
  clear: both;
}
```
```
$ node test/test-runner.js

  clearfix()
    ✓ should output a clearfix styles to an element (136ms)
```
