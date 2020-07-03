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
