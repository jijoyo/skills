# Capacitor Deploy Ritual

Buy on Agensi: https://agensi.io/skills/capacitor-deploy-ritual · $14.99

You build, you deploy, and the APK installs fine — but nothing changed. The old version is still running. This skill kills that pain.

## What it does

- **Bundle proof** — verifies the built APK actually contains your latest change (checksum + version string check) before installing.
- **Deploy chain** — the full Capacitor Android deploy sequence: build → verify → install → confirm, with a gate that refuses to install an APK that doesn't carry your change.
- **Shim tests** — tested against real shims (no device, no emulator) so it works in CI and on a bare machine.

## Measured

Extracted from the real `deploy-android.sh` used in production. The bundle proof caught 2 cases where the build was stale but the install succeeded silently.

## Honest limits

Requires a working Capacitor + Android SDK setup. The skill provides the ritual, not the SDK. If your build environment is broken, this won't fix it — it will just refuse to deploy a bad APK.
