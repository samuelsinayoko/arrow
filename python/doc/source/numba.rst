.. Licensed to the Apache Software Foundation (ASF) under one
.. or more contributor license agreements.  See the NOTICE file
.. distributed with this work for additional information
.. regarding copyright ownership.  The ASF licenses this file
.. to you under the Apache License, Version 2.0 (the
.. "License"); you may not use this file except in compliance
.. with the License.  You may obtain a copy of the License at

..   http://www.apache.org/licenses/LICENSE-2.0

.. Unless required by applicable law or agreed to in writing,
.. software distributed under the License is distributed on an
.. "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
.. KIND, either express or implied.  See the License for the
.. specific language governing permissions and limitations
.. under the License.

.. currentmodule:: pyarrow.lib
.. _extending:

Using PyArrow with Numba
==================================

This section describes how to process arrow objects efficiently with `Numba <https://numba.pydata.org/>`_. Converting such objects to Pandas may be computationally expensive as it may require copies of part of the object. Such copies can be avoided by implementing a view of the object that is compatible with `Numba <https://numba.pydata.org/>`_. This document is a tutorial on how to expand pyarrow with Numba.

Numba supports NumPy `arrays <http://numba.pydata.org/numba-doc/latest/reference/types.html#arrays>`_, so one way to process a pyarrow array with Numba is to construct a view of the object as a NumPy array.

PyArrow strings with Numba
------------------------------

.. ipython:: python
	     # TODO
