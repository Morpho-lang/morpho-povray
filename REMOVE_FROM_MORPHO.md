# Remove bundled povray from Morpho-lang/morpho

Do this after morpho-povray is the copy users import. Paths are relative to the morpho repository root.

CMake installs `modules/*.morpho` and `help/*.md` by glob, so deleting the files is enough. No `CMakeLists.txt` edit.

## Delete

- `modules/povray.morpho`
- `help/povray.md`
- `test/modules/povray.morpho`
- `examples/povray/testCamera.morpho`
- `examples/povray/testpovray.morpho`
- `examples/povray/testpovraytext.morpho`
- `examples/povray/testpovraytransmitfilter.morpho`
- `examples/povray/text.morpho`

## Edit

- `help/index.rst` — remove the `povray` entry from the Modules toctree.

## Leave

- `releasenotes/version-0.5.4.md` and `releasenotes/version-0.6.2.md` record povray changes. Keep them.
- Examples that import povray stay in core. Once the bundled module is gone, those examples need this package on the module path:
  - `examples/dla/dla.morpho`
  - `examples/elementtypes/qtensorCG2.morpho`
  - `examples/implicitmesh/threesurface.morpho`
  - `examples/qtensor/qtensor.morpho`
  - `examples/tactoid/tactoid.morpho`
  - `examples/tactoid/tactoid2dmesh.morpho`
- `README.md` and `.github/workflows/examples.yml` install the POV-Ray executable. `render` still calls that program.
- `help/graphics.md` and `help/plot.md` document `filter` and `transmit`, which this module reads. Keep them.
