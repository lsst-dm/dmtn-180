.. image:: https://img.shields.io/badge/dmtn--180-lsst.io-brightgreen.svg
   :target: https://dmtn-180.lsst.io
.. image:: https://travis-ci.com/lsst-dm/dmtn-180.svg
   :target: https://travis-ci.com/lsst-dm/dmtn-180

#######################################################
DEx1: The First LSST-MPC Data Exchange Challenge Report
#######################################################

DMTN-180
========

This note describes the result of the first data exchange test (DEx1) between the Minor Planet Center and the Rubin Observatory. It covered four key goals: a) assess Rubin's ability to generate valid ADES-formatted submissions, ii) assess MPC’s current and expected future ability to ingest LSST-sized submissions, iii) exercise/understand the submission process and iv) establish relationships between the MPC and Rubin teams. To do so, we have simulated the first 17 nights of Rubin Solar System object discoveries, generated ADES files, and submitted them to the MPC. These were (manually) processed by the MPC to both compute orbits for new discoveries, and extend arcs for re-observations of known objects. Based on the simulations used here, we found the LSST is expected to discover approximately 0.5M new objects in the first month of operations. Designations of such objects will have unprecedentedly high cycle counts (e.g., 2023 UX$_{5678}$), which cannot be written in packed form following the present scheme. The packed provisional designation scheme will therefore have to be updated to accommodate (ideally) $O(1\mathrm{M})$ new discoveries in any half-month (or abandoned). Other than that issue, assuming necessary automation is implemented and further computational resources added, this test found no fundamental obstacles in MPC being able to process the LSST data. Future tests will focus on automation and injecting further realism in the simulated dataset.

Links
=====

- Live drafts: https://dmtn-180.lsst.io
- GitHub: https://github.com/lsst-dm/dmtn-180

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-dm/dmtn-180

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the `acronyms.tex` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
