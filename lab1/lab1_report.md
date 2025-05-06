University: ITMO University Faculty: FICT Course: Cloud platforms as the basis of technology entrepreneurship ADD link Year: 2024/2025 Group: OPOTP Author: Suvorova Ksenia Lab: Lab1 Date of create: 21.04.2025 Date of finished: 21.04.2025
Вкладка IAM создали service account с ролью Storage Admin. Создал compute engine с Machine type e2-micro в режиме spot. ( до этого момента, не знала, что нужны скрины в отчете, извините)
Далее с помощью утилиты gsutils найдите бакет lab1-bucket-itmo и скопируйте 3 файла в локальную папку на VM. Используя команду ls -lah отобразили что эти файлы хранятся у нас на VM.
![image](https://github.com/user-attachments/assets/1d9455bb-b298-4fae-8637-a59a0f5c5b03)
![image](https://github.com/user-attachments/assets/34feb0a0-0669-4cee-ac00-eae1f9c074d0)
![image](https://github.com/user-attachments/assets/a5d9d347-786c-49e9-bd0e-0061f152cbf4)
Поменяла права доступа для service account с Storage Admin на Compute Viewer.  Не получается подключиться к VM
![image](https://github.com/user-attachments/assets/0c520e32-d76a-4f59-a20d-45c0f61fa682)
