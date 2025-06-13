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





### 2. Vulnerability - Path Traversal

**OWASP:** [A01:2021-Broken Access Control](https://owasp.org/Top10/A01_2021-Broken_Access_Control/)

**Уровень риска:** Высокий

**Целевая страница:** `http://92.51.39.106:8050/admin/index.php?page=home`

**Краткое описание:**

Существует возможность взаимодействия с файловой системой, включая доступ к файлам на хосте и исходному коду веб-страниц.

**Реализация:**

<details>
<summary>Пошаговая реализация</summary>

- **Step 1. Структура файловой системы**
    
Ранее реализовав уязвимость **Unrestricted File Upload**, удалось получить представление о структуре файловой системы на сервере.

![](screenshots/OSINT/Censys/censys1.png)

- **Step 2. Получение исходного кода страницы**

Для примера возьмем страницу `/include/admins`, которую удалось обнаружить в директории сервера.
    
Сервер не дает прямого доступа к исходному коду, необходимо выгрузить его в формате **base64**.
    
Для выгрузки исходного кода воспользуемся инструментом `curl` + **base64-encode**.
    
```
curl "http://92.51.39.106:8050/admin/index.php?page=php://filter/read=convert.base64-encode/resource=../include/admins"
```

![](screenshots/SCANNING/nmap/nmap_8050.png)
   
- **Step 3. Декодирование кода**

Далее при помощи все того же `curl`, декодируем исходную страницу.

```
curl "http://92.51.39.106:8050/admin/index.php?page=php://filter/read=convert.base64-encode/resource=../include/admins" -s | base64 -d
```

![](screenshots/SCANNING/nmap/nmap_8050.png)

- **Вывод**
    
Исходный код страницы получен, **уязвимость подтверждена**.

Исходный код страницы `/include/admins` : [admins](other/code/admins_code.txt).

</details>

**Рекомендации по устранению:**

___

### 3. Vulnerability - Weak Admin Password

**OWASP:** [A07:2021-Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/)

**Уровень риска:**

**Целевая страница:**

**Краткое описание:**

**Реализация:**

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

