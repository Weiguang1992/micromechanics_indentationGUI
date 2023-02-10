[![Linting](https://github.com/micromechanics/micromechanics/actions/workflows/pylint.yml/badge.svg)](https://github.com/micromechanics/micromechanics/actions/workflows/pylint.yml)
[![Documentation](https://github.com/micromechanics/micromechanics/actions/workflows/docs.yml/badge.svg)](https://github.com/micromechanics/micromechanics/actions/workflows/docs.yml)
[![pypi.org](https://github.com/micromechanics/micromechanics/actions/workflows/pypi.yml/badge.svg)](https://github.com/micromechanics/micromechanics/actions/workflows/pypi.yml)

# Nanoindentation library for experimental micromechanics
This library allows to read datafiles from different nanoindenters and allows to analyse it by evaluating the hardness and Young's modulus using the Oliver-Pharr method. It also includes functions for frame stiffness and area function calibration as well as a number of plotting functions.

The library can read:
- xls files from the vendors MTS, Agilent, Keysight, which produced the XP and G200 indenters
- hap files from the Fischer-Scope
- zip-files which include all the files of the Micromaterials NanoXtreme
- some common format which is based on the NeXus common data format

Install by
``` bash
pip install nanoindentation
```

Run test using the default data
``` python
from nanoindentation import Indentation
i = Indentation()
i.plotAll()
```

More information as well as tutorials can be found at: [Read the docs](https://micromechanics.github.io/micromechanics/)

If you want to contribute to the development, we develop at [github](https://github.com/micromechanics/micromechanics)


# Contributors
- Steffen Brinckmann
- Velislava Yonkova
- Ruomeng (Nicole) Chen


# Information for developers
## Please first test the code
``` bash
pylint src/nanoindentation/
python tests/testAgilent_xls.py
python tests/testFischerScope_hdf5.py
python tests/testMicromaterials_hdf5.py
python tests/testVerification.py
python tests/testAllFiles.py
```

Then upload/create-pull-request to github, via
``` bash
git commit -a -m 'my message'
```

## For publication on pypi
1. Increase version number in pyproject.toml
2. do the following steps in shell
``` bash
python3 -m build
python3 -m twine upload dist/*
rm dist/*
git commit -a -m 'Version 1.0.0'
git push
```
