# Projeto | Up Trips - Viagens e Turismo 🏝️
___
Repositório de desenvolvimento do projeto de extensão da empresa Up Trips - Viagens e Turismo o projeto completo pode ser encontrado neste repositório, com a instalação da api e do frontend podendo ser realizada via docker.
[link do projeto](https://github.com/PedroClemonini/projeto_uptrips).

Separamos o projeto em dois repositórios, frontend e api
A API será desenvolvida em PHP 8.2 utilizando o Framework Laravel, servidor apache e Banco de Dados em MYSQL.
O Frontend será desenvolvido utilizando a biblioteca React JS e Tailwind

##  Passos para subir o container Docker 🐳:

### 1. Instalando o Docker para sistemas Linux (Exemplos feitos em Debian)
Adicione o repositório docker em sua lista de repositórios mais
[Mais informações](https://docs.docker.com/engine/install/)
```bash
$ sudo apt-get update
$ sudo apt-get install ca-certificates curl
$ sudo install -m 0755 -d /etc/apt/keyrings
$ sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
$ sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
$ echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
$ sudo apt-get update
```
Instale os pacotes
```bash
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
### 2. Clone o repositório em sua máquina de forma recursiva
```bash
$ git clone --recursive https://github.com/PedroClemonini/projeto_uptrips.git
```

### 3. Crie o (.env) do Laravel
```bash
$ cd uptrips_api/laravel-app
$ cp .env.example .env
```

### 4. Crie o (.env) do React
```bash
$ cd uptrips_frontend/app
$ cp .env.example .env
```

### 5. Subindo o container 📦

```bash
$ docker compose up --build -d
```

### 6. Instalando dependências
```bash
$ docker compose exec -T app composer install
```

### 7. Realizar as migrations do banco
```bash
$ docker compose exec -T app php artisan migrate
```
