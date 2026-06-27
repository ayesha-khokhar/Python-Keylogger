# ⌨️ Keylogger

A simple keylogger built with Python that monitors and logs all keystrokes to a text file using the `pynput` library.

---

## 📋 Description

This program listens to keyboard input in the background. Every key pressed is recorded and saved to a `log.txt` file. The program keeps running until the **ESC** key is pressed.

---

## 🚀 Usage

```bash
python3 keylogger.py
```

Once running, all keystrokes will be:
- Printed to the terminal
- Saved to `log.txt` in the same directory

Press **`ESC`** to stop the keylogger.

---

## 🛠️ Requirements

- Python 3.x
- `pynput` library (external)

Install the dependency with:

```bash
pip install pynput
```

---

## ⚙️ How It Works

1. Starts a `Listener` from `pynput.keyboard` to monitor keyboard events.
2. **`on_press(key)`** — called every time a key is pressed:
   - Appends the key to a list.
   - Calls `write_file()` to save all keys to `log.txt`.
   - Prints alphanumeric keys normally; special keys (Shift, Ctrl, etc.) are caught via `AttributeError`.
3. **`write_file(keys)`** — writes all recorded keys to `log.txt`:
   - Cleans up formatting by removing single quotes from key strings.
   - Adds a space between each key for readability.
4. **`on_release(key)`** — called when a key is released:
   - Prints which key was released.
   - If **ESC** is pressed → returns `False` to stop the listener.

---

## 📄 Output

All keystrokes are saved in **`log.txt`** in the project folder. Example output:

```
h e l l o Key.space w o r l d Key.enter
```

---

## ⚠️ Important Notice

> This project is for **educational purposes only.**
> Using a keylogger on any system **without explicit permission** is **illegal and unethical.**
> Only run this on your **own machine** in a controlled environment.

---

## 📁 Project Structure

```
Keylogger/
│
├── keylogger.py      # Main keylogger script
└── log.txt           # Auto-generated log file (created on first run)
```

---

## 👩‍💻 Author

Made with Python 🐍
