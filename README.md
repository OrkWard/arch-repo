# Personal Arch Linux Repository

Personal Arch Linux package repository hosted on GitHub Pages.

## Packages Included

| Package | Version | Description |
|---------|---------|-------------|
| 1password | 8.12.2-37 | Password manager |
| 1password-cli | 2.32.1-1 | 1Password CLI tool |
| alttab | 1.7.1-3 | Window switcher for minimal window managers |
| berry | 0.1.13-1 | Healthy, bite-sized window manager |
| google-chrome | 145.0.7632.109-1 | Web browser from Google |
| simplescreenrecorder | 0.4.4-4 | Screen recorder for Linux |

## Usage

Add this repository to your `/etc/pacman.conf`:

```ini
[orkward]
SigLevel = Optional TrustAll
Server = https://orkward.github.io/arch-repo/$arch
```

Then update:

```bash
sudo pacman -Sy
```

## Repository Structure

```
arch-repo/
├── x86_64/           # Package files (.pkg.tar.zst)
│   ├── repo.db       # Package database
│   └── repo.files    # Files database
└── README.md
```

## Updating Packages

1. Build/download new package files to `x86_64/`
2. Run `repo-add` to update the database:
   ```bash
   cd x86_64 && repo-add orkward.db.tar.gz *.pkg.tar.zst
   ```
3. Commit and push to GitHub

## GitHub Pages Setup

This repository is served via GitHub Pages from the `main` branch.
