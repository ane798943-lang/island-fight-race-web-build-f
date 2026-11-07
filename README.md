# Island Fight Race - slim Web template kit
1. Upload this folder to a GitHub repo (keep `.github/`).
2. Actions -> "Build slim Godot Web template" -> Run workflow (set the Emscripten version your old template used).
3. Download `web_nothreads_release.zip`. If the run fails, download `build-logs` and read `build.log` (search for "error").
4. Godot -> Export -> Web -> Custom Template -> Release = that zip. Thread support OFF, Extensions OFF.
5. Apply `patches/0001-remove-crypto-dependency.patch` to the game (or copy `patches/patched_files/*`), or run the workflow with keep_mbedtls = true.
6. `python3 -I tools/audit_project.py <project_folder>` fails if a removed class is still used.
