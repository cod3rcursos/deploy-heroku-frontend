# Deploy Heroku (Frontend)

## Passos para o deploy...

### 1) Você fez o deploy do **_backend_**?

Siga os passos para deploy do **_backend_** [aqui](https://github.com/cod3rcursos/deploy-heroku-backend).

### 2) Clonar repositório do projeto **_frontend_**

```bash
$ git clone https://github.com/cod3rcursos/deploy-heroku-frontend
```

### 3) Entrar na pasta do projeto **_frontend_**

```bash
$ cd deploy-heroku-frontend
```

### 4) Instalar as dependência do projeto **_frontend_**

```bash
$ npm i
```

### 5) Alterar o arquivo **_src/consts.js_**

```javascript
export default {
    API_URL: 'https://<seu-backend>.herokuapp.com/api',
    OAPI_URL: 'https://<seu-backend>.herokuapp.com/oapi',
}
```

### 6) Executar o script para gerar o build de produção

```bash
$ npm run production
```

### 7) Adicionar e Commitar localmente o arquivo **_src/consts.js_**

```bash
$ git add .
$ git commit -am 'Ajustando URLs do backend'
```

### 8) Criar um projeto no Heroku via _Heroku CLI_

```bash
$ heroku create cod3r-my-money-app-frontend
```

> **IMPORTANTE**
> 
> Como exemplo, chamaremos a aplicação no Heroku de **cod3r-my-money-app-frontend**, mas você precisa escolher um outro nome único.

### 9) Selecionar o buildpack para NodeJS

```bash
$ heroku buildpacks:set heroku/nodejs
```

### 10) Configurar o repositório remoto

```bash
$ heroku git:remote -a cod3r-my-money-app-frontend
```

> **IMPORTANTE**
> 
> Usar o **nome** do seu projeto.

### 11) Fazer deploy da aplicação via **push** no repositório.

```bash
$ git push heroku master
```

### 12) Definir o tipo de escalonamento mínimo (grátis) - Passo **Opcional**

```bash
$ heroku ps:scale web=1
```

### 13) Abrir aplicação

```bash
$ heroku open
```

### 14) Consultar o log e verificar se tudo ocorreu bem - Passo **Opcional**

```bash
$ heroku logs --tail
```