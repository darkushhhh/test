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



### 4. Vulnerability - Insecure Transmission of Sensitive Data

**OWASP:** [A02:2021 – Cryptographic Failures](https://owasp.org/Top10/A02_2021-Cryptographic_Failures/)

**Уровень риска:**

**Целевая страница:**

**Краткое описание:**
Данные пользователя передаются в незашифрованном виде, что делает их уязвимыми для различных атак, включая атаку типа "человек посередине" (MITM).

**Реализация:**

<details>
<summary>Пошаговая реализация</summary>


- **Step 1. Авторизация**
    
Переходим на страницу авторизации пользователя и отправляем запрос:
`http://92.51.39.106:8050/users/login.php`
    
![](screenshots/OSINT/Censys/censys1.png)


- **Step 2. Перехват трафика**

С помощью программы Burp Suite осуществляем перехват аутентификационных данных пользователя:

![](screenshots/SCANNING/nmap/nmap_8050.png)
   


- **Вывод**
    
В `Burp Suite` видим перехваченные аутентификационные данные пользователя `admin/admin`, передаваемые в незашифрованном виде, **уязвимость подтверждена**.


</details>

**Рекомендации по устранению:**

___

### 5. Vulnerability - SQL Injection

**OWASP:** [A03:2021-Injection](https://owasp.org/Top10/A03_2021-Injection/)

**Уровень риска:**

**Целевая страница:**

**Краткое описание:**

**Реализация:**

**Рекомендации по устранению:**

___

### 6. Vulnerability - Brute Force Attack 

**OWASP:** [A07:2021-Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/)

**Уровень риска:**

**Целевая страница:**

**Краткое описание:**

**Реализация:**

**Рекомендации по устранению:**

___

### 7. Vulnerability - Cross-Site Scripting (XSS)

**OWASP:** [A03:2021-Injection](https://owasp.org/Top10/A03_2021-Injection/)

**Уровень риска:**

**Целевая страница:**

**Краткое описание:**

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

