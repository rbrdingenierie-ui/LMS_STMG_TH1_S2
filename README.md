# Les sources du droit — parcours en autonomie (1re STMG, Droit, Séquence 2)

Site web statique (HTML, CSS, JavaScript) : aucune installation, aucun serveur, aucun compte pour les élèves.
Le contenu reprend votre cours corrigé (`Sequence_2_corrig_.docx`) : 5 modules (un par séance), 32 étapes, avec un
diagnostic de départ (5 affirmations), un quiz final (20 questions, 4 par module, avec un résultat « acquis / à consolider / à revoir » pour chaque module) et un bilan à rendre.

| Module | Titre | Étapes | Temps indicatif |
|---|---|---|---|
| 1 | La Constitution | 6 | 2 h |
| 2 | Le droit de l'Union européenne | 7 | 1 h |
| 3 | La loi et le règlement | 6 | 3 h |
| 4 | La jurisprudence et le droit négocié | 8 | 2 h |
| 5 | La hiérarchie des normes | 5 | 2 h |

Les temps viennent de votre fiche de séquence (total : 10 h, diagnostic : 10 min). Ils sont donnés à l'élève à titre indicatif.
Pour les changer, ouvrez `js/content.js` et cherchez `duree` (par module) ou `dureeTotale` / `dureeDiag`.

## 1. Mettre le site en ligne avec GitHub Pages

1. Connectez-vous à GitHub, puis **New repository** (nom au choix). Choisissez **Public** (GitHub Pages gratuit sur un compte personnel).
2. Dans le dépôt : **Add file → Upload files**.
3. Décompressez le zip, puis glissez-déposez **le contenu** du dossier : `index.html`, les dossiers `css`, `js`, `img`
   (et `.nojekyll` si votre ordinateur l'affiche — il est facultatif). Les fichiers doivent être **à la racine** du dépôt,
   pas dans un sous-dossier.
4. Cliquez sur **Commit changes**.
5. **Settings → Pages → Build and deployment → Source : Deploy from a branch**, branche `main`, dossier `/ (root)`, puis **Save**.
6. Au bout d'une à deux minutes, l'adresse apparaît en haut de la page Pages :
   `https://VOTRE-IDENTIFIANT.github.io/NOM-DU-DEPOT/`
   C'est cette adresse (ou un QR code qui y mène) que vous donnez aux élèves.

**Variante la plus simple** : déposer uniquement le fichier unique `index.html` (version « un seul fichier » : texte, images et styles
sont tous dedans). Il suffit alors de remplacer le fichier `index.html` du dépôt (**Add file → Upload files**, même nom, **Commit changes**).

**Mettre à jour** : remplacez le fichier concerné (même nom), puis « Commit changes ». Le site se met à jour en une à deux minutes.

**Important après une mise à jour du contenu** : l'avancement des élèves est enregistré dans leur navigateur. Cette version utilise un
nouvel emplacement de sauvegarde : un élève qui avait commencé la version précédente repart d'un parcours vierge.

Testez toujours l'adresse sur un téléphone avant de la diffuser.

## 2. Utiliser le site sans Internet (variante)

Le dossier peut aussi être donné tel quel (zip) : décompresser, puis ouvrir `index.html` dans un navigateur récent (double-clic).
Seules les vidéos demandent une connexion.

## 3. Vidéos et liens

Deux vidéos : « La Constitution » (module 1, lien Lumni) et « Qui fait la loi ? » (module 3, lien Google Drive issu de votre QR code,
avec un lien secondaire vers Lumni). **Vérifiez que le partage du fichier Drive est réglé sur « Toute personne disposant du lien »**, sinon
les élèves verront une demande d'accès.
Pour changer un lien : ouvrez `js/content.js` (sur GitHub, icône crayon), cherchez `"url":` puis remplacez l'adresse entre guillemets.

## 4. Fonctionnement pédagogique

- **Reprise du travail** : le bouton de l'accueil et le bouton « Continuer : étape X » en haut de chaque page de module ramènent l'élève à sa première étape non terminée. Un oubli de réponse est signalé précisément (nombre restant, première question entourée en orange) et le résultat d'une vérification s'affiche toujours à l'écran.
- **Accueil et pages de module** : objectifs pédagogiques et savoirs associés, avec les deux pictogrammes de votre cours (`img/ico_objectifs.webp`, `img/ico_savoirs.webp`).
- **Contexte** : la situation de départ de votre cours (Samia et son projet d'embauche) est reprise sur l'accueil, au début de chaque module et sur la première étape.
- **Progression verrouillée** : l'élève ne peut ouvrir l'étape suivante qu'après avoir terminé l'étape en cours. « J'ai terminé cette étape » n'est
  disponible qu'une fois toutes les activités de l'étape faites (vrai/faux, relier, textes à trous, tableaux, réponses rédigées, synthèses).
- **Exercices à relier** : on touche un élément puis sa réponse (un trait apparaît) ; utilisable au clavier et au doigt, sans glisser-déposer.
- **Synthèses rédigées** : la synthèse doit faire au moins 15 mots pour être validée ; la proposition de correction apparaît ensuite et l'élève
  s'auto-évalue.
- **Synthèse visuelle** (dernière étape de chaque module) : l'élève réalise la sienne sur papier ; il coche « J'ai réalisé ma synthèse visuelle »,
  puis le modèle s'affiche.
- **Quiz final** : 20 questions, 4 par module, tirées des objectifs de chaque module. Après correction, un tableau « Mes acquis, module par module » indique pour chaque module « acquis » (3 bonnes réponses sur 4 ou plus), « à consolider » (2 sur 4) ou « à revoir » (moins), avec un lien pour revoir le module. Les mêmes résultats figurent dans le bilan. Le quiz est verrouillé tant que les 32 étapes ne sont pas terminées (l'élève qui tente d'y accéder est ramené à sa première étape non terminée). Les questions se trouvent dans `js/content.js`, repère `"quiz"` ; chaque question porte le numéro de son module dans le champ `m`.
- **Badges** (gamification) : 15 badges, page « Mes badges » (`#/badges`) et aperçu sur l'accueil. Ils se gagnent tout seuls : diagnostic fait, premier exercice sans faute, chacun des 5 modules terminé, parcours complet (32 étapes), diagnostic refait, « maîtrise » de chaque module au quiz final (3 bonnes réponses sur 4 ou plus), quiz sans faute. Une notification apparaît quand un badge est gagné (elle se ferme seule). Un badge gagné reste acquis, même si l'élève recommence un exercice. Les noms, pictogrammes et conditions se modifient dans `js/content.js` (repère `"badges"`) ; le nombre de badges obtenus figure dans le bilan. Les badges sont enregistrés avec le reste du travail de l'élève (sur son appareil, comme le reste).
- **Arcade de Mnémosia** (jeu de révision, lien dans `js/content.js`, repère `"arcade"`) : verrouillée sur l'accueil tant que les 32 étapes ne sont pas terminées ; elle se débloque dès la dernière étape terminée, sans attendre le quiz ni le bilan. Ce verrou est pédagogique : l'adresse reste visible dans le code du site pour qui sait l'y chercher.
- **Points** : calculés sur les exercices auto-corrigés ; ils servent à l'élève à se situer, pas à la notation. Les réponses rédigées ne sont pas notées.
- **XP (points d'expérience)** : un compteur « ⭐ N XP » reste affiché en haut de chaque page ; il monte à chaque bonne réponse à un exercice corrigé automatiquement (diagnostic, exercices, quiz final, y compris le diagnostic refait en fin de parcours), avec un « +N » animé. **1 bonne réponse = 1 XP** ; le total possible (94 XP) est affiché sur l'accueil (« 0 XP sur 94 possibles », avec une barre de progression). **Les XP ne baissent jamais** : le meilleur résultat de chaque exercice est conservé, même si l'élève recommence. Les réponses rédigées, comparées à la réponse attendue, ne rapportent pas d'XP. Le total figure dans le bilan (tableau et texte à rendre). Les XP sont enregistrés avec le reste du travail, sur l'appareil ; un élève qui avait déjà commencé retrouve ses XP calculés d'après ses exercices déjà corrigés. Comme les points, ils servent à se situer, pas à la notation.
- **Temps passé** : le site relève le temps passé sur chaque module (et sur le diagnostic et le quiz final). Il est affiché sur la page de chaque module (« Temps déjà passé ici : 25 min »), sur sa carte de l'accueil, puis repris dans **Mon bilan** : colonne « Temps passé » et ligne « Temps total passé sur le cours » dans le tableau, rubrique « TEMPS PASSÉ » dans le texte à rendre. Le temps est compté tant que la page est ouverte **et active** : il se met en pause quand l'onglet est caché ou après 3 minutes sans aucune action (clic, frappe, défilement, toucher). C'est une mesure approximative, enregistrée sur l'appareil comme le reste (rien n'est envoyé) ; elle ne distingue pas un élève qui lit de un élève qui laisse la page ouverte en bougeant la souris : à prendre comme une indication, pas comme une preuve ni pour la notation. Pour changer le seuil de pause, ajouter dans `js/content.js`, juste après `"meta": {`, la ligne `"inactiviteSec": 300,` (en secondes ; 180 par défaut).
- **Non repris dans le site** : le TD noté et l'évaluation sommative.

## 5. Ce que le site enregistre (et ce qu'il ne transmet pas)

- **Rien n'est envoyé à qui que ce soit par le site.** Ni serveur, ni compte, ni suivi, ni statistiques.
- La progression, les réponses et les synthèses restent dans le navigateur de l'élève (stockage local de l'appareil).
  Si l'élève change d'appareil, utilise la navigation privée ou vide les données du site, il retrouve un parcours vierge.
  **Conseil** : faire travailler les élèves à partir de l'adresse web (GitHub Pages) plutôt qu'avec le fichier `index.html` ouvert depuis un dossier de l'ordinateur : l'enregistrement automatique y est plus fiable (certains navigateurs le gèrent mal pour un fichier ouvert directement). La version « un seul fichier » convient pour une consultation ponctuelle ou hors connexion ; l'élève peut toujours utiliser « Télécharger ma sauvegarde » dans Mon bilan.
- Pour que vous voyiez son travail, l'élève ouvre **Mon bilan**, indique prénom, nom et classe, puis clique sur « Imprimer / enregistrer en PDF »
  (c'est la seule façon de rendre son travail proposée dans le bilan) et vous remet le document obtenu (ENT, mail).
  « Télécharger ma sauvegarde » (`.json`) et « Charger une sauvegarde » permettent de reprendre son travail sur un autre appareil.

## 6. Confort de lecture et usage mobile

Bouton « Accessibilité » en haut de chaque page :

- **Police adaptée** : Verdana, espacement élargi (utile en cas de dyslexie).
- **Contraste renforcé**.
- **Taille du texte** : 7 niveaux, jusqu'à +50 %.
- **Mode FALC** : texte plus grand, lignes courtes et aérées, éléments secondaires masqués (durées, icônes de contexte).
- **Lecture au survol** (synthèse vocale du navigateur) et **réduction des animations**.

Vérifié sur ordinateur, sur téléphone en 375 px et 320 px de large, en mode paysage, avec texte agrandi : aucun débordement horizontal,
zones tactiles d'environ 44 px de haut, champs de saisie en 16 px (pas de zoom automatique sur iPhone), navigation complète au clavier,
tableaux larges défilables au clavier, fenêtre d'agrandissement des images fermée avec Échap.
Le site n'a pas été conçu spécifiquement pour les lecteurs d'écran (pas de transcriptions détaillées des images).

## 7. Contenu du dossier

```
index.html       page unique du site
css/style.css    mise en forme
js/content.js    tout le contenu pédagogique (textes, questions, corrections, durées, liens de vidéos)
js/store.js      sauvegarde locale
js/blocks.js     types d'activités (vrai/faux, relier, textes à trous, remise en ordre, tri, QCM, écrits…)
js/app.js        navigation, verrouillage, menu, accessibilité, bilan
img/             bandes dessinées, documents et synthèses visuelles (WebP)
```

Cours conçu par Benjamin RICHARD.
