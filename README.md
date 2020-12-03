# Surfaxe

Surfaxe is a python package for automating and simplifying surface calculations, as well as providing some analytical tools for bulk and surface calculations. It relies primarily on [Pymatgen](pymatgen.org) for manipulating crystal structures and interfacing with VASP.

The main features include:

1. **Slab generation:** Automated generation of surface slabs from command line.
  * All unique zero-dipole symmetric terminations of slabs are cleaved from a bulk structure.
  * Slabs can be sorted into separate labelled folders, optionally with or all the required VASP input files to run each calculation.

2. **Raw data parsing:** Extracting data from convergence tests.
  * Parsing the convergence testing folders created using the slab generation scripts.
  * Plotting scripts visualising convergence (with respect to slab and vacuum thickness. 

3. **Analysis:** Various scripts for surface and bulk calculations.
  * Electrostatic potential tool, based on Keith Butler's [MacroDensity](https://github.com/WMD-group/MacroDensity) code, for the calculation of absolute electron energies (ionisation potential, electron affinity).
  * Nearest neighbours and bond analysis scripts.

Surfaxe primarily supports VASP, however we would like to add support for other solid-state codes in the future.

Development notes
-----------------

### TODO 
* tests
* docs

### Bugs, features and questions
Please use the Issue Tracker to report bugs or request features in the first instance. 

### Code contributions
Contributions to interface with this package are most welcome. Please use the ["Fork and Pull"](https://guides.github.com/activities/forking/) workflow to make contributions and stick as closely as possible to the following:

- Code style should comply with [PEP8](http://www.python.org/dev/peps/pep-0008) where possible. [Google's house style](https://google.github.io/styleguide/pyguide.html)
is also helpful, including a good model for docstrings.
- Please use comments liberally!
- Add tests wherever possible, and use the test suite to check if you broke anything.


## Usage
Surfaxe can be used via the command line and python API. The manual, including tutorials and API documentation can be found here. Additionally, the built-in `- h` option is available in the command line interface for each of the scripts.

The `examples` folder contains the jupyter notebooks with detailed explanations 
of functionality of all aspects of the package. 

The scripts are separated into four stages; creation, convergence, analysis and data. 

Creation:
* `surfaxe-getall`: For generating all unique symmetric zero-dipole surface slabs up to a maximum Miller index specified.
* `surfaxe-gethkl`: For generating all unique symmetric zero-dipole surface slabs for one specified Miller index.

Convergence:
* `surfaxe-parsefols`: For parsing the convergence folders set up with `surfaxe-gethkl` or `surfaxe-getone`.

Analysis:
* `surfaxe-bonds`
* `surfaxe-simplenn`
* `surfaxe-complexnn`
* `surfaxe-potential`
* `surfaxe-cartdisp` 

Data: 
* `surfaxe-core` 
* `surfaxe-vacuum` 

## Installation
Surfaxe is a Python 3 package and requires pymatgen and other standard scientific python packages.

Recommended installation is to git clone and install with `pip`:

```sh
git clone https://github.com/brlec/surfaxe.git
cd surfaxe
pip install --user .
```

 For development work, `--user` can be replaced with `-e`, which creates links to the source folder so any changes to the code are reflected on the path.


#### Tests
Unit tests are in the `tests/` directory and can be run from the top directory using `pytest`. Please run these tests whenever submitting bug fix pull requests and include new tests for new features as appropriate. 

## License and how to cite

Surfaxe is free to use under the [sort licence out, probably MIT]. Please cite [add link] if you use it in your research.

## Detailed requirements 
Surfaxe is compatible with python 3.6+ and requires the following packages:

* Pymatgen
* Pandas
* Matplotlib
