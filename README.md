# 🖥️ Home Server Setup (Linux Mint + SSH Access)

This project documents my personal home server setup on a headless Linux Mint system using an NVIDIA RTX 2060 GPU and SSH key-based authentication from a Windows PC. The goal is to create a secure, headless environment for development, remote access, and future cybersecurity/home lab projects.
> ⚠️ Note: All usernames, IP addresses, and file paths shown here are placeholders for security purposes.

---

## 🧰 Hardware Specs

* **CPU**: AMD Ryzen 7 2700X (8 cores)
* **GPU**: NVIDIA RTX 2060 (headless via dummy HDMI plug)
* **RAM**: 16GB DDR4 @ 2400 MHz
* **Storage**: 250GB NVMe SSD (OS drive), 2TB SATA HDD
* **Motherboard**: Asus Prime X470-Pro ATX AM4

---

## 🔧 Technologies Used

| Tool / Stack    | Purpose                       |
| --------------- | ----------------------------- |
| Linux Mint      | Server OS (headless)          |
| Windows 11      | SSH client                    |
| OpenSSH         | Remote access protocol        |
| Dummy HDMI Plug | Simulate headless GPU display |
| PowerShell      | Windows terminal for SSH      |

---

## 🔐 SSH Configuration (Key-Based Login)

* SSH server installed and enabled on Linux Mint
* Private key stored on Windows PC (`~/.ssh/ServerKeyNameFile`)
* Public key appended to Linux server’s `~/.ssh/authorized_keys`
* Password authentication disabled (optional but planned)
* Root login disabled for added security

```bash
# Sample SSH config on Windows
Host homeserver
    HostName 192.168.x.xxx
    User linux-user
    IdentityFile C:/Users/User-Name/.ssh/ServerKeyNameFile
```

---

## 🧠 Skills Demonstrated

* Linux terminal and file system navigation
* SSH key-pair generation and secure authentication
* `scp` file transfers between OSes
* Permissions management (`chmod`, `chown`)
* Editing secure configs (`sshd_config`)
* Optional hardening: disabling root login, UFW, custom SSH ports

---

## 🔜 Future Plans

*

---

## 💼 Why This Matters

This setup mirrors real-world practices for securing servers, managing headless environments, and authenticating users without relying on passwords. It reflects core skills relevant to:

* 🔐 Cybersecurity roles
* ☁️ DevOps/Infrastructure jobs
* 🧰 IT systems administration

---

## 📎 Sample Commands

```bash
# Start SSH server (Linux)
sudo systemctl enable --now ssh

# Transfer key from Windows to Linux (PowerShell)
scp C:\Users\user-name\.ssh\ServerKeyNameFile linux-user@192.168.x.xxx:/home/user-name/.ssh/

# Fix permissions
chmod 700 ~/.ssh && chmod 600 ~/.ssh/authorized_keys
```

---

## 📌 Notes

* No sensitive information is stored in this repository.
* This is for personal development and learning in system administration and cybersecurity.

