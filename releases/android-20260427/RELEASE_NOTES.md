Hotfix assets refreshed on 2026-04-27 from commit 76e37aa7.

Includes:
- fix for Android startup failure caused by missing geoip-only-cn-private.dat
- fallback to bundled geoip.dat when the extra geo asset is absent
- quieter VLESS import logs for plain VLESS links
- Xray-core coverage test for VLESS + XHTTP + MLKEM startup

Artifacts: signed F-Droid release APKs for universal and arm64-v8a.
