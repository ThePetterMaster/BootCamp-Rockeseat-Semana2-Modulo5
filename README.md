# BootCamp-Rockeseat-Semana2-Modulo5

# O que é React?
Biblioteca para construção de interfaces

Tudo fica dentro do Javascript
````
import React from 'react';
import './button.css';
import icon from './button.png';
function Button() {
  return (
    <button>
      <img src={icon} />
    <button>
 );
}
````

# Componentização

A aplicação é dividida em componentes.Componente é uma parte independente da aplicação.

# JSX 

Escrever HTML dentro do JavaScript

# Babel / Webpack

 O browser não entende todo esse código;

O Babel converte o código JS de uma forma que o browser entenda;

O Webpack possui várias funcões:

• Criação do bundle, arquivo com todo código da aplicação;

• Ensinar ao JavaScript como importar arquivos CSS, imagens e etc;

• Live reload com Webpack Dev Server;

# Iníciando o projeto
````
yarn init -y
````

# Instalando babel e webpack
````
yarn add @babel/core @babel/preset-env @babel/preset-react webpack webpack-cli -d
````

# Instalando react 
````
yarn add react react-dom
````

# Arquivo de configuração do babel(babel.config.js)
````
module.exports={
    presets:[
        //traduz a sintaxe do javascript
        "@babel/preset-env",
        //traduz a sintaxe do react
        "@babel/preset-react"
    ],
};
````
# Arquivo de configuração do webpack
````
const path=require('path');
module.exports={
    //o arquivo local do arquivo js com sintaxe nova com nome de bundle.js 
    entry:path.resolve(__dirname,'src','index'),
    //o arquivo local para onde será colocada o arquivo com sintaxe antiga
    output:{
        path:path.resolve(__dirname,'public'),
        filename:'bundle.js'
    },
    //localização do arquivo que será atualizado constatemente("nodemon do react")
    devServer:{
        contentBase:path.resolve(__dirname,'public'),
    },
    module:{
        //vai dizer que o babel tem que traduzir antes do webpack
        rules:[
            {
                //traduzir apenas arquivos que terminem em .js
                test:/\.js$/,
                exclude:/node_modules/,
                use:{
                    loader:'babel-loader'
                },{
                test:/\.css$/,
                use:[
                    {loader:'style-loader'},
                    {loader:'css-loader'}
                ]
              },{
                test:/.*\.(gif|png|jpe?g)$/i,
                use:{
                    loader:'file-loader'
                }
                 
                
            }
            }
        ]
    }
}
````

# Scripts do package.json
Antes tem que ter o "yarn" no comando


````
"scripts": {
    "build2": "webpack --mode development",
    "build": "webpack --mode production",
    "dev": "webpack-dev-server --mode development"
 },
````
build2= o bundle.js fica legível(com quebra de linha e espaços.

build= o bundle.js fica compacto

dev=seria o nodemon do react. Após isso será possível ver em http://localhost:8080/

# Instalando biblioteca para carregamento de css pelo webpack

````
yarn add style-loader css-loader -d
````

# Instalando biblioteca para carregamento de imagens pelo webpack

````
yarn add file-loader -d
````
