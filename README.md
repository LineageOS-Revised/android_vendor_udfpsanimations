# UDFPS animations

Each directory under `overlays/` is a `runtime_resource_overlay` built from source. SystemUI and
ThemePicker find them by the `category.systemui.fingerprint.anim` overlay category and read the
resources straight from the package, so the overlays never need to be enabled.

Each package holds:

- `res/drawable-nodpi/kgd_fingerprint_element_60fps_<n>` — the looping frames drawn over the sensor
- `res/values/udfps_anim.xml` — label, frame count and frame rate
- `res/drawable-xxhdpi/icon` — the picker thumbnail
- `res/raw/anim.mp4` — the picker preview, rendered from the loop frames

To add an animation, copy one of the directories, give it a new package name and module name,
replace the frames and add the module to `udfpsanimations.mk`.

The build files and XML are Apache-2.0. The frame artwork was taken from OxygenOS and is not
covered by that license.
