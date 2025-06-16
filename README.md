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

**Уровень риска:** Средний

**Целевая страница:** `http://92.51.39.106:8050/pictures/view.php` , `http://92.51.39.106:8050/guestbook.php`

**Краткое описание:**

Уязвимость XSS, позволяет внедрить и выполнить вредоносный JavaScript-код в веб-приложении, что может привести к краже данных пользователя или выполнению несанкционированных действий.

**Реализация:**

<details>
<summary>Пошаговая реализация</summary>


- **Step 1. XSS на странице View.php**
    
Для реализации уязвимости на странице `http://92.51.39.106:8050/pictures/view.php`, была использована полезная нагрузка, которая выполняет JavaScript-код, вызывающий функцию Alert, в качестве содержимого окна выводится значение `document.cookie` пользователя:

```
<script>alert(document.cookie)</script>
```

![](screenshots/TESTING/XSS/8050)


    
- **Step 2. XSS на странице Guestbook.php**

Для реализации уязвимости на странице `http://92.51.39.106:8050/guestbook.php`, была использована полезная нагрузка, которая выполняет JavaScript-код, вызывающий функцию Alert, в качестве содержимого окна выводится значение `document.cookie` пользователя:    

```
<script>alert(document.cookie)</script>
```

![](screenshots/TESTING/XSS/8050)
   


- **Вывод**
    
В результате эксплуатации уязвимости **XSS** были получены данные `document.cookie` пользователя, **уязвимость подтверждена**. 

Использование полученных cookie открывает возможность для проведения дальнейших атак, таких как перехват сессии **(Session Hijacking Attack)**.


</details>

**Рекомендации по устранению:**

___

### 8. Vulnerability - Session Hijacking Attack 

**OWASP:** [A07:2021-Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/)

**Уровень риска:**

**Целевая страница:**

**Краткое описание:**

**Реализация:**

**Рекомендации по устранению:**

