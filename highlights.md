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

## Bug Fixes

## Breaking Changes

## Documentation
