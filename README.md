# Пример хранения Terraform State в Yandex Cloud с использованием Yandex Object Storage и YDB

Чтобы управлять инфраструктурой могли несколько пользователей одновременно, состояния Terraform можно автоматически загружать и хранить в [Yandex Object Storage](https://yandex.cloud/ru/docs/tutorials/infrastructure-management/terraform-state-storage).

Когда несколько пользователей одновременно работают с одним состоянием из Object Storage, возможны конфликты. Чтобы предотвратить их, вы можете развернуть базу данных в [Yandex Managed Service for YDB](https://yandex.cloud/ru/docs/ydb/) и использовать ее для механизма блокировок, встроенного в Terraform (state locking). При каждом изменении инфраструктуры через Terraform состояние будет автоматически блокироваться, пока изменение не применится.

Пример конфигурационного файла Terraform `main.tf` с настройкой бэкенда, описывающий хранение состояния, расположен в этом репозитории.

Чтобы настроить хранение состояний с использованием Yandex Object Storage и YDB, воспользуйтесь практическим руководством [Блокировка состояний Terraform с помощью Yandex Managed Service for YDB](https://yandex.cloud/ru/docs/tutorials/infrastructure-management/terraform-state-lock).
