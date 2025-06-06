:github_url: hide

.. DO NOT EDIT THIS FILE!!!
.. Generated automatically from Godot engine sources.
.. Generator: https://github.com/godotengine/godot/tree/master/doc/tools/make_rst.py.
.. XML source: https://github.com/godotengine/godot/tree/master/doc/classes/PhysicsMaterial.xml.

.. _class_PhysicsMaterial:

PhysicsMaterial
===============

**Inherits:** :ref:`Resource<class_Resource>` **<** :ref:`RefCounted<class_RefCounted>` **<** :ref:`Object<class_Object>`

Holds physics-related properties of a surface, namely its roughness and bounciness.

.. rst-class:: classref-introduction-group

Description
-----------

Holds physics-related properties of a surface, namely its roughness and bounciness. This class is used to apply these properties to a physics body.

.. rst-class:: classref-reftable-group

Properties
----------

.. table::
   :widths: auto

   +---------------------------+------------------------------------------------------------+-----------+
   | :ref:`bool<class_bool>`   | :ref:`absorbent<class_PhysicsMaterial_property_absorbent>` | ``false`` |
   +---------------------------+------------------------------------------------------------+-----------+
   | :ref:`float<class_float>` | :ref:`bounce<class_PhysicsMaterial_property_bounce>`       | ``0.0``   |
   +---------------------------+------------------------------------------------------------+-----------+
   | :ref:`float<class_float>` | :ref:`friction<class_PhysicsMaterial_property_friction>`   | ``1.0``   |
   +---------------------------+------------------------------------------------------------+-----------+
   | :ref:`bool<class_bool>`   | :ref:`rough<class_PhysicsMaterial_property_rough>`         | ``false`` |
   +---------------------------+------------------------------------------------------------+-----------+

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Property Descriptions
---------------------

.. _class_PhysicsMaterial_property_absorbent:

.. rst-class:: classref-property

:ref:`bool<class_bool>` **absorbent** = ``false`` :ref:`🔗<class_PhysicsMaterial_property_absorbent>`

.. rst-class:: classref-property-setget

- |void| **set_absorbent**\ (\ value\: :ref:`bool<class_bool>`\ )
- :ref:`bool<class_bool>` **is_absorbent**\ (\ )

If ``true``, subtracts the bounciness from the colliding object's bounciness instead of adding it.

.. rst-class:: classref-item-separator

----

.. _class_PhysicsMaterial_property_bounce:

.. rst-class:: classref-property

:ref:`float<class_float>` **bounce** = ``0.0`` :ref:`🔗<class_PhysicsMaterial_property_bounce>`

.. rst-class:: classref-property-setget

- |void| **set_bounce**\ (\ value\: :ref:`float<class_float>`\ )
- :ref:`float<class_float>` **get_bounce**\ (\ )

The body's bounciness. Values range from ``0`` (no bounce) to ``1`` (full bounciness).

\ **Note:** Even with :ref:`bounce<class_PhysicsMaterial_property_bounce>` set to ``1.0``, some energy will be lost over time due to linear and angular damping. To have a physics body that preserves all its energy over time, set :ref:`bounce<class_PhysicsMaterial_property_bounce>` to ``1.0``, the body's linear damp mode to **Replace** (if applicable), its linear damp to ``0.0``, its angular damp mode to **Replace** (if applicable), and its angular damp to ``0.0``.

.. rst-class:: classref-item-separator

----

.. _class_PhysicsMaterial_property_friction:

.. rst-class:: classref-property

:ref:`float<class_float>` **friction** = ``1.0`` :ref:`🔗<class_PhysicsMaterial_property_friction>`

.. rst-class:: classref-property-setget

- |void| **set_friction**\ (\ value\: :ref:`float<class_float>`\ )
- :ref:`float<class_float>` **get_friction**\ (\ )

The body's friction. Values range from ``0`` (frictionless) to ``1`` (maximum friction).

.. rst-class:: classref-item-separator

----

.. _class_PhysicsMaterial_property_rough:

.. rst-class:: classref-property

:ref:`bool<class_bool>` **rough** = ``false`` :ref:`🔗<class_PhysicsMaterial_property_rough>`

.. rst-class:: classref-property-setget

- |void| **set_rough**\ (\ value\: :ref:`bool<class_bool>`\ )
- :ref:`bool<class_bool>` **is_rough**\ (\ )

If ``true``, the physics engine will use the friction of the object marked as "rough" when two objects collide. If ``false``, the physics engine will use the lowest friction of all colliding objects instead. If ``true`` for both colliding objects, the physics engine will use the highest friction.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |required| replace:: :abbr:`required (This method is required to be overridden when extending its base class.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
.. |bitfield| replace:: :abbr:`BitField (This value is an integer composed as a bitmask of the following flags.)`
.. |void| replace:: :abbr:`void (No return value.)`
