# Gerador de Nomes Fullstack -> Vue , GraphQL , Bootstrap , Node  (Projeto COMPLETO 2019 - Vue.js, GraphQL e Node)

# Como instalar o projeto e rodar 

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

## Install Bootstrap 
npm install bootstrap --save 

## Install Font Awaysome 
npm install font-awesome --save 

## Use view error in application 
"lint": "vue-cli-service lint --no-fix" -> Alterate in package.json 
* Don't correct error automatics 
npm run lint

## Definindo Regras para a Aplicação 
package.json Rules {}
"rules": {
      "quotes": ["error", "double" ], -> aspas 
      "indent": ["error", "tab"],-> espaços
      "semi": ["error", "always"] -> col
    },

## Diretivas - V-bind 

## Passar parametros com ENTER do teclado no Input 
v-on:keyup.enter="addPrefix(prefix)"


##Methodo Delete 
v-on:click="deleteSufix(sufix)"

