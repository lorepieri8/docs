# Feature comparison

A list of features present in [Gazebo-classic](https://github.com/osrf/gazebo/)
version 11 and the status of their migration to
[Ignition Edifice](https://ignitionrobotics.org/).

All the issues below are labeled with
[close the gap](https://github.com/search?q=org%3Aignitionrobotics+label%3A%22close+the+gap%22&type=Issues)
on GitHub.

## Sensors

Sensor | Gazebo-classic | Ignition Gazebo
-- | -- | --
Air pressure | ✕  | ✓
Altimeter | ✓ | ✓
Bounding Box camera | ✕ | ✕  (available from Fortress)
Camera | ✓ | ✓
Contact sensor | ✓ | ✓
Depth camera | ✓ | ✓
Force-torque | ✓ | ✕  (available from Fortress)
GPS / NavSat | ✓ |  ✕  (available from Fortress)
GPU Ray | ✓ | ✓ Renamed to GPU Lidar
IMU | ✓ | ✓
Logical camera | ✓ | ✓
Magnetometer | ✓ | ✓
Multi-camera | ✓ | ✕  Use individual cameras with same update rate
Ray | ✓ | [Issue](https://github.com/ignitionrobotics/ign-sensors/issues/26)
RFID sensor and tag | ✓ | [Issue](https://github.com/ignitionrobotics/ign-sensors/issues/27)
RGBD camera | ✕ | ✓
Segmentation camera | ✕ | ✕  (available from Fortress)
Sonar | ✓ | [Issue](https://github.com/ignitionrobotics/ign-sensors/issues/19)
Thermal camera | ✕  | ✓
Wide-angle camera | ✓ | [Issue](https://github.com/ignitionrobotics/ign-sensors/issues/24)
Wireless | ✓ | [Issue](https://github.com/ignitionrobotics/ign-sensors/issues/28)

Sensor features | Gazebo-classic | Ignition Gazebo
-- | -- | --
Custom update rate | ✓ | ✓
Gaussian noise | ✓ | ✓
Custom sensors | ✓ |  ✕  (available from Fortress)
Laser retroreflection | ✓ | ✓
Camera distortion | ✓ | [Issue](https://github.com/ignitionrobotics/ign-sensors/issues/107)
Performance metrics | ✓ |  ✓

## SDF Features

Feature | Gazebo-classic | Ignition Gazebo
-- | -- | --
SDF frame semantics |✓| ✓
SDF parametrization | ✕ | [✓](http://sdformat.org/tutorials?tut=param_passing_proposal)
Load models from local files | ✓ | [✓](https://ignitionrobotics.org/api/gazebo/5.3/resources.html)
Closed kinematic chains | ✓  | [Issue](https://github.com/ignitionrobotics/ign-physics/issues/25)
Nested models | ✓ | ✓
Populations | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/240)
Actors | ✓ | ✓
Markers | ✓ | ✓
Heightmaps | ✓ | ✓ (Ogre 1 from Edifice, Ogre 2 from Fortress)
DEM (Digital Elevation Models) | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/235)
Polylines | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/186)
World plugins | ✓ | ✓ Now called System plugin
Model plugins | ✓ | ✓ Now called System plugin
Sensor plugins | ✓ | ✓ Now called System plugin
Visual plugins | ✓ | ✕  (available from Fortress)
GUI plugins | ✓ | ✓ Ignition GUI plugins and Gazebo GUI systems
System plugins | ✓ | ✓ Through Ignition Launch

## Plugins

### Model plugins

Plugin | Gazebo-classic | Ignition Gazebo
-- | -- | --
ActorPlugin | ✓ | ✕ See [FollowActor](https://github.com/ignitionrobotics/ign-gazebo/blob/main/src/systems/follow_actor/FollowActor.hh) for a demo of Actor APIs
ActuatorPlugin | ✓ |
ArduCopterPlugin | ✓ |
AttachLightPlugin | ✓ | ✕ Does not apply, use SDF
Breadcrumbs | ✕ | ✓
BuoyancyPlugin | ✓ | [✓](https://github.com/ignitionrobotics/ign-gazebo/blob/ign-gazebo5/examples/worlds/buoyancy.sdf)
CartDemoPlugin | ✓ | ✕
CessnaPlugin | ✓ |
DiffDrivePlugin | ✓ | ✓
ElevatorPlugin | ✓ |
FlashLightPlugin | ✓ |
FollowerPlugin | ✓ |
GimbalSmall2dPlugin | ✓ |
GravityCompensationPlugin | ✓ |
HarnessPlugin | ✓ |
HydraDemoPlugin | ✓ |
InitialVelocityPlugin | ✓ | ✓ (use VelocityControl or JointController)
JointControlPlugin | ✓ (force / pos / vel, from SDF) | ✓ (vel, from msg)
JointStatePublisher | ✕ | ✓
JointTrajectoryPlugin | ✓ |
KeysToCmdVelPlugin | ✓ | Use `ignition::gui::KeyPublisher` with `ignition::gazebo::systems::TriggeredPublisher`
KeysToJointsPlugin | ✓ | Use `ignition::gui::KeyPublisher` with `ignition::gazebo::systems::TriggeredPublisher`
LedPlugin | ✓ |
LiftDragPlugin | ✓ | ✓
LinearBatteryConsumerPlugin | ✓ | ✓
LinearBatteryPlugin | ✓ | ✓
LinkPlot3DPlugin | ✓ | ✓ (renamed to Plot3D)
MudPlugin | ✓ |
MulticopterMotorModel | ✕ | ✓
PlaneDemoPlugin | ✓ |
PosePublisher | ✕ | ✓
RandomVelocityPlugin | ✓ |
RegionEventBoxPlugin | ✓ |
SimpleTrackedVehiclePlugin | ✓ | ✓
SkidSteerDrivePlugin | ✓ | ✓
SphereAtlasDemoPlugin | ✓ | ✕
TouchPlugin | ✓ | ✓
TrackedVehiclePlugin | ✓ | ✓
VariableGearboxPlugin | ✓ |
VehiclePlugin | ✓ |
WheelSlipPlugin | ✓ | ✓
WheelTrackedVehiclePlugin | ✓ | ✓
KineticEnergyMonitor | ✕ | ✓
Buoyancy engine | ✓ | ✕  (available from Fortress)

### World plugins

Plugin | Gazebo-classic | Ignition Gazebo
-- | -- | --
ArrangePlugin | ✓ |
ContainPlugin | ✓ | Partial port, [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/162)
HydraPlugin | ✓ |
JoyPlugin | ✓ | ✓ Migrated as an Ignition Launch plugin
MisalignmentPlugin | ✓ |
RubblePlugin | ✓ |
StaticMapPlugin | ✓ |
TransporterPlugin | ✓ |
WindPlugin | ✓ | ✓

### Sensor plugins

Plugin | Gazebo-classic | Ignition Gazebo
-- | -- | --
BreakableJointPlugin | ✓ |
CameraPlugin | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/49)
ContactPlugin | ✓ | ✓
DepthCameraPlugin | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/49)
FiducialCameraPlugin | ✓ |
ForceTorquePlugin | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/49)
GpuRayPlugin | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/49)
ImuSensorPlugin | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/49)
LensFlareSensorPlugin | ✓ |
PressurePlugin | ✓ |
RayPlugin | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/49)
RaySensorNoisePlugin | ✓ | ✕ Use SDF
SonarPlugin | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/49)

### Visual plugins

Plugin | Gazebo-classic | Ignition Gazebo
-- | -- | --
AmbientOcclusionVisualPlugin | ✓ |
BlinkVisualPlugin | ✓ |
HeightmapLODPlugin | ✓ |
ShaderParamVisualPlugin | ✓ | ✕ (available from Fortress)

### GUI plugins

Plugin | Gazebo-classic | Ignition Gazebo
-- | -- | --
CessnaGUIPlugin | ✓ |
KeyboardGUIPlugin | ✓ | `ignition::gui::KeyPublisher`
LookAtDemoPlugin | ✓ |
TimerGUIPlugin | ✓ |

### System plugins

Plugin | Gazebo-classic | Ignition Gazebo
-- | -- | --
ModelPropShop | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/100)
RestUiPlugin | ✓ |
RestWebPlugin | ✓ |
StopWorldPlugin | ✓ |

## GUI

Feature | Gazebo-classic | Ignition Gazebo
-- | -- | --
Play / pause / step | ✓ | ✓
Reset world / models | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/203)
World stats | ✓ | ✓
Topic echo | ✓ | ✓
Image viewer | ✓ | ✓
Translate / rotate | ✓ | ✓
Scale models | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/195)
Insert models from Fuel | Partial support | ✓
Insert models from disk | ✓ | ✓
Insert simple shapes | ✓ | ✓
Insert simple lights | ✓ | ✓
Delete models | ✓ | ✓
World tree | ✓ | ✓
Scene properties | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/246)
Log recording / playback | ✓ | ✓
Plotting | ✓ | ✓
Video recording | ✓ | ✓
Screenshot | ✓ | [✓](https://ignitionrobotics.org/api/gui/3.5/screenshot.html)
View angles | ✓ | ✓
Apply force / torque | ✓ |
Visualize as transparent | ✓ | ✕ (available from Fortress)
Visualize as wireframe | ✓ | ✕ (available from Fortress)
Visualize joints | ✓ |  ✕ (available from Fortress)
Visualize collisions | ✓ | ✓
Visualize inertia | ✓ | ✕ (available from Fortress)
Visualize CoM | ✓ |  ✕ (available from Fortress)
Visualize contacts | ✓ | ✓
Visualize lights | ✓ | ✓
Follow / move to | ✓ | ✓
Copy / paste | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/102)
Building editor | ✓ |
Model editor | ✓ | [Issues](https://github.com/ignitionrobotics/ign-gazebo/issues?q=is%3Aissue+is%3Aopen+label%3Aeditor)
FPS view control | ✓ |
Orthographic projection | ✓ | ✕ (available from Fortress)
Undo / redo | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/104)
Save world | ✓ | ✓
Save GUI configuration | ✓ | ✓
Color scheme and themes | ✕ | ✓
Position, resize and configure widgets | ✕ | ✓
Load GUI plugins from menu | ✕ | ✓
Edit model pose | ✓ | ✓
Edit light properties | ✓ | ✓
Edit physics properties | ✓ | ✓

## Physics

In Ignition Physics, physics engines are integrated as plugins, so any engine
can be integrated without changing the core source code, as it was the case
in Gazebo.

Feature | Gazebo-classic | Ignition Gazebo
-- | -- | --
ODE engine | ✓ | [Issue](https://github.com/ignitionrobotics/ign-physics/issues/63)
Bullet engine | ✓ | ✓
DART engine | ✓ | ✓ Plugin shipped with ign-physics
Simbody engine | ✓ | [Issue](https://github.com/ignitionrobotics/ign-physics/issues/63)
TPE engine | ✕ | ✓
Custom engine plugins | ✕ | ✓
Collide bitmasks | ✓ | ✓
Restitution coefficient | ✓ | ✓
Collision detector | ✓ |  ✓
Solver | ✓ |  ✓

## Rendering

In Ignition Rendering, render engines are integrated as plugins, so any engine
can be integrated without changing the core source code.

Feature | Gazebo-classic | Ignition Gazebo
-- | -- | --
Ogre 1.x engine | ✓ | ✓
Ogre 2.x engine | ✕ | ✓
Optix engine | ✕ | ✓ Partial support
Custom engine plugins | ✕ | [✓](https://ignitionrobotics.org/api/rendering/5.0/renderingplugin.html)
Sky | ✓ | ✓
Fog | ✓ |
Material scripts | ✓ (Ogre 1.x scripts) | Does not apply
Physically Based Rendering (PBR) | ✕ | ✓ (with engines that support it, like Ogre 2)
Normal maps | ✓ | ✓
Environment maps | ✕  | ✓
Lightmaps | ✕  | ✓
Particle effects | ✕  | ✓
Render order | ✕  | ✓

## ROS integration

ROS integration through the
[ros_ign](https://github.com/ignitionrobotics/ros_ign) packages.

Supported versions:

* ROS 1 Noetic (from source)
* ROS 2 Galactic (binaries)

## Platforms

Platform | Gazebo-classic | Ignition Gazebo
-- | -- | --
Ubuntu | ✓ | ✓
OSX | ✓ | Most of the stack works, outstanding issues: [command line](https://github.com/ignitionrobotics/ign-gazebo/issues/25), [render window](https://github.com/ignitionrobotics/ign-gazebo/issues/44)
Windows | ✓ | All libraries compile, low-level libraries function well: [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/168)

## Others

Feature | Gazebo-classic | Ignition Gazebo
-- | -- | --
Nested models | ✓ | ✓
Log / playback | ✓ | ✓
Web client (GzWeb) | ✓ |
COLLADA meshes | ✓ | ✓
OBJ meshes | ✓ | ✓
STL meshes | ✓ | ✓
Code introspection | ✓ | All simulation state is accessible from system plugins or through the `SceneBroadcaster`'s state topic
Distribute simulation across processes | ✕ | (coming up)
Incrementally load levels | ✕ | ✓
Online model database | [gazebo_models repository](https://github.com/osrf/gazebo_models/) | [Ignition Fuel](https://app.ignitionrobotics.org/fuel/models)
Saved simulation states | ✓ | [Issue](https://github.com/ignitionrobotics/ign-gazebo/issues/137)
Sphere, cylinder and box primitives | ✓ | ✓
Ellipsoid and capsule primitives | ✕ | ✓
Hydrodynamics | ✕  | ✓
Ocean currents | ✕  | ✓
Test fixture | ✓ | [✓](https://ignitionrobotics.org/api/gazebo/5.3/test_fixture.html)
Spherical coordinates | ✓ | ✕ (available from Fortress)
