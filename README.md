# camilladsp-debs

Debian packages for [CamillaDSP](https://github.com/HEnquist/camilladsp) and [CamillaGUI](https://github.com/HEnquist/camillagui-backend) targeting armhf (Raspberry Pi and similar).

## Packages

- **camilladsp** — the DSP engine, runs as a systemd service on port 1234
- **camillagui** — web interface, runs on port 5005, depends on camilladsp

## Installation

Download the `.deb` files from [Actions](../../actions) artifacts, then:

```sh
sudo dpkg -i camilladsp_*.deb camillagui_*.deb
```

## Configuration

| File | Purpose |
|------|---------|
| `/etc/camilladsp/config.yml` | CamillaDSP pipeline config |
| `/etc/camillagui/camillagui.yml` | GUI backend config |
| `/var/lib/camilladsp/statefile.yml` | Active config state |
| `/var/lib/camilladsp/configs/` | Config library |
| `/var/lib/camilladsp/coeffs/` | FIR coefficient files |

## Updating versions

Edit the version variables at the top of `.github/workflows/build-debs.yml`:

```yaml
env:
  CAMILLADSP_VER: "3.0.1"
  CAMILLAGUI_VER: "3.0.3"
```
