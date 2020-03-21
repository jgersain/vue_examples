# gersain_app

## Vuex

Vuex puede ser utilizado para propagar eventos de componentes anidados a un nivel global de la aplicación

### Pasos para propagar un evento a nivel global

- Abrir el archivo store.js
- Generar un nuevo estado, con el valor inicial del modal
```
state: {
  modals: {
    login: false
  }
}
```
- Agregar una nueva acción, el cual contendrá la lógica que modificara el estado inicial, recibe un commit y el payload que se envia a la acción
```
actions: {
  TOGGLE_MODAL_STATE: ({ commit }, { name, value }) => {
    commit('SET_MODAL_STATE', { name, value })
  }
}
```
- Agregamos una mutación, la cual se encargará de hacer la modificación del estado, recibe un state y el payload de datos que modificaran el estado
```
mutation: {
  SET_MODAL_STATE: (state, { name, value }) => {
    state.modals[name] = value;
  }
}
```
- Lanzamos la acción del store, y le pasamos lo nuevos datos (esto es en el componente en donde se disparará el evento)
```
getLogin() {
  this.$store.dispatch('TOGGLE_MODAL_STATE', {
    name: 'login',
    value: true
  })
}
```
- Ahora es necesario llamar los datos nuevos desde el state, por tal motivo generamos getters para obtenerlos de una mejor manera (store.js)
```
getters: {
  modals: state => state.modals
}
```
- Actualizamos el componente global con los nuevos datos
```
import { mapGetters } from 'vuex';
computed: {
  ...mapGetters([
    'modals',
  ])
}
```
- Ahora la variable modal ya esta disponible, para acceder a ella y pasarla como props o como valor a un componente solamente hay que utilizarla directamente como `modals.login`
- Para hacer el proceso inverso, hay que generar un nuevo método 
```
closeModal() {
  this.$state.dispatch('TOGGLE_MODAL_STATE', {
    name: 'login',
    value: false,
  });
}
```
