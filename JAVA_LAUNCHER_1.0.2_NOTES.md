# Java Launcher Unofficial 1.0.2 — source preview

Based on the user-supplied Amethyst-iOS-main source snapshot.

## Applied
- iOS bundle identifier: `com.dualboot-gaming.mcjavalauncher`
- Display name: `Java Launcher Unofficial`
- Version: `1.0.2`
- Updated Makefile IPA output naming and generated signing identifier template.
- Retained the original URL scheme `amethyst` for callback compatibility (must be tested).

## No-JIT investigation
The native launch code checks `isJITEnabled()` in `Natives/LauncherMenuViewController.m`, and runtime startup checks JIT in `Natives/main.m`. Merely skipping those checks does NOT provide a functional no-JIT JVM. No-JIT has NOT been implemented. The runtime must be validated for interpreted execution and iOS memory-execution restrictions before enabling a user-facing toggle.

## Important
- This is a source ZIP, **not a built or signed IPA**.
- Build and device testing require an Apple-capable toolchain, dependencies and signing.
- This archive is from the `main` branch snapshot, not verified as the exact 1.2.0 release tag.
- The original Amethyst copyright and GPL license are retained.
