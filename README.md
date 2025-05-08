<h2>🛠️ Configuração do Biome no projeto (usando npm)</h2>

<ol>
  <li>
    <strong>Instale a extensão do Biome no VS Code:</strong><br />
    <a href="https://marketplace.visualstudio.com/items?itemName=biomejs.biome" target="_blank">Clique aqui para instalar</a>
  </li>

  <li>
    <strong>Instale o Biome como dependência de desenvolvimento:</strong><br />
    <pre><code>npm install --save-dev --save-exact @biomejs/biome</code></pre>
  </li>

  <li>
    <strong>Inicie o Biome no projeto:</strong><br />
    <pre><code>npx biome init</code></pre>
  </li>

  <li>
    <strong>Substitua o conteúdo do <code>biome.json</code> com a configuração abaixo:</strong><br />
    <a href="https://gist.github.com/fernandes-vinicius/0d0140af5b39970b8ab6d8aba5c00789" target="_blank">Clique aqui para ver o Gist</a><br />
    Copie o conteúdo e cole no seu <code>biome.json</code> na raiz do projeto.
  </li>

  <li>
    <strong>Crie o arquivo <code>.vscode/settings.json</code> e adicione o seguinte conteúdo:</strong><br />
    <pre><code>{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "biomejs.biome",
  "editor.codeActionsOnSave": {
    "source.fixAll.biome": "explicit",
    "source.organizeImports.biome": "explicit"
  }
}</code></pre>
    Isso garante que o editor organize tudo automaticamente ao salvar o arquivo.
  </li>

  <li>
    <strong>Adicione os scripts no seu <code>package.json</code>:</strong><br />
    <pre><code>"scripts": {
  "lint": "biome check ./src",
  "format": "biome check --write ./src",
  "check-types": "tsc --pretty --noEmit",
  "check-all": "npm run lint && npm run check-types && npm run build"
}</code></pre>
    Esses scripts ajudam a automatizar tarefas comuns com Biome e TypeScript.
  </li>
</ol>

<p>✨ Pronto! Agora seu projeto está configurado com o Biome para formatação e linting automáticos.</p>
