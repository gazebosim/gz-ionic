# Gazebo Ionic Release Notes

## gazebosim/docs:

- [Add tutorial on how to a migrate ROS 2 package that uses Gazebo Classic](https://github.com/gazebosim/docs/pull/425)
- [Add additional docs on sensors and ROS 2 usage](https://github.com/gazebosim/docs/pull/433)
- [Add documentation for Gazebo vendor packages](https://github.com/gazebosim/docs/pull/443)
- [Installing Gazebo11 side by side with new Gazebo Tutorial](https://github.com/gazebosim/docs/pull/438)
- [Extend ROS integration documentation](https://github.com/gazebosim/docs/pull/448)
- [Build documentation using Sphinx](https://github.com/gazebosim/docs/pull/441)
- [Add instructions to run ros_buildfarm jobs](https://github.com/gazebosim/docs/pull/477)

## gazebosim/gz-utils:

- [Add Logging utility class based on `spdlog`](https://github.com/gazebosim/gz-utils/pull/134).
  Also see [gz-utils#145](https://github.com/gazebosim/gz-utils/pull/145),
  [gz-utils#144](https://github.com/gazebosim/gz-utils/pull/144),
  [gz-utils#142](https://github.com/gazebosim/gz-utils/pull/142),
  [gz-utils#141](https://github.com/gazebosim/gz-utils/pull/141),
  [gz-utils#139](https://github.com/gazebosim/gz-utils/pull/139)
- [Add new functions for manipulating the environment](https://github.com/gazebosim/gz-utils/pull/114)
- [Make the single argument constructor of `Subprocess` inherit the env](https://github.com/gazebosim/gz-utils/pull/113)
- [bazel: Build and test subprocess functionality](https://github.com/gazebosim/gz-utils/pull/123)
- [bazel: Add license checking support](https://github.com/gazebosim/gz-utils/pull/108)
- [Add package.xml](https://github.com/gazebosim/gz-utils/pull/125)
- [Require cmake version 3.22.1](https://github.com/gazebosim/gz-utils/pull/132)

## gazebosim/gz-physics:

- Improve bullet-featherstone physics plugin:
  - [Add support for nested model](https://github.com/gazebosim/gz-physics/pull/574)
  - [Add support for off-diagnoal inertial](https://github.com/gazebosim/gz-physics/pull/574)
  - [Optimize static object collisions](https://github.com/gazebosim/gz-physics/pull/611)
  - [Improve mesh collision stability](https://github.com/gazebosim/gz-physics/pull/600)
  - [Enable auto deactivation](https://github.com/gazebosim/gz-physics/pull/630)
  - [Add support for mesh convex decomposition](https://github.com/gazebosim/gz-physics/pull/606)
  - [Enforce joint velocity and effort limits for velocity control commands](https://github.com/gazebosim/gz-physics/pull/658)
  - [Publish JointFeedback forces.](https://github.com/gazebosim/gz-physics/pull/628)
  - [Support empty links](https://github.com/gazebosim/gz-physics/pull/665)
- [Support setting max contacts in dartsim's ODE collision detector](https://github.com/gazebosim/gz-physics/pull/582)
- [Support setting solver iterations](https://github.com/gazebosim/gz-physics/pull/609)
- [Add package.xml](https://github.com/gazebosim/gz-physics/pull/608)
- [Enforce fixed constraints recursively when setting pose on freegroups](https://github.com/gazebosim/gz-physics/pull/646)
- [Ray intersection simulation feature](https://github.com/gazebosim/gz-physics/pull/641)
- [Add Cone as a primitive parametric shape.](https://github.com/gazebosim/gz-physics/pull/638)
- [Add no gravity link support](https://github.com/gazebosim/gz-physics/pull/633)

## gazebosim/gz-common:

- [Extend AssimpLoader to parse material transmission factor](https://github.com/gazebosim/gz-common/pull/577)
- [Adds new function in MeshManager for performing convex decomposition](https://github.com/gazebosim/gz-common/pull/585)
- [Add package.xml](https://github.com/gazebosim/gz-common/pull/587)
- [DEM: Add support for GDAL vsicurl, vsizip support and avoid segfaults with huge VRT datasets](https://github.com/gazebosim/gz-common/pull/597)
- [Use self-pipe trick to implement signal handlers](https://github.com/gazebosim/gz-common/pull/618)
- [Replace GTS with CDT](https://github.com/gazebosim/gz-common/pull/617)
- [Reimplement console logging using `spdlog`](https://github.com/gazebosim/gz-common/pull/615)

## gazebosim/gz-fuel-tools:

- [CLI for creating config.yaml](https://github.com/gazebosim/gz-fuel-tools/pull/413)
- [Add package.xml](https://github.com/gazebosim/gz-fuel-tools/pull/408)

## gazebosim/gz-gui:

- [Add a flexible mechanism to combine user and default plugins](https://github.com/gazebosim/gz-gui/pull/631)
- [Added motion duration to the 'move to pose' service of the camera tracking plugin.](https://github.com/gazebosim/gz-gui/pull/594)
- [Add package.xml](https://github.com/gazebosim/gz-gui/pull/613)
- [Add optional binary relocatability](https://github.com/gazebosim/gz-gui/pull/580)
- [Enhanced tracking camera and user visualization experience](https://github.com/gazebosim/gz-gui/pull/619)
- [Add Cone as a primitive parametric shape.](https://github.com/gazebosim/gz-gui/pull/620)
- [Added dark mode for drawer and menu buttons](https://github.com/gazebosim/gz-gui/pull/626)
- [Expose shadow texture size for directional lighting in SDF](https://github.com/gazebosim/gz-gui/pull/633)
- [Add a flexible mechanism to combine user and default plugins](https://github.com/gazebosim/gz-gui/pull/631)

## gazebosim/gz-launch:

- [Add optional binary relocatability](https://github.com/gazebosim/gz-launch/pull/218)
- [Add package.xml](https://github.com/gazebosim/gz-launch/pull/249)

## gazebosim/gz-math:

- [Added MecanumDriveOdometry Python wrapper](https://github.com/gazebosim/gz-math/pull/549)
- [Expose non-const reference to edges in Graph.hh](https://github.com/gazebosim/gz-math/pull/580)
- [Add package.xml](https://github.com/gazebosim/gz-math/pull/581)
- [Add Cone as a primitive parametric shape.](https://github.com/gazebosim/gz-math/pull/593)
- [Add CoordinateVector3 and use it in SphericalCoordinates](https://github.com/gazebosim/gz-math/pull/616)
- [buffer_protocol for vectors and matrices in python bindings](https://github.com/gazebosim/gz-math/pull/524)

## gazebosim/gz-msgs:

- [Added motion duration to gui_camera.proto](https://github.com/gazebosim/gz-msgs/pull/408)
- [Update material_color to use Entity.](https://github.com/gazebosim/gz-msgs/pull/415)
- [Add proto message for MaterialColor.](https://github.com/gazebosim/gz-msgs/pull/414)
- [Support standalone executable in gz-msgs11](https://github.com/gazebosim/gz-msgs/pull/357)
- [Allow topic and service to construct messages from description files](https://github.com/gazebosim/gz-msgs/pull/428)
- [Add package.xml](https://github.com/gazebosim/gz-msgs/pull/432)
- [CameraTrack message for advanced tracking and following.](https://github.com/gazebosim/gz-msgs/pull/440)
- [Add Cone as a primitive parametric shape.](https://github.com/gazebosim/gz-msgs/pull/441)

## gazebosim/gz-plugin:

- [Add package.xml](https://github.com/gazebosim/gz-plugin/pull/139)

## gazebosim/gz-rendering:

- [Add projection matrix set/get functions to Ogre Depth camera](https://github.com/gazebosim/gz-rendering/pull/928)
- [Extend ogre 1.x custom shaders support](https://github.com/gazebosim/gz-rendering/pull/908)
- [Support skybox in wide angle cam view](https://github.com/gazebosim/gz-rendering/pull/901)
- [Add LookAt function to GizmoVisual class](https://github.com/gazebosim/gz-rendering/pull/882)
- Performance Improvements:
  - [Improve Ogre2GpuRays performance](https://github.com/gazebosim/gz-rendering/pull/955)
  - [Skip particle passes in Ogre2GpuRays if there are no particles in the scene](https://github.com/gazebosim/gz-rendering/pull/973)
  - [Skip particle passes in Ogre2DepthCamera if there are no particles in the scene](https://github.com/gazebosim/gz-rendering/pull/971)
  - [Use single cubemap camera in lidar](https://github.com/gazebosim/gz-rendering/pull/1013)
  - [Optimization: remove extra copy of data buffer in Ogre2GpuRays and Ogre2DepthCamera](https://github.com/gazebosim/gz-rendering/pull/1022)
- [Ogre2RenderEngine: on Windows if useCurrentGLContext is specified, set the externalWindowHandle ogre-next option](https://github.com/gazebosim/gz-rendering/pull/992)
- [Add package.xml](https://github.com/gazebosim/gz-rendering/pull/981)
- [ogre2: Set custom projection matrix for other types of cameras](https://github.com/gazebosim/gz-rendering/pull/1002)
- [Add Cone as a primitive parametric shape.](https://github.com/gazebosim/gz-rendering/pull/1001)
- [Add gamma correction to simple_demo_qml example](https://github.com/gazebosim/gz-rendering/pull/1019)
- [Install Roboto fonts to ogre plugin](https://github.com/gazebosim/gz-rendering/pull/1035)
- [Expose shadow texture size for directional lighting in SDF](https://github.com/gazebosim/gz-rendering/pull/1034)

## gazebosim/gz-sensors:

- [Set lens intrinsics in Depth and Rgbd camera sensors](https://github.com/gazebosim/gz-sensors/pull/390)
- Performance Improvements:
  - [DepthCamera and RGBDCamera - optimize RGB point cloud connection](https://github.com/gazebosim/gz-sensors/pull/413)
  - [Publish lidar scan only if there are lidar scan connections](https://github.com/gazebosim/gz-sensors/pull/447)
- [Add package.xml](https://github.com/gazebosim/gz-sensors/pull/422)
- [Add API to check if sensor is in trigger mode](https://github.com/gazebosim/gz-sensors/pull/441)
- [ForceTorqueSensor: add API for newest measurement](https://github.com/gazebosim/gz-sensors/pull/449)
- [Use `//sensor/frame_id` SDFormat element](https://github.com/gazebosim/gz-sensors/pull/444)

## gazebosim/gz-sim:

- [Standardize Doxygen parameter formatting for systems](https://github.com/gazebosim/gz-sim/pull/2183), [gazebosim/gz-sim#2212](https://github.com/gazebosim/gz-sim/pull/2212)
- [Support specifying the name of light associated with lens flares](https://github.com/gazebosim/gz-sim/pull/2172)
- [Allow removal of model that has joint_position_controller plugin.](https://github.com/gazebosim/gz-sim/pull/2252)
- [wind addition to advanced_lift_drag plugin](https://github.com/gazebosim/gz-sim/pull/2226)
- [Implements a method to get the link inertia](https://github.com/gazebosim/gz-sim/pull/2218)
- [Porting Advanced Lift Drag Plugin to Gazebo](https://github.com/gazebosim/gz-sim/pull/2185)
- [Maritime tutorials 💧](https://github.com/gazebosim/gz-sim/pull/2260), [gazebosim/gz-sim#2259](https://github.com/gazebosim/gz-sim/pull/2259),
 [#2258](https://github.com/gazebosim/gz-sim/pull/2258), [#2257](https://github.com/gazebosim/gz-sim/pull/2257)
- [Light entity match SDF boolean for UserCommands.](https://github.com/gazebosim/gz-sim/pull/2295)
- [Change an entities visual material color by topic.](https://github.com/gazebosim/gz-sim/pull/2286)
- [Support for Gazebo materials](https://github.com/gazebosim/gz-sim/pull/2269)
- [Add tutorial for using components in systems](https://github.com/gazebosim/gz-sim/pull/2207)
- [Add entity and sdf parameters to Server's AddSystem interface](https://github.com/gazebosim/gz-sim/pull/2324)
- [Add package.xml](https://github.com/gazebosim/gz-sim/pull/2337)
- [Optimize rendering sensor pose updates](https://github.com/gazebosim/gz-sim/pull/2425)
- [Support mesh optimization when using AttachMeshShapeFeature](https://github.com/gazebosim/gz-sim/pull/2417)
- [Update sensors with pending trigger immediately in Sensors system](https://github.com/gazebosim/gz-sim/pull/2408)
- [Add Track and  Follow options in gui EntityContextMenu](https://github.com/gazebosim/gz-sim/pull/2402)
- [Parse and set bullet solver iterations](https://github.com/gazebosim/gz-sim/pull/2351)
- [Lighter Than Air Dynamics Systems](https://github.com/gazebosim/gz-sim/pull/2241)
- [Consolidate entity creation.](https://github.com/gazebosim/gz-sim/pull/2452)
- [Add GravityEnabled boolean component](https://github.com/gazebosim/gz-sim/pull/2451)
- [Parse voxel resolution SDF param when decomposing meshes](https://github.com/gazebosim/gz-sim/pull/2445)
- [Add Cone as a primitive parametric shape.](https://github.com/gazebosim/gz-sim/pull/2404)
- [Add support for no gravity link](https://github.com/gazebosim/gz-sim/pull/2398)
- [Permit to run gz sim -g on Windows](https://github.com/gazebosim/gz-sim/pull/2382)
- [Support visualizing mesh collisions with convex decomposition](https://github.com/gazebosim/gz-sim/pull/2352)
- [Set max contacts for collision pairs](https://github.com/gazebosim/gz-sim/pull/2270)
- [Add tutorial for using the Pose component](https://github.com/gazebosim/gz-sim/pull/2219)
- [Improve signal handling](https://github.com/gazebosim/gz-sim/pull/2501)
- [Specify System::PreUpdate, Update execution order](https://github.com/gazebosim/gz-sim/pull/2487)
- [Magnetometer: correct field calculation](https://github.com/gazebosim/gz-sim/pull/2460)
- [Add support for spacecraft thrusters](https://github.com/gazebosim/gz-sim/pull/2431)
- [Remove systems if their parent entity is removed](https://github.com/gazebosim/gz-sim/pull/2232)
- [Force Qt to use xcb plugin on Wayland](https://github.com/gazebosim/gz-sim/pull/2526)
- [Add System interface to set default priority](https://github.com/gazebosim/gz-sim/pull/2500)
- [Add a flexible mechanism to combine user and default plugins](https://github.com/gazebosim/gz-sim/pull/2497)
- [ForceTorque system: write WrenchMeasured to ECM](https://github.com/gazebosim/gz-sim/pull/2494)
- [Physics: set link velocity from *VelocityReset components](https://github.com/gazebosim/gz-sim/pull/2489)
- [Set link velocity from `set_model_state` plugin](https://github.com/gazebosim/gz-sim/pull/2440)
- [Detachable joint: support for nested models of the same name](https://github.com/gazebosim/gz-sim/pull/1097)
- [Enabling Global Illumination (GI VCT) for sensors in SDF](https://github.com/gazebosim/gz-sim/pull/2550)

## gazebosim/gz-tools:

- [Support building with gz-cmake3 or gz-cmake4](https://github.com/gazebosim/gz-tools/pull/128)
- [Add package.xml](https://github.com/gazebosim/gz-tools/pull/136)

## gazebosim/sdformat:

- [Add mesh optimization attribute to `<mesh>`](https://github.com/gazebosim/sdformat/pull/1382), [sdformat#1403](https://github.com/gazebosim/sdformat/pull/1403)

## gazebosim/gz-transport:

- [Adds the python bindings tutorial](https://github.com/gazebosim/gz-transport/pull/450)
- [Support for bazel on garden](https://github.com/gazebosim/gz-transport/pull/399)
- [No input service request from the command line](https://github.com/gazebosim/gz-transport/pull/487)
- [Use a default timeout when requesting a service from CLI.](https://github.com/gazebosim/gz-transport/pull/486)
- [Oneway service request from the command line](https://github.com/gazebosim/gz-transport/pull/477)
- [Add package.xml](https://github.com/gazebosim/gz-transport/pull/485)
- [Add option to ignore local messages](https://github.com/gazebosim/gz-transport/pull/506)
- [Allow programmatic configuration of unicast relays.](https://github.com/gazebosim/gz-transport/pull/498)
- [Add frequency to topic CLI.](https://github.com/gazebosim/gz-transport/pull/503)

## gazebosim/gz-usd:

- [Support Gazebo Harmonic and Ionic](https://github.com/gazebosim/gz-usd/pull/24)

## gazebosim/ros_gz:

- [Add support for Harmonic/Humble pairing](https://github.com/gazebosim/ros_gz/pull/462)
- [Add messages for 2D Bounding Boxes to ros_gz_bridge](https://github.com/gazebosim/ros_gz/pull/458)
- [Filter ROS arguments before gflags parsing](https://github.com/gazebosim/ros_gz/pull/453)
- [Added support for using ROS 2 parameters to spawn entities in Gazebo using ros_gz_sim::create](https://github.com/gazebosim/ros_gz/pull/475)
- [Add conversion for geometry_msgs/msg/TwistStamped <-> gz.msgs.Twist](https://github.com/gazebosim/ros_gz/pull/468)
- [Add option to change material color from ROS.](https://github.com/gazebosim/ros_gz/pull/486)
- [Correctly export ros_gz_bridge for downstream targets](https://github.com/gazebosim/ros_gz/pull/503)
- [Add conversion for Detection3D and Detection3DArray](https://github.com/gazebosim/ros_gz/pull/523)
- [Use resource_retriever in the bridge](https://github.com/gazebosim/ros_gz/pull/515)
- [Add ROS namespaces to GZ topics](https://github.com/gazebosim/ros_gz/pull/512)
- [Support `<gazebo_ros>` in `package.xml` exports](https://github.com/gazebosim/ros_gz/pull/492)
- [Launch file for running gzserver](https://github.com/gazebosim/ros_gz/pull/532)
- [Use gz_vendor packages](https://github.com/gazebosim/ros_gz/pull/531)
- [Launch file for running gz_bridge](https://github.com/gazebosim/ros_gz/pull/530)
- [Launch gz_spawn_model from xml](https://github.com/gazebosim/ros_gz/pull/551)
- [Launch ros_gz_bridge from xml](https://github.com/gazebosim/ros_gz/pull/550)
- [Launch gzserver from xml](https://github.com/gazebosim/ros_gz/pull/548)
- [Launch file for combined spawn_model + bridge](https://github.com/gazebosim/ros_gz/pull/534)
- [Launch file for combined gzserver + bridge](https://github.com/gazebosim/ros_gz/pull/533)
- [Launch gzserver and the bridge as composable nodes](https://github.com/gazebosim/ros_gz/pull/528)
- [Add a ROS node that runs Gazebo](https://github.com/gazebosim/ros_gz/pull/500)
- [Add support for gz.msgs.EntityWrench](https://github.com/gazebosim/ros_gz/pull/573)
- [Use `ignoreLocalMessages` in the bridge](https://github.com/gazebosim/ros_gz/pull/559)
- [Add `override_timestamps_with_wall_time` parameter](https://github.com/gazebosim/ros_gz/pull/562)
- [Wait for create service to be available.](https://github.com/gazebosim/ros_gz/pull/588)
- [Add deadline and liveliness QoSPolicyKinds to qos_overriding_options](https://github.com/gazebosim/ros_gz/pull/609)

## gazebosim/ros_gz_project_template:

- [Support for Harmonic](https://github.com/gazebosim/ros_gz_project_template/pull/35)

## gazebosim/gz-cmake:

- [Use visibility hidden by default](https://github.com/gazebosim/gz-cmake/pull/392)
- [Require cmake version 3.22.1](https://github.com/gazebosim/gz-cmake/pull/396)
- [Deprecate BUILD_DOCS: generate always the doc target but exclude from default make](https://github.com/gazebosim/gz-cmake/pull/434)
- [Deprecate GzPython.cmake in favor of find_package(Python3)](https://github.com/gazebosim/gz-cmake/pull/431)
