# Valve PC Checking Tool

Windows forensic scanner (Ocean-style). **Standalone project** — separate from Myst (public/private DLL).

## Run from source

```powershell
cd "D:\Valve Pc Checking Tool"
python -m pip install -r requirements.txt
python valve.py
```

Run as **Administrator** for full scan coverage (MFT, USN journal, hive checks).

## Build EXE

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File "D:\Valve Pc Checking Tool\build.ps1"
```

Output: `D:\Valve Pc Checking Tool\dist\ValveScan.exe`

Right-click the EXE → **Run as administrator** for full kernel/recovery scans.

## Scan coverage (kernel / recovery)

- **MFT Recovery** — inactive (deleted) FILE records + `$STANDARD_INFORMATION` timestamp anomalies
- **USN Journal** — delete/rename events, USN gaps, mass-delete patterns, missing journal
- **Hive Integrity** — Amcache/SYSTEM hive `.LOG1`/`.LOG2` activity, recent hive writes
- **Trace Prevention** — cleared event logs, empty prefetch, USN journal deleted

## Keys

`https://raw.githubusercontent.com/JustValkz/valve-keysystem/refs/heads/main/keys`
