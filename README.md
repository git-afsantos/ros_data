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

  - `launch_data` contains aggregated data for each launch file. Package dependencies were calculated, and data aggregated from those packages.

  - `global_data` contains global results, aggregated from all analysed packages.

## Collected Data

The intent of our study was to understand how ROS software is developed and used. To do so, we gathered usage statistics on a number of features. With this data, it is possible to identify common patterns, and, knowing those patterns, it is possible to revise existing tutorials and coding standards, or develop new ones. These data are also useful for someone who intends to build code analysis tools, as is our case.

### Publisher Data

These statistics regard the usage of ROS publishers. They were extracted from C++ source files, and can be found in [`publisher_pkg`](./package_data/publisher_pkg.csv), [`publisher_launch`](./launch_data/publisher_launch.csv) and [`publisher`](./global_data/publisher.csv).

  - **Advertise Calls:** the total number of calls to `ros::NodeHandle::advertise`.
  - **Literal Topics:** the total number of topic names in the form of string literals.
  - **Reference Topics:** the total number of topic names in the form of variable reads.
  - **Function Call Topics:** the total number of topic names in the form of function calls.
  - **Operator Topics:** the total number of topic names in the form of unary/binary operators.
  - **Param Topics:** the total number of topic names that may come from the ROS parameter server.
  - **Global Topics:** the total number of Literal Topics that use global names.
  - **Repeating Topics:** the total number of repeating Literal Topic names within `advertise` calls.
  - **Latching Publishers:** the total number of `advertise` calls that use `latch = true`.
  - **Use of SubscriberStatus:** the total number of `advertise` calls that set callbacks for subscriber status.
  - **Literal Queue Sizes:** the total number of queue sizes in the form of number literals.
  - **Reference Queue Sizes:** the total number of queue sizes in the form of variable reads.
  - **Function Call Queue Sizes:** the total number of queue sizes in the form of function calls.
  - **Operator Queue Sizes:** the total number of queue sizes in the form of unary/binary operators.
  - **Param Queue Sizes:** the total number of queue sizes that may come from the ROS parameter server.
  - **Infinite Queues:** the total number of Literal Queue Sizes that are `0`.
  - **Median Queue Size:** the average literal queue size.
  - **Min. Queue Size:** the minimum literal queue size.
  - **Max. Queue Size:** the maximum literal queue size.
  - **Median Control Nesting:** the average control flow nesting level of an `advertise` call, within the function in which it occurs.
  - **Min. Control Nesting:** the minimum control flow nesting level of an `advertise` call, within the function in which it occurs.
  - **Max. Control Nesting:** the maximum control flow nesting level of an `advertise` call, within the function in which it occurs.
  - **Publish Calls:** the total number of calls to `ros::Publisher::publish`.
  - **Median Pub Control Nesting:** the average control flow nesting level of a `publish` call, within the function in which it occurs.
  - **Min. Pub Control Nesting:** the minimum control flow nesting level of a `publish` call, within the function in which it occurs.
  - **Max. Pub Control Nesting:** the maximum control flow nesting level of a `publish` call, within the function in which it occurs.
  - **Custom Msgs:** the total number of `advertise` calls that use a custom message type (not in `std_msgs` or `common_msgs`).

### Subscriber Data

These statistics regard the usage of ROS subscribers. They were extracted from C++ source files, and can be found in [`subscriber_pkg`](./package_data/subscriber_pkg.csv), [`subscriber_launch`](./launch_data/subscriber_launch.csv) and [`subscriber`](./global_data/subscriber.csv).

  - **Subscribe Calls:** the total number of calls to `ros::NodeHandle::subscribe`.
  - **Literal Topics:** the total number of topic names in the form of string literals.
  - **Reference Topics:** the total number of topic names in the form of variable reads.
  - **Function Call Topics:** the total number of topic names in the form of function calls.
  - **Operator Topics:** the total number of topic names in the form of unary/binary operators.
  - **Param Topics:** the total number of topic names that may come from the ROS parameter server.
  - **Global Topics:** the total number of Literal Topics that use global names.
  - **Repeating Topics:** the total number of repeating Literal Topic names within `subscribe` calls.
  - **Use of TransportHints:** the total number of `subscribe` calls that define an explicit transport layer.
  - **Function Callbacks:** the total number of callbacks in the form of a regular function.
  - **Method Callbacks:** the total number of callbacks in the form of a class member function.
  - **Boost Function Callbacks:** the total number of callbacks in the form of a Boost function.
  - **Literal Queue Sizes:** the total number of queue sizes in the form of number literals.
  - **Reference Queue Sizes:** the total number of queue sizes in the form of variable reads.
  - **Function Call Queue Sizes:** the total number of queue sizes in the form of function calls.
  - **Operator Queue Sizes:** the total number of queue sizes in the form of unary/binary operators.
  - **Param Queue Sizes:** the total number of queue sizes that may come from the ROS parameter server.
  - **Infinite Queues:** the total number of Literal Queue Sizes that are `0`.
  - **Median Queue Size:** the average literal queue size.
  - **Min. Queue Size:** the minimum literal queue size.
  - **Max. Queue Size:** the maximum literal queue size.
  - **Median Control Nesting:** the average control flow nesting level of a `subscribe` call, within the function in which it occurs.
  - **Min. Control Nesting:** the minimum control flow nesting level of a `subscribe` call, within the function in which it occurs.
  - **Max. Control Nesting:** the maximum control flow nesting level of a `subscribe` call, within the function in which it occurs.
  - **Custom Msgs:** the total number of `subscribe` calls that use a custom message type (not in `std_msgs` or `common_msgs`).

### Service Data

These statistics regard the usage of ROS services. They were extracted from C++ source files, and can be found in [`service_pkg`](./package_data/service_pkg.csv), [`service_launch`](./launch_data/service_launch.csv) and [`service`](./global_data/service.csv).

  - **Total Services:** the total number of calls to `ros::NodeHandle::advertiseService` and `ros::NodeHandle::serviceClient`.
  - **Literal Services:** the total number of service names in the form of string literals.
  - **Reference Services:** the total number of service names in the form of variable reads.
  - **Function Call Services:** the total number of service names in the form of function calls.
  - **Operator Services:** the total number of service names in the form of unary/binary operators.
  - **Param Services:** the total number of service names that may come from the ROS parameter server.
  - **Global Services:** the total number of Literal Services that use global names.
  - **Service Servers:** the total number of calls to `ros::NodeHandle::advertiseService`.
  - **Repeating Servers:** the total number of repeating Literal Service names within `advertiseService` calls.
  - **Function Callbacks:** the total number of callbacks in the form of a regular function.
  - **Method Callbacks:** the total number of callbacks in the form of a class member function.
  - **Boost Function Callbacks:** the total number of callbacks in the form of a Boost function.
  - **Median Control Nesting:** the average control flow nesting level of an `advertiseService` call, within the function in which it occurs.
  - **Min. Control Nesting:** the minimum control flow nesting level of an `advertiseService` call, within the function in which it occurs.
  - **Max. Control Nesting:** the maximum control flow nesting level of an `advertiseService` call, within the function in which it occurs.
  - **Service Clients:** the total number of calls to `ros::NodeHandle::serviceClient`.
  - **Repeating Clients:** the total number of repeating Literal Service names within `serviceClient` calls.
  - **Median Client Control Nesting:** the average control flow nesting level of a `serviceClient` call, within the function in which it occurs.
  - **Min. Client Control Nesting:** the minimum control flow nesting level of a `serviceClient` call, within the function in which it occurs.
  - **Max. Client Control Nesting:** the maximum control flow nesting level of a `serviceClient` call, within the function in which it occurs.

### Spinner Data

These statistics regard the usage of ROS spinners (`ros::Rate`, `ros::Duration`, etc.). They were extracted from C++ source files, and can be found in [`spin_pkg`](./package_data/spin_pkg.csv) and [`spin`](./global_data/spin.csv).

  - **Spinner:** the type of spinner (`ros::Rate`, `ros::Duration`, etc.).
  - **Total:** the total number of occurrences for a type of spinner.
  - **Literal:** the total number of time units in the form of a number literal.
  - **Reference:** the total number of time units in the form of variable reads.
  - **Function Call:** the total number of time units in the form of function calls.
  - **Operator:** the total number of time units in the form of unary/binary operators.
  - **Parameter:** the total number of time units that may come from the ROS parameter server.
  - **Median Value:** the average literal time unit value.
  - **Min. Value:** the minimum literal time unit value.
  - **Max. Value:** the maximum literal time unit value.

### Parameter Data

These statistics regard the usage of ROS parameters. They were extracted from C++ source files, and can be found in [`param_pkg`](./package_data/param_pkg.csv), [`param_launch`](./launch_data/param_launch.csv) and [`param`](./global_data/param.csv).

  - **Total Read Parameters:** the total number of calls to `ros::NodeHandle::param`, `ros::NodeHandle::getParam` and `ros::NodeHandle::getParamCached`.
  - **Literal Parameters:** the total number of parameter names in the form of string literals.
  - **Global Parameters:** the total number of Literal Parameters that use global names.
  - **Uses Default Value:** the total number of Read Parameters that provide default values.
  - **Total Modified Parameters:** the total number of calls to `ros::NodeHandle::setParam`.

Additionally, there are statistics regarding the use of ROS parameter types. They can be found in [`param_type`](./global_data/param_type.csv).

### Launch Data

These statistics regard the use of various ROS launch features. They were extracted from Launch files, and can be found in [`launch_stats`](./launch_data/launch_stats.csv).

  - **Arg:** the total number of `arg` tags.
  - **Arg Value:** the total number of `arg` tags with a `value`.
  - **Param:** the total number of `param` tags.
  - **ROSParam:** the total number of `rosparam` tags.
  - **Nodes:** the total number of `node` tags.
  - **Unique Nodes:** the number of unique nodes (excludes nodelets).
  - **Nodelets:** the total number of nodelets in `node` tags.
  - **Conditional Nodes:** the total number of `node` tags that are affected by an unresolved value (`if`, `$(arg)`, etc.).
  - **Disabled Nodes:** the total number of `node` tags that are excluded by an `if` or an `unless`.
  - **Required Nodes:** the total number of `node` tags with `required`.
  - **Respawn Nodes:** the total number of `node` tags with `respawn`.
  - **Remote Nodes:** the total number of `node` tags with `machine`.
  - **Node Args:** the total number of `node` tags with command-line arguments passed to the node.
  - **Machines:** the total number of `machine` tags.
  - **Tests:** the total number of `test` tags.
  - **Packages:** the total number of package names referenced throughout the launch file.
  - **Conditional Packages:** the total number of package dependencies that are present within conditional tags.
  - **Remaps:** the total number of `remap` tags.
  - **Conditionals:** the total number of `if` and `unless` attributes.
  - **Includes:** the total number of `include` tags.
  - **Repeated Includes:** the total number of repeating `include`s within a single launch file.
  - **Unknown Includes:** the total number of `include`s that could not be analysed.
  - **Include Args:** the total number of `arg` tags passed to an `include`.
  - **Env. Sets:** the total number of (now deprecated) `env` tags.
  - **Unknown References:** the total number of references to unknown values (`arg`, environment variable, package).
  - **Unknown Arg:** the total number of unresolved `$(arg)`.
  - **Unknown Env:** the total number of unresolved `$(env)`.
  - **File Params:** the total number of `param` and `rosparam` that use a data file.
  - **Cmd Params:** the total number of `param` whose values come from command-line commands.
  - **Env Reads:** the total number of `$(env)`.

### Feature Data

These statistics regard the presence (`1`) or absence (`0`) of certain features within an aggregation scope (package, launch, global). They can be found in [`features`](./global_data/features.csv), [`features_launch`](./launch_data/features_launch.csv) and [`features_pkg`](./package_data/features_pkg.csv).

  - **Literal Publisher-Subscriber:** whether there is an occurrence of `advertise` or `subscribe` with a literal topic name.
  - **Other Publisher-Subscriber:** whether there is an occurrence of `advertise` or `subscribe` with a non-literal topic name.
  - **Nested Publisher-Subscriber:** whether there is an occurrence of `advertise` or `subscribe` with a control flow nesting above zero.
  - **Literal Service:** whether there is an occurrence of `advertiseService` or `serviceClient` with a literal service name.
  - **Other Service:** whether there is an occurrence of `advertiseService` or `serviceClient` with a non-literal service name.
  - **Nested Service:** whether there is an occurrence of `advertiseService` or `serviceClient` with a control flow nesting above zero.
  - **Spinners:** whether there is an occurrence of a spinner.
  - **Custom Messages:** whether custom message or service types are used.
  - **Params:** whether there are readings or changes to the ROS parameter server (`getParam`, `setParam`, etc.).
  - **File Params:** whether there are parameters defined from data files.
  - **Cmd Params:** whether there are parameters defined from command-line commands.
  - **Nodelets:** whether nodelets are used.
  - **Remaps:** whether remappings are used.
  - **Non-const Args:** whether there are `arg` tags in launch files without a `value`.
  - **Env Vars:** whether environment variables are used in launch files.
  - **Includes:** whether launch files include other launch files.
  - **Basic Profile:** the amount of packages that have *Other Publisher-Subscriber*, *Nested Publisher-Subscriber*, *Other Service* and *Nested Service* set to zero.
  - **Variable Profile:** the amount of packages that have *Nested Publisher-Subscriber* and *Nested Service* set to zero.
  - **Nested Profile:** the amount of packages that have *Other Publisher-Subscriber* and *Other Service* set to zero.

### Other Data

These statistics are largely experimental and may not reveal much insight. Namely, there is a relation between [Message Types and Queue Sizes](./global_data/message.csv), or the amount of [functions that each function calls](./global_data/other.csv).
