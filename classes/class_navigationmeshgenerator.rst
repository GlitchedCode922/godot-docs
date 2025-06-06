:github_url: hide

.. DO NOT EDIT THIS FILE!!!
.. Generated automatically from Godot engine sources.
.. Generator: https://github.com/godotengine/godot/tree/master/doc/tools/make_rst.py.
.. XML source: https://github.com/godotengine/godot/tree/master/doc/classes/NavigationMeshGenerator.xml.

.. _class_NavigationMeshGenerator:

NavigationMeshGenerator
=======================

**Deprecated:** This class may be changed or removed in future versions.

**Inherits:** :ref:`Object<class_Object>`

Helper class for creating and clearing navigation meshes.

.. rst-class:: classref-introduction-group

Description
-----------

This class is responsible for creating and clearing 3D navigation meshes used as :ref:`NavigationMesh<class_NavigationMesh>` resources inside :ref:`NavigationRegion3D<class_NavigationRegion3D>`. The **NavigationMeshGenerator** has very limited to no use for 2D as the navigation mesh baking process expects 3D node types and 3D source geometry to parse.

The entire navigation mesh baking is best done in a separate thread as the voxelization, collision tests and mesh optimization steps involved are very slow and performance-intensive operations.

Navigation mesh baking happens in multiple steps and the result depends on 3D source geometry and properties of the :ref:`NavigationMesh<class_NavigationMesh>` resource. In the first step, starting from a root node and depending on :ref:`NavigationMesh<class_NavigationMesh>` properties all valid 3D source geometry nodes are collected from the :ref:`SceneTree<class_SceneTree>`. Second, all collected nodes are parsed for their relevant 3D geometry data and a combined 3D mesh is build. Due to the many different types of parsable objects, from normal :ref:`MeshInstance3D<class_MeshInstance3D>`\ s to :ref:`CSGShape3D<class_CSGShape3D>`\ s or various :ref:`CollisionObject3D<class_CollisionObject3D>`\ s, some operations to collect geometry data can trigger :ref:`RenderingServer<class_RenderingServer>` and :ref:`PhysicsServer3D<class_PhysicsServer3D>` synchronizations. Server synchronization can have a negative effect on baking time or framerate as it often involves :ref:`Mutex<class_Mutex>` locking for thread security. Many parsable objects and the continuous synchronization with other threaded Servers can increase the baking time significantly. On the other hand only a few but very large and complex objects will take some time to prepare for the Servers which can noticeably stall the next frame render. As a general rule the total number of parsable objects and their individual size and complexity should be balanced to avoid framerate issues or very long baking times. The combined mesh is then passed to the Recast Navigation Object to test the source geometry for walkable terrain suitable to :ref:`NavigationMesh<class_NavigationMesh>` agent properties by creating a voxel world around the meshes bounding area.

The finalized navigation mesh is then returned and stored inside the :ref:`NavigationMesh<class_NavigationMesh>` for use as a resource inside :ref:`NavigationRegion3D<class_NavigationRegion3D>` nodes.

\ **Note:** Using meshes to not only define walkable surfaces but also obstruct navigation baking does not always work. The navigation baking has no concept of what is a geometry "inside" when dealing with mesh source geometry and this is intentional. Depending on current baking parameters, as soon as the obstructing mesh is large enough to fit a navigation mesh area inside, the baking will generate navigation mesh areas that are inside the obstructing source geometry mesh.

.. rst-class:: classref-introduction-group

Tutorials
---------

- :doc:`Using NavigationMeshes <../tutorials/navigation/navigation_using_navigationmeshes>`

.. rst-class:: classref-reftable-group

Methods
-------

.. table::
   :widths: auto

   +--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | |void| | :ref:`bake<class_NavigationMeshGenerator_method_bake>`\ (\ navigation_mesh\: :ref:`NavigationMesh<class_NavigationMesh>`, root_node\: :ref:`Node<class_Node>`\ )                                                                                                                                                                                                                  |
   +--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | |void| | :ref:`bake_from_source_geometry_data<class_NavigationMeshGenerator_method_bake_from_source_geometry_data>`\ (\ navigation_mesh\: :ref:`NavigationMesh<class_NavigationMesh>`, source_geometry_data\: :ref:`NavigationMeshSourceGeometryData3D<class_NavigationMeshSourceGeometryData3D>`, callback\: :ref:`Callable<class_Callable>` = Callable()\ )                              |
   +--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | |void| | :ref:`clear<class_NavigationMeshGenerator_method_clear>`\ (\ navigation_mesh\: :ref:`NavigationMesh<class_NavigationMesh>`\ )                                                                                                                                                                                                                                                     |
   +--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | |void| | :ref:`parse_source_geometry_data<class_NavigationMeshGenerator_method_parse_source_geometry_data>`\ (\ navigation_mesh\: :ref:`NavigationMesh<class_NavigationMesh>`, source_geometry_data\: :ref:`NavigationMeshSourceGeometryData3D<class_NavigationMeshSourceGeometryData3D>`, root_node\: :ref:`Node<class_Node>`, callback\: :ref:`Callable<class_Callable>` = Callable()\ ) |
   +--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Method Descriptions
-------------------

.. _class_NavigationMeshGenerator_method_bake:

.. rst-class:: classref-method

|void| **bake**\ (\ navigation_mesh\: :ref:`NavigationMesh<class_NavigationMesh>`, root_node\: :ref:`Node<class_Node>`\ ) :ref:`🔗<class_NavigationMeshGenerator_method_bake>`

**Deprecated:** This method is deprecated due to core threading changes. To upgrade existing code, first create a :ref:`NavigationMeshSourceGeometryData3D<class_NavigationMeshSourceGeometryData3D>` resource. Use this resource with :ref:`parse_source_geometry_data()<class_NavigationMeshGenerator_method_parse_source_geometry_data>` to parse the :ref:`SceneTree<class_SceneTree>` for nodes that should contribute to the navigation mesh baking. The :ref:`SceneTree<class_SceneTree>` parsing needs to happen on the main thread. After the parsing is finished use the resource with :ref:`bake_from_source_geometry_data()<class_NavigationMeshGenerator_method_bake_from_source_geometry_data>` to bake a navigation mesh.

Bakes the ``navigation_mesh`` with source geometry collected starting from the ``root_node``.

.. rst-class:: classref-item-separator

----

.. _class_NavigationMeshGenerator_method_bake_from_source_geometry_data:

.. rst-class:: classref-method

|void| **bake_from_source_geometry_data**\ (\ navigation_mesh\: :ref:`NavigationMesh<class_NavigationMesh>`, source_geometry_data\: :ref:`NavigationMeshSourceGeometryData3D<class_NavigationMeshSourceGeometryData3D>`, callback\: :ref:`Callable<class_Callable>` = Callable()\ ) :ref:`🔗<class_NavigationMeshGenerator_method_bake_from_source_geometry_data>`

Bakes the provided ``navigation_mesh`` with the data from the provided ``source_geometry_data``. After the process is finished the optional ``callback`` will be called.

.. rst-class:: classref-item-separator

----

.. _class_NavigationMeshGenerator_method_clear:

.. rst-class:: classref-method

|void| **clear**\ (\ navigation_mesh\: :ref:`NavigationMesh<class_NavigationMesh>`\ ) :ref:`🔗<class_NavigationMeshGenerator_method_clear>`

Removes all polygons and vertices from the provided ``navigation_mesh`` resource.

.. rst-class:: classref-item-separator

----

.. _class_NavigationMeshGenerator_method_parse_source_geometry_data:

.. rst-class:: classref-method

|void| **parse_source_geometry_data**\ (\ navigation_mesh\: :ref:`NavigationMesh<class_NavigationMesh>`, source_geometry_data\: :ref:`NavigationMeshSourceGeometryData3D<class_NavigationMeshSourceGeometryData3D>`, root_node\: :ref:`Node<class_Node>`, callback\: :ref:`Callable<class_Callable>` = Callable()\ ) :ref:`🔗<class_NavigationMeshGenerator_method_parse_source_geometry_data>`

Parses the :ref:`SceneTree<class_SceneTree>` for source geometry according to the properties of ``navigation_mesh``. Updates the provided ``source_geometry_data`` resource with the resulting data. The resource can then be used to bake a navigation mesh with :ref:`bake_from_source_geometry_data()<class_NavigationMeshGenerator_method_bake_from_source_geometry_data>`. After the process is finished the optional ``callback`` will be called.

\ **Note:** This function needs to run on the main thread or with a deferred call as the SceneTree is not thread-safe.

\ **Performance:** While convenient, reading data arrays from :ref:`Mesh<class_Mesh>` resources can affect the frame rate negatively. The data needs to be received from the GPU, stalling the :ref:`RenderingServer<class_RenderingServer>` in the process. For performance prefer the use of e.g. collision shapes or creating the data arrays entirely in code.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |required| replace:: :abbr:`required (This method is required to be overridden when extending its base class.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
.. |bitfield| replace:: :abbr:`BitField (This value is an integer composed as a bitmask of the following flags.)`
.. |void| replace:: :abbr:`void (No return value.)`
