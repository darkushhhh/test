# Этап №1. OSINT Исследование

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
<summary>Скриншот Shodan</summary>
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
<summary>Скриншот</summary>
![](pic/Censys.png)
</details>

**Вывод:**
- Обнаружены открытые порты с развернутыми сервисами:
  - **22 (SSH)** — OpenBSD OpenSSH 8.2
  - **8050 (HTTP)** — Apache HTTPD 2.4.7, PHP 5.5.9

---

### Пункт 3: Анализ в ZoomEye

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

---

## Итоги OSINT исследования

На основании анализа, проведенного с использованием сканеров Shodan, Censys Search и ZoomEye, установлено, что на IP-адресе `92.51.39.106` развернуты два веб-приложения:

<details>
<summary>Скриншот результатов сканирования</summary>
![](pic/Shodan.png)
</details>

<details>
<summary>Скриншот результатов сканирования</summary>
![](pic/Shodan.png)
</details>

---

Далее: Страница [**OSINT**](./osint.md)
