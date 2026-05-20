# Porfolio
## exemple de code
- <span style='color:red'> html </span>

```html

            <button commandfor="tp4-navigation-accessible" command="show-modal">
              Voir les détails du projet
            </button>
            
            <dialog id="tp4-navigation-accessible">
              <p class="affichage"> détails du projet</p>
              <h2>Projet Portfolio: navigation accessible</h2>
              <div class="section_semaine_indicatif"><p>Semaine 9</p>  <div class="pop-over_projet"><p>TP</p></div></div>
              <p class="objectif">Création d'une navigation accessible conformément aux recommandations WCAG.</p>
              <div class="apprentissage_vrac"><p>Apprentissage en vrac:</p><div class=" some-Pop_overs"> <div class="pop-over"><p>navigation par régions</p></div><div class="pop-over"><p>menu adaptatif (responsive) accessible</p></div></div></div>
 <button commandfor="tp4-navigation-accessible" command="close">Fermer</button>
</dialog>


```
- <span style='color:red'> css </span>
```css
.lignedutemps {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
justify-content: flex-start;

   
 position: relative;
    width: 2px;
    background-color: var(--couleur-entete);

}
```
-----------
## questions 
### Questions-clés 
1.	Explique ce qu’est l'approche en amélioration progressive et donne un exemple concret tiré d'un de tes TPs.
html d'abord (c'est la base du document), css ensuite(pour la décoration) et parce que de un on peut deja faire marcher a peu pres tout sans, et qu'il prend le plus de temps a charger, en dernier on fait le javascript.
2.	Quelle est la différence entre `em` et `rem`
em: relative à la taille de police du parent direct ou de lui-meme. 
rem. relative à la taille de police de l'element racine du document, c'est à dire le <html>
3.	Pourquoi privilégie-t-on les `rem` dans les déclarations de dimensions et de média queries dans les TPs ? Donne un exemple.
parce qu'en premier lieu, les tailles de polices seront plus uniformisées parce que ils s'appuisent sur un seul élément universel et non eux-même, ce qui permet entre-autre une accessibilité optimale.
4.	Qu’est-ce qu’une erreur 404?
quand un document ou une page est introuvable pour plusieurs raisons différentes
Banque de questions possibles
1.	Comment fonctionne la cascade en CSS ? Quelles sont les sources de styles et leur ordre de priorité ?
hierarchisation des styles, afin de déterminer la valeur donnée pour chaque propriété de chaque élément
2.	Explique le calcul de spécificité avec les quatre colonnes (a, b, c, d). Compare `.intro` et `div ul li a`.

| a.selecteur universel     | b.Sélecteurs de classe, attributs et pseudo-classes   | c. selecteur d'id               | d. les style appliqués directement sur un element html     |
.intro serait plus précis que div ul li a et va dans les selecteur de classe. div va dans le a. parce qu'il est le selecteur le plus universel

3.	Qu'est-ce que le modèle de boîte CSS ? Quelle est la différence entre `content-box` et `border-box` ?
4.	Pourquoi on applique `box-sizing: border-box` avec l'astuce d'héritage `*, *::before, *::after { box-sizing: inherit }` ?
5.	Explique la nomenclature BEM (Block, Element, Modifier). Donne un exemple où tu choisis `__titre` plutôt que `__h1` et explique pourquoi.
6.	Qu'est-ce que l'approche mobile-first ? Pourquoi on l'utilise plutôt que desktop-first ?
7.	Explique la différence entre un « hard » Reset CSS (Eric Meyer) et Normalize.css. Lequel as-tu utilisé dans tes TPs ?
8.	Comment fonctionne l'héritage CSS ? Donne deux propriétés qui s'héritent et deux qui ne s'héritent pas.
### TP1 — Flexbox et HTML sémantique
Questions-clés
1.	Pourquoi utiliser `<header>`, `<main>`, `<footer>`, `<nav>`, `<section>`, `<article>` plutôt que des `<div>` génériques ? Donne deux bénéfices concrets (accessibilité, SEO – search engine optimization, ou autre).
accessibilité: les balises mentionnées avant les divs sont plus indicatif selon l'endroit dans le quel tu te retrouves sur la page.
search engine optimization: prend moins de temps au système pour reconnaitre la section dans laquelle tu est.
2.	Explique comment fonctionne flexbox : conteneur parent vs items enfants. Quelles sont les propriétés du conteneur (`display: flex`, `flex-direction`, `justify-content`, `align-items`, `gap`, `flex-wrap`) et comment les as-tu utilisées dans le TP1 ?
flex: appliqué sur l'élément parent, display: flex; permet un meilleur control sur la direction dans lequels seront placés les éléments (flex-direction), sur l'alignement (justify-content, align-items, etc.) et sur l'espacement (margin, padding, etc.)
Banque de questions possibles
1.	À quoi sert la balise `<picture>` avec ses `<source media="...">` ? Quel ordre as-tu mis pour le mobile-first et pourquoi ? picture sert à pré-déterminer les tailles d'image selon la taille d'écran
2.	Pourquoi `<figcaption>` doit-il être à l'intérieur de `<figure>` et pas dans `<picture>` ?
parce que c'est une legende d'image mais pas tout les image on besoin d'en avoir un figcaption, et picture s'occupe plutot d'ajuster l'image selon l'écran
3.	À quoi sert `<time>`? Donne un exemple typique d'utilisation. 
à sturcturer des informations temporelles de manière standardisée.
peut être utilisée entre autres pour archiver une date de publication ou rendre accessible un évènement pour qu'un utilisateur puisse placer l'évènement dans son calendrier numérique
4.	Pourquoi peut-on marquer certains mots en anglais avec `<span lang="en">` ? Quel est l'impact pour un lecteur d'écran ?
5.	Quelle est la différence entre `justify-content` et `align-items` dans un conteneur flex ? Donne un cas d'usage pour chacun.
justify-content est pour l'axe horizontal tendis que align items est pour l'axe vertical. cela sert principalement à aligner le contenu pour rendre le tout visuellement attrayant. un exemple pour "align-items" serait les élément liens dans le menu mobile, qui permetterait un bon alignement basique 
6.	Comment as-tu géré la transition mobile → desktop dans le header et le footer du TP1 ? Quelle propriété flexbox a permis le passage de vertical à horizontal ? flex-direction. il suffit de bien diriger les éléments selon l'écran.
7.	Qu'est-ce qu'une stratégie d'intégration ? Pourquoi annoter la maquette avant d'écrire du HTML ?
une stratégie d'intégration est appliqué afin de réduire la tache de cherche et trouve avec quelle propriété de quel élément aura quelle valeur lorsque viendra le temps d'écrire le html.
8.	Pourquoi mettre les majuscules avec `text-transform: uppercase` plutôt qu'en tapant directement le texte en majuscule dans le HTML ?
ou font-variant: small-caps; C'est pour permettre au texte de garder son format original dans le cas ou on ne veut plus la propriété c'est bien plus écologique pour le temps. 
9.	Pourquoi la hiérarchie des titres (`h1` à `h6`) doit-elle être respectée sans saut de niveau ? Quel outil permet de tester ça ?
accessibilité pour mieux se retrouver dans la page. l'Outil qui permet de le vérifier entre autre serait Le W3C validator en ligne.
### TP2 — Grille CSS (CSS Grid)
Questions-clés 
1.	Explique ce que fait `grid-column: 1 / -1` sur un item de grille. Pourquoi c'est si pratique pour faire un élément à fond perdu (« bleed ») dans une grille à plusieurs colonnes?
 parce que ca permet de le placer directement et efficacement à la dernière ligne sans qu'il n'y est de grand risque de dépassement. 
2.	Quelle est l’avantage d’utiliser `grid-template-area` plutôt que plusieurs déclarations `grid-column-start/end` et `grid-row-start/end`?
plus rapide et moins de répititions
3.	Qu'est-ce que l'unité `fr` ? En quoi diffère-t-elle des pourcentages ? : Fraction de l’espace restant.
Banque de questions possibles
1.	Comment définit-on une grille de base avec `display: grid` ? Quelle est la différence entre `grid-template-columns` et `grid-template-rows` ?
2.	Que fait `grid-template-columns: repeat(12, 1fr)` ? Et `repeat(auto-fit, minmax(250px, 1fr))` ?
3.	Qu'est-ce que l'unité `fr` ? En quoi diffère-t-elle des pourcentages ?
parce que les pourcentage prennent une valeur fixe, les "fr" sont pour la fraction de l'espace restant. le contenu ou colonne en fr vont s'ajuster selon l'espace qui reste.
4.	Comment fonctionne `gap`? Quelle est la différence avec une marge appliquée à chaque item ?
5.	Quelle est la différence entre `justify-items`, `align-items`, `justify-content` et `align-content` dans une grille ? Donne un exemple où tu utilises chacun.
6.	Comment as-tu géré le passage d'une grille mobile (1 colonne) à une grille desktop (plusieurs colonnes) ? Avec quelle media query ?
7.	Quelle est la méthode qu’il faut utiliser pour éviter de répéter une valeur plusieurs fois dans la déclaration d’une grille? (ex. : `grid-template-columns : 1fr 1fr 1fr 1fr;`)
### TP3 — Formulaire interactif (camouflage des radios)
Questions-clés 
1.	Pourquoi camoufle-t-on un input `radio` avec une technique CSS plutôt que de le cacher avec `display: none` ? Quels problèmes d'accessibilité `display: none` et `visibility: hidden` causent-ils ?
la balise n'est plus visible et dont ignoré à la navigation au clavier.
2.	Décris la technique du camouflage visuellement accessible (souvent appelée `.sr-only`, `.screen-reader-only` ou `.visually-hidden`)? Quelle est son utilité?
de faire disparaitre l'élément, mais sans l'ignorer complètement ce qui permet à l'utilisateur d'être certain d'avoir fait tout le formulaire.
3.	Quels sont les deux attributs qui nous permettent de relier un élément `<label>` à son `<input>`? for et id
Banque de questions possibles 
1.	Pourquoi associer chaque `<input>` à un `<label>` correspondant ? Que se passe-t-il quand on clique sur le label ?
2.	Quelle est la différence entre `<input type="radio">` et `<input type="checkbox">` ? Quand utiliser l'un plutôt que l'autre ?
3.	À quoi sert l'attribut `name` sur des boutons radios ? Que se passe-t-il si plusieurs radios partagent le même `name` ? Et si chacune a un `name` différent ?
4.	À quoi servent `<fieldset>` et `<legend>` dans un formulaire ? Pourquoi sont-ils particulièrement importants pour des groupes de radios ?
5.	Comment styliser visuellement le label associé à un radio coché ? Quel pseudo-sélecteur CSS utiliser? ::before, donc se qui vient avant l'élément
6.	Quelle est la différence entre `+` (sélecteur de voisin direct) et `~` (sélecteur de voisin indirect) ? Donne un cas où l'un fonctionne et pas l'autre. direct ne fonctionne pas si le voisin sélectionné ne l'est pas. 
7.	À quoi sert `:focus-visible` ? Pourquoi est-ce important quand on camoufle un input radio ?
oui, parce que juste :focus peut aussi être appliqué quand on clic sur un élément.
8.	Comment indiquer qu'un champ est obligatoire ? Quelle est la différence entre l'attribut et juste un astérisque visuel?

9.	À quoi sert l'attribut `aria-live`? Quelle est la différence entre sa valeur `polite` et `assertive`?
10.	Quand utiliser `<input type="email">`, `<input type="tel">` ou `<input type="number">` plutôt que `type="text"` ? Quel est le benefice?
 Surtout en mobile ? la précision pour le système. 
11.	À quoi sert l’attribut `inputmode` ?
### TP4 — Navigation accessible
Questions-clés
1.	Pourquoi ajouter le bouton de la navigation mobile en JavaScript seulement? Explique le concept d’amélioration progressive dans tes mots.
2.	À quoi sert un lien d'évitement (« skip link » ou « aller au contenu principal ») ? Comment le construit-on et pourquoi est-il visible seulement au focus ?
 pour le cacher pour ceux qui ne naviguent pas au clavier puisqu'ils n'en on pas de besoins #
Banque de questions possibles
1.	Pourquoi utiliser un `<button>` pour ouvrir/fermer le menu hamburger plutôt qu'un `<a href="#">` ? Quelles sont les différences sémantiques et conséquences pour le clavier et les lecteurs d'écran ?
2.	Explique le rôle de `aria-expanded` et `aria-controls` sur le bouton hamburger. Pourquoi faut-il mettre à jour `aria-expanded` en JavaScript quand on bascule le menu ?
3.	Pourquoi avoir une seule liste de liens en HTML (même menu mobile et desktop) plutôt que de dupliquer le menu ?
4.	Quelle est la différence entre `aria-label` et `aria-labelledby` ? Donne un exemple d'utilisation pour une `<nav>`.
5.	Pourquoi la navigation doit-elle être utilisable au clavier seul (Tab, Shift+Tab, Entrée, Espace) ? Comment teste-t-on ça ?
6.	Pourquoi retirer les styles de mise en évidence tel que `outline: none` sans alternative est-il un problème majeur d'accessibilité ? Comment fournir un focus visible personnalisé sans casser l'accessibilité ?
7.	Pourquoi les rôles ARIA implicites (comme `<nav>` qui a déjà `role="navigation"`) ne doivent pas être redoublés ? Donne deux autres exemples d’éléments sémantiques qui permettent d’éviter d’ajouter un attribut `role` .
8.	Pourquoi `display: none` sur notre menu mobile pouvait être acceptable, alors que c'est problématique pour un input camouflé (TP3) ? Quelle est la nuance ?
9.	Si un menu hamburger ouvre un panneau qui couvre la page, où devrait aller le focus ?
10.	Quelle autre interaction au clavier, à ajouter en JavaScript, est recommandée pour conserver l’accessibilité? 

