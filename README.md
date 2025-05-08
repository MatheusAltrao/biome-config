<h2>🛠️ Configurando o Biome com NPM no seu projeto</h2>

<ol>
  <li>
    <strong>Instale a extensão do Biome no VS Code:</strong><br />
    <a href="https://marketplace.visualstudio.com/items?itemName=biomejs.biome" target="_blank">Biome Formatter</a>
  </li>

  <li>
    <strong>Instale o Biome no projeto:</strong><br />
    <pre><code>npm install --save-dev --save-exact @biomejs/biome</code></pre>
  </li>

  <li>
    <strong>Inicialize o Biome:</strong><br />
    <pre><code>npx biome init</code></pre>
  </li>

  <li>
    <strong>Substitua o conteúdo do arquivo <code>biome.json</code> pelo seguinte:</strong>
    <pre><code>{
  "$schema": "https://biomejs.dev/schemas/1.9.4/schema.json",
  "vcs": { "enabled": false, "clientKind": "git", "useIgnoreFile": false },
  "files": { "ignoreUnknown": false, "ignore": [] },
  "formatter": {
    "enabled": true,
    "indentStyle": "space",
    "indentWidth": 2,
    "lineEnding": "lf",
    "lineWidth": 120,
    "bracketSpacing": true,
    "useEditorconfig": true
  },
  "organizeImports": { "enabled": true },
  "linter": {
    "enabled": true,
    "rules": {
      "recommended": true,
      "nursery": {
        "useSortedClasses": {
          "fix": "safe",
          "level": "error",
          "options": {
            "attributes": ["className", "classList"],
            "functions": ["clsx", "cva", "tw", "tw.*"]
          }
        }
      }
    },
    "ignore": [".next"]
  },
  "javascript": {
    "formatter": {
      "jsxQuoteStyle": "double",
      "quoteProperties": "asNeeded",
      "trailingCommas": "all",
      "semicolons": "asNeeded",
      "arrowParentheses": "always",
      "bracketSameLine": false,
      "quoteStyle": "single",
      "attributePosition": "auto",
      "bracketSpacing": true
    }
  }
}</code></pre>
  </li>

  <li>
    <strong>Crie o arquivo <code>.vscode/settings.json</code> e cole o seguinte:</strong>
    <pre><code>{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "biomejs.biome",
  "editor.codeActionsOnSave": {
    "source.fixAll.biome": "explicit",
    "source.organizeImports.biome": "explicit"
  }
}</code></pre>
  </li>

  <li>
    <strong>Adicione os scripts ao seu <code>package.json</code>:</strong>
    <pre><code>"scripts": {
  "lint": "biome check ./src",
  "format": "biome check --write ./src",
  "check-types": "tsc --pretty --noEmit",
  "check-all": "npm run lint && npm run check-types && npm run build"
}</code></pre>
  </li>
</ol>

<p>🚀 Pronto! Seu projeto agora está com o Biome configurado para lint, formatação automática e organização de imports.</p>
