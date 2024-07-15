## CommonJS vs ESModule

#### English

There are many differences between CommonJS and ESM, the most noticeable being the difference in syntax when importing or exporting a module.

```javascript
// With ESM
import http from "http";

// With CommonJS
const http = require("http");
```

The way to enable ESM in NodeJS projects is to edit the `package.json` file at the root of the project, adding the line `type:"module"`

---

#### Português

Existem muitas diferenças entre o CommonJS e o ESM, a mais perceptivel é a diferença de sintaxe na hora de importar ou exportar um modulo.

```javascript
// Com ESM
import http from "http";

// Com CommonJS
const http = require("http");
```

A maneira de ativar o ESM em projetos NodeJS é editando o arquivo `package.json` na raiz do projeto, adicionando a linha `type: "module"`

#### Links

- https://caiofuzatto.com.br/post/entendendo-ecmascript-modules/
