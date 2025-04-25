# kerbrute Tool

`kerbrute` is a fast and flexible tool for **enumerating and attacking Kerberos services** on Active Directory networks. It's often used during **reconnaissance** and **credential bruteforcing** in red teaming and penetration testing.

- GitHub: [https://github.com/ropnop/kerbrute](https://github.com/ropnop/kerbrute)

---

## ⚙️ Installation

Download the precompiled binary or build from source:

```bash
git clone https://github.com/ropnop/kerbrute.git
cd kerbrute
go build
```

Or download from releases:
```bash
wget https://github.com/ropnop/kerbrute/releases/latest/download/kerbrute_linux_amd64
chmod +x kerbrute_linux_amd64
mv kerbrute_linux_amd64 /usr/local/bin/kerbrute
```

---

## 🚀 Common Use Cases

### 1. **User Enumeration**
Check for valid usernames in Active Directory:

```bash
kerbrute userenum -d example.com usernames.txt --dc 10.0.0.1
```

- `-d` = domain name
- `--dc` = Domain Controller IP or hostname

---

### 2. **Password Spraying**
Spray passwords across multiple users:

```bash
kerbrute passwordspray -d example.com users.txt 'Winter2024!' --dc 10.0.0.1
```

---

### 3. **Brute Force a Single User**

```bash
kerbrute bruteuser -d example.com passwords.txt administrator --dc 10.0.0.1
```

---

### 4. **Key Takeaways**

- Kerberos doesn't lock out users on ticket requests, making enumeration possible.
- Valid usernames = TGT requests that return responses (rather than errors).
- It's fast and can be used in stealthy red team scenarios.

---

## 🛠️ Tips

- Use in coordination with `impacket`, `crackmapexec`, and `bloodhound`.
- Avoid aggressive bruteforcing — it can cause account lockouts if not careful.
- Great tool for discovering valid accounts before attempting password attacks.

---

Let me know if you want this saved as a `.md` file or used in a lab/demo!
