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




### 8. Vulnerability - Session Hijacking Attack 

**OWASP:** [A07:2021-Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/)

**Уровень риска:** Высокий

**Целевая страница:** `http://92.51.39.106:8050/users/home.php`

**Краткое описание:**

Session Hijacking — это атака, при которой происходит перехват идентификатора сессии пользователя, чтобы получить несанкционированный доступ к его активной сессии в веб-приложении.

**Реализация:**

**Рекомендации по устранению:**

