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
- [bazel: build and test subprocess functionality](https://github.com/gazebosim/gz-utils/pull/123)
- [bazel:Add license checking support](https://github.com/gazebosim/gz-utils/pull/108)
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

- [Support visualizing mesh collisions with convex decomposition](https://github.com/gazebosim/gz-sim/pull/2352)
- [Support mesh optimization when using AttachMeshShapeFeature](https://github.com/gazebosim/gz-sim/pull/2417)
- [Add a flexible mechanism to combine user and default plugins](https://github.com/gazebosim/gz-sim/pull/2497)

## gazebosim/sdformat:

- [Add mesh optimization attribute to `<mesh>`](https://github.com/gazebosim/sdformat/pull/1382), [sdformat#1403](https://github.com/gazebosim/sdformat/pull/1403)

## gazebosim/gz-cmake:

- [Use visibility hidden by default](https://github.com/gazebosim/gz-cmake/pull/392)
- [Require cmake version 3.22.1](https://github.com/gazebosim/gz-cmake/pull/396)
- [Deprecate BUILD_DOCS: generate always the doc target but exclude from default make](https://github.com/gazebosim/gz-cmake/pull/434)
- [Deprecate GzPython.cmake in favor of find_package(Python3)](https://github.com/gazebosim/gz-cmake/pull/431)
