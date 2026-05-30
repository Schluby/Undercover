# Thèmes distants — Jeu de l'Imposteur

Ce dossier contient les thèmes publiés que l'application télécharge automatiquement.

## Structure

```
remote/
  index.json              # Liste de tous les thèmes (lu par l'app au démarrage)
  themes/
    general.json
    league_of_legends.json
    minecraft.json
    one_piece.json
    anime.json
    ...
```

## Format de index.json

```json
{
  "schema_version": 1,
  "themes": [
    {
      "id": "league_of_legends",
      "name": "League of Legends",
      "emoji": "⚔️",
      "version": 2,
      "url": "themes/league_of_legends.json",
      "pairs": 230
    }
  ]
}
```

## Ajouter un nouveau thème

1. Créer ou éditer le JSON dans le dossier `assets/themes/` du projet
2. Incrémenter la `version` du thème dans son JSON
3. Lancer :
   ```powershell
   cd scripts
   python generate_index.py
   ```
4. Git push :
   ```powershell
   cd remote
   git add .
   git commit -m "Nouveau thème : X"
   git push
   ```
5. Les apps installées détecteront le nouveau thème au prochain lancement
