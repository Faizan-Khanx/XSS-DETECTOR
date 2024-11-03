# XSS-DETECTOR

**XSS-DETECTOR** is a Python-based tool crafted to identify Cross-Site Scripting (XSS) vulnerabilities in web applications. By automating the injection of multiple payloads, this tool assists security researchers and developers in identifying potential security flaws. It’s also valuable for digital forensics, as it can help decode and analyze encoded payloads commonly used in real-world XSS attacks.

## Overview

XSS-DETECTOR simplifies the detection of XSS vulnerabilities by injecting various payloads and identifying parameters that are susceptible. This tool is ideal for cybersecurity enthusiasts, penetration testers, developers, and forensic analysts working on decoding and understanding XSS payloads in digital evidence.

## Key Features

- **Automated XSS Payload Injection**: Tests for vulnerabilities by injecting a range of payloads.
- **Wide Payload Range**: Includes basic, obfuscated, and advanced payloads for robust testing.
- **Color-Coded Output**: Highlights detected vulnerabilities for easier readability.
- **Decoding and Analysis**: Helps forensic analysts convert encoded payloads (e.g., `%3Cscript%3Ealert%28XSS%29%3C%2Fscript%3E`) back to readable form for further investigation.
- **Simple Usage**: Runs with a single Python command.
- **Versatile Testing**: Suitable for multiple input types and XSS variations.

## Table of Payloads

The table below lists sample payloads used by **XSS-DETECTOR** to test for XSS vulnerabilities. These cover a range of injections and encoded versions, helping forensic analysts decode and analyze them effectively.

| Payload ID | Payload Description                        | Example Usage                                 |
|------------|-------------------------------------------|-----------------------------------------------|
| 1          | Basic Alert Injection                     | `<script>alert('XSS')</script>`               |
| 2          | Encoded Alert Injection                   | `%3Cscript%3Ealert%28%27XSS%27%29%3C/script%3E` |
| 3          | Image Tag Injection                       | `<img src=x onerror=alert('XSS')>`            |
| 4          | Encoded Image Tag Injection               | `%3Cimg src=x onerror=alert(%27XSS%27)%3E`    |
| 5          | Event Handler Injection                   | `<body onload=alert('XSS')>`                  |
| 6          | Encoded Event Handler Injection           | `%3Cbody onload=alert(%27XSS%27)%3E`          |
| 7          | Custom JavaScript Injection               | `"><script>alert('XSS')</script>`             |
| 8          | SVG Injection                             | `<svg/onload=alert('XSS')>`                   |

*Note: Additional payloads can be added to expand testing capabilities.*

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Faizan-Khanx/XSS-DETECTOR.git
   ```
2. **Navigate to the directory**:
   ```bash
   cd XSS-DETECTOR
   ```
3. **Install dependencies** (if any):
   ```bash
   pip install -r requirements.txt
   ```

## Usage

To run the XSS-DETECTOR tool, use the following command:

```bash
python3 xss.py
```

During usage, encoded payloads are automatically converted to readable form, helping forensic analysts examine suspicious input fields with ease.

### Example Output

```plaintext
Enter the URL or payload to check for XSS: <input your payload>

[VULNERABLE] Parameter 'q' appears vulnerable to XSS.
Decoded Payload: <script>alert('XSS')</script>

[SAFE] Parameter 'user' shows no XSS vulnerability.
```

## Exported File Structure

XSS-DETECTOR outputs results to the terminal. For analysts who need structured data, the script can be modified to export results in JSON or CSV format.

## Contributing

Contributions are welcome! To contribute, fork the repository and submit a pull request with your improvements.

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For questions or suggestions, reach out:

- GitHub: [Faizan Khanx](https://github.com/Faizan-Khanx)
