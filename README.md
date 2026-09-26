# morpho-povray

Morpho package that writes POV-Ray scene files from graphics and optionally renders them.

The module depends on the core `constants`, `graphics`, `color`, and `fonts` modules. `render` runs the `povray` executable, which must be on the path.

## Installation

You can install the package with morphopm in the Terminal app:

    morphopm install povray

Load it in Morpho with:

    import povray

Help is available from the Morpho prompt with `? povray`.

## Usage

`POVRaytracer` serializes a graphic to POV-Ray SDL. `write` saves a `.pov` file. `render` writes the file, runs POV-Ray, and opens the PNG.

    import povray

    var pov = POVRaytracer(graphic)
    pov.write("out.pov")
    pov.render("out.pov")

Pass a `Camera` to set the view. `Camera` accepts `antialias`, `width`, `height`, `viewangle`, `viewpoint`, `look_at`, and `sky`.

    var camera = Camera(look_at=Matrix([0, 0, 0]))
    var pov = POVRaytracer(graphic, camera=camera)

`render` accepts `quiet`, `display`, `shadowless`, and `transparent`.

## Examples

Scripts in `examples` render sample scenes. They use `plot`, and some use `morphoview`, `meshtools`, or `implicitmesh`.

    morpho6 examples/text.morpho

## Tests

From the `test` directory:

    python test.py

The repository root must appear in `~/.morphopackages` so `import povray` loads this package rather than a bundled copy.
