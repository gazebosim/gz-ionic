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
