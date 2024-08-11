# [Version 👉 française du Lisez-Moi](#version_francaise)
# [English 👉 version of the Read-Me](#english-version)

<a id="version_francaise"></a>

# Oh my que ça a pris du temps à mettre en ligne ! 😮‍💨

Version française plus complète à venir, promis! Désolée 🦐

En attendant: quelques détails, ainsi que d'autres problèmes résolus:

## Quelques outils de mon «&nbsp;stack&nbsp;»

- [Tweego](https://github.com/tmedwards/tweego) (Merci Thomas M.
  Edwards);
- [Twee 3 Language
  Tools](https://marketplace.visualstudio.com/items?itemName=cyrusfirheir.twee3-language-tools);
- [Twine bien sûr!](https://twinery.org);


## Messages d'erreurs bizarres

Quand j'ai enfin vu mon premier passage d'histoire à la place d'une page
d'erreur 404, j'avais deux alertes cryptiques :

``` Error [tw-user-script-0]: Invalid or unexpected token. ```

et 

``` Error [tw-user-script-1]: Invalid or unexpected token. ```

Les deux arrivaient parce que j'avais des caractères tels que des
accents dans mes titres de passages. Merci à [Greyelf](https://twinery.org/forum/discussion/comment/15162/#Comment_15162) pour avoir fait remarquer
ça, autrement je n'aurais pas vraiment eu l'idée aussi vite:

> My first guess would be that your Story either has Passage Names with
> an illegal character in them (don't use punctuation or
> meta-characters) or that the contents of the first passage contains an
> illegal character(s) in it which needs to be parsed by Javascript
> using Regular Expressions to be shown so if there are illegal
> character(s) then you could get the error message you saw. 

Il y a avait aussi : `gh-pages deploy error: Action failed with "The
process '/usr/bin/git' failed with exit code 128"` qui je pense était dû
à ce que je devais configurer mes permissions et les secrets de
`GH_PAGES_DEPLOY_TOKEN`... mais normalement je ne devrais pas avoir à le faire.

Oh et...peut-être que, quand un script compile un fichier dans un
fichier `index.html` qui se trouve dans la page «&nbsp;Gh-Pages&nbsp;»,
il faut régler le déploiement de la branche en question dans les
*settings* 😜.

### Le format d'histoire!

Je voulais le format SugarCube le plus récent (2.36.1), qui n'était pas inclus
avec la version de Tweego que j'avais téléchargé (2.30.0 quelque chose).

Donc, il a bien fallu aller chercher ce dossier de format et le mettre au bon
endroit (dans la racine du projet --*root*).''

### Quelques dépendances mises à jour

- setup-go: https://github.com/actions/setup-go/releases/tag/v5.0.1
- jaxxstorm / action-install-gh-release:
  https://github.com/jaxxstorm/action-install-gh-release/releases/tag/v1.12.0
- actions/checkout@v4
- peaceiris/actions-gh-pages@v4

## Comment assurer une version bilingue ?

Cette section est en développement et sert à documenter quelques
efforts.

J'ai tenté d'inclure les deux langues en même temps sur une page, en
changeant le CSS pour l'anglais et en créant un *toggle* confectionné à
partir du [Day and Night Mode Sample Code de
HiEv](https://hiev-heavy-ind.com/Sample_Code/Sample_Code.html#Day%20and%20Night%20Mode%20Setting).

Pour l'instant ça ne fonctionne pas bien car le réglage n'est plus actif
après le premier passage alors:

- [ ] TODO : publier une question à ce propos sur le forum Twine.

## D'autres trucs *fancy* à envisager

- Re-créer une animation CSS de [machine à écrire](https://css-tricks.com/typewriter-animation-that-handles-anything-you-throw-at-it/).
- Explorer d'autres [APIs publics](https://github.com/public-apis/public-apis) en plus de ceux de [cat facts](https://github.com/alexwohlbruck/cat-facts)!
- Explorer des [APIs peu documentés](https://jvns.ca/blog/2022/03/10/how-to-use-undocumented-web-apis/) (avec considération et respect bien
  sûr!);
- [ ] TODO : Créer un API.
- [ ] TODO : Changer l'histoire pour avoir le choix de quelles punitions
  la terre va infliger.
- [ ] TODO : ajouter l'histoire du monstre microplastique Godzilla carte
  de crédit.
- [ ] TODO : ajouter le jeu de lançage de tomates sur des *space
  invaders* composés de Teslas pilotées par des armées de compagnies de
  consultants.
  

<a id="english-version"></a>

# Too long, didn't read (TLDR)

An evolving interactive [Twine](https://twinery[.org) story (using the
[SugarCube story format](https://www.motoslave.net/sugarcube/2/) and
[Tweego command line compiler](https://www.motoslave.net/tweego/docs/))
about earth eating the ultra-rich. 

Kindly find digressions, many thanks, and more or less technical details below.

## Wow that really took a while to put online ! 😮‍💨

Many people really dig writing code. Others
are very much into other kinds of writing, or "*graphies*" such as dance
(chore*graphy*), photo*graphy*, calli*graphy*, or into design,
poetry, painting, drawing, and so on —and they
have more or less time for programming. A lot of people combine
practices. Some of them transpose ideas from an art or a science to
another, —-from different kinds of writing-- making their way towards awesome sauce.

Nowadays though, it takes a special kind of stubborn to get going with
code beyond the basics and deal with the mayhem and *N*th circles hell of
🔥 💣 💥 👹 👿 👺 😈 💀 👻 🤯... The silver lining: more strength in
persistence along with higher tolerance to a
unique kind of discomfort.

This repository is a mess of different writings. Though so far, I'd say
I've give more attention to much less than 1% of this repository's
code: the tiny bits of code that that didn't work. The code that didn't compile.

### What took so long ?

I have a big problem with writing on a computer. I'm seldom happy with
where and how I write what --talk about writer's block! If you're
looking for endless ways to procrastinate, this graces the sundae with a
cherry that will magically appear on top every time you eat it 🍒. 

![I love you computer](./media/happy-in-love-gif-by-line-friends.gif)

In this case, I wanted to explore [Twine](https://twinery.org) with Visual
Studio Code as a text editor. I found the Twee 3 language tools
extension and had local fun until I decided I wanted to recreate this
[fantastic
setup](https://blog.lazerwalker.com/azure,/game/dev/2020/01/16/a-modern-developers-workflow-for-twine.html)
[Emilia Lazer-Walker](https://github.com/lazerwalker) detailed to publish
stories through
continuous integration.

I was soooo motivated. I didn't give up 🔥💪🔥! Not through the cryptic
error messages --especially the one whose best solution is
to just restart the code editor...and which takes in retrospect an
absurdly long time to figure out! 

And that explains the almost 8 hours over 2
days it took to make this work. 

#### I had to update a few things

I went though both of Emilia Lazer-Walker's tutorials I found: [this one
on Dev.to](https://dev.to/lazerwalker/a-modern-developer-s-workflow-for-twine-4imp)
and the one I linked to above. I also found much wisdom in the comments
and am very grateful to Emilia Lazer-Walker as well as the commenters
and countless contributors to forums I've roamed into to look up errors.

With my gruff --but functional-- knowledge of node.js and npm, I
managed to update dependencies. I now have this [GitHub action workflow](https://github.com/schoukah/Twine_Manger_les_riches_Eat_the_rich/blob/main/.github/workflows/build.yml)
which --as of the last commit date you'll find-- still works.

So here we are. Thanks again everyone \\( ﾟヮﾟ)/




