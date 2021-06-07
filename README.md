# Configuración Principal de Enzyme en React JS 17^

Antes de iniciar test o instalar Enzyme, necesitamos ejecutar el siguiente comando para poder ejecutar los test sin problema en las versiones de React superiores a **17^**


`$ npm install --save-dev enzyme`

## Instalación 
Antes de realizar cualquier paso aquí mencionado, es necesario revisar la documentación oficial de [Enzyme](https://enzymejs.github.io/enzyme/ "Enzyme") y seguir la instalación recomendada.

Actualmente Enzyme tiene problemas para la versión 17 en React, por lo que para usar enzyme en la versión 17 tenemos que ejecutar los siguientes comandos:

`$ npm install --save-dev @wojtekmaj/enzyme-adapter-react-17`

**Puedes ver la documentación al respecto en el siguiente enlace: [Enzyme for React 17 ](https://github.com/wojtekmaj/enzyme-adapter-react-17 "Enzyme for React 17 ")**

### Instalación de enzyme-to-json

Aquí puede ver la documentación para instalar [enzyme-to-json](https://www.npmjs.com/package/enzyme-to-json "enzyme-to-json")

Sería suficiente con ejecutar este comando dentro del directorio del proyecto:

`$ npm install --save-dev enzyme-to-json`


## setupTests.js

Configuración en setupTests .js

Verifica hacer las importaciones correspondientes: 

```javascript
import Enzyme from 'enzyme';
import Adapter from '@wojtekmaj/enzyme-adapter-react-17';
import {createSerializer} from 'enzyme-to-json';

Enzyme.configure({ adapter: new Adapter() });
expect.addSnapshotSerializer(createSerializer({mode: 'deep'}));
```

## Importaciones en test.js
  
  ```javascript
import Enzyme from 'enzyme';
import Adapter from '@wojtekmaj/enzyme-adapter-react-17';
import {createSerializer} from 'enzyme-to-json';

Enzyme.configure({ adapter: new Adapter() });
expect.addSnapshotSerializer(createSerializer({mode: 'deep'}));
```
