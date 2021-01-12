learning about auto components.
with autocomponents, we don't have to manually import components in our script tag. c'est à cause d'un paramètre certain dans notre fichier nuxt.config.js. cette ligne-ci: 

```javascript
  // Auto import components (https://go.nuxtjs.dev/config-components)
  components: true,
```

pourvu que la valeur de cette propriété (components) est ```true```, il nous faut pas importer les composant manuellement. mais si la valeur est ```false``` on doit faire les importations comme d'hab.

NOTE: puisque je sais cette chose, comment vais-je gérer mes composants dans mon site portfolio ? je vais decider...