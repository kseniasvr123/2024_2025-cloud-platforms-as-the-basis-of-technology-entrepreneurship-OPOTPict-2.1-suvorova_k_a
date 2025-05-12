University: ITMO University Faculty: FICT Course: Cloud platforms as the basis of technology entrepreneurship ADD link Year: 2024/2025 Group: OPOTP Author: Suvorova Ksenia Lab: Lab4 Date of create: 10.05.2025 Date of finished: 11.05.2025

# 0. Идея приложения
Сервис для генерации чек листа на основе документации или любого другого текстового файла
# 1. Начальный этап
**Архитектура**
![image](https://github.com/user-attachments/assets/c7cc72cf-1c6f-4f14-8e9c-3aa0959bea29)
Пользователь загружает документ через веб- или мобильное приложение,запрос проходит через Google Cloud API Gateway для безопасной маршрутизации. Обработка изображения осуществляется на Google Cloud Run с использованием контейнеризированных микросервисов, после чего изображение сохраняется в Google Cloud Storage. Далее вызывается модель, развернутая в Vertex AI, для получения чек листа.

**Обоснование:**
Vertex AI LLM API - Дешевле кастомных моделей
Cloud Run - возможность масштабирования, поминутная тарификация
Cloud Storage - дешево и надежно

**Расчеты**
при нагрузке 1000 req/day

Vertex AI LLM: ≈ 450 K токенов = 18$

Cloud Run: 1 vCPU 512 MB × 4 ч = 6$

Storage = 3$

**Итог для MVP** - 27$

# 2.Тестирование партнерами
**Архитектура**
![image](https://github.com/user-attachments/assets/0687beb0-6e09-4d57-b50e-3ca8ef325c46)
Добавили балансировщик нагрузки для стабильной работы. Cloud SQL используется для сложных запросов, заменяя Firestore, а Memorystore ускоряет доступ к данным через кеширование. Архитектура поддерживает до 1,000 запросов в секунду с помощью ручного масштабирования. Это обеспечивает надежную и масштабируемую платформу с высокой производительностью и безопасностью.

**Обоснование:**
Cloud Run все еще дешевле Kubernetes на партнерских нагрузках
Memorystore: Ускоряет запросы к AI-моделям
Cloud SQL: Подходит для больших структурированных данных партнеров.

**Расчеты**
Vertex AI LLM: ≈ 4,5 M токенов = 180$
Cloud Run (~35 ч vCPU) = 25$
Cloud SQL (~10 гб) = 10$
Cloud Logging / Monitoring = 10$
**Итог для партнеров** - 225$

# 3.Продовое решение
**Архитектура**
![image](https://github.com/user-attachments/assets/542bf074-9832-4509-8992-2b8f14bf340a)
Масштабируемый кластер Kubernetes управляет микросервисами бекенда. Заменяем базу данных на Cloud Spanner. 
**Обоснование:**
Kubernetes обеспечивает отказоустойчивость. Cloud Spanner - репликация для отказоустойчивости.

**Расчеты**
Managed Kubernetes = 50$
Cloud Load Balancer = $30

Vertex AI LLM ≈ 8 M токенов = 1200$
Cloud Spaner ≈ 100 гб = 600$
Monitoring = 25$
**Итог для прода** - 1950$
