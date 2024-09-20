# Gazebo Ionic Release Notes

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

- [Adds new function in MeshManager for performing convex decomposition](https://github.com/gazebosim/gz-common/pull/585)


## gazebosim/gz-sim:

- [Support visualizing mesh collisions with convex decomposition](https://github.com/gazebosim/gz-sim/pull/2352)
- [Support mesh optimization when using AttachMeshShapeFeature](https://github.com/gazebosim/gz-sim/pull/2417)


## gazebosim/sdformat:

- [Add mesh optimization attribute to `<mesh>`](https://github.com/gazebosim/sdformat/pull/1382), [sdformat#1403](https://github.com/gazebosim/sdformat/pull/1403)
