# action-ice

This action is a [composite action](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action)
that will install on Ubuntu 22.04:
 - Java (default 11)
 - Python 3.10
 - Ice 3.6.5 
 - Ice Python binding

 The Java version can be passed as a parameter

 To use the action in a workflow:

 ```
on: [push]

jobs:
  install_job:
    runs-on: ubuntu-22.04
    name: A job to install Ice 3.6.5
    steps:
      - uses: actions/checkout@v4
      - name: Install Ice
        uses: ome/action-ice@v3
 ```

If you wish to change the Java version, for example use Java 1.8

 ```
on: [push]

jobs:
  install_job:
    runs-on: ubuntu-22.04
    name: A job to install Ice 3.6.5
    steps:
      - uses: actions/checkout@v4
      - name: Install Ice
        uses: ome/action-ice@v3
        with:
          java-version: 1.8
 ```