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



### Example Output for Various Scenarios

#### Scenario 1: Basic XSS Vulnerability Detected

```plaintext
Enter the URL or payload to check for XSS: https://example.com/search?q=<script>alert('XSS')</script>

[VULNERABLE] Parameter 'q' appears vulnerable to XSS.
Decoded Payload: <script>alert('XSS')</script>
Suggested Mitigation: Consider encoding special characters or sanitizing input on the server side.

[SAFE] Parameter 'user' shows no XSS vulnerability.
```

---

#### Scenario 2: Encoded XSS Payload

```plaintext
Enter the URL or payload to check for XSS: https://example.com/profile?username=%3Cscript%3Ealert%281%29%3C%2Fscript%3E

[VULNERABLE] Parameter 'username' appears vulnerable to XSS.
Decoded Payload: <script>alert(1)</script>
Suggested Mitigation: Apply input sanitization and output encoding on user-controlled inputs.

[SAFE] Parameter 'session_id' shows no XSS vulnerability.
```

---

#### Scenario 3: Parameter with HTML Injection

```plaintext
Enter the URL or payload to check for XSS: https://example.com/comments?text=<b>Comment</b><script>alert('XSS')</script>

[VULNERABLE] Parameter 'text' appears vulnerable to HTML/JS injection.
Decoded Payload: <b>Comment</b><script>alert('XSS')</script>
Suggested Mitigation: Strip HTML tags and encode JavaScript characters.

[SAFE] Parameter 'post_id' shows no XSS vulnerability.
```

---

#### Scenario 4: Safe URL (No Vulnerability Detected)

```plaintext
Enter the URL or payload to check for XSS: https://safe-example.com/home?lang=en

[SAFE] Parameter 'lang' shows no XSS vulnerability.
[SAFE] Parameter 'user_id' shows no XSS vulnerability.

Summary: No XSS vulnerabilities detected. The input appears safe.
```

---

#### Scenario 5: Multiple Parameters, One Vulnerable

```plaintext
Enter the URL or payload to check for XSS: https://example.com/update?title=<script>alert('XSS')</script>&status=active

[VULNERABLE] Parameter 'title' appears vulnerable to XSS.
Decoded Payload: <script>alert('XSS')</script>
Suggested Mitigation: Implement content security policy (CSP) and sanitize inputs.

[SAFE] Parameter 'status' shows no XSS vulnerability.
```

---

#### Scenario 6: Inline Event Handler Injection

```plaintext
Enter the URL or payload to check for XSS: https://example.com/display?input="onmouseover=alert('XSS')"

[VULNERABLE] Parameter 'input' appears vulnerable to inline event handler injection.
Decoded Payload: "onmouseover=alert('XSS')"
Suggested Mitigation: Encode inline event attributes and sanitize inputs for potentially dangerous characters.
```

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

For any questions or feedback, please contact [E-Mail Me](mailto:fk776794@gmail.com?subject=Feedback%20on%20Faizan%20Net&body=Hello%20Faizan,%0A%0AI%20have%20some%20feedback%20to%20share%20about%20your%20Faizan%20Net%20tool.%0A%0A%2D%20Issue%2FComplaint%3A%20[Please%20describe%20the%20issue%20or%20complaint]%0A%2D%20Suggestions%2FChanges%3A%20[Please%20provide%20your%20suggestions%20or%20changes]%0A%0AThank%20you!%0A%0ARegards,%0A[Your%20Name])

<!-- display the social media buttons in your README -->

[![instagram](https://github.com/shikhar1020jais1/Git-Social/blob/master/Icons/Instagram.png (Instagram))][2]
[![twitter](https://github.com/shikhar1020jais1/Git-Social/blob/master/Icons/Twitter.png (Twitter))][3]
[![linkedin](https://github.com/shikhar1020jais1/Git-Social/blob/master/Icons/LinkedIn.png (LinkedIn))][4]
[![github](https://github.com/shikhar1020jais1/Git-Social/blob/master/Icons/Github.png (Github))][5]

<!-- To Link your profile to the media buttons -->

[2]: https://www.instagram.com/EthicalFaizan
[3]: https://www.twitter.com/EthicalFaizan
[4]: https://www.linkedin.com/in/EthicalFaizan
[5]: https://www.github.com/faizan-khanx

## GITHUB STATS

![Faizan's GitHub stats](https://github-readme-stats.vercel.app/api?username=faizan-khanx&show=reviews,discussions_started,discussions_answered,prs_merged,prs_merged_percentage&theme=dark#gh-dark-mode-only)
