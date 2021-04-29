dynamic pages (tu en sais)
for dynamic pages, we add an underscore. we already know this.

NOTE: DO NOT BE THROWN OFF. slug and id are exactly the same concept.
la difference que je vois, possiblement" ce que slug peut être une chaine des lettres et id et reservé seulement aux chiffres. Si j'ai tort, je vais revenir pour changer les notes, but I'm confident voila ce qui se passe.
Dans ce cas-ci, slug et id ne sont pas tout pareil. et ça depend sur le API utiliser pour accueilir les données. Some API data will contain slug, some will contain id, and some both. 

IMPORTANT: They still work the EXACT SAME WAY
for the sake of keeping naming consistent, I will rechange the name of the dynamic page from _id back go _slug.

I see, the dynamic page could be named anything, it just has to mach the name in the params.(pageName).
So if we name our page _mountains, it will be params.mountains. 
At the moment we named it _slug, so it is params.slug.


#### Attempt to summarise the notes above
- this is the exact same functionality you are using in your **Nuxt Pokedex App**. don't overthink it.
- it is an easy way to make our pages dynamic using data from our API
- think of slug like an id. so far i do not see much difference between their purposes
- we are defining the the data to use to make the page dynamic in our MountainCards.vue page in our NuxtLink
- then we are using that data (again, called the slug) to make our dynamic page in pages/_slug/index.vue
- the _ before the directory name under pages indicates that the page is dynamique.