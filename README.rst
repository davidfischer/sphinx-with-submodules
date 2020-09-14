Sphinx with Submodules
======================

This project shows an example of using a `Sphinx documentation project <https://www.sphinx-doc.org/>`_
with `Git submodules <https://git-scm.com/book/en/v2/Git-Tools-Submodules>`_.

Here's a few notes:

* Sphinx cannot include documents from directories above its source directory.
  So you can't include documents from the common submodule directly with the ``toctree::`` directive.
  Instead, you must include documents from the source directory,
  and those can use the ``include::`` directive to include files from higher level folders.

* The `Read the Docs configuration file <https://docs.readthedocs.io/en/stable/config-file/v2.html>`_ (``.readthedocs.yml``)
  can include all submodules in the build or it can include or exclude a subset.

* In this example, the common submodule contents (``common/`` in this example and controlled in ``.gitmodules``)
  are not copied by Git into the Sphinx source directory (``source/``).
  This way not all the common sources are included in the Sphinx build output.