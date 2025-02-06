# action-ice

This action is a [composite action](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action)
that will install on Ubuntu 24.04:
 - Java (default 11)
 - Python (default 3.12)
 - Ice 3.6.5 
 - Ice Python binding

 The Java and Python versions can be passed as parameters.

 To use the action in a workflow:

 ```
on: [push]

jobs:
  install_job:
    runs-on: ubuntu-24.04
    name: A job to install Ice 3.6.5
    steps:
      - uses: actions/checkout@v4
      - name: Install Ice
        uses: ome/action-ice@main
 ```

If you wish to change the Java version and Python version, for example use Java 1.8 and Python 3.10

 ```
on: [push]

jobs:
  install_job:
    runs-on: ubuntu-24.04
    name: A job to install Ice 3.6.5
    steps:
      - uses: actions/checkout@v4
      - name: Install Ice
        uses: ome/action-ice@v3
        with:
          java-version: 1.8
          python-version: '3.10'
 ```