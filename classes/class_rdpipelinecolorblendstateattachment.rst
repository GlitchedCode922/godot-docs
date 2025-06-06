:github_url: hide

.. DO NOT EDIT THIS FILE!!!
.. Generated automatically from Godot engine sources.
.. Generator: https://github.com/godotengine/godot/tree/master/doc/tools/make_rst.py.
.. XML source: https://github.com/godotengine/godot/tree/master/doc/classes/RDPipelineColorBlendStateAttachment.xml.

.. _class_RDPipelineColorBlendStateAttachment:

RDPipelineColorBlendStateAttachment
===================================

**Inherits:** :ref:`RefCounted<class_RefCounted>` **<** :ref:`Object<class_Object>`

Pipeline color blend state attachment (used by :ref:`RenderingDevice<class_RenderingDevice>`).

.. rst-class:: classref-introduction-group

Description
-----------

Controls how blending between source and destination fragments is performed when using :ref:`RenderingDevice<class_RenderingDevice>`.

For reference, this is how common user-facing blend modes are implemented in Godot's 2D renderer:

\ **Mix:**\ 

::

    var attachment = RDPipelineColorBlendStateAttachment.new()
    attachment.enable_blend = true
    attachment.color_blend_op = RenderingDevice.BLEND_OP_ADD
    attachment.src_color_blend_factor = RenderingDevice.BLEND_FACTOR_SRC_ALPHA
    attachment.dst_color_blend_factor = RenderingDevice.BLEND_FACTOR_ONE_MINUS_SRC_ALPHA
    attachment.alpha_blend_op = RenderingDevice.BLEND_OP_ADD
    attachment.src_alpha_blend_factor = RenderingDevice.BLEND_FACTOR_ONE
    attachment.dst_alpha_blend_factor = RenderingDevice.BLEND_FACTOR_ONE_MINUS_SRC_ALPHA

\ **Add:**\ 

::

    var attachment = RDPipelineColorBlendStateAttachment.new()
    attachment.enable_blend = true
    attachment.alpha_blend_op = RenderingDevice.BLEND_OP_ADD
    attachment.color_blend_op = RenderingDevice.BLEND_OP_ADD
    attachment.src_color_blend_factor = RenderingDevice.BLEND_FACTOR_SRC_ALPHA
    attachment.dst_color_blend_factor = RenderingDevice.BLEND_FACTOR_ONE
    attachment.src_alpha_blend_factor = RenderingDevice.BLEND_FACTOR_SRC_ALPHA
    attachment.dst_alpha_blend_factor = RenderingDevice.BLEND_FACTOR_ONE

\ **Subtract:**\ 

::

    var attachment = RDPipelineColorBlendStateAttachment.new()
    attachment.enable_blend = true
    attachment.alpha_blend_op = RenderingDevice.BLEND_OP_REVERSE_SUBTRACT
    attachment.color_blend_op = RenderingDevice.BLEND_OP_REVERSE_SUBTRACT
    attachment.src_color_blend_factor = RenderingDevice.BLEND_FACTOR_SRC_ALPHA
    attachment.dst_color_blend_factor = RenderingDevice.BLEND_FACTOR_ONE
    attachment.src_alpha_blend_factor = RenderingDevice.BLEND_FACTOR_SRC_ALPHA
    attachment.dst_alpha_blend_factor = RenderingDevice.BLEND_FACTOR_ONE

\ **Multiply:**\ 

::

    var attachment = RDPipelineColorBlendStateAttachment.new()
    attachment.enable_blend = true
    attachment.alpha_blend_op = RenderingDevice.BLEND_OP_ADD
    attachment.color_blend_op = RenderingDevice.BLEND_OP_ADD
    attachment.src_color_blend_factor = RenderingDevice.BLEND_FACTOR_DST_COLOR
    attachment.dst_color_blend_factor = RenderingDevice.BLEND_FACTOR_ZERO
    attachment.src_alpha_blend_factor = RenderingDevice.BLEND_FACTOR_DST_ALPHA
    attachment.dst_alpha_blend_factor = RenderingDevice.BLEND_FACTOR_ZERO

\ **Pre-multiplied alpha:**\ 

::

    var attachment = RDPipelineColorBlendStateAttachment.new()
    attachment.enable_blend = true
    attachment.alpha_blend_op = RenderingDevice.BLEND_OP_ADD
    attachment.color_blend_op = RenderingDevice.BLEND_OP_ADD
    attachment.src_color_blend_factor = RenderingDevice.BLEND_FACTOR_ONE
    attachment.dst_color_blend_factor = RenderingDevice.BLEND_FACTOR_ONE_MINUS_SRC_ALPHA
    attachment.src_alpha_blend_factor = RenderingDevice.BLEND_FACTOR_ONE
    attachment.dst_alpha_blend_factor = RenderingDevice.BLEND_FACTOR_ONE_MINUS_SRC_ALPHA

.. rst-class:: classref-reftable-group

Properties
----------

.. table::
   :widths: auto

   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+
   | :ref:`BlendOperation<enum_RenderingDevice_BlendOperation>` | :ref:`alpha_blend_op<class_RDPipelineColorBlendStateAttachment_property_alpha_blend_op>`                 | ``0``     |
   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+
   | :ref:`BlendOperation<enum_RenderingDevice_BlendOperation>` | :ref:`color_blend_op<class_RDPipelineColorBlendStateAttachment_property_color_blend_op>`                 | ``0``     |
   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+
   | :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>`       | :ref:`dst_alpha_blend_factor<class_RDPipelineColorBlendStateAttachment_property_dst_alpha_blend_factor>` | ``0``     |
   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+
   | :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>`       | :ref:`dst_color_blend_factor<class_RDPipelineColorBlendStateAttachment_property_dst_color_blend_factor>` | ``0``     |
   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+
   | :ref:`bool<class_bool>`                                    | :ref:`enable_blend<class_RDPipelineColorBlendStateAttachment_property_enable_blend>`                     | ``false`` |
   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+
   | :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>`       | :ref:`src_alpha_blend_factor<class_RDPipelineColorBlendStateAttachment_property_src_alpha_blend_factor>` | ``0``     |
   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+
   | :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>`       | :ref:`src_color_blend_factor<class_RDPipelineColorBlendStateAttachment_property_src_color_blend_factor>` | ``0``     |
   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+
   | :ref:`bool<class_bool>`                                    | :ref:`write_a<class_RDPipelineColorBlendStateAttachment_property_write_a>`                               | ``true``  |
   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+
   | :ref:`bool<class_bool>`                                    | :ref:`write_b<class_RDPipelineColorBlendStateAttachment_property_write_b>`                               | ``true``  |
   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+
   | :ref:`bool<class_bool>`                                    | :ref:`write_g<class_RDPipelineColorBlendStateAttachment_property_write_g>`                               | ``true``  |
   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+
   | :ref:`bool<class_bool>`                                    | :ref:`write_r<class_RDPipelineColorBlendStateAttachment_property_write_r>`                               | ``true``  |
   +------------------------------------------------------------+----------------------------------------------------------------------------------------------------------+-----------+

.. rst-class:: classref-reftable-group

Methods
-------

.. table::
   :widths: auto

   +--------+--------------------------------------------------------------------------------------+
   | |void| | :ref:`set_as_mix<class_RDPipelineColorBlendStateAttachment_method_set_as_mix>`\ (\ ) |
   +--------+--------------------------------------------------------------------------------------+

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Property Descriptions
---------------------

.. _class_RDPipelineColorBlendStateAttachment_property_alpha_blend_op:

.. rst-class:: classref-property

:ref:`BlendOperation<enum_RenderingDevice_BlendOperation>` **alpha_blend_op** = ``0`` :ref:`🔗<class_RDPipelineColorBlendStateAttachment_property_alpha_blend_op>`

.. rst-class:: classref-property-setget

- |void| **set_alpha_blend_op**\ (\ value\: :ref:`BlendOperation<enum_RenderingDevice_BlendOperation>`\ )
- :ref:`BlendOperation<enum_RenderingDevice_BlendOperation>` **get_alpha_blend_op**\ (\ )

The blend mode to use for the alpha channel.

.. rst-class:: classref-item-separator

----

.. _class_RDPipelineColorBlendStateAttachment_property_color_blend_op:

.. rst-class:: classref-property

:ref:`BlendOperation<enum_RenderingDevice_BlendOperation>` **color_blend_op** = ``0`` :ref:`🔗<class_RDPipelineColorBlendStateAttachment_property_color_blend_op>`

.. rst-class:: classref-property-setget

- |void| **set_color_blend_op**\ (\ value\: :ref:`BlendOperation<enum_RenderingDevice_BlendOperation>`\ )
- :ref:`BlendOperation<enum_RenderingDevice_BlendOperation>` **get_color_blend_op**\ (\ )

The blend mode to use for the red/green/blue color channels.

.. rst-class:: classref-item-separator

----

.. _class_RDPipelineColorBlendStateAttachment_property_dst_alpha_blend_factor:

.. rst-class:: classref-property

:ref:`BlendFactor<enum_RenderingDevice_BlendFactor>` **dst_alpha_blend_factor** = ``0`` :ref:`🔗<class_RDPipelineColorBlendStateAttachment_property_dst_alpha_blend_factor>`

.. rst-class:: classref-property-setget

- |void| **set_dst_alpha_blend_factor**\ (\ value\: :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>`\ )
- :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>` **get_dst_alpha_blend_factor**\ (\ )

Controls how the blend factor for the alpha channel is determined based on the destination's fragments.

.. rst-class:: classref-item-separator

----

.. _class_RDPipelineColorBlendStateAttachment_property_dst_color_blend_factor:

.. rst-class:: classref-property

:ref:`BlendFactor<enum_RenderingDevice_BlendFactor>` **dst_color_blend_factor** = ``0`` :ref:`🔗<class_RDPipelineColorBlendStateAttachment_property_dst_color_blend_factor>`

.. rst-class:: classref-property-setget

- |void| **set_dst_color_blend_factor**\ (\ value\: :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>`\ )
- :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>` **get_dst_color_blend_factor**\ (\ )

Controls how the blend factor for the color channels is determined based on the destination's fragments.

.. rst-class:: classref-item-separator

----

.. _class_RDPipelineColorBlendStateAttachment_property_enable_blend:

.. rst-class:: classref-property

:ref:`bool<class_bool>` **enable_blend** = ``false`` :ref:`🔗<class_RDPipelineColorBlendStateAttachment_property_enable_blend>`

.. rst-class:: classref-property-setget

- |void| **set_enable_blend**\ (\ value\: :ref:`bool<class_bool>`\ )
- :ref:`bool<class_bool>` **get_enable_blend**\ (\ )

If ``true``, performs blending between the source and destination according to the factors defined in :ref:`src_color_blend_factor<class_RDPipelineColorBlendStateAttachment_property_src_color_blend_factor>`, :ref:`dst_color_blend_factor<class_RDPipelineColorBlendStateAttachment_property_dst_color_blend_factor>`, :ref:`src_alpha_blend_factor<class_RDPipelineColorBlendStateAttachment_property_src_alpha_blend_factor>` and :ref:`dst_alpha_blend_factor<class_RDPipelineColorBlendStateAttachment_property_dst_alpha_blend_factor>`. The blend modes :ref:`color_blend_op<class_RDPipelineColorBlendStateAttachment_property_color_blend_op>` and :ref:`alpha_blend_op<class_RDPipelineColorBlendStateAttachment_property_alpha_blend_op>` are also taken into account, with :ref:`write_r<class_RDPipelineColorBlendStateAttachment_property_write_r>`, :ref:`write_g<class_RDPipelineColorBlendStateAttachment_property_write_g>`, :ref:`write_b<class_RDPipelineColorBlendStateAttachment_property_write_b>` and :ref:`write_a<class_RDPipelineColorBlendStateAttachment_property_write_a>` controlling the output.

.. rst-class:: classref-item-separator

----

.. _class_RDPipelineColorBlendStateAttachment_property_src_alpha_blend_factor:

.. rst-class:: classref-property

:ref:`BlendFactor<enum_RenderingDevice_BlendFactor>` **src_alpha_blend_factor** = ``0`` :ref:`🔗<class_RDPipelineColorBlendStateAttachment_property_src_alpha_blend_factor>`

.. rst-class:: classref-property-setget

- |void| **set_src_alpha_blend_factor**\ (\ value\: :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>`\ )
- :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>` **get_src_alpha_blend_factor**\ (\ )

Controls how the blend factor for the alpha channel is determined based on the source's fragments.

.. rst-class:: classref-item-separator

----

.. _class_RDPipelineColorBlendStateAttachment_property_src_color_blend_factor:

.. rst-class:: classref-property

:ref:`BlendFactor<enum_RenderingDevice_BlendFactor>` **src_color_blend_factor** = ``0`` :ref:`🔗<class_RDPipelineColorBlendStateAttachment_property_src_color_blend_factor>`

.. rst-class:: classref-property-setget

- |void| **set_src_color_blend_factor**\ (\ value\: :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>`\ )
- :ref:`BlendFactor<enum_RenderingDevice_BlendFactor>` **get_src_color_blend_factor**\ (\ )

Controls how the blend factor for the color channels is determined based on the source's fragments.

.. rst-class:: classref-item-separator

----

.. _class_RDPipelineColorBlendStateAttachment_property_write_a:

.. rst-class:: classref-property

:ref:`bool<class_bool>` **write_a** = ``true`` :ref:`🔗<class_RDPipelineColorBlendStateAttachment_property_write_a>`

.. rst-class:: classref-property-setget

- |void| **set_write_a**\ (\ value\: :ref:`bool<class_bool>`\ )
- :ref:`bool<class_bool>` **get_write_a**\ (\ )

If ``true``, writes the new alpha channel to the final result.

.. rst-class:: classref-item-separator

----

.. _class_RDPipelineColorBlendStateAttachment_property_write_b:

.. rst-class:: classref-property

:ref:`bool<class_bool>` **write_b** = ``true`` :ref:`🔗<class_RDPipelineColorBlendStateAttachment_property_write_b>`

.. rst-class:: classref-property-setget

- |void| **set_write_b**\ (\ value\: :ref:`bool<class_bool>`\ )
- :ref:`bool<class_bool>` **get_write_b**\ (\ )

If ``true``, writes the new blue color channel to the final result.

.. rst-class:: classref-item-separator

----

.. _class_RDPipelineColorBlendStateAttachment_property_write_g:

.. rst-class:: classref-property

:ref:`bool<class_bool>` **write_g** = ``true`` :ref:`🔗<class_RDPipelineColorBlendStateAttachment_property_write_g>`

.. rst-class:: classref-property-setget

- |void| **set_write_g**\ (\ value\: :ref:`bool<class_bool>`\ )
- :ref:`bool<class_bool>` **get_write_g**\ (\ )

If ``true``, writes the new green color channel to the final result.

.. rst-class:: classref-item-separator

----

.. _class_RDPipelineColorBlendStateAttachment_property_write_r:

.. rst-class:: classref-property

:ref:`bool<class_bool>` **write_r** = ``true`` :ref:`🔗<class_RDPipelineColorBlendStateAttachment_property_write_r>`

.. rst-class:: classref-property-setget

- |void| **set_write_r**\ (\ value\: :ref:`bool<class_bool>`\ )
- :ref:`bool<class_bool>` **get_write_r**\ (\ )

If ``true``, writes the new red color channel to the final result.

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Method Descriptions
-------------------

.. _class_RDPipelineColorBlendStateAttachment_method_set_as_mix:

.. rst-class:: classref-method

|void| **set_as_mix**\ (\ ) :ref:`🔗<class_RDPipelineColorBlendStateAttachment_method_set_as_mix>`

Convenience method to perform standard mix blending with straight (non-premultiplied) alpha. This sets :ref:`enable_blend<class_RDPipelineColorBlendStateAttachment_property_enable_blend>` to ``true``, :ref:`src_color_blend_factor<class_RDPipelineColorBlendStateAttachment_property_src_color_blend_factor>` to :ref:`RenderingDevice.BLEND_FACTOR_SRC_ALPHA<class_RenderingDevice_constant_BLEND_FACTOR_SRC_ALPHA>`, :ref:`dst_color_blend_factor<class_RDPipelineColorBlendStateAttachment_property_dst_color_blend_factor>` to :ref:`RenderingDevice.BLEND_FACTOR_ONE_MINUS_SRC_ALPHA<class_RenderingDevice_constant_BLEND_FACTOR_ONE_MINUS_SRC_ALPHA>`, :ref:`src_alpha_blend_factor<class_RDPipelineColorBlendStateAttachment_property_src_alpha_blend_factor>` to :ref:`RenderingDevice.BLEND_FACTOR_SRC_ALPHA<class_RenderingDevice_constant_BLEND_FACTOR_SRC_ALPHA>` and :ref:`dst_alpha_blend_factor<class_RDPipelineColorBlendStateAttachment_property_dst_alpha_blend_factor>` to :ref:`RenderingDevice.BLEND_FACTOR_ONE_MINUS_SRC_ALPHA<class_RenderingDevice_constant_BLEND_FACTOR_ONE_MINUS_SRC_ALPHA>`.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |required| replace:: :abbr:`required (This method is required to be overridden when extending its base class.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
.. |bitfield| replace:: :abbr:`BitField (This value is an integer composed as a bitmask of the following flags.)`
.. |void| replace:: :abbr:`void (No return value.)`
