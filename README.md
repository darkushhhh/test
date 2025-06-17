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


## Заключение

Проведенное тестирование выявило десять уязвимостей различной степени критичности, затрагивающих информационные системы на портах 8050 и 7788. Наибольшую угрозу представляют уязвимости критического уровня: SQL Injection, Command Injection и Unrestricted File Upload, которые могут привести к полной компрометации системы. Уязвимости высокого уровня, такие как Path Traversal, Exposed Credentials in Public GitHub Repository, Insecure Transmission of Sensitive Data и Session Hijacking Attack, создают значительные риски, особенно при их комбинированном использовании. Уязвимости среднего уровня — Weak Admin Password, Brute Force Attack и Cross-Site Scripting (XSS) — сами по себе менее критичны, но могут быть использованы злоумышленниками для подготовки более сложных атак.









