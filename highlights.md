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

- [Support specifying plugins in SDF files without overriding default
  plugins](https://github.com/gazebosim/gz-sim/pull/2497) and [gz-gui#631](https://github.com/gazebosim/gz-gui/pull/631)

  - In prior Gazebo versions, if a user specified a server plugin at the
    world level, it would override all default plugins. This required
    users to have in-depth knowledge and specify every plugin necessary
    for a simulation to run correctly. Omitting critical plugins would
    lead to unexpected simulation behavior, causing confusion,
    particularly for new Gazebo users.

  - Gazebo Ionic addresses this issue by loading default plugins even when
    users specify additional plugins. Gazebo Ionic also introduces
    `<gz:policy>` settings to revert this behavior to how it functioned in
    previous Gazebo versions, if desired.  For example, the
    `contact_sensor.sdf` example can now include just the additional Contact
    system:

    ```xml
    <world name="contact_sensor">
      <plugin filename="gz-sim-contact-system" name="gz::sim::systems::Contact"/>
      ...
    </world>

    ```

    whereas previously, the SDF file has all the default plugins:

    ```xml
    <world name="contact_sensor">
      <plugin
        filename="gz-sim-physics-system"
        name="gz::sim::systems::Physics">
      </plugin>
      <plugin
        filename="gz-sim-contact-system"
        name="gz::sim::systems::Contact">
      </plugin>
      <plugin
        filename="gz-sim-user-commands-system"
        name="gz::sim::systems::UserCommands">
      </plugin>
      <plugin
        filename="gz-sim-scene-broadcaster-system"
        name="gz::sim::systems::SceneBroadcaster">
      </plugin>

      ...
    </world>

    ```

<<<<<<< HEAD
- Improvements to gz-transport CLI ergonomics and extra option to ignore local messages.
See [gz-transport#477](https://github.com/gazebosim/gz-transport/pull/477), [gz-transport#486](https://github.com/gazebosim/gz-transport/pull/486), [gz-transport#487](https://github.com/gazebosim/gz-transport/pull/487) and [gz-transport#506](https://github.com/gazebosim/gz-transport/pull/506/).

  - An extra option has been added to the `SubscriberOptions` class allowing the ability to ignore messages when publisher
  and subscriber share the same node. This feature was particularly interesting to avoid loops in the `ros_gz` bridge.
  See more context [here](https://github.com/gazebosim/ros_gz/issues/555).

  - Most of the gz-transport functionality can be exercised via command line with the `gz topic` or `gz service` subcommands.
  We've reduced the amount of typing needed to request certain services from CLI. Here's a summary:
    - Gazebo Ionic allows to request one-way service requests directly from the command line. In prior Gazebo versions, users
    had to specify `--reptype gz.msgs.Empty ` to simulate one-way service requests.
    - The synchronous service requests have now a default timeout, reducing the amount of typing from the CLI.
    - Gazebo Ionic allows to request no-input service requests directly from the command line. In prior Gazebo versions, users
    had to specify `--reqtype gz.msgs.Empty ` to simulate no-input service requests.


=======
- Gazebo/ROS Vendor Packages

Gazebo libraries and simulator are now available directly from
packages.ros.org via vendor packages. The packages are built in the ROS
buildfarm and as part of their build process, fetch the sources of the
underlying Gazebo library and build it. In addition, the vendor packages
provide CMake shims that make it possible to use CMake targets without
version numbers. See the documentation for full details.

- Improved ros_gz Launch Files

ROS launch files used to start Gazebo, spawn models in simulation, and
start the ros_gz bridge are now much simpler and more idiomatic. New XML
and YAML elements are available to simplify the creation of launch files.
As an example, here's how you can start gzserver and the bridge from an
XML file:

```xml
<launch>
  <gz_server world_sdf_file="$(find-pkg-share my_package)/worlds/my_world.sdf" />
  <ros_gz_bridge config_file="$(find-pkg-share my_package)/config/bridge_config.yaml" />
</launch>
```

- Improved ros_gz_bridge performance

A new parameter use_composition is also available all the new  launch
files to leverage the ability to launch composable nodes. This feature
allows us to run Gazebo, the ros_gz_bridge, and other potential ROS
composable nodes within the same process. This improves performance by
avoiding message serialization and network transport between Gazebo and
ROS.


- Gazebo Transport Improvements:

  - The command line tool used for making service requests has been
    improved such that many of the arguments are no longer needed.

>>>>>>> d25478428f4db76bd92ebfc7f99e2ead09161c15
## Bug Fixes

## Breaking Changes

## Documentation

- [Improved Gazebo Documentation Website](https://github.com/gazebosim/docs/pull/441)
  - The main documentation [website](https://gazebosim.org/docs) has been
    migrated to a statically generated site built with
    [Sphinx](https://sphinx-doc.org/). This adds a number of features and solves
    a number of problems with the previous website, namely:
    - Documentation authors can easily preview their changes by downloading the
      generated website instead of having to set up a local development
      environment
    - The website is updated automatically instead of being manually triggered
      after each PR.
    - Search functionality is now available
    - Improved layout and UX on mobile devices
    - Dark and light modes
    - Improved SEO as the content is now more easily accessible to search
      engines.
    - Use of Sphinx as a common documentation tool for both Gazebo and ROS.
