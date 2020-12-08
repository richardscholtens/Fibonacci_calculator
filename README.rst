====================
Fibonacci Calculator
====================


.. image:: https://img.shields.io/pypi/v/fibonacci_calculator.svg
        :target: https://pypi.python.org/pypi/fibonacci_calculator

.. image:: https://img.shields.io/travis/richardscholtens/fibonacci_calculator.svg
        :target: https://travis-ci.org/richardscholtens/Fibonacci_Calculator

.. image:: https://readthedocs.org/projects/fibonacci-calculator/badge/?version=latest
        :target: https://fibonacci-calculator.readthedocs.io/en/latest/?badge=latest
        :alt: Documentation Status


.. image:: https://pyup.io/repos/github/richardscholtens/Fibonacci_Calculator/shield.svg
     :target: https://pyup.io/repos/github/richardscholtens/Fibonacci_Calculator/
     :alt: Updates


A calculator that calculates Fibonacci numbers from 0 to n, indexes n-number and returns n-number.


* Free software: MIT license
* Documentation: https://fibonacci-calculator.readthedocs.io.


Features
--------

* TODO

Credits
-------

This package was created with Cookiecutter_ and the `audreyr/cookiecutter-pypackage`_ project template.

.. _Cookiecutter: https://github.com/audreyr/cookiecutter
.. _`audreyr/cookiecutter-pypackage`: https://github.com/audreyr/cookiecutter-pypackage

-------
Cython modules
-------

The library was enhanced using the Cython library to improve speed efficiency.

https://cython.readthedocs.io/en/latest/

##Important

To make the library available for Linux and Windows the setup.py file
has to be run on both operational systems.

``
python3 setup.py sdist bdist_wheel
``

However, when used on Linux one gets a corrupted file that needs to be repaired
with auditwheel.

``
auditwheel repair dist/fibonacci-calculator-0.1.28-cp38-cp38-linux_86_64.whl
``

It can happen that the auditwheel is not backward compatible. However, it is forward
compatible. If run into any issues please use a Docker container using the following
code:

``
docker run -i -t -v `pwd`:/io quay.io/pypa/manylinux1_x86_64 /bin/bash
``

Try using git to retrieve the fibonacci-calculator-0.1.28-cp38-cp38-linux_86_64.whl
package and repair it within the container. After repairing push it in the repository
and store it again in the dist repository. Remove the fibonacci-calculator-0.1.28-cp38-cp38-linux_86_64.whl
wheel package.

After this one can upload the package to pypi.

``
python3 -m twine upload --repository pypi dist/*
``
