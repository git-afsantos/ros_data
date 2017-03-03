# ROS Usage Statistics

This is a repository for collected data on ROS software.
Currently, there are metrics and statistics for C++ and Launch files.
Python and other languages, or features, may be supported at some point in the future.

All data found in this repository was collected automatically, using a tool that is still under development.
As such, keep in mind that any reported values may deviate slightly from the actual corresponding values.
This tool will be disclosed as a plugin for [HAROS](https://github.com/git-afsantos/haros), after some minimal polishing.

## Repository Structure

In this repository there are three directories, aggregating data with different levels of granularity.

  - `package_data` contains data on a package by package analysis. Files inside a package were scanned, and the collected data aggregated for that package.

  - `launch_data` contains aggregated data for each launch file. Package dependencies were calculated, and data aggregated for those packages.

  - `global_data` contains global results, aggregated from all analysed packages.

## Collected Data

The intent of our study was to understand how ROS software is developed and used. To do so, we gathered usage statistics on a number of features. With this data, it is possible to identify common usage patterns, and, knowing those patterns, it is possible to revise existing tutorials and coding standards, or develop new ones. These data are also useful for someone who intends to build code analysis tools, as is our case.

### Publisher Data

These statistics regard the usage of ROS publishers. They were extracted from C++ source files, and can be found in [`publisher_pkg`](./package_data/publisher_pkg.csv), [`publisher_launch`](./launch_data/publisher_launch.csv) and [`publisher`](./global_data/publisher.csv).

### Subscriber Data

These statistics regard the usage of ROS subscribers. They were extracted from C++ source files, and can be found in [`subscriber_pkg`](./package_data/subscriber_pkg.csv), [`subscriber_launch`](./launch_data/subscriber_launch.csv) and [`subscriber`](./global_data/subscriber.csv).

### Service Data

These statistics regard the usage of ROS services. They were extracted from C++ source files, and can be found in [`service_pkg`](./package_data/service_pkg.csv), [`service_launch`](./launch_data/service_launch.csv) and [`service`](./global_data/service.csv).

### Spinner Data

These statistics regard the usage of ROS spinners (`Rate`, `Duration`, etc.). They were extracted from C++ source files, and can be found in [`spin_pkg`](./package_data/spin_pkg.csv) and [`spin`](./global_data/spin.csv).

### Parameter Data

These statistics regard the usage of ROS parameters. They were extracted from C++ source files, and can be found in [`param_pkg`](./package_data/param_pkg.csv), [`param_launch`](./launch_data/param_launch.csv) and [`param`](./global_data/param.csv).

Additionally, there are statistics regarding the use of ROS parameter types. They can be found in [`param_type`](./global_data/param_type.csv).

### Launch Data

These statistics regard the use of various ROS launch features. They were extracted from Launch files, and can be found in [`launch_stats`](./launch_data/launch_stats.csv), [`features_launch`](./launch_data/features_launch.csv) and [`launch_pkg_depends`](./launch_data/launch_pkg_depends.csv).
