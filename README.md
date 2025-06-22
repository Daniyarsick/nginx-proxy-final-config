# Развертывание Nginx Proxy & Let's Encrypt

**Выполнил: Аннануров Даниил Петрович, группа ИВТ 1.2**

* сервера больше нет 

---

Этот репозиторий содержит `docker-compose.yaml` для развертывания связки Nginx Proxy + Let's Encrypt для обслуживания нескольких приложений с автоматическим получением SSL-сертификатов.

## Инструкции по развертыванию

### 1. Предварительные требования

- Сервер с доступом в интернет (например, Ubuntu).
- Установленный Docker и Docker Compose (v2).
- Доменное имя с доступом к редактированию DNS.

### 2. Настройка DNS

Необходимо создать `A`-записи для всех доменов/поддоменов, указывающие на IP-адрес сервера, в панели управления доменного регистратора.

**Конфигурация для данного проекта:**
- `A`-запись для `whoami1.daniyrsick.ru` -> `5.129.195.214`.
- `A`-запись для `whoami2.daniyrsick.ru` -> `5.129.195.214`.

*Корректные A-записи необходимы для успешного выпуска SSL-сертификата Let's Encrypt.*

### 3. Запуск

1.  Клонировать репозиторий на сервер:
    ```bash
    git clone https://github.com/Daniyarsick/nginx-proxy-final-config.git
    cd nginx-proxy-final-config
    ```

2.  Файл `docker-compose.yaml` в репозитории настроен для доменов `whoami1.daniyrsick.ru` и `whoami2.daniyrsick.ru`. При использовании других доменов, необходимо внести в файл соответствующие изменения.

3.  Запустить все сервисы в фоновом режиме:
    ```bash
    docker compose up -d
    ```
    *(Примечание: команда `docker compose` используется без дефиса)* 


![image](https://github.com/user-attachments/assets/aa0a6873-6821-4629-b2d3-fd0bfd5e640d)
![image](https://github.com/user-attachments/assets/9e7aed68-819e-4c7a-945b-15f32addd27a)
![image](https://github.com/user-attachments/assets/6a4de007-ed83-42f4-a56c-6ae105736d72)
![image](https://github.com/user-attachments/assets/7c3b8b22-1948-417c-b9ca-c1ea5354a8cb)
![image](https://github.com/user-attachments/assets/9d28ae2f-7d73-4aea-8a74-bc022eb30460)

