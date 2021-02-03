Ok. This one was cool, et il aurait pu me donner une solution pour mon site web portfolio. 

IMPORTANT: I changed the file structure for the app pour qu'il ressemble celle de Debbie

Tout ce qu'il faut faire c'est ajouter le mot Lazy avant le composant: le composant ```<Dog/>``` deviendra ```<LazyDog>```

L'evidence de lazy loading s'affiche sur les onglets Network/XHR et Network/JS.
for XHR, the the data in our component will be fetched only after clicking the button (the way our component is designed. We use a v-if to show our lazy component only if our show value becomes true. This value is switched to true by clicking the show mountains button)

this is more visible in XHR/JS. when lazy loading, we don't see our Javascript for our component until the button is clicked. I'll come back to this later.

TODO: for testing, remove the world lazy from the component call, and refresh the page. remarques-tu de différence aux onglets Network/XHR et Network/JS?

TODO: check if this works for manually imported components as well