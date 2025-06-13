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



### 3. Vulnerability - Weak Admin Password

**OWASP:** [A07:2021-Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/)

**Уровень риска:**

**Целевая страница:**

**Краткое описание:**

Существует риск несанкционированного доступа к административной панели сайта из-за использования стандартной и предсказуемой комбинации логина и пароля.

логин/пароль : `admin/admin`

**Реализация:**
<details>
<summary>Пошаговая реализация</summary>


- **Step 1. Авторизация**
    
Переходим на страницу авторизации **Admin**:
`http://92.51.39.106:8050/admin/index.php?page=login`
    
![](screenshots/OSINT/Censys/censys1.png)


- **Step 2. Получаем доступ**

Вводим стандартную комбинацию логин/пароль : `admin/admin`

![](screenshots/SCANNING/nmap/nmap_8050.png)
   


- **Вывод**
    
Доступ к **Admin** части сайта получена, **уязвимость подтверждена**.


</details>

**Рекомендации по устранению:**

___

### 4. Vulnerability - Insecure Transmission of Sensitive Data

**OWASP:** [A02:2021 – Cryptographic Failures](https://owasp.org/Top10/A02_2021-Cryptographic_Failures/)

**Уровень риска:**

**Целевая страница:**

**Краткое описание:**

**Реализация:**

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

