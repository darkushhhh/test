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


### 5. Vulnerability - SQL Injection

**OWASP:** [A03:2021-Injection](https://owasp.org/Top10/A03_2021-Injection/)

**Уровень риска:** Критический 

**Целевая страница:** `http://92.51.39.106:8050/users/login.php`

**Краткое описание:**

Уязвимость SQLi, позволяет внедрить произвольные SQL-запросы, что может привести к несанкционированному доступу и компрометации учетной записи.

**Реализация:**
<details>
<summary>Пошаговая реализация</summary>


- **Step 1. Сканирование инструментом sqlmap**
    
Для проверки целевого веб-ресурса на наличие уязвимостей типа SQL-инъекций был использован инструмент `sqlmap`. Данный инструмент позволяет в автоматическом режиме выявлять уязвимости, связанные с некорректной обработкой SQL-запросов.
    
![](screenshots/TESTING/SQL_Injection/8050/sqlmap.png)


- **Step 2. Реализация SQLi**

В результате анализа было выявлено, что тестируемая веб-страница уязвима к атакам типа **SQLi**. Для подтверждения уязвимости на странице авторизации была введена следующая SQL-команда: `' OR TRUE #`.

![](screenshots/TESTING/SQL_Injection/8050/sample_log.png)

![](screenshots/TESTING/SQL_Injection/8050/sample.pmg)
   

- **Вывод**
    
После ввода указанной SQL-команды система авторизации предоставила доступ под учётной записью встроенного пользователя `Sample User`, **уязвимость подтверждена**.


</details>

**Рекомендации по устранению:**

- **Использование параметризованных запросов** : Применяйте параметризованные запросы для предотвращения внедрения пользовательского ввода в SQL-запросы.
- **Экранирование данных** : Используйте функции для корректного экранирования специальных символов в пользовательском вводе.
- **Валидация и фильтрация ввода** : Проверяйте и ограничивайте пользовательский ввод, допуская только ожидаемые форматы данных.


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

