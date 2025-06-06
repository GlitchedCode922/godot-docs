:github_url: hide

.. meta::
	:keywords: network

.. DO NOT EDIT THIS FILE!!!
.. Generated automatically from Godot engine sources.
.. Generator: https://github.com/godotengine/godot/tree/master/doc/tools/make_rst.py.
.. XML source: https://github.com/godotengine/godot/tree/master/doc/classes/MultiplayerAPI.xml.

.. _class_MultiplayerAPI:

MultiplayerAPI
==============

**Inherits:** :ref:`RefCounted<class_RefCounted>` **<** :ref:`Object<class_Object>`

**Inherited By:** :ref:`MultiplayerAPIExtension<class_MultiplayerAPIExtension>`, :ref:`SceneMultiplayer<class_SceneMultiplayer>`

High-level multiplayer API interface.

.. rst-class:: classref-introduction-group

Description
-----------

Base class for high-level multiplayer API implementations. See also :ref:`MultiplayerPeer<class_MultiplayerPeer>`.

By default, :ref:`SceneTree<class_SceneTree>` has a reference to an implementation of this class and uses it to provide multiplayer capabilities (i.e. RPCs) across the whole scene.

It is possible to override the MultiplayerAPI instance used by specific tree branches by calling the :ref:`SceneTree.set_multiplayer()<class_SceneTree_method_set_multiplayer>` method, effectively allowing to run both client and server in the same scene.

It is also possible to extend or replace the default implementation via scripting or native extensions. See :ref:`MultiplayerAPIExtension<class_MultiplayerAPIExtension>` for details about extensions, :ref:`SceneMultiplayer<class_SceneMultiplayer>` for the details about the default implementation.

.. rst-class:: classref-reftable-group

Properties
----------

.. table::
   :widths: auto

   +-----------------------------------------------+-------------------------------------------------------------------------+
   | :ref:`MultiplayerPeer<class_MultiplayerPeer>` | :ref:`multiplayer_peer<class_MultiplayerAPI_property_multiplayer_peer>` |
   +-----------------------------------------------+-------------------------------------------------------------------------+

.. rst-class:: classref-reftable-group

Methods
-------

.. table::
   :widths: auto

   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`MultiplayerAPI<class_MultiplayerAPI>`     | :ref:`create_default_interface<class_MultiplayerAPI_method_create_default_interface>`\ (\ ) |static|                                                                                                            |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`StringName<class_StringName>`             | :ref:`get_default_interface<class_MultiplayerAPI_method_get_default_interface>`\ (\ ) |static|                                                                                                                  |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`PackedInt32Array<class_PackedInt32Array>` | :ref:`get_peers<class_MultiplayerAPI_method_get_peers>`\ (\ )                                                                                                                                                   |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`int<class_int>`                           | :ref:`get_remote_sender_id<class_MultiplayerAPI_method_get_remote_sender_id>`\ (\ )                                                                                                                             |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`int<class_int>`                           | :ref:`get_unique_id<class_MultiplayerAPI_method_get_unique_id>`\ (\ )                                                                                                                                           |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`bool<class_bool>`                         | :ref:`has_multiplayer_peer<class_MultiplayerAPI_method_has_multiplayer_peer>`\ (\ )                                                                                                                             |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`bool<class_bool>`                         | :ref:`is_server<class_MultiplayerAPI_method_is_server>`\ (\ )                                                                                                                                                   |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Error<enum_@GlobalScope_Error>`           | :ref:`object_configuration_add<class_MultiplayerAPI_method_object_configuration_add>`\ (\ object\: :ref:`Object<class_Object>`, configuration\: :ref:`Variant<class_Variant>`\ )                                |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Error<enum_@GlobalScope_Error>`           | :ref:`object_configuration_remove<class_MultiplayerAPI_method_object_configuration_remove>`\ (\ object\: :ref:`Object<class_Object>`, configuration\: :ref:`Variant<class_Variant>`\ )                          |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Error<enum_@GlobalScope_Error>`           | :ref:`poll<class_MultiplayerAPI_method_poll>`\ (\ )                                                                                                                                                             |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | :ref:`Error<enum_@GlobalScope_Error>`           | :ref:`rpc<class_MultiplayerAPI_method_rpc>`\ (\ peer\: :ref:`int<class_int>`, object\: :ref:`Object<class_Object>`, method\: :ref:`StringName<class_StringName>`, arguments\: :ref:`Array<class_Array>` = []\ ) |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | |void|                                          | :ref:`set_default_interface<class_MultiplayerAPI_method_set_default_interface>`\ (\ interface_name\: :ref:`StringName<class_StringName>`\ ) |static|                                                            |
   +-------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Signals
-------

.. _class_MultiplayerAPI_signal_connected_to_server:

.. rst-class:: classref-signal

**connected_to_server**\ (\ ) :ref:`🔗<class_MultiplayerAPI_signal_connected_to_server>`

Emitted when this MultiplayerAPI's :ref:`multiplayer_peer<class_MultiplayerAPI_property_multiplayer_peer>` successfully connected to a server. Only emitted on clients.

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_signal_connection_failed:

.. rst-class:: classref-signal

**connection_failed**\ (\ ) :ref:`🔗<class_MultiplayerAPI_signal_connection_failed>`

Emitted when this MultiplayerAPI's :ref:`multiplayer_peer<class_MultiplayerAPI_property_multiplayer_peer>` fails to establish a connection to a server. Only emitted on clients.

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_signal_peer_connected:

.. rst-class:: classref-signal

**peer_connected**\ (\ id\: :ref:`int<class_int>`\ ) :ref:`🔗<class_MultiplayerAPI_signal_peer_connected>`

Emitted when this MultiplayerAPI's :ref:`multiplayer_peer<class_MultiplayerAPI_property_multiplayer_peer>` connects with a new peer. ID is the peer ID of the new peer. Clients get notified when other clients connect to the same server. Upon connecting to a server, a client also receives this signal for the server (with ID being 1).

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_signal_peer_disconnected:

.. rst-class:: classref-signal

**peer_disconnected**\ (\ id\: :ref:`int<class_int>`\ ) :ref:`🔗<class_MultiplayerAPI_signal_peer_disconnected>`

Emitted when this MultiplayerAPI's :ref:`multiplayer_peer<class_MultiplayerAPI_property_multiplayer_peer>` disconnects from a peer. Clients get notified when other clients disconnect from the same server.

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_signal_server_disconnected:

.. rst-class:: classref-signal

**server_disconnected**\ (\ ) :ref:`🔗<class_MultiplayerAPI_signal_server_disconnected>`

Emitted when this MultiplayerAPI's :ref:`multiplayer_peer<class_MultiplayerAPI_property_multiplayer_peer>` disconnects from server. Only emitted on clients.

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Enumerations
------------

.. _enum_MultiplayerAPI_RPCMode:

.. rst-class:: classref-enumeration

enum **RPCMode**: :ref:`🔗<enum_MultiplayerAPI_RPCMode>`

.. _class_MultiplayerAPI_constant_RPC_MODE_DISABLED:

.. rst-class:: classref-enumeration-constant

:ref:`RPCMode<enum_MultiplayerAPI_RPCMode>` **RPC_MODE_DISABLED** = ``0``

Used with :ref:`Node.rpc_config()<class_Node_method_rpc_config>` to disable a method or property for all RPC calls, making it unavailable. Default for all methods.

.. _class_MultiplayerAPI_constant_RPC_MODE_ANY_PEER:

.. rst-class:: classref-enumeration-constant

:ref:`RPCMode<enum_MultiplayerAPI_RPCMode>` **RPC_MODE_ANY_PEER** = ``1``

Used with :ref:`Node.rpc_config()<class_Node_method_rpc_config>` to set a method to be callable remotely by any peer. Analogous to the ``@rpc("any_peer")`` annotation. Calls are accepted from all remote peers, no matter if they are node's authority or not.

.. _class_MultiplayerAPI_constant_RPC_MODE_AUTHORITY:

.. rst-class:: classref-enumeration-constant

:ref:`RPCMode<enum_MultiplayerAPI_RPCMode>` **RPC_MODE_AUTHORITY** = ``2``

Used with :ref:`Node.rpc_config()<class_Node_method_rpc_config>` to set a method to be callable remotely only by the current multiplayer authority (which is the server by default). Analogous to the ``@rpc("authority")`` annotation. See :ref:`Node.set_multiplayer_authority()<class_Node_method_set_multiplayer_authority>`.

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Property Descriptions
---------------------

.. _class_MultiplayerAPI_property_multiplayer_peer:

.. rst-class:: classref-property

:ref:`MultiplayerPeer<class_MultiplayerPeer>` **multiplayer_peer** :ref:`🔗<class_MultiplayerAPI_property_multiplayer_peer>`

.. rst-class:: classref-property-setget

- |void| **set_multiplayer_peer**\ (\ value\: :ref:`MultiplayerPeer<class_MultiplayerPeer>`\ )
- :ref:`MultiplayerPeer<class_MultiplayerPeer>` **get_multiplayer_peer**\ (\ )

The peer object to handle the RPC system (effectively enabling networking when set). Depending on the peer itself, the MultiplayerAPI will become a network server (check with :ref:`is_server()<class_MultiplayerAPI_method_is_server>`) and will set root node's network mode to authority, or it will become a regular client peer. All child nodes are set to inherit the network mode by default. Handling of networking-related events (connection, disconnection, new clients) is done by connecting to MultiplayerAPI's signals.

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Method Descriptions
-------------------

.. _class_MultiplayerAPI_method_create_default_interface:

.. rst-class:: classref-method

:ref:`MultiplayerAPI<class_MultiplayerAPI>` **create_default_interface**\ (\ ) |static| :ref:`🔗<class_MultiplayerAPI_method_create_default_interface>`

Returns a new instance of the default MultiplayerAPI.

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_method_get_default_interface:

.. rst-class:: classref-method

:ref:`StringName<class_StringName>` **get_default_interface**\ (\ ) |static| :ref:`🔗<class_MultiplayerAPI_method_get_default_interface>`

Returns the default MultiplayerAPI implementation class name. This is usually ``"SceneMultiplayer"`` when :ref:`SceneMultiplayer<class_SceneMultiplayer>` is available. See :ref:`set_default_interface()<class_MultiplayerAPI_method_set_default_interface>`.

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_method_get_peers:

.. rst-class:: classref-method

:ref:`PackedInt32Array<class_PackedInt32Array>` **get_peers**\ (\ ) :ref:`🔗<class_MultiplayerAPI_method_get_peers>`

Returns the peer IDs of all connected peers of this MultiplayerAPI's :ref:`multiplayer_peer<class_MultiplayerAPI_property_multiplayer_peer>`.

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_method_get_remote_sender_id:

.. rst-class:: classref-method

:ref:`int<class_int>` **get_remote_sender_id**\ (\ ) :ref:`🔗<class_MultiplayerAPI_method_get_remote_sender_id>`

Returns the sender's peer ID for the RPC currently being executed.

\ **Note:** This method returns ``0`` when called outside of an RPC. As such, the original peer ID may be lost when code execution is delayed (such as with GDScript's ``await`` keyword).

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_method_get_unique_id:

.. rst-class:: classref-method

:ref:`int<class_int>` **get_unique_id**\ (\ ) :ref:`🔗<class_MultiplayerAPI_method_get_unique_id>`

Returns the unique peer ID of this MultiplayerAPI's :ref:`multiplayer_peer<class_MultiplayerAPI_property_multiplayer_peer>`.

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_method_has_multiplayer_peer:

.. rst-class:: classref-method

:ref:`bool<class_bool>` **has_multiplayer_peer**\ (\ ) :ref:`🔗<class_MultiplayerAPI_method_has_multiplayer_peer>`

Returns ``true`` if there is a :ref:`multiplayer_peer<class_MultiplayerAPI_property_multiplayer_peer>` set.

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_method_is_server:

.. rst-class:: classref-method

:ref:`bool<class_bool>` **is_server**\ (\ ) :ref:`🔗<class_MultiplayerAPI_method_is_server>`

Returns ``true`` if this MultiplayerAPI's :ref:`multiplayer_peer<class_MultiplayerAPI_property_multiplayer_peer>` is valid and in server mode (listening for connections).

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_method_object_configuration_add:

.. rst-class:: classref-method

:ref:`Error<enum_@GlobalScope_Error>` **object_configuration_add**\ (\ object\: :ref:`Object<class_Object>`, configuration\: :ref:`Variant<class_Variant>`\ ) :ref:`🔗<class_MultiplayerAPI_method_object_configuration_add>`

Notifies the MultiplayerAPI of a new ``configuration`` for the given ``object``. This method is used internally by :ref:`SceneTree<class_SceneTree>` to configure the root path for this MultiplayerAPI (passing ``null`` and a valid :ref:`NodePath<class_NodePath>` as ``configuration``). This method can be further used by MultiplayerAPI implementations to provide additional features, refer to specific implementation (e.g. :ref:`SceneMultiplayer<class_SceneMultiplayer>`) for details on how they use it.

\ **Note:** This method is mostly relevant when extending or overriding the MultiplayerAPI behavior via :ref:`MultiplayerAPIExtension<class_MultiplayerAPIExtension>`.

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_method_object_configuration_remove:

.. rst-class:: classref-method

:ref:`Error<enum_@GlobalScope_Error>` **object_configuration_remove**\ (\ object\: :ref:`Object<class_Object>`, configuration\: :ref:`Variant<class_Variant>`\ ) :ref:`🔗<class_MultiplayerAPI_method_object_configuration_remove>`

Notifies the MultiplayerAPI to remove a ``configuration`` for the given ``object``. This method is used internally by :ref:`SceneTree<class_SceneTree>` to configure the root path for this MultiplayerAPI (passing ``null`` and an empty :ref:`NodePath<class_NodePath>` as ``configuration``). This method can be further used by MultiplayerAPI implementations to provide additional features, refer to specific implementation (e.g. :ref:`SceneMultiplayer<class_SceneMultiplayer>`) for details on how they use it.

\ **Note:** This method is mostly relevant when extending or overriding the MultiplayerAPI behavior via :ref:`MultiplayerAPIExtension<class_MultiplayerAPIExtension>`.

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_method_poll:

.. rst-class:: classref-method

:ref:`Error<enum_@GlobalScope_Error>` **poll**\ (\ ) :ref:`🔗<class_MultiplayerAPI_method_poll>`

Method used for polling the MultiplayerAPI. You only need to worry about this if you set :ref:`SceneTree.multiplayer_poll<class_SceneTree_property_multiplayer_poll>` to ``false``. By default, :ref:`SceneTree<class_SceneTree>` will poll its MultiplayerAPI(s) for you.

\ **Note:** This method results in RPCs being called, so they will be executed in the same context of this function (e.g. ``_process``, ``physics``, :ref:`Thread<class_Thread>`).

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_method_rpc:

.. rst-class:: classref-method

:ref:`Error<enum_@GlobalScope_Error>` **rpc**\ (\ peer\: :ref:`int<class_int>`, object\: :ref:`Object<class_Object>`, method\: :ref:`StringName<class_StringName>`, arguments\: :ref:`Array<class_Array>` = []\ ) :ref:`🔗<class_MultiplayerAPI_method_rpc>`

Sends an RPC to the target ``peer``. The given ``method`` will be called on the remote ``object`` with the provided ``arguments``. The RPC may also be called locally depending on the implementation and RPC configuration. See :ref:`Node.rpc()<class_Node_method_rpc>` and :ref:`Node.rpc_config()<class_Node_method_rpc_config>`.

\ **Note:** Prefer using :ref:`Node.rpc()<class_Node_method_rpc>`, :ref:`Node.rpc_id()<class_Node_method_rpc_id>`, or ``my_method.rpc(peer, arg1, arg2, ...)`` (in GDScript), since they are faster. This method is mostly useful in conjunction with :ref:`MultiplayerAPIExtension<class_MultiplayerAPIExtension>` when extending or replacing the multiplayer capabilities.

.. rst-class:: classref-item-separator

----

.. _class_MultiplayerAPI_method_set_default_interface:

.. rst-class:: classref-method

|void| **set_default_interface**\ (\ interface_name\: :ref:`StringName<class_StringName>`\ ) |static| :ref:`🔗<class_MultiplayerAPI_method_set_default_interface>`

Sets the default MultiplayerAPI implementation class. This method can be used by modules and extensions to configure which implementation will be used by :ref:`SceneTree<class_SceneTree>` when the engine starts.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |required| replace:: :abbr:`required (This method is required to be overridden when extending its base class.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
.. |bitfield| replace:: :abbr:`BitField (This value is an integer composed as a bitmask of the following flags.)`
.. |void| replace:: :abbr:`void (No return value.)`
