### React Native Template Basic Barebones

<!-- ABOUT THE PROJECT -->

## Sobre o Projeto

Este projeto visa a criação de um template que possa ser utilizado no momento de criação de projetos utilizando React Native, visto que o processo de instalação e configuração das libs no início de um projeto podem gerar certa complexidade e muitas vezes até erros que atrasam o processo, atrapalhando assim o fluxo de desenvolvimento.

<!-- GETTING STARTED -->

## Começando

Para conseguir utilizar o template, seja através do React Native CLI ou com uma cópia local dos arquivos, siga os passos abaixo.

### Instalação

1. Para instalar e utilizar esse template o processo é bem simples, basta criar um projeto novo utilizando o comando:

```sh
react-native init NomeDoProjeto --template basic-barebones
```

2. Depois do projeto criado você pode deletar o arquivo `App.js` da raiz, pois o arquivo `index.js` agora aponta para a pasta **src**.

Com isso o projeto será criado com todas as dependências do template devidamente instaladas e linkadas, tal como os arquivos de configuração que são copiados para o projeto.

---

#### Passo Adicional no Android

Para que os gestos sejam habilitados no Android é necessário um passo a mais, que é bem simples, abra o arquivo `android/app/src/main/java/<pacote_do_projeto>/MainActivity.java`, e comece importando os pacotes como abaixo:

```java
// ...
import com.facebook.react.ReactActivity;
// Importações adicionadas
import com.facebook.react.ReactActivityDelegate;
import com.facebook.react.ReactRootView;
import com.swmansion.gesturehandler.react.RNGestureHandlerEnabledRootView;
```

Feito a importação vamos criar um método novo, logo abaixo do `getMainComponentName()`, ficando:

```java
public class MainActivity extends ReactActivity {
  @Override
  protected String getMainComponentName() { ... }
  // Método adicionado
  @Override
  protected ReactActivityDelegate createReactActivityDelegate() {
    return new ReactActivityDelegate(this, getMainComponentName()) {
      @Override
      protected ReactRootView createRootView() {
        return new RNGestureHandlerEnabledRootView(MainActivity.this);
      }
    };
  }
}
```

---

<!-- LICENSE -->

## Licença

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.