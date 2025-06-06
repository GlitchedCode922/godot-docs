:github_url: hide

.. DO NOT EDIT THIS FILE!!!
.. Generated automatically from Godot engine sources.
.. Generator: https://github.com/godotengine/godot/tree/master/doc/tools/make_rst.py.
.. XML source: https://github.com/godotengine/godot/tree/master/doc/classes/VideoStream.xml.

.. _class_VideoStream:

VideoStream
===========

**Inherits:** :ref:`Resource<class_Resource>` **<** :ref:`RefCounted<class_RefCounted>` **<** :ref:`Object<class_Object>`

**Inherited By:** :ref:`VideoStreamTheora<class_VideoStreamTheora>`

Base resource for video streams.

.. rst-class:: classref-introduction-group

Description
-----------

Base resource type for all video streams. Classes that derive from **VideoStream** can all be used as resource types to play back videos in :ref:`VideoStreamPlayer<class_VideoStreamPlayer>`.

.. rst-class:: classref-introduction-group

Tutorials
---------

- :doc:`Playing videos <../tutorials/animation/playing_videos>`

- :doc:`Runtime file loading and saving <../tutorials/io/runtime_file_loading_and_saving>`

.. rst-class:: classref-reftable-group

Properties
----------

.. table::
   :widths: auto

   +-----------------------------+----------------------------------------------+--------+
   | :ref:`String<class_String>` | :ref:`file<class_VideoStream_property_file>` | ``""`` |
   +-----------------------------+----------------------------------------------+--------+

.. rst-class:: classref-reftable-group

Methods
-------

.. table::
   :widths: auto

   +-------------------------------------------------------+------------------------------------------------------------------------------------------------------+
   | :ref:`VideoStreamPlayback<class_VideoStreamPlayback>` | :ref:`_instantiate_playback<class_VideoStream_private_method__instantiate_playback>`\ (\ ) |virtual| |
   +-------------------------------------------------------+------------------------------------------------------------------------------------------------------+

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Property Descriptions
---------------------

.. _class_VideoStream_property_file:

.. rst-class:: classref-property

:ref:`String<class_String>` **file** = ``""`` :ref:`🔗<class_VideoStream_property_file>`

.. rst-class:: classref-property-setget

- |void| **set_file**\ (\ value\: :ref:`String<class_String>`\ )
- :ref:`String<class_String>` **get_file**\ (\ )

The video file path or URI that this **VideoStream** resource handles.

For :ref:`VideoStreamTheora<class_VideoStreamTheora>`, this filename should be an Ogg Theora video file with the ``.ogv`` extension.

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Method Descriptions
-------------------

.. _class_VideoStream_private_method__instantiate_playback:

.. rst-class:: classref-method

:ref:`VideoStreamPlayback<class_VideoStreamPlayback>` **_instantiate_playback**\ (\ ) |virtual| :ref:`🔗<class_VideoStream_private_method__instantiate_playback>`

Called when the video starts playing, to initialize and return a subclass of :ref:`VideoStreamPlayback<class_VideoStreamPlayback>`.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |required| replace:: :abbr:`required (This method is required to be overridden when extending its base class.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
.. |bitfield| replace:: :abbr:`BitField (This value is an integer composed as a bitmask of the following flags.)`
.. |void| replace:: :abbr:`void (No return value.)`
