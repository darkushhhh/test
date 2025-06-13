___

```
nmap -A -sV --version-all -O -p 8050 --reason -T4 --defeat-rst-ratelimit 92.51.39.106
```

___

<details>
<summary>screenshot Nmap(8050)</summary>
  
![](screenshots/SCANNING/nmap/nmap_8050.png)

</details>

___

`8050`.

___

[NmapReport_8050](reports/nmap/nmap_report.txt)

___

# Этап №3. Testing

## Вводная информация

На предыдущем этапе было проведено сканирование двух целевых веб-приложений — `NetologyVulnApp.com (8050)` и `Beemer (7788)`, в результате которого были выявлены основные уязвимости, ставшие основой для дальнейшего ручного Penetration testing.

Однако полученный перечень уязвимостей не является исчерпывающим, также дополнительно будут исследованы потенциальные уязвимости, которые могли быть пропущены автоматическими сканерами.

Основными источниками информации для тестирования послужили:
- [OWASP Web Security Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [OWASP Cheat Sheets](https://cheatsheetseries.owasp.org/)
- [Книга Андрея Бирюкова «Информационная безопасность. Защита и нападение»](https://dmkpress.com/catalog/computer/securuty/978-5-93700-219-8/?srsltid=AfmBOopHiNlFCvwZMa-awRfJnO7HYnrBu95LsXbc_cnN_9TyI6LgVBV3)

### Таблица с обнаруженными уязвимостями по OWASP Top 10
| №  | Уровень риска | Уязвимость                                  | OWASP                                          | Уязвимая ИС (port) |
|----|---------------|---------------------------------------------|------------------------------------------------|--------------------|
| 1  | Критический   | SQL Injection                               | [A03:2021-Injection](https://owasp.org/Top10/A03_2021-Injection/)                        | 8050, 7788         |
| 2  | Критический   | Command Injection                           | [A03:2021-Injection](https://owasp.org/Top10/A03_2021-Injection/)                          | 7788               |
| 3  | Критический   | Unrestricted File Upload                    | [A05:2021-Security Misconfiguration](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)          | 8050, 7788         |
| 4  | Высокий       | Path Traversal                              | [A01:2021-Broken Access Control](https://owasp.org/Top10/A01_2021-Broken_Access_Control/)              | 8050, 7788         |
| 5  | Высокий       | Exposed credentials in public GitHub repository | [A07:2021-Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/) | 7788               |
| 6  | Высокий       | Insecure Transmission of Sensitive Data     | [A02:2021-Cryptographic Failures](https://owasp.org/Top10/A02_2021-Cryptographic_Failures/)             | 8050, 7788         |
| 7  | Высокий       | Session Hijacking Attack                    | [A07:2021-Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/) | 8050               |
| 8  | Средний       | Weak Admin Password                         | [A07:2021-Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/) | 8050               |
| 9  | Средний       | Brute Force Attack                          | [A07:2021-Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/) | 8050, 7788         |
| 10 | Средний       | Cross-Site Scripting (XSS)                  | [A03:2021-Injection](https://owasp.org/Top10/A03_2021-Injection/)                          | 8050, 7788         |

---

## Тестирование NetologyVulnApp.com (8050)

### 1. Vulnerability - Unrestricted File Upload

**OWASP:** A05:2021-Security Misconfiguration

**Уровень риска:**

**Целевая страница:**

**Реализация:**

**Рекомендации по устранению:**

___

### 2. Vulnerability - Path Traversal

**OWASP:** A01:2021-Broken Access Control

**Уровень риска:**

**Целевая страница:**

**Реализация:**

**Рекомендации по устранению:**

___

### 3. Vulnerability - Weak Admin Password

**OWASP:** A07:2021-Identification and Authentication Failures

**Уровень риска:**

**Целевая страница:**

**Реализация:**

**Рекомендации по устранению:**

___

### 4. Vulnerability - Insecure Transmission of Sensitive Data

**OWASP:** A02:2021 – Cryptographic Failures

**Уровень риска:**

**Целевая страница:**

**Реализация:**

**Рекомендации по устранению:**

___

### 5. Vulnerability - SQL Injection

**OWASP:** A03:2021-Injection

**Уровень риска:**

**Целевая страница:**

**Реализация:**

**Рекомендации по устранению:**

___

### 6. Vulnerability - Brute Force Attack 

**OWASP:** A07:2021-Identification and Authentication Failures

**Уровень риска:**

**Целевая страница:**

**Реализация:**

**Рекомендации по устранению:**

___

### 7. Vulnerability - Cross-Site Scripting (XSS)

**OWASP:** A03:2021-Injection

**Уровень риска:**

**Целевая страница:**

**Реализация:**

**Рекомендации по устранению:**

___

### 8. Vulnerability - Session Hijacking Attack 

**OWASP:** A07:2021-Identification and Authentication Failures

**Уровень риска:**

**Целевая страница:**

**Реализация:**

**Рекомендации по устранению:**

