# Python Keylogger

A simple, educational Python keylogger for demonstrating keyboard event capturing.

**⚠️ IMPORTANT DISCLAIMER ⚠️**

This project is created for **educational purposes and security research only**. Keyloggers can be powerful tools, and their misuse can have serious legal and ethical consequences.

* **DO NOT use this software on any system without explicit, informed consent from the owner.**
* **Unauthorized logging of keystrokes is illegal in most jurisdictions.**
* The author is not responsible for any misuse or damage caused by this software. Use responsibly and ethically.

---
---

## About The Project

This Python keylogger is a basic implementation designed to capture keystrokes. It demonstrates how to interact with keyboard events at a low level using Python libraries. The captured keystrokes can be saved to a local file, making it useful for understanding keyboard input mechanisms or for legitimate monitoring scenarios (e.g., parental control on your own child's device with their knowledge, or self-monitoring for productivity, or in a controlled penetration testing environment).

**Please reiterate the disclaimer: Use this tool responsibly and ethically.**

## Features

* Captures individual keystrokes (alphanumeric, symbols, special keys like Shift, Ctrl, Alt).
* Logs captured keystrokes to a specified output file.
* Handles common special keys gracefully.
* Lightweight and easy to understand.

## How it Works

The keylogger primarily uses the `pynput` library to listen for keyboard events.

1.  **Event Listener:** A `Listener` object from `pynput.keyboard` is initialized.
2.  **Callback Functions:**
    * `on_press(key)`: This function is called every time a key is pressed. It processes the `key` object, converting it into a readable string (e.g., 'a', 'shift', 'space'), and then logs it.
    * `on_release(key)`: This function is called every time a key is released. It can be used for specific actions (e.g., stopping the listener after a certain key is pressed, though not implemented by default in this basic version).
3.  **Logging:** The captured keystrokes are appended to a text file (`keylog.txt` by default).
4.  **Threading:** The `pynput` listener runs in its own thread, allowing the main program to continue or to be controlled.

## Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/python-keylogger.git](https://github.com/your-username/python-keylogger.git)
    cd python-keylogger
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    # On Windows
    .\venv\Scripts\activate
    # On macOS/Linux
    source venv/bin/activate
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    *(If `requirements.txt` isn't provided, you'll likely only need `pynput`)*
    ```bash
    pip install pynput
    ```

## Usage

**Before running, ensure you have understood and accepted the ethical considerations and legal implications.**

1.  **Run the keylogger:**
    ```bash
    python keylogger.py
    ```

2.  **Monitoring:** Once started, the keylogger will run in the background (or in your terminal if you don't daemonize it). All keystrokes you type will be recorded.

3.  **Stop the keylogger:**
    * To stop the keylogger, you'll typically need to interrupt the script's execution (e.g., by pressing `Ctrl+C` in the terminal where it's running).
    * For a more robust stopping mechanism, you might implement a specific "stop key" or a timed stop.

4.  **View Logs:**
    The captured keystrokes will be saved in `keylog.txt` (or whatever `LOG_FILE` you configure). Open this file with any text editor to view the log.

    ```bash
    cat keylog.txt
    ```

## Configuration

You can easily modify the logging behavior by editing the `keylogger.py` file:

* `LOG_FILE`: The path to the file where keystrokes will be saved.
    ```python
    LOG_FILE = "keylog.txt"
    ```
    You can change this to any desired path (e.g., `/var/log/my_system_activity.log` or `C:\Users\YourUser\Documents\my_typed_keys.log`).

## Contributing

Contributions are welcome, especially for educational enhancements or ethical use-case implementations!

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## Contact

Your Name - pavanreddy4680@gmail.com
Project Link: [https://github.com/your-username/python-keylogger](https://github.com/your-username/python-keylogger)
