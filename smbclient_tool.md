# smbclient Tool

`smbclient` is a command-line utility from the **Samba suite** used to interact with Windows SMB/CIFS shares from Unix/Linux systems.

---

## 🔧 Basic Syntax

```bash
smbclient //hostname/share -U username
```

---

## ✅ Features

- Browse SMB/CIFS file shares
- Upload/download files
- Create/remove directories
- Interactive shell or single-command mode

---

## 🔥 Common Use Cases

### 1. List Available Shares on a Host

```bash
smbclient -L //10.0.0.1 -U guest
```

### 2. Connect to a Specific Share

```bash
smbclient //10.0.0.1/shared -U guest
```

You’ll enter an interactive shell:
```
smb: \> ls
```

### 3. Download a File

```bash
smb: \> get secrets.txt
```

### 4. Upload a File

```bash
smb: \> put myscript.sh
```

### 5. One-Liner File Download (Non-Interactive)

```bash
smbclient //10.0.0.1/shared -U guest -c "get notes.txt"
```

---

## 🛠️ Tips

- Use `-N` to suppress password prompt (useful for guest/no-auth shares).
- Combine with `crackmapexec` or `enum4linux` for pentesting.
- Useful in both **system administration** and **penetration testing** scenarios.

---

Let me know if you want to automate tasks or use this in a script!
