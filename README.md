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


### 7. Vulnerability - Cross-Site Scripting (XSS)

**OWASP:** [A03:2021-Injection](https://owasp.org/Top10/A03_2021-Injection/)

**Уровень риска:**

**Целевая страница:**

**Краткое описание:**

Уязвимость XSS, позволяет внедрить и выполнить вредоносный JavaScript-код в веб-приложении, что может привести к краже данных пользователя или выполнению несанкционированных действий.

**Реализация:**

**Рекомендации по устранению:**

___

### 8. Vulnerability - Session Hijacking Attack 

**OWASP:** [A07:2021-Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/)

**Уровень риска:**

**Целевая страница:**

**Краткое описание:**

**Реализация:**

**Рекомендации по устранению:**

