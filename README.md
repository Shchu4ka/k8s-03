# Домашнее задание к занятию «Запуск приложений в K8S»

## Задание 1. Создать Deployment и обеспечить доступ к репликам приложения из другого Pod

- Готовим манифест для деплоймента. Ошибка связана с тем, что по умолчанию multitool использует 80 порт, который занят nginx

 ![image](https://github.com/user-attachments/assets/ce998f07-8d6e-4801-a31a-ae5d729c6b5e)

- Применяем манифест и проверяем, что все взлетело

  ![image](https://github.com/user-attachments/assets/e306fd85-d217-4363-afad-d5ad9aeab456)

- Количество реплик увеличивается в разделе replicas деплоймента. Увеличим до 2 по условию. Предупреждение связано с отсутствием последней успешной конфигурации для отката.

  ![image](https://github.com/user-attachments/assets/047f03fb-89e7-49d3-8f27-233e070db407)

- Создаем манифест для сервиса, применяем его и проверяем статус

  ![image](https://github.com/user-attachments/assets/7fe5c516-6cd6-4776-8dac-63cd1800247f)

- Проверяем курлами работу сервиса

  ![image](https://github.com/user-attachments/assets/1bcf5de8-8cd2-4c9c-8a70-377d3e8fe522)
  ![image](https://github.com/user-attachments/assets/9b6f1dd3-811b-4922-aef5-31a3b34ed9ff)

- Создаем отдельный под и применяем его

  ![image](https://github.com/user-attachments/assets/7189738a-e535-482c-a29f-7589439808bb)

- Проверяем доступность портов из пода multitool

  ![image](https://github.com/user-attachments/assets/ab57aa36-cdc0-433b-9fa2-e0404b5e80c8)


## Задание 2. Создать Deployment и обеспечить старт основного контейнера при выполнении условий

- Проверяем, включен ли модуль DNS в microk8s, пишем манифест для деплоймента, применяем его

  ![image](https://github.com/user-attachments/assets/352a09c6-1de4-49c0-ac67-06bdad12bed8)

- Видим, что под не стартует, как и было описано в деплое

  ![image](https://github.com/user-attachments/assets/5eec24e6-59b0-4a70-b16e-b90b265067db)

- Применяем манифест сервиса, через какое-то время под стартует

![image](https://github.com/user-attachments/assets/0707d697-2120-4812-9d85-332821ef067a)
![image](https://github.com/user-attachments/assets/0b55f28b-a773-4b2d-9589-db07c9caa82d)
