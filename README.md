# Caelestia Wallpaper Macro (AHK-style for Wayland)

A lightweight Bash script designed for **Caelestia Shell** (https://github.com/caelestia-dots/shell) on **Hyprland (Arch Linux)**. Since Caelestia lacks a native keybind to trigger the wallpaper selection menu directly, this macro automates the process by simulating keystrokes using `wtype`.

## Features
- **Instant Access**: Open the wallpaper menu with a single keyboard shortcut (`Alt + B`).
- **Reliable Execution**: Uses a specific keycode workaround (`KP_Enter`) to ensure focus acknowledgment in the Quickshell environment.


## 📦 Dependencies
- `wtype`: For emulating keyboard input on Wayland.
- `caelestia-shell`: The target environment.

## 🚀 Installation

1. **Create script** in your config directory:
   ```bash
   nano ~/.config/hypr/wal_macro.sh
2. **Paste** the following code:
   ```bash
   #!/bin/bash
   sleep 0.05
   caelestia shell drawers toggle launcher
   sleep 0.15
   wtype ">wal"
   sleep 0.4
   wtype -k KP_Enter
3. **Make the script executable**:
   ```bash
   chmod +x ~/.config/hypr/wal_macro.sh
4. **Add a shortcut** to your config:
   ```bash
   cd /home/user/.config/hypr/hyprland/
   nano keybinds.conf
   bind = Alt, B, exec, ~/.config/hypr/wal_macro.sh   
   
  
