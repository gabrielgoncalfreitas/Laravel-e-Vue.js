# Anotações - Aula 252

- Para importar via CDN a versão 2.6.14 do Vue.js ao projeto:
```html
<script src="https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
```
<br>

#### O Vue.js funciona da seguinte maneira:
- Nós criamos uma **nova instância** da `Vue` passando como parâmetro ao seu construtor, o elemento em que a aplicação será montada;
- Por padrão, toda a aplicação Vue.js é montada dentro de uma `div` com `id="app"`. Semelhantemente ao React.js que também é montado dentro de uma `div` porém com `id="root"`. Para iniciar a instância do Vue.js:
- Para iniciar a instância do Vue.js:

  ```html
  <div id="app"></div>
  ```

  ```javascript
  const vm = new Vue({  // vm === ViewModel
      el: '#app', // (# -> id) ou (. -> class)
  })
  ```
- Também é possível, ao invés de passar o id, passar como parâmtro a classe do element:

  ```html
  <div class="app"></div>
  ```

  ```javascript
  const vm = new Vue({  // vm === ViewModel
      el: '.app', // (# -> id) ou (. -> class)
  })
  ```
<hr>

- O atributo `data` guarda em si ***variáveis*** e ***atributos***. Sendo assim, trabalhando de forma *reativa* a cada frame, nunca perdendo o **ESTADO**. 

- Para passar uma simples *string* e renderizá-la dentro da nossa aplicação montada *(`#app`)* é possível guardar o valor da mensagem dentro de data desta forma:

    ```html
    <div id="app">
        {{ mensagem }}
    </div>
    ```

    ```javascript
    const vm = new Vue(options = {
        el: '#app',
        data: { // **variáveis**/atributos reativos
            mensagem: 'Primeiro template controlado pelo Vue'
        }
    })
    ```

***Obs 1***.: é importante observar que dentro da div em que a aplicação será montada, foi inserido um "*Double Mustache*" (ferramenta semelhante ao Blade do Laravel), e dentro deste doublue mustache foi passado como atributo a ser renderizado, a *variável* de nome **mensagem**. É importante lembrar que o mesmo nome dentro do double mustache deve ser o da variável, se não, o esperado pelo programador não acontecerá.

***Obs 2***.: Este vínculo entre o atributo passsado ao double mustache e a variável guardada dentro de `data` se chama ***BINDING***, que em resumo, significa *vinculação de um nome a um valor ou comportamento*.