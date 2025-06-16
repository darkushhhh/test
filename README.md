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

<details>
<summary>Пошаговая реализация</summary>

- **Step 1. XSS + Сookie**
    
В результате успешной эксплуатации уязвимости XSS были получены cookie учётной записи пользователя `Admin`.
    
PHPSESSID = `gslch34c1r3fhq1buc1ln99if5`


   
- **Step 2. Реализация Session Hijacking**

Для проведения атаки перехвата сессии, необходимо подменить cookie текущего пользователя на cookie, ранее полученные в результате эксплуатации XSS. 
Идентификатор сессии пользователя **Admin**: `PHPSESSID=gslch34c1r3fhq1buc1ln99if5 `.


![](screenshots/TESTING/Session_Hijacking_Attack/admin_cookie.png)
   


- **Вывод**
    
В результате успешного проведения атаки **Session Hijacking**, был получен доступ к cookie сессии учётной записи **Admin**, **уязвимость подтверждена**.


</details>

**Рекомендации по устранению:**

- **Использование HTTPS** : Обеспечьте передачу данных по протоколу HTTPS для предотвращения перехвата cookie в сетевых атаках.

- **Установка флагов Secure и HttpOnly** : Настройте cookie сессий с атрибутами Secure и HttpOnly, чтобы снизить риск их кражи через XSS.

- **Регенерация идентификатора сессии** : Реализуйте обновление идентификатора сессии (PHPSESSID) после успешной авторизации или при важных действиях пользователя.

- **Ограничение срока действия сессии** : Установите короткий срок действия cookie сессии и используйте механизмы автоматического истечения сессии при бездействии.

___
