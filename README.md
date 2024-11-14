# Projeto | Up Trips - Viagens e Turismo 🏝️
___
Repositório de desenvolvimento do projeto de extensão da empresa Up Trips - Viagens e Turismo o projeto completo pode ser encontrado neste repositório, com a instalação da api e do frontend podendo ser realizada via docker.
[link do projeto](https://github.com/PedroClemonini/projeto_uptrips).

Separamos o projeto em dois repositórios, frontend e api
A API será desenvolvida em PHP 8.2 utilizando o Framework Laravel, servidor apache e Banco de Dados em MYSQL.
O Frontend será desenvolvido utilizando a biblioteca React JS e Tailwind
## Como trabalhar nesse projeto:

### 1. Clone o repositório original
Você deve clonar este repositório para subir e testar corretamente o projeto por completo.
```bash
git clone --recursive https://github.com/PedroClemonini/projeto_uptrips.git
```

### 2. Faça um Fork do repositório que deseja trabalhar para sua conta

Você pode trabalhar no uptrips_api ou no uptrips_frontend, para isso, no github entre dentro do repositório desejado e faça um fork dele para sua conta. Se trabalhar nos dois, repita o processo 2, 3, 4 e 5.

### 3. Aponte corretamente os repositórios origin e upstream

```bash
git remote set-url origin https://github.com/<seu_usuario>/<nome_do_repositorio_trabalhado>.git
git remote add upstream https://github.com/PedroClemonini/<nome_do_repositorio_trabalhado.git
```

### 4. Verifique se o repostório foi clonado corretamente

```bash
git remote -v
```

Você deve fer algo assim
```bash
origin    https://github.com/<usuario>/<nome_do_repositorio_trabalhado..git (fetch)
origin    https://github.com/<usuario>/<nome_do_repositorio_trabalhado..git (push)
upstream  https://github.com/PedroClemonini/<nome_do_repositorio_trabalhado..git (fetch)
upstream  https://github.com/PedroClemonini/<nome_do_repositorio_trabalhado..git (push)
```

### 5. Sempre sincronize seu repositório com o original
```bash
git pull upstream main
```

##  Passos para subir o container Docker 🐳:

### 1. Instalando o Docker para sistemas Linux (Exemplos feitos em Debian)
Adicione o repositório docker em sua lista de repositórios mais
[Mais informações](https://docs.docker.com/engine/install/)
```bash
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
### 1. Instale os pacotes
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### 2. Crie o (.env) do Laravel
```bash
cd uptrips_api/laravel-app
cp .env.example .env
```

### 3. Crie o (.env) do React
```bash
cd uptrips_frontend/app
cp .env.example .env
```

### 4. Subindo o container 📦

```bash
docker compose up --build -d
```

### 5. Instalando dependências
```bash
docker compose exec -T app composer install
```

### 6. Realizar as migrations do banco
```bash
$ docker compose exec -T app php artisan migrate
```


