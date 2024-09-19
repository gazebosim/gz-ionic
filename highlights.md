# Gazebo Ionic Highlights

## New Features

- [Add new console logging functionality based on `spdlog`](https://github.com/gazebosim/gz-common/pull/615).
  Also see [gz-utils#134](https://github.com/gazebosim/gz-utils/pull/134)

  - Console logging has been reimplemented using `spdlog`. While the existing
    macros such as `gzerr`, `gzwarn`, and `gzmsg` continue to work as before,
    you can now get access to the raw `spdlog` logger, which provides greater
    control and flexibility. A new macro, `gztrace` is also provided, which can
    be useful in debugging or data collection scenarios. With `spdlog`, you also
    get the ability to use format strings. Here's a quick example:

    ```c++
    auto logger = gz::common::Console::Root().RawLoggerPtr();
    logger->trace("π to 5th decimal = {:.5f}\n", M_PI);
    ```

- Improvements to the bullet-featherstone physics plugin

  - Many new features and bugfixes were made to the bullet-featherstone plugin
    in gz-physics, which include support for nested models,
    off-diagonal inertia, enforcing joint velocity and effort limits,
    configuring solver iterations, and more. There are also features for
    performance improvements and physics stability such as auto-deactivation,
    static object collision optimization, and use of convex hull shapes for
    convex decomposed meshes.

- [Support for mesh optimization](https://github.com/gazebosim/gz-sim/pull/2417),
[gzsim#2352](https://github.com/gazebosim/gz-sim/pull/2352),
[gz-common#585](https://github.com/gazebosim/gz-common/pull/585),
[sdformat#1382](https://github.com/gazebosim/gz-common/pull/585), and
[gz-physics#606](https://github.com/gazebosim/gz-physics/pull/606)

  - Added support for mesh optimization on the collision mesh. Users can now
    specify whether or not to perform mesh optimization on a
    collision mesh in SDF (requires SDF spec version >= 1.11). Two optimization
    methods are currently supported: `convex_decomposition` and `convex_hull`.
    Gazebo uses the open source
    [V-HACD](https://github.com/kmammou/v-hacd) library to perform
    convex decomposition to split the mesh into multiple submeshes.
    Example SDF usage:


    ```xml
    <collision>
      <mesh optimization="convex_decomposition">
        <convex_decomposition>
          <max_convex_hulls>16</max_convex_hulls>
          <voxel_resolution>400000</voxel_resolution>
        </convex_decomposition>
        <uri>/path/to/mesh.dae</uri>
      </mesh>
    </collision>
    ```

## Bug Fixes

## Breaking Changes

## Documentation
