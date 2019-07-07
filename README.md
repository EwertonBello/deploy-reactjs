# Deploy ReactJS
Fazendo deploy de um app default do ReactJS no GitHub Pages<br/>
<Strong>ReactJS: </Strong>(https://pt-br.reactjs.org/)<br/>
<Strong>gh-pages: </Strong>(https://www.npmjs.com/package/gh-pages)<br/>
<Strong>Demo: </Strong>(https://ewertonbello.github.io/deploy-reactjs/)

### Procedimento

1. Crie um repositório e vincule seu projeto a ele, na pasta do seu projeto faça:
    ```
    git init
    git add .
    git commit -m "primeiro commit"
    git remote add origin https://github.com/NomeDeUsuario/nome-do-repositorio.git
    git push -u origin master
    ```
2. Depois insira uma linha no `package.json` do seu projeto, `"homepage": "https://nomedeusuario.github.io/nome-do-repositorio"`. 
<br/>Exemplo:
    ```
    "name": "deploy-app",
    "version": "0.1.0",
    "private": true,
    "homepage": "https://ewertonbello.github.io/deploy-reactjs",
    ```
3. Agora faça o build do seu app, dentro da pasta do seu projeto execute `npm run build` ou `yarn build` se preferir utilizar o yarn. Obs: insira a propriedade `basename={process.env.PUBLIC_URL}` no BrowserRouter do arquivo index.js caso ocorra problemas de rotas como não encontrar a página inicial (404).<br/>
    ```
    <BrowserRouter basename={process.env.PUBLIC_URL}>
        <Switch>
        .
        .
        .
    ```
4. Depois utilize o comando `npx gh-pages -d build` para fazer o deploy da pasta build do seu app no branch gh-pages, utilizando o pacote gh-pages.
