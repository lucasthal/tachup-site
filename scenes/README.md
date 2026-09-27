# Scenes

The baked 3D fields TachUp downloads for Pattern work. The app carries the mountain valley; these are the other nine.

- `index.json` lists them: `{ version, baseUrl, scenes: [{ id, name, dir, bytes, manifestSha256, fieldElevationFt }] }`.
  The app reads it at most once a day and keeps a copy compiled in for when it is offline.
- `<scene>/<first 12 hex of the manifest's sha256>/` holds one bake: `manifest.json` and every file it lists, each with
  its byte count and sha256, which the app checks after download. The aircraft the manifests name are not here; they
  ship in the app.
- A new bake is a new folder. Delete an old folder only once `index.json` no longer names it and a day has passed.

Written by `content/art/render/host_scenes.py` in the app repository (after `bake_scene.py` and `verify_bundle.py`).
The art is the project's own and a CC0 kit.
