# PMC-Eight ASCOM Driver — Compiled Release (WiFi fix)

Drop-in compiled **ASCOM telescope driver** for the Explore Scientific PMC-Eight.

**This build includes the WiFi connectivity fix** — the driver now holds a single
**persistent/enduring TCP connection** (opened once at Connect, reused for every
command, closed at Disconnect) instead of the old scheme that opened and closed a
new socket for *every* command and made WiFi unreliable.

## Install

Copy `ASCOM.ES_PMC8.Telescope.dll` into your ASCOM telescope driver directory,
overwriting the existing file:

```
C:\Program Files (x86)\Common Files\ASCOM\Telescope\
```

Requires the ASCOM Platform to be installed. If ASCOM doesn't pick up the new build,
re-register it (admin Command Prompt):

```
"C:\Windows\Microsoft.NET\Framework\v4.0.30319\RegAsm.exe" /codebase "C:\Program Files (x86)\Common Files\ASCOM\Telescope\ASCOM.ES_PMC8.Telescope.dll"
```

## Notes

- Built from the `wifi-fix` branch of the ES PMC-Eight ASCOM driver source.
- This repository holds **only the latest compiled DLL** — it is overwritten with
  each new build, not versioned in depth.
