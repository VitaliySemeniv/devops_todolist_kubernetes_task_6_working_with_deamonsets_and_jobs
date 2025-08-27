# Task 6 — DaemonSet & CronJob for ToDo app

## Передумови
- У кластері вже задеплоєний ToDo app у неймспейсі `mateapp`.
- Існує ClusterIP Service `todoapp-clusterip` у `mateapp`, який віддає додаток на порті `8000` і має endpoint `/api/health`.
  - Якщо сервіс відсутній, створіть його (приклад нижче у розділі “Додатково (опційно)”).

## Деплой

```bash
# 1) Переконайся, що неймспейс існує
kubectl get ns mateapp || kubectl create namespace mateapp

# 2) Застосуй маніфести
kubectl -n mateapp apply -f .infrastructure/daemonset.yml
kubectl -n mateapp apply -f .infrastructure/cronjob.yml
