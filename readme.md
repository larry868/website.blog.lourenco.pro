# Readme website laurentlourenco.pro

Ce repository contient les sources du site web [laurentlourenco.pro](https://laurentlourenco.pro)

Le site est généré avec [StudioJekyll](https://mikemaggire.github.io/blogging-studio-jekyll/guide/preparer-vs.html), dans un environnement Visual Studio Code sous Windows 10. StudioJekyll s'appuie sur Jekyll 3.8 et Boostrap4.

## Mises à jours

Le flow est le suivant :

1. S'assurer de bien avoir la dernière version des sources : [GitHub laurentlourenco/laurentlourenco.pro](https://github.com/laurentlourenco/laurentlourenco.pro)
1. Réaliser les modifications et tester le résultat en lançant le live rendering `CTRL + R`
1. Stopper le live `CTRL C`
1. Incrémenter la version dans le fichier `_studiojekyll/_version.yml`
1. Lancer la génération de la PROD avec la tache `sjekyll build PROD env.`.
1. Envoyez vos modifications sur git : commit & push
1. Rafraichissez la page [laurentlourenco.pro](https://laurentlourenco.pro) et vérifiez en bas le numéro de version.

## Auteurs

- [Mike Maggire](https://github.com/mikemaggire)  pour la structure originale du site.
- [Laurent Lourenço](https://github.com/laurentlourenco) pour le contenu.

## License

Tous droits réservés CC-BY-SA-4.0. Voir [licence](LICENSE.txt).
