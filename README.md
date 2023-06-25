# ScadLib

ScadLib is an OpenSCAD library that contains a collection of useful functions and modules.

## Usage

To use ScadLib in your project, follow these steps:

1. Clone the ScadLib repository using the command:
   ```powershell
   git clone https://github.com/enginestein/ScadLib.git
   ```

2. Include the `scadlib.scad` file in your project by adding the following line:
   ```openscad
   include <scadlib.scad>
   ```

For more information on how to use ScadLib, refer to the [examples](https://github.com/enginestein/ScadLib/blob/main/examples.scad) and the documentation provided below.

## Documentation

### Constants

* Millimeters per inch
* Pi
* Metric nuts/screw dimensions
* Component dimensions

### Helper Functions/Modules

* `circumference(r)`: Calculates the circumference of a circle.
* `clamp(value, v1, v2)`: Clamps a value between two other values.
* `contains(needle, haystack)`: Checks if a vector contains a given value.
* `error(msg)`: Logs an error message to the console.
* `for_unity3d(scale = 0.001)`: Scales and orients models for use in Unity3D.
* `get_fragments_from_r(r, fa = $fa, fn = $fn, fs = $fs)`: Derives `$fn` from radius, as per the documentation.
* `helix_angle(r, pitch)`: Determines the angle of a helix at a given pitch and radius.
* `index_of(needle, haystack)`: Finds the index of a given value in a vector.
* `join(values, sep = ", ")`: Creates a string from vector elements.
* `linear_extrude_chamfer(h, chamfer, round = false, center = false, convexity = 1, $fn = $fn)`: Applies `linear_extrude` and `minkowski` operations to a shape, resulting in a chamfered edge.
* `linear_rotate_extrude(h = 1, a = 360, center = true, convexity = 1, $fn = 0)`: Mimics `rotate_extrude` while applying a linear transform. Note: This is a workaround using `hull` operations.
* `lookup_vector(i, table)`: Same as `lookup`, but also works with vector values.
* `offset_point(p, delta = 0)`: Investigate `delta * 2` - should it be `*1`?
* `oscillate(min = -1, max = 1, t = $t)`: Sweeps a value between the given minimum and maximum for animation purposes.
* `poly_coords(n, r = 1, mid = true)`: Creates a vector of points with faces at the given radius instead of points.
* `print_registration_bounds(bounds = [180, 180], h = 0.2, t = 0.5)`: Used to ensure position when slicing separate models on one plate (e.g., two-material prints).
* `print(msg)`: Logs a message to the console.
* `reflect(x = true, y = true, z = false)`: Mirrors children across axes.
* `rotate_point_x(p, a)`: Rotates a given point around the x-axis.
* `rotate_point_y(p, a)`: Rotates a given point around the y-axis.
* `rotate_point_z(p, a)`: Rotates a given point around the z-axis.
*

 `rotate_point(p, a)`: Rotates a given point around all axes.
* `rotate_points(p, a)`: Rotates given points around all axes.
* `show_half(r = [0, 0, 0], t = [0, 0, 0], d = 1000, 2d = false)`: Cuts children in half for internal investigation or simple bisections.
* `sum(v)`: Sums the numeric values of a vector.
* `translate_point(p, a)`: Translates a given point.
* `translate_points(p, a)`: Translates given points.
* `transpose(pos = [])`: Positions children reflected without mirroring across all axes.
* `warn(msg)`: Logs a warning message to the console.

### 2-Dimensional Functions

* `arc(a, r1, r2, $fn = $fn)`: Draws an arc with a rainbow-like shape.
* `bezier(points, width = 0.5, connect = true, n = -1)`: Draws a Bezier curve using three (cubic) or four (quadratic) given points, with an optional width parameter.
* `circle_true(r, center = true, $fa = $fa, $fn = $fn, $fs = $fs)`: Draws a circle with edges at the radius instead of points.
* `grid(coords = [100, 100], x = 10, y = 10, walls = 1, edges = false, center = false)`: Draws a grid of lines.
* `l(dim = [10, 10], t = 1, t1, t2)`: Draws an "L" shape, commonly used for beams.
* `rounded_gear(r = 10, n = 3, inset = true, s = [1, 1], $fn = $fn)`: Creates a simple lobed gear (e.g., for knob handles).
* `rounded_square(dim, r, center = true)`: Draws a square with rounded corners of a given radius.
* `segment(a, r, $fn = $fn)`: Draws a portion of a circle with a given angle.
* `semicircle(r = 1, $fa = $fa, $fn = $fn, $fs = $fs)`: Draws a semicircle.
* `semicircle_true(r = 1, $fa = $fa, $fn = $fn, $fs = $fs)`: Draws a semicircle with edges at the radius instead of points.
* `smooth(r)`: Applies two consecutive `offset` operations to achieve a simple smoothing effect.
* `smooth_acute(r = 0, dim = [1000, 1000])`: Smoothing that also applies to acute angles.
* `sq(dim, center = true)`: Convenience wrapper for a centered square; handles dimension array lengths greater than 2.
* `star(r, n = 5, inset = 0.5)`: Creates star shapes with a given side inset.
* `t(dim = [10, 10], t = 1, t1, t2)`: Draws a "T" shape, commonly used for beams.
* `u(dim = [10, 10], t = 1, t1, t2)`: Draws a "U" shape, commonly used for beams.

### 3-Dimensional Functions

* `capsule(h = 10, r, r1, r2, center = false)`: Creates a cylinder with semi-spherical ends.
* `cylinder_true(h, r = 0, r1 = 0, r

2 = 0, center = true, $fa = $fa, $fn = $fn, $fs = $fs)`: Creates a cylinder with faces at the radius instead of edges.
* `pie(a = 90, r = 1, h = 1, center = true)`: Extrudes a segment into a pie shape.
* `rounded_cube(dim, r, edges = false, center = true, $fa = $fa, $fn = $fn, $fs = $fs)`: Creates a cube with edges of a given radius.
* `rounded_cylinder(h, r, f, f1, f2, r1, r2, center = true, $fa = $fa, $fn = $fn, $fs = $fs)`: Creates a cylinder with top and bottom edges of given radii.
* `sphere_true(r, $fa = $fa, $fn = $fn, $fs = $fs)`: Creates a sphere with faces at the radius instead of edges.
* `torus(r1, r2, fa = $fa, fn = $fn, fs = $fs)`: Creates a torus (donut shape).
* `torus_true(r1, r2, $fa = $fa, $fn = $fn, $fs = $fs)`: Creates a torus with an extruded circle having edges at the radius instead of points.

## Hardware Sections

### Electrical

* Buzzer
* Chip
* Connectors
* Displays
* Jacks
* LEDs
* Pin headers
* Potentiometers
* Stepper motors
* Switches (DIP, slide, tact)
* Voltage regulators
* Wire

### Engineering

* Beams (L/T/U)
* Bearings
* Gears
* Nuts
* Screws
* Threads
* Truss
* Washers

### Mechanical

* Centrifugal fan (blower)
* Duct/pipe flange

### RC

* 5.8GHz antenna
* Batteries
* Cameras
* DVRs
* ESCs
* Flight controllers
* GPS
* Motors
* Propellers
* Receivers
* Servos
* Video receivers
* Video transmitters
