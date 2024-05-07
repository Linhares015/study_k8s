# Criando um pod gitsync com o volume compartilhado

Vamos criar um pod que sincroniza um repositório git com um volume compartilhado.

Aqui está o arquivo de manifesto do pod:

[manifesto.yaml](/gitsync/pod_git_sync.yml)

## Principais cofigurações:

- Gerar uma chave ssh para o git:
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com" -f my-ssh-key -N ""
```

- Gerar arquivo known_hosts:
```bash
ssh-keyscan github.com > known_hosts
```

- Criar secret com a chave ssh e o arquivo known_hosts:
```bash
kubectl create secret generic git-ssh-key --from-file=my-ssh-key --from-file=known_hosts --namespace git-sync
```

## Principais configurações git-sync:

- `GIT_SYNC_REPO`: URL do repositório git
- `GIT_SYNC_BRANCH`: Branch do repositório git
- `GIT_SYNC_REV`: Revisão do repositório git
- `GIT_SYNC_DEST`: Diretório de destino do repositório git
- `GIT_SYNC_WAIT`: Tempo de espera entre as sincronizações
- `GIT_SYNC_SSH`: Habilitar autenticação ssh
- `GIT_SYNC_SSH_KEY_FILE`: Arquivo da chave ssh
- `GIT_SYNC_SSH_KNOWN_HOSTS_FILE`: Arquivo known_hosts
- `GIT_SYNC_ONE_TIME`: Sincronizar apenas uma vez
- `GIT_SYNC_DEPTH`: Profundidade da sincronização
- `GIT_SYNC_ROOT`: Diretório raiz do repositório git
- `GIT_SYNC_PERMISSIONS`: Permissões do diretório de destino
- `GIT_SYNC_USERNAME`: Usuário do repositório git
- `GIT_SYNC_PASSWORD`: Senha do repositório git
- `GIT_SYNC_MAX_SYNC_FAILURES`: Número máximo de falhas de sincronização
- `GIT_SYNC_SYNC_TAG`: Sincronizar tags
- `GIT_SYNC_WEBHOOK_REF`: Referência do webhook
- `GIT_SYNC_WEBHOOK_SECRET`: Segredo do webhook
- `GIT_SYNC_WEBHOOK_URL`: URL do webhook
- `GIT_SYNC_GIT`: Comando git
