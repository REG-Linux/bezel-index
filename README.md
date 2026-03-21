# REG-Linux Bezel Index

Pre-computed index files for [The Bezel Project](https://github.com/thebezelproject), used by REG-ES to download per-game bezels.

## Structure

```
tbp_systems.txt                    # System list: name, GitHub URL, path, system bezel
thebezelproject/
  tbp_<system>.txt                 # Per-system index: md5 + bezel filename
  default.png                      # Default fallback bezel
  default.info                     # Default bezel viewport geometry
scripts/
  tbp-md5gen                       # Index generator script
  tbp_systems.txt                  # Source systems list
  resources/default.{png,info}     # Default bezel assets
```

## CDN URLs

Served via jsDelivr CDN:

```
https://cdn.jsdelivr.net/gh/REG-Linux/bezel-index@main/tbp_systems.txt
https://cdn.jsdelivr.net/gh/REG-Linux/bezel-index@main/thebezelproject/tbp_snes.txt
```

## Automated updates

A GitHub Actions workflow runs monthly (1st of each month) to regenerate all index files from The Bezel Project GitHub repos. It can also be triggered manually.

## Index file format

**tbp_systems.txt** (tab/space separated):
```
system_name  github_url  bezels_path  system_bezel_file
snes  https://github.com/thebezelproject/bezelproject-SNES  SNES  Super-Nintendo-Entertainment-System.png
```

**tbp_\<system\>.txt** (space separated):
```
md5_hash  bezel_filename.png
980055960bb22cc4c1a9cc7c992df30f  Inindo - Way of the Ninja (USA).png
```
