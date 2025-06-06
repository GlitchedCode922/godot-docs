:github_url: hide

.. DO NOT EDIT THIS FILE!!!
.. Generated automatically from Godot engine sources.
.. Generator: https://github.com/godotengine/godot/tree/master/doc/tools/make_rst.py.
.. XML source: https://github.com/godotengine/godot/tree/master/doc/classes/TextServerManager.xml.

.. _class_TextServerManager:

TextServerManager
=================

**Inherits:** :ref:`Object<class_Object>`

A singleton for managing :ref:`TextServer<class_TextServer>` implementations.

.. rst-class:: classref-introduction-group

Description
-----------

**TextServerManager** is the API backend for loading, enumerating, and switching :ref:`TextServer<class_TextServer>`\ s.

\ **Note:** Switching text server at runtime is possible, but will invalidate all fonts and text buffers. Make sure to unload all controls, fonts, and themes before doing so.

.. rst-class:: classref-reftable-group

Methods
-------

.. table::
   :widths: auto

   +------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | |void|                                                           | :ref:`add_interface<class_TextServerManager_method_add_interface>`\ (\ interface\: :ref:`TextServer<class_TextServer>`\ )             |
   +------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`TextServer<class_TextServer>`                              | :ref:`find_interface<class_TextServerManager_method_find_interface>`\ (\ name\: :ref:`String<class_String>`\ ) |const|                |
   +------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`TextServer<class_TextServer>`                              | :ref:`get_interface<class_TextServerManager_method_get_interface>`\ (\ idx\: :ref:`int<class_int>`\ ) |const|                         |
   +------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`int<class_int>`                                            | :ref:`get_interface_count<class_TextServerManager_method_get_interface_count>`\ (\ ) |const|                                          |
   +------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Array<class_Array>`\[:ref:`Dictionary<class_Dictionary>`\] | :ref:`get_interfaces<class_TextServerManager_method_get_interfaces>`\ (\ ) |const|                                                    |
   +------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`TextServer<class_TextServer>`                              | :ref:`get_primary_interface<class_TextServerManager_method_get_primary_interface>`\ (\ ) |const|                                      |
   +------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | |void|                                                           | :ref:`remove_interface<class_TextServerManager_method_remove_interface>`\ (\ interface\: :ref:`TextServer<class_TextServer>`\ )       |
   +------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | |void|                                                           | :ref:`set_primary_interface<class_TextServerManager_method_set_primary_interface>`\ (\ index\: :ref:`TextServer<class_TextServer>`\ ) |
   +------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Signals
-------

.. _class_TextServerManager_signal_interface_added:

.. rst-class:: classref-signal

**interface_added**\ (\ interface_name\: :ref:`StringName<class_StringName>`\ ) :ref:`🔗<class_TextServerManager_signal_interface_added>`

Emitted when a new interface has been added.

.. rst-class:: classref-item-separator

----

.. _class_TextServerManager_signal_interface_removed:

.. rst-class:: classref-signal

**interface_removed**\ (\ interface_name\: :ref:`StringName<class_StringName>`\ ) :ref:`🔗<class_TextServerManager_signal_interface_removed>`

Emitted when an interface is removed.

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Method Descriptions
-------------------

.. _class_TextServerManager_method_add_interface:

.. rst-class:: classref-method

|void| **add_interface**\ (\ interface\: :ref:`TextServer<class_TextServer>`\ ) :ref:`🔗<class_TextServerManager_method_add_interface>`

Registers a :ref:`TextServer<class_TextServer>` interface.

.. rst-class:: classref-item-separator

----

.. _class_TextServerManager_method_find_interface:

.. rst-class:: classref-method

:ref:`TextServer<class_TextServer>` **find_interface**\ (\ name\: :ref:`String<class_String>`\ ) |const| :ref:`🔗<class_TextServerManager_method_find_interface>`

Finds an interface by its ``name``.

.. rst-class:: classref-item-separator

----

.. _class_TextServerManager_method_get_interface:

.. rst-class:: classref-method

:ref:`TextServer<class_TextServer>` **get_interface**\ (\ idx\: :ref:`int<class_int>`\ ) |const| :ref:`🔗<class_TextServerManager_method_get_interface>`

Returns the interface registered at a given index.

.. rst-class:: classref-item-separator

----

.. _class_TextServerManager_method_get_interface_count:

.. rst-class:: classref-method

:ref:`int<class_int>` **get_interface_count**\ (\ ) |const| :ref:`🔗<class_TextServerManager_method_get_interface_count>`

Returns the number of interfaces currently registered.

.. rst-class:: classref-item-separator

----

.. _class_TextServerManager_method_get_interfaces:

.. rst-class:: classref-method

:ref:`Array<class_Array>`\[:ref:`Dictionary<class_Dictionary>`\] **get_interfaces**\ (\ ) |const| :ref:`🔗<class_TextServerManager_method_get_interfaces>`

Returns a list of available interfaces, with the index and name of each interface.

.. rst-class:: classref-item-separator

----

.. _class_TextServerManager_method_get_primary_interface:

.. rst-class:: classref-method

:ref:`TextServer<class_TextServer>` **get_primary_interface**\ (\ ) |const| :ref:`🔗<class_TextServerManager_method_get_primary_interface>`

Returns the primary :ref:`TextServer<class_TextServer>` interface currently in use.

.. rst-class:: classref-item-separator

----

.. _class_TextServerManager_method_remove_interface:

.. rst-class:: classref-method

|void| **remove_interface**\ (\ interface\: :ref:`TextServer<class_TextServer>`\ ) :ref:`🔗<class_TextServerManager_method_remove_interface>`

Removes an interface. All fonts and shaped text caches should be freed before removing an interface.

.. rst-class:: classref-item-separator

----

.. _class_TextServerManager_method_set_primary_interface:

.. rst-class:: classref-method

|void| **set_primary_interface**\ (\ index\: :ref:`TextServer<class_TextServer>`\ ) :ref:`🔗<class_TextServerManager_method_set_primary_interface>`

Sets the primary :ref:`TextServer<class_TextServer>` interface.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |required| replace:: :abbr:`required (This method is required to be overridden when extending its base class.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
.. |bitfield| replace:: :abbr:`BitField (This value is an integer composed as a bitmask of the following flags.)`
.. |void| replace:: :abbr:`void (No return value.)`
