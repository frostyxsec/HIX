# HIX - Host Header Injection Scanner

**Author:** Frostyxsec  
**Language:** Bash  
**License:** MIT  
**Purpose:** Quickly scan multiple URLs for potential **Host Header Injection** vulnerabilities using customizable payloads and multi-threaded execution.

---

## 🚀 Features

- Scans a list of URLs for Host Header Injection vulnerabilities
- Custom Host header payloads
- Multi-threaded scanning
- Interactive ASCII-art banner
- Auto-detects vulnerable responses via status codes and body contents
- Saves results to an output file
- Gracefully handles interruptions and cleanup

---

## 📦 Requirements

- `bash` (Linux/macOS)
- `curl`
- `flock` (usually part of `util-linux`)

---

## 🔧 Usage

```bash
./hix -l <url_list> -t <threads> -o <output.txt>
```

### Parameters

| Flag | Description |
|------|-------------|
| `-l` | File containing list of target URLs (one per line) **[Required]** |
| `-t` | Number of concurrent threads (default: `10`) |
| `-o` | Output file for results (default: `hix_output.txt`) |

---

## 🧪 Example

```bash
./hix -l targets.txt -t 20 -o results.txt
```

This command will scan all URLs in `targets.txt` using 20 threads and write any vulnerable results to `results.txt`.

---

## 🧬 Payloads Used

The script uses the following common payloads in the `Host` header:

```
evil.com  
localhost  
127.0.0.1  
example.com  
attacker.com  
hacker.com
```

---

## 🛑 Interrupt Handling

Press `Ctrl+C` anytime during the scan to gracefully exit and clean up temporary files.

---

## 📁 Output

Vulnerable results will be logged in this format:

```
[VULNERABLE] http://example.com - Payload: attacker.com
```

---

## ⚠️ Disclaimer

This script is intended for educational and authorized security testing only. Do **not** use it on systems without explicit permission.

---

## 📜 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).
