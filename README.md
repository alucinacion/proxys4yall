# proxys4yall

Welcome to the **proxys4yall** repository! This project maintains a public list of HTTP(S) and SOCKS5 proxies that are automatically refreshed on GitHub. Use it for testing, development, or other networking tools.

---

## 📝 Description

The **proxys4yall** repository contains a collection of public proxies (HTTP, HTTPS, and SOCKS5) that are validated and updated periodically. The goal is to provide a centralized, always up-to-date source for developers, testers, and security enthusiasts.

---

## 📂 How to Use

1. **Clone the repository**:
   ```bash
   git clone https://github.com/alucinacion/proxys4yall.git
   cd proxys4yall
   ```

2. **Download the raw list**:
   ```bash
   curl -s https://raw.githubusercontent.com/alucinacion/proxys4yall/main/proxys.txt -o proxys.txt
   ```

3. **Integrate into your script**:
   ```bash
   # Bash example
   while read proxy; do
     curl -x "$proxy" https://example.com
   done < proxys.txt
   ```

4. **Filter by type** (HTTP, HTTPS, SOCKS5):
   ```bash
   grep "^HTTP" proxys.txt     # HTTP proxies only
   grep "SOCKS5" proxys.txt    # SOCKS5 proxies only
   ```

---

## 🔧 List Format

Each line in `proxys.txt` follows the format:

```
<TYPE>://<IP>:<PORT>
```

- **TYPE**: HTTP, HTTPS, or SOCKS5
- **IP**: IPv4 or IPv6 address
- **PORT**: Connection port

**Example**:
```
HTTP://203.0.113.45:8080
HTTPS://198.51.100.23:443
SOCKS5://192.0.2.10:1080
```

---

## ⏱️ Automatic Updates

The list is refreshed every 6 hours via a **GitHub Actions** workflow that:

1. Downloads proxies from various public sources.
2. Validates the availability of each proxy.
3. Generates a new `proxys.txt` file.
4. Opens an automatic pull request if changes are detected.
5. Merges the PR after checks pass.

Check the workflow in `.github/workflows/update.yml`.

---

## 🤝 Contributing

Contributions are welcome! You can:

- **Report** proxies that fail or broken links (open an issue).
- **Suggest** new proxy sources in an issue.
- **Submit a PR** with improvements to the script or filters.

When submitting a PR, make sure to:

- Follow the `proxys.txt` format.
- Add your name and profile if you make significant contributions.

---

## 📬 Contact

- **Author**: alucinacion ([@alucinacion](https://github.com/alucinacion))

Thank you for using **proxys4yall**! 🚀
