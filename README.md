# Vue.js

Vue es un __framework__ open source de JavaScript para la construcción de interfaces de usuario.  diferencia de otros marcos 
monolíticos, Vue está diseñado desde cero para ser incrementalmente adoptable. La biblioteca principal 
se centra solo en la capa de vista y es fácil de recoger e integrar con otras bibliotecas o proyectos 
existentes. Por otro lado, Vue también es perfectamente capaz de impulsar aplicaciones sofisticadas de 
una sola página cuando se usa en combinación con herramientas modernas y bibliotecas de soporte.

La forma más fácil de probar Vue.js es utilizando su __cdn__, puede crear un archivo _index.html_ 
e incluir Vue con:

```html
<!-- production version, optimized for size and speed -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```
>Ejemplo [vue con cdn](https://codesandbox.io/s/github/vuejs/vuejs.org/tree/master/src/v2/examples/vue-20-hello-world).

La característica de ser __progresivo__ permite la adaptabilidad de vue, incluso con otros lenguajes de
programación, esto es posible gracias a su cdn, insertando pequeñas funcionalidades o script que
realicen ciertas tareas en medio de un proyecto PHP por ejemplo. Pero también podemos tener un 
proyecto completo y robusto con solo vue.

Una de las características que diferencian a Vue es su discreto sistema de reactividad. Los modelos 
simplemente son objetos de JavaScript. Cuando los modifique, se actualizará la vista. Esto hace que 
el gestor de estados sea simple e intuitivo, pero también es importante entender como funciona para 
prevenir algunos errores comunes. En esta sección, vamos a indagar en algunos detalles de bajo nivel 
del sistema de reactividad de Vue.

### Componentes
Ejemplo simple de un componente en Vue:
```javascript
// Definir un nuevo componente llamado ButtonContainer
Vue.component('ButtonContainer', {
  data: function () {
    return {
      count: 0
    }
  },
  template: '<button v-on:click="count++">Me ha pulsado {{ count }} veces.</button>'
})
```
Los componentes son instancias reutilizables de Vue con un nombre: en este caso, <ButtonContainer>. 
Podemos usar este componente como un elemento personalizado dentro de una instancia de Vue raíz 
creada con new Vue:

```html
<div id="components-demo">
  <ButtonContainer></ButtonContainer>
</div>
```

### Archivos .vue
Los componentes den vue tiene pueden ser organizados en archivos .vue e importarlos para ser 
reutilizados en diferentes compoenentes. Estos componentes tiene un estructura como la giguiebte:
```html
<template>
    <button v-on:click="count++">Me ha pulsado {{ count }} veces.</button>
</template>

<script>
    // exportacion del componente
    export default {
        name: 'ButtonComponent', // nombre del cmponenete 
        props:{
            // Propiedades que recibe el compoenete
        },
        data() {
            return {
                count: 0
            }
        },
        methods: {
           // finciones o metodos a ser ejecutados por evento
        }
    }
</script>

<style scoped>
    <!-- Estilos de la pagina   -->
</style>
```

## Ejemplo Webapp Vue
#### Instalación de dependencias
```shell script
yarn install
```
#### Despliegue servidor de desarrollo
```shell script
yarn serve
```
#### Compilación para producción
```shell script
yarn build
```
