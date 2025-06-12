# Отчет по OSINT и сканированию IP-адреса 92.51.39.106

## Инструменты OSINT

Для анализа и сбора данных об указанном IP-адресе были использованы следующие инструменты:
- [Shodan](https://www.shodan.io)
- [Censys Search](https://search.censys.io)
- [ZoomEye](https://www.zoomeye.ai)

### Анализ в Shodan
**Входные данные:**
- IP-адрес: `92.51.39.106`

**Результаты сканирования:**  
<details>
<summary>Скриншот</summary>
![](pic/Shodan.png)
</details>

**Вывод:**
- Обнаружен открытый порт с развернутым сервисом:
  - **22 (SSH)** — OpenBSD OpenSSH 8.2

### Анализ в Censys Search
**Входные данные:**
- IP-адрес: `92.51.39.106`

**Результаты сканирования:**  
<details>
<summary>Скриншот</summary>
![](pic/Censys.png)
</details>

**Вывод:**
- Обнаружены открытые порты с развернутыми сервисами:
  - **22 (SSH)** — OpenBSD OpenSSH 8.2
  - **8050 (HTTP)** — Apache HTTPD 2.4.7, PHP 5.5.9

### Анализ в ZoomEye
**Входные данные:**
- IP-адрес: `92.51.39.106`

**Результаты сканирования:**  
<details>
<summary>Скриншот</summary>
![](pic/ZoomEye.png)
</details>

**Вывод:**
- Обнаружен открытый порт с развернутым сервисом:
  - **7788 (HTTP)** — Tornado httpd 5.1.1

### Итоги OSINT исследования
На основании анализа, проведенного с использованием сканеров Shodan, Censys Search и ZoomEye, установлено, что на IP-адресе `92.51.39.106` развернуты два веб-приложения:
- **Beemer** (порт 7788)
- **NetologyVulnApp.com** (порт 8050)

<details>
<summary>Скриншоты обнаруженных сайтов</summary>
![](pic/NetologyVulnApp.com.png)
![](pic/Beemer.png)
</details>

---

Далее: Страница [**OSINT**](./osint.md)
