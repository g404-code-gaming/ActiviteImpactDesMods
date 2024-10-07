# ActiviteImpactDesMods

But : Créer un mod qui ajoute une nouvelle plante comestible que les joueurs peuvent utiliser pour restaurer leur santé.

## Installation de Minetest :
Télécharge la version la plus récente de Minetest depuis [minetest.net.](https://www.minetest.net/)

## Création de la Structure du Mod :
- Dans le répertoire "mods" de Minetest, crée un nouveau dossier nommé "simple_plant_mod".
- À l'intérieur, crée un fichier init.lua où tu codes les fonctionnalités principales du mod.

## Écrire le Code Basique :

```lua
-- Register a new plant
minetest.register_node("simple_plant_mod:sweet_plant", {
    description = "Sweet Plant",
    drawtype = "plantlike",
    tiles = {"sweet_plant.png"},
    inventory_image = "sweet_plant.png",
    wield_image = "sweet_plant.png",
    paramtype = "light",
    sunlight_propagates = true,
    walkable = false,
    selection_box = {
        type = "fixed",
        fixed = {-0.25, -0.5, -0.25, 0.25, 0.5, 0.25},
    },
    groups = {snappy=3, flammable=2},
    can_dig = function(pos, player)
        return true
    end,
    on_use = minetest.item_eat(2),
})

-- Register crafting recipe (optional)
minetest.register_craft({
    type = "shapeless",
    output = "simple_plant_mod:sweet_plant",
    recipe = {"group:leaves"},
})
```

## Création des Textures :
Crée une image nommée "sweet_plant.png" qui représente ta plante. Utilise un éditeur d'images pour créer une simple texture de 16x16 px.
Place la texture dans le dossier du mod.

## Activer le Mod dans Minetest :
Lance Minetest, crée un nouveau monde et assure-toi que "simple_plant_mod" est activé dans les paramètres des mods pour ce monde.

## Test et Amélioration :
Connecte-toi au monde, trouve ta plante, et teste ses fonctionnalités.
Améliore le mod en ajoutant des fonctionnalités comme croissance à partir de graines, ou effets spéciaux.
