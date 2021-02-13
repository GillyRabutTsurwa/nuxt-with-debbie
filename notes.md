accessing nested directories with nested component
* making the folder, puting the word of the folder in front of the component file name and calling it as so. I do this with the work nested

second: like this. let's say we wanted to access the components under a folder named base without having to modify the name of our component (car ce nom pourraient devenir longs et bizzares).

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

Avec ceci, chaque fichier composant trouver dans le dossier base, qui est sous celui de components, sera automatiquement "prefixed" avec Base. Il nous faudra plus le faire manuellement comme auparavant

NOTE: TO access the mountains that are using the automatic nested way, via the code above, go the page ```MountainsDeux```

Success. All works well