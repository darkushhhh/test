# Этап №1. OSINT

## Инструменты OSINT

Для анализа и сбора данных об указанном IP-адресе были использованы следующие инструменты:
- [Shodan](https://www.shodan.io)
- [Censys Search](https://search.censys.io)
- [ZoomEye](https://www.zoomeye.ai)

---

## Сканирование IP-адреса

### 1. Shodan

**Входные данные:**
- IP-адрес: `92.51.39.106`

**Результаты сканирования:**  
<details>
<summary>screenshot Shodan</summary>
![](pic/Shodan.png)
</details>

**Вывод:**  

Обнаружен открытый порт с развернутым сервисом:  
- **22 (SSH)** — OpenBSD OpenSSH 8.2

---

### 2. Censys Search

**Входные данные:**
- IP-адрес: `92.51.39.106`

**Результаты сканирования:**  
<details>
<summary>screenshot Censys Search</summary>
![](pic/Censys.png)
</details>

**Вывод:**

Обнаружены открытые порты с развернутыми сервисами:
- **22 (SSH)** — OpenBSD OpenSSH 8.2
- **8050 (HTTP)** — Apache HTTPD 2.4.7, PHP 5.5.9

---

### 3. ZoomEye

**Входные данные:**
- IP-адрес: `92.51.39.106`

**Результаты сканирования:**  
<details>
<summary>screenshot ZoomEye</summary>
![](pic/ZoomEye.png)
</details>

**Вывод:**

Обнаружен открытый порт с развернутым сервисом:
  - **7788 (HTTP)** — Tornado httpd 5.1.1

---

## Итоги OSINT исследования

На основании анализа, проведенного с использованием сканеров Shodan, Censys Search и ZoomEye, установлено, что на IP-адресе `92.51.39.106` развернуты два веб-приложения:

<details>
<summary>Beemer (7788)</summary>
![](pic/Shodan.png)
</details>

<details>
<summary>NetologyVulnApp.com (8050)</summary>
![](pic/Shodan.png)
</details>

---

## Перейти к следующей странице
 
Далее: Этап №2. [**SCANNING**](./SCANNING.md)

---
