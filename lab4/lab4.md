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

Vertex AI LLM: ≈ 450 K токенов = 18$

Cloud Run: 1 vCPU 512 MB × 4 ч = 6$

Storage = 3$

**Итог для MVP** - 27$

# 2.Тестирование партнерами
