# Terraform AWS Infrastructure

## Опис проекту
Цей проект містить Terraform конфігурацію для розгортання базової AWS інфраструктури, що включає:
- S3 бакет та DynamoDB для зберігання та блокування Terraform стейту
- VPC з публічними та приватними підмережами
- ECR репозиторій для Docker образів

## Структура проекту
lesson-5/<br>
│
├── main.tf  <br>                # Головний файл для підключення модулів
├── backend.tf   <br>            # Налаштування бекенду для стейтів (S3 + DynamoDB)
├── outputs.tf       <br>

## Передумови
- AWS CLI встановлений та налаштований
- Terraform версії >= 1.0.0
- Відповідні права доступу до AWS

## Порядок розгортання
1. Ініціалізація та створення бекенду:
   ```bash
   cd lesson-5
   terraform init
   terraform apply -target=module.s3_backend
   ```

2. Налаштування віддаленого бекенду та розгортання інфраструктури:
   ```bash
   terraform init -reconfigure
   terraform plan
   terraform apply
   ```