University: ITMO University Faculty: FICT Course: Cloud platforms as the basis of technology entrepreneurship ADD link Year: 2024/2025 Group: OPOTP Author: Suvorova Ksenia Lab: Lab2 Date of create: 05.05.2025 Date of finished: 05.05.2025

В Clour Run и создали Service с портом 8080
![image](https://github.com/user-attachments/assets/d7d978c3-cdf2-4a04-9dbf-2b1c4b674286)
![image](https://github.com/user-attachments/assets/1c69e4cd-7717-42f5-afc1-1ed63c48f398)
Перешли по ссылки и он запустился
![image](https://github.com/user-attachments/assets/919469e8-bb3b-4289-b1ba-b86c986cdd06)
Логи
![image](https://github.com/user-attachments/assets/f376c97c-4958-4c24-9749-cace43f09790)
И метрики
![image](https://github.com/user-attachments/assets/5cf91cbd-f28e-43ef-8927-09e56c28082b)
![image](https://github.com/user-attachments/assets/e76bfa5b-13c6-451d-8c59-0a14643ec747)
![image](https://github.com/user-attachments/assets/4a3deece-8f41-42b7-9d53-31a3ce2bddd0)
![image](https://github.com/user-attachments/assets/afb3e808-7b26-44c7-92f4-37820b8c8132)
![image](https://github.com/user-attachments/assets/346ccf6a-556e-44c4-bfa5-ea6b551c3a22)
Далее меняем порт на 8090
![image](https://github.com/user-attachments/assets/13603286-c561-4f7f-988e-b521d4b30f1d)
И повторно смотрим логи. Видим, что контейнер переключился на новый порт - 8090.
![image](https://github.com/user-attachments/assets/884a8980-eb57-4f90-ab3a-9786d72f860a)
ReplaceService - сервис обновился, новый порт запустился
![image](https://github.com/user-attachments/assets/4fe82141-c33b-4777-88d2-3306121945e7)
И метрики
![image](https://github.com/user-attachments/assets/3abd9c51-c0df-4ec9-83d5-ecff66a1365d)
На графиках видно, 2 работающих сервиса
![image](https://github.com/user-attachments/assets/e040b75b-583e-4d74-9f99-172f3860a7d7)
Максимальное количество запросов 2. Максимальная нагрузка 1%, задрежка запроса 9,9мс, используемая память -5%
![image](https://github.com/user-attachments/assets/ea7f173d-49bd-4ea9-8d91-1ac9e1368471)









