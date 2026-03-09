## 📝 **Готовый `README.md` для папы**

Всё хорошо, но для папы нужно **чуть больше уважения и тепла**. Вот исправленный вариант с пояснениями, что я изменил:

```markdown
# Terraform Configuration for Yandex Cloud CDN + Object Storage

**Описание проекта:** конфигурация Terraform для развёртывания CDN с источником в Yandex Object Storage.

## Цель проекта

Автоматизировать развёртывание инфраструктуры в Yandex Cloud:
* создать бакет в Yandex Object Storage;
* загрузить статический контент (`index.html`);
* настроить CDN‑ресурс с источником из бакета;
* обеспечить быструю отдачу статического контента через CDN.

## Состав инфраструктуры

* **Yandex Object Storage** — хранилище файлов (бакет);
* **Yandex CDN** — сеть доставки контента;
* **Статический сайт** (`index.html`) — пример контента для отдачи через CDN.

## Предварительные требования

Перед использованием конфигурации убедитесь, что у вас есть:

1. Аккаунт в Yandex Cloud.
2. Установленный [Yandex Cloud CLI](https://cloud.yandex.ru/docs/cli/) и настроенная аутентификация (`yc init`).
3. Установленный [Terraform](https://www.terraform.io/downloads) версии ≥ 1.14.
4. Права доступа в Yandex Cloud (роль `editor` или выше для нужных сервисов).

## Использование

### Инициализация

```bash
terraform init
```

### Просмотр плана изменений

```bash
terraform plan
```

### Применение конфигурации (создание ресурсов)

```bash
terraform apply
```
Подтвердите действие, введя `yes`.

### Удаление ресурсов

Чтобы избежать лишних затрат, удалите созданные ресурсы, когда они больше не нужны:

```bash
terraform destroy
```
Подтвердите действие, введя `yes`.

## Структура проекта

```
yc-terraform-project/
├── .gitignore
├── README.md
├── .terraform.lock.hcl
├── index.html             # статический файл для CDN
├── yc-cdn-storage-integration-config.tf  # конфигурация Terraform
└── yc-cdn-storage-integration.auto.tfvars  # переменные
```

## Переменные

Основные переменные задаются в файле `yc-cdn-storage-integration.auto.tfvars`. Пример содержимого:

```hcl
folder_id       = "your-folder-id"
bucket_name     = "my-cdn-bucket"
cdn_origin     = "my-cdn-bucket.storage.yandexcloud.net"
index_file_path = "./index.html"
```

**Важно:** не храните секреты (пароли, API‑ключи) в открытом виде. Используйте переменные Terraform или секреты GitHub Actions.

## Благодарности

Отдельная благодарность моему отцу — за поддержку, мудрые советы и помощь на всех этапах работы над этим проектом. Спасибо, что всегда рядом.

## Автор

Проект подготовлен AnnaChurasheva

---

**Статус:** проект в разработке.
**Лицензия:** MIT
```
