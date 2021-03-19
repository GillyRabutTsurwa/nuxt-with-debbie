## Accessing nested directories in Nuxt

* We will use two methods, the manual way, and the automatic way (duquel un peu de configuration dans le fichier nuxt.config.js est requiert)
* making the folder, puting the word of the folder in front of the component file name and calling it as so. I do this with the folder named *nested*
* as a result, MountainCards.vue becomes NestedMountainCards.vue

second: like this. let's say we wanted to access the components under a folder named whose name won't match the folder as before, (we are using the name *base* as an example) without having to modify the name of our component (car ce nom pourraient devenir longs et bizzares).

En fait ceci, evidemment, dans notre nuxt.config.js

```js
components: {
    dirs: [
        "~/components", {
            path: "~/components/base,
            prefix: "Base"
        }
    ]
}
```

Avec ceci, chaque fichier composant trouvé dans le dossier base -- qui est sous celui de components -- sera automatiquement "prefixed" avec Base. Il nous faudra plus le faire manuellement comme auparavant

NOTE: To access the mountains that are using the automatic nested way, via the code above, go the page ```MountainsDeux```

Success. All works well