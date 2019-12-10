# Reactotron

#### 1. Instalação

**Instalação da versão desktop:**

https://github.com/infinitered/reactotron/releases (Arquivo .deb)

**Instalação no projeto**

`$ yarn add reactotron-react-js reactotron-redux`

**Arquivo src/config/ReactotronConfig.js**

```js
import Reactotron from 'reactotron-react-js';
import { reactotronRedux } from 'reactotron-redux';

if (process.env.NODE_ENV === 'development') {
  const tron = Reactotron.configure()
    .use(reactotronRedux())
    .connect();

  tron.clear();

  console.tron = tron;
}
```

**Remoção do erro de console no .eslintrc.js**

```js
'no-console': ["error", { allow: ["tron"]}]
```

**Importação (após as importações de módulos) do Reactotron no arquivo src/App.js**

```js
import './config/ReactotronConfig';
```

**Arquivo src/store/index.js**

Alterações no store e adição da variável enhancer:

```js
const enhancer =
  process.env.NODE_ENV === 'development' ? console.tron.createEnhancer() : null;

const store = createStore(rootReducer, enhancer);
```