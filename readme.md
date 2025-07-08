# Linux Malware Samples for Ethical Hacking & Malware Analysis

This repository contains a collection of simple linux-based malware programs.  
⚠️ **These programs are intended for isolated testing environments only.**

---

## I_malware.c – Reverse Shell (CLI)

A basic Linux reverse shell implemented in C.

- **Execution**: Manual via command-line.
- **Function**: Connects back to a remote host using `nc` (Netcat).
- **Target**: Linux systems.
- **Use case**: Demonstrates reverse shell behavior for dynamic analysis labs.

---

## II_malware.c – Hidden Background Process

This sample simulates user-triggered malware that runs in the background.

- **Execution**: User runs binary manually (e.g., clicks).
- **Function**:
  - Detects if the OS is Linux.
  - Forks into a child process.
  - Attempts to connect to a remote host using `nc` in background.
- **Use case**: Testing behavioral monitoring tools for background execution.

---

## III_malware.c – Terminal Keylogger

A simple keylogger that monitors terminal input and logs it to a file.

- **Execution**: Manual execution in terminal.
- **Function**:
  - Switches terminal to raw mode.
  - Logs every typed character into `log_file.txt`.
  - Stops logging when user types `q`.
- **Use case**: Analysis of user-level keyloggers that rely on terminal interaction.

---

## IV_malware.c – Kernel-Level Keylogger + Telegram Exfiltration

A more advanced keylogger that:

- **Execution**: Forks and runs silently in the background.
- **Function**:
  - Detects active keyboard input device in `/dev/input/`.
  - Logs keypresses into `/tmp/.keys.log`.
  - Sends each keystroke to a specified Telegram bot using a dynamically created Python script.
- **Exfiltration**: Telegram API.
- **Use case**: Demonstrates data exfiltration and persistence using Linux input system.

> **Stopping it:**
> - Use `ps aux | grep <executable_name>` to find and kill the process.
> - Delete the binary and `/tmp/.runner.py`, `/tmp/.keys.log`.

---

## ⚠️ Disclaimer

These programs are provided **strictly for educational and research purposes**. Do **not** run them on any system you don't own or have explicit permission to test.  
The author is **not responsible** for any misuse.

---

## License

This repository is released under the [MIT License](LICENSE).
