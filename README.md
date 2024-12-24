# Comentários Vue.js

Este é um projeto simples criado com Vue.js que permite aos usuários adicionar comentários. O aplicativo é composto por dois componentes principais: `UserComment` e `FormTodo`. 

O componente `FormTodo` é responsável por capturar o nome e a mensagem do usuário, enquanto o componente `UserComment` gerencia e exibe a lista de comentários adicionados.

## Funcionalidades

- Adicionar comentários com nome e mensagem.
- Substituir o nome pelo valor "Anonymous" caso o campo de nome não seja preenchido.
- Excluir comentários da lista.

## Tecnologias Utilizadas

- **Vue.js**: Framework JavaScript para construção de interfaces de usuário reativas.
- **Bootstrap (opcional)**: Classes CSS para estilização dos botões e formulários.

## Estrutura do Projeto

```
- src/
  - components/
    - FormTodo.vue    # Formulário para adicionar comentários
    - UserComment.vue # Componente para exibir a lista de comentários
  - App.vue          # Componente principal
  - main.js          # Arquivo de entrada
```

## Instalação

Certifique-se de que você possui o [Node.js](https://nodejs.org/) instalado em sua máquina.

### Passos

1. Clone o repositório:
   ```bash
   git clone https://github.com/marcelodfreitas/vuejs-cli.git
   ```

2. Navegue até a pasta do projeto:
   ```bash
   cd vuejs-cli
   ```

3. Instale as dependências:
   ```bash
   npm install
   ```

## Executando o Projeto

### Ambiente de Desenvolvimento

Para rodar o projeto localmente:
```bash
npm run serve
```

Isso iniciará um servidor de desenvolvimento. O projeto estará acessível em [http://localhost:8080](http://localhost:8080).

### Ambiente de Produção

Para criar uma versão otimizada para produção:
```bash
npm run build
```

Os arquivos otimizados serão gerados na pasta `dist/`.

### Linter

Para verificar problemas de lint:
```bash
npm run lint
```

## Melhorias Futuras

- Adicionar armazenamento local (LocalStorage) para persistência de comentários.
- Melhorar o design com uma biblioteca de componentes como Vuetify ou TailwindCSS.
- Implementar testes unitários.

## Contribuição

Contribuições são bem-vindas! Siga os passos abaixo para contribuir:

1. Faça um fork do repositório.
2. Crie uma branch para sua feature/bugfix: `git checkout -b minha-feature`.
3. Commit suas alterações: `git commit -m 'Minha nova feature'`.
4. Faça o push da branch: `git push origin minha-feature`.
5. Abra um Pull Request no GitHub.

