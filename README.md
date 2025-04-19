# Домашнее задание к занятию "`Хранение в K8s. Часть 2`" - `Бакулев Евгений`

## Задание 1. Создать Deployment приложения, использующего локальный PV, созданный вручную.

- [Манифест Deployment](https://github.com/garrkiss/storagek8s-2/blob/main/manifest/task1/deployment.yaml)
- [Манифест PV](https://github.com/garrkiss/storagek8s-2/blob/main/manifest/task1/pv.yaml)
- [Манифест PVC](https://github.com/garrkiss/storagek8s-2/blob/main/manifest/task1/pvc.yaml)


### Демонстрация, что multitool может читать файл
![Ссылка](https://github.com/garrkiss/storagek8s-2/blob/main/img/1.png)

### Что изменилось после удаления Deployment и PVC?
- Статус изменился с `Bound` на `Released` т.к. PVC больше не существует, но PV сохраняется в кластере из-за политики `Retain`, если бы политика была `Delete`, PV был бы удален вместе с PVC.

![Ссылка](https://github.com/garrkiss/storagek8s-2/blob/main/img/2.png)

### Что произошло после удаления PV?
- При удалении PV файлы сохранятся т.к. у меня прописана политика Retain

![Ссылка](https://github.com/garrkiss/storagek8s-2/blob/main/img/3.png)


## Задание 2. Создать Deployment приложения, которое может хранить файлы на NFS с динамическим созданием PV.

- [Манифест DaemonSet](https://github.com/garrkiss/storagek8s-1/blob/main/manifest/multitool-log-reader.yaml)

![Ссылка](https://github.com/garrkiss/storagek8s-1/blob/main/img/3.png)