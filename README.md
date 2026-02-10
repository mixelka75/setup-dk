# setup-deploy-key

Скрипт для быстрой настройки SSH deploy-ключей. Генерирует ключ, настраивает `~/.ssh/config` и клонирует репозиторий.

## Установка и запуск

```bash
bash <(curl -sL https://raw.githubusercontent.com/mixelka75/setup-dk/main/setup-deploy-key.sh) git@github.com:user/repo.git
```

## Что делает скрипт

1. Парсит SSH URL (`git@host:owner/repo.git`)
2. Генерирует ed25519 SSH-ключ в `~/.ssh/deploy_<host>_<owner>_<repo>`
3. Добавляет host-алиас в `~/.ssh/config`
4. Выводит публичный ключ и прямую ссылку для добавления deploy-ключа в репозиторий
5. Ждёт подтверждения и клонирует репозиторий через новый ключ

## Поддерживаемые платформы

- GitHub
- GitLab
- Bitbucket
- Любой хост с форматом `git@host:owner/repo.git`

## Примеры

```bash
bash <(curl -sL https://raw.githubusercontent.com/mixelka75/setup-dk/main/setup-deploy-key.sh) git@github.com:user/repo.git
bash <(curl -sL https://raw.githubusercontent.com/mixelka75/setup-dk/main/setup-deploy-key.sh) git@gitlab.com:group/project.git
bash <(curl -sL https://raw.githubusercontent.com/mixelka75/setup-dk/main/setup-deploy-key.sh) git@bitbucket.org:team/repo.git
```

## Требования

- Bash 4+
- `ssh-keygen`
- `git`
