---

# 📘 Artificial-Window-ZOE – Complete Documentation

---

## 🧠 Project Overview

**Artificial-Window-ZOE** is a Windows utility that allows you to **capture any open window** (especially fullscreen games) and **embed it inside a dedicated fullscreen window**, removing borders and enabling seamless overlay support.  
It is designed for users who want to run their games inside a controlled container while allowing other applications (like the ZOE menu) to appear on top.

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| **Window Reparenting** | Moves the target window inside the main application. |
| **Borderless Maximize** | Removes all borders and title bar buttons when maximized. |
| **Fullscreen Container** | The host window always runs in fullscreen mode. |
| **O+P Hotkey** | Press `O+P` together to toggle between Maximized and Windowed mode. |
| **Window List** | Displays all visible windows for easy selection. |
| **Release Function** | Returns the captured window to its original parent and state. |
| **Auto Admin Request** | Automatically requests Administrator privileges. |

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| **Python 3.12** | Core programming language |
| **Tkinter** | Graphical User Interface (GUI) |
| **pywin32 (win32gui, win32con, win32api)** | Windows API interaction for window management |
| **ctypes** | System-level function calls and Admin handling |
| **PyInstaller** | Packaging into a standalone `.exe` file |

---

## 📁 File Structure

```
Artificial-Window-ZOE/
├── artificial_window_zoe.py    ← Main source code
├── Artificial-Window-ZOE.exe   ← Executable file (after build)
├── icon.ico                    ← Optional application icon
└── README.md                   ← Project documentation
```

---

## 🚀 How to Run

### Run Directly (with Python)

```cmd
pip install pywin32
python artificial_window_zoe.py
```

### Build Executable (EXE)

```cmd
pyinstaller --onefile --noconsole --name "Artificial-Window-ZOE" --icon=icon.ico --uac-admin artificial_window_zoe.py
```

> After building, the `.exe` file will be located in the `dist` folder.

---

## 🎮 Keyboard Shortcuts

| Key | Action |
|-----|--------|
| **O + P** (simultaneously) | Toggle between Maximized and Windowed mode for the captured window |
| **Esc** | Exit fullscreen mode (application stays open) |

---

## 🖥️ Step-by-Step Usage

| Step | Action |
|------|--------|
| **1** | Launch the application (opens in fullscreen mode). |
| **2** | From the **Windows** list, select the target window (e.g., TLauncher or a game). |
| **3** | Click the **Catch** button to bring the window inside the container. |
| **4** | Press **O+P** to maximize the window without borders. |
| **5** | Press **O+P** again to return to windowed mode. |
| **6** | Click **Release** to return the window to its original state and parent. |
| **7** | Click **Exit** or close the window to terminate the application. |

---

## 🧪 Tested Scenarios

| Scenario | Result |
|----------|--------|
| Run on desktop | ✅ |
| Capture TLauncher window | ✅ |
| Capture Minecraft (fullscreen) | ✅ |
| Maximize without borders | ✅ |
| Restore to windowed mode | ✅ |
| Release and restore original state | ✅ |
| Close app with captured window | ✅ (auto-release) |

---

## 🧩 Internal Architecture

### 1. Main Class: `ArtificialWindowZOE`

- Manages the fullscreen host window.
- Retrieves the window list using `EnumWindows`.
- Transfers windows using `SetParent`.
- Modifies styles using `SetWindowLong`.

### 2. O+P Hotkey Handling

- Detected using `KeyPress` and `KeyRelease` events.
- Triggers `toggle_maximize()` when both keys are pressed simultaneously.

### 3. Core Functions

| Function | Purpose |
|----------|---------|
| `_catch()` | Captures and embeds the selected window. |
| `_release()` | Releases the window back to its original parent. |
| `toggle_maximize()` | Switches between Maximized and Windowed modes. |
| `_refresh_list()` | Updates the list of open windows. |

---

## 🔐 System Requirements

| Requirement | Description |
|-------------|-------------|
| **OS** | Windows 10 or 11 |
| **Privileges** | Must run as **Administrator** |
| **Python** | Version 3.12 or higher (if running directly) |
| **Libraries** | `pywin32` |

---

## ⚠️ Important Notes

- The program **must be run with Administrator rights** to control other windows.
- When the application is closed, any captured window is **automatically released**.
- In **Maximize mode**, title bar buttons (Close, Minimize, Maximize) are hidden.
- Press **Esc** to exit the host window’s fullscreen mode.

---

## 📌 Summary

**Artificial-Window-ZOE** is a lightweight yet powerful tool for managing fullscreen game windows. It allows users to embed any window inside a borderless fullscreen container, making it ideal for overlay applications like the **ZOE menu**.  
It is stable, easy to use, and fully compatible with Windows 10/11.

---

**Developer:** ZOE Project  
**Version:** 2.0  
**Release Date:** 2026

---
