# React Toastify

## 1. Instalação

`$ yarn add react-toastify`

## 2. O uso

**Arquivo src/App.js**

Importação do ToastContainer

```js
import { ToastContainer } from 'react-toastify';
```

Chamada do componente para sumir automaticamente em 3 segundos (em qualquer lugar dentro das rotas)

```js
<ToastContainer autoClose={3000} />
```

Modelo de exemplo da função ao todo

```js
import store from './store';

function App() {
  return (
    <Provider store={store}>
      <BrowserRouter>
        <Header />
        <Routes />
        <GlobalStyle />
        <ToastContainer autoClose={3000} />
      </BrowserRouter>
    </Provider>
  );
}

export default App;
```

**Arquivo src/styles/global.js**

Importação dos estilos do Toast nos `estilos globais`

```js
import 'react-toastify/dist/ReactToastify.css';
```

**Arquivo src/store/modules/cart/sagas.js**

Importação do módulo

```js
import { toast } from 'react-toastify';
```

Uso do `Toast` em uma situação de erro

```js
if (amount > stockAmount) {
  toast.error('Quantidade solicitada indisponível no estoque.');

  return;
}
```