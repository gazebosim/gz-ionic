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
    collision mesh in SDFormat (requires SDFormat spec version >= 1.11). Two optimization
    methods are currently supported: `convex_decomposition` and `convex_hull`.
    Gazebo uses the open source
    [V-HACD](https://github.com/kmammou/v-hacd) library to perform
    convex decomposition to split the mesh into multiple submeshes.
    Example SDFormat usage:

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

- [Support specifying plugins in SDFormat files without overriding default
  plugins](https://github.com/gazebosim/gz-sim/pull/2497) and [gz-gui#631](https://github.com/gazebosim/gz-gui/pull/631)

  - In prior Gazebo versions, if a user specified a server plugin at the
    world level, it would override all default plugins. This required
    users to have in-depth knowledge and specify every plugin necessary
    for a simulation to run correctly. Omitting critical plugins would
    lead to unexpected simulation behavior, causing confusion,
    particularly for new Gazebo users.

    Gazebo Ionic addresses this issue by loading default plugins even when
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

    whereas previously, the SDFormat file has all the default plugins:

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

- Specify execution order for System `PreUpdate` and `Update` callbacks
  ([gz-sim#2487](https://github.com/gazebosim/gz-sim/pull/2487),
  [gz-sim#2500](https://github.com/gazebosim/gz-sim/pull/2500)).

  - While the `PreUpdate`, `Update`, and `PostUpdate` phases of gz-sim systems
    allow some control over the order in which code is executed, there are
    cases in which more control is desired. For example, the `UserCommands`
    system can create new models during its `PreUpdate` callback in response
    to `EntityFactory` messages (see the
    [entity creation tutorial](https://gazebosim.org/api/sim/9/entity_creation.html)),
    and that callback should happen before any other system callbacks that
    expect to operate on all entities in the scene. Now, the order of execution
    for `PreUpdate` and `Update` callbacks for a System can be specified using
    an integer priority value, with smaller values executing first.
    The default system priority can be specified at compilation time by
    implementing a new `SystemConfigurePriority` interface in that system,
    and the priority can be overridden by specifying an XML parameter in the
    system's SDFormat `<plugin/>` tag.
  - Constant priority values have been defined in
    [gz/sim/System.hh](https://github.com/gazebosim/gz-sim/blob/gz-sim9_9.0.0-pre1/include/gz/sim/System.hh#L106-L129)
    for the `Physics` and `UserCommands` systems to ensure that
    `UserCommands::PreUpdate` and `Physics::Update` execute before other
    system callbacks with default priority.

- Improve determinism of ForceTorque sensor
  ([gz-sensors#449](https://github.com/gazebosim/gz-sensors/pull/449),
  [gz-sim#2487](https://github.com/gazebosim/gz-sim/pull/2487),
  [gz-sim#2494](https://github.com/gazebosim/gz-sim/pull/2494),
  [gz-sim#2500](https://github.com/gazebosim/gz-sim/pull/2500)).

  - The wrenches measured by ForceTorque sensors are now written to the ECM
    in addition to publishing to a gz-transport topic, offering a more
    deterministic data path for sensor data.
  - Writing sensor data to the ECM required moving the sensor update from the
    `PostUpdate` callback, which allows read-only access to the ECM with
    parallel execution, to the `Update` callback, which allows write-access to
    the ECM with sequential execution. It also uses the system execution order
    priority to ensure that the ForceTorque `Update` callback occurs after
    the `Physics` system `Update`.

- Gazebo Transport improvements.
See [gz-transport#477](https://github.com/gazebosim/gz-transport/pull/477), [gz-transport#486](https://github.com/gazebosim/gz-transport/pull/486), [gz-transport#487](https://github.com/gazebosim/gz-transport/pull/487), [gz-transport#503](https://github.com/gazebosim/gz-transport/pull/503), and [gz-transport#506](https://github.com/gazebosim/gz-transport/pull/506).

  - An extra option has been added to the `SubscriberOptions` class allowing the ability to ignore messages when publisher
  and subscriber share the same node. This feature was particularly interesting to avoid loops in the `ros_gz` bridge.
  See more context [here](https://github.com/gazebosim/ros_gz/issues/555).

  - Most of the gz-transport functionality can be exercised via command line with the `gz topic` or `gz service` subcommands.
  We've reduced the amount of typing needed to request certain services from CLI. Here's a summary:
    - Gazebo Ionic allows to request one-way service requests directly from the command line. In prior Gazebo versions, users
    had to specify `--reptype gz.msgs.Empty ` to simulate one-way service requests.
    - The synchronous service requests have now a default timeout, reducing the amount of typing from the CLI.
    - Gazebo Ionic allows to request no-input service requests directly from the command line. In prior Gazebo versions, users had to specify `--reqtype gz.msgs.Empty ` to simulate no-input service requests.
    - Closer `gz topic` behaviour to ROS CLI by adding topic frequency `gz topic -f <topic_name>`.

- Gazebo camera tracking.

  - Control tracking, following and see current tracking status from the gui as well as through gz topics. See [gz-gui#619](https://github.com/gazebosim/gz-gui/pull/619), [gz-msgs#440](https://github.com/gazebosim/gz-msgs/pull/440), and [gz-sim#2402](https://github.com/gazebosim/gz-sim/pull/2402).


- Change materials dynamically.

  - Can now make opaque objects translucent, simulate LEDs or other lighting by setting emissivity when source turned on or off from a `gz-transport` message or over `ros-gz` bridge. See [gz-msgs#414](https://github.com/gazebosim/gz-msgs/pull/414), [gz-msgs#415](https://github.com/gazebosim/gz-msgs/pull/415), [gz-msgs#416](https://github.com/gazebosim/gz-msgs/pull/416), [ros_gz#486](https://github.com/gazebosim/ros_gz/pull/486), and [gz-sim#2286](https://github.com/gazebosim/gz-sim/pull/2286).


- Add new primitive geometry for cones.

  - Create a parametric cone primitive from the gui or in SDFormat. Useful for sensor visualization, nosecones, and much more. See [gz-gui#621](https://github.com/gazebosim/gz-gui/pull/621), [gz-math#594](https://github.com/gazebosim/gz-math/pull/594), [gz-msgs#442](https://github.com/gazebosim/gz-msgs/pull/442), [gz-physics#639](https://github.com/gazebosim/gz-physics/pull/639), [gz-rendering#1003](https://github.com/gazebosim/gz-rendering/pull/1003), [gz-sim#2410](https://github.com/gazebosim/gz-sim/pull/2410), and [sdformat#1418](https://github.com/gazebosim/sdformat/pull/1418).


- Gazebo/ROS Vendor Packages

  - Gazebo libraries and simulator are now available directly from
    packages.ros.org via vendor packages. The packages are built in the
    ROS buildfarm and as part of their build process, fetch the sources of
    the underlying Gazebo library and build it. In addition, the vendor
    packages provide CMake shims that make it possible to use CMake
    targets without version numbers. See the documentation for full
    details.

- Improved ros_gz Launch Files

  - ROS launch files used to start Gazebo, spawn models in simulation, and
    start the ros_gz bridge are now much simpler and more idiomatic. New
    XML and YAML elements are available to simplify the creation of launch
    files. As an example, here's how you can start gzserver and the bridge
    from an XML file:

  ```xml
  <launch>
    <gz_server world_sdf_file="$(find-pkg-share my_package)/worlds/my_world.sdf" />
    <ros_gz_bridge config_file="$(find-pkg-share my_package)/config/bridge_config.yaml" />
  </launch>
  ```

- Improved ros_gz_bridge performance

  - A new parameter use_composition is also available all the new  launch
    files to leverage the ability to launch composable nodes. This feature
    allows us to run Gazebo, the ros_gz_bridge, and other potential ROS
    composable nodes within the same process. This improves performance by
    avoiding message serialization and network transport between Gazebo
    and ROS.


- [New setup-gazebo GitHub Action](https://github.com/marketplace/actions/setup-gazebo-environment)

  - A new GitHub Action to install the different versions of Gazebo is
    available through the GitHub marketplace named `setup-gazebo`. It
    supports Linux, Mac and Windows as target platforms and the use of
    different repositories for Gazebo packages: stable, prerelease or
    nightly. The Linux installation can also be combined with ROS 2 to
    install the `ros_gz_bridge` packages.

  ```yaml
    - name: 'Install Gazebo Ionic from nightlies'
      uses: gazebo-tooling/setup-gazebo@v0.2.0
      with:
        required-gazebo-distributions: 'ionic'
        use-gazebo-prerelease: 'true'
        use-gazebo-nightly: 'true'
  ```

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
