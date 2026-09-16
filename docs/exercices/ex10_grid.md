# Exercice 10 - CSS Grid

## Partie 1

Après les grenouilles et les zombies, on va maintenant arroser un jardin avec le tutoriel [Grid Garden](https://codepip.com/games/grid-garden/){target=_blank}. Complétez les 28 niveaux.

![ex08_01](../../images/ex10_01.png){.center .shadow}

## Partie 2

Dans votre dossier designweb créez un sous-dossier nommé **ex10_grid** ou vous allez créer les fichiers des parties 2 et 3 de cet exercice.

Reproduisez la mise en page suivante en utilisant **Grid** pour la disposition principale dans un fichier **index.html**.

![ex08_02](../../images/ex10_02.png){.center .shadow}

!!! astuce

    - Ajoutez cette règle css en premier dans votre fichier css, elle va permettre d'utiliser la totalité de la page sans être obligé de redimensionner les containers : 

    ``````css
    body {
      margin: 0;
      min-height: 100vh;
    }
    ``````

    - J'ai utilisé une grille 3x3 pour cet exercice
    
- Utilisez les balises `<nav>`, `<header>`, `<article>`, `<aside>` et `<footer>` pour créer les conteneurs et les items.
- Votre conteneur principale (le "Grid Container") comportera ==3 colonnes et 3 lignes==.
- La première colonne `<nav>` a une largeur fixe de **200 pixels**.
- Utilisez l'unité de mesure **fr** pour les colonnes 2 et 3: la colonne du centre doit être 4 fois plus grande que la colonne de droite.
- La hauteur des lignes sera exprimé avec l'unité de mesure vh, **60vh** pour la ligne du centre et **20vh** pour chacune des deux autres.
- Le texte dans chacune des sections doit être centré horizontalement et verticalement et avoir une taille 3 fois plus grande que le défaut (utilisez l'unité **rem** pour la taille de la police et Flexbox pour réaliser l'alignement).
- L'image dans la section du centre (article) doit être aussi centré.
- Bien sûr l'image et les couleurs sont à votre choix. Par contre assurez-vous que ==l'image ne déborde pas de son conteneur==.

## Partie 3

Créez dans votre répertoire **ex10_grid** un nouveau fichier html nommé **article.html** et reproduisez l'article suivant. Prenez le temps de lire toutes les instructions avant de vous lancer dans le projet.

<figure markdown>
  ![Maquette partie 3](../../images/ex10_03.png){.center .shadow}
  <figcaption><a href="../../images/ex10_03.png" target="_blank">Taille réelle</a></figcaption>
</figure>

### Mise en page

- L'article est centré et il y a une marge de chaque côté de celui-ci
- La disposition est fait avec Grid et peut être décomposée en 4 zones : 
    - Le nom de l'auteur et la date
    - Le titre et le sous-titre de l'article
    - Le texte sous l'article (qui est affiché en deux colonnes)
    - La colonne de texte à droite.

!!! Astuce

    Pour centrer l'article, je lui ai donné une largeur maximale avec la propriété **max-width** et une marge automatique à droite et à gauche avec **margin: 0 auto** (le 0 correspond à la marge en haut et en bas, vous pouvez aussi l'ajuster).

<figure markdown>
  ![Maquette partie 3](../../images/ex10_grid_layout.png){.center .shadow}
  <figcaption>Visualisation de mon découpage Grid (<a href="../../assets/images/ex10_grid_layout.png" target="_blank">Taille réelle</a>)</figcaption>
</figure>

### Texte

Essayez de reproduite le plus fidèlement possible la maquette présentée. Pour formater le texte j'ai utilisé les propriétés suivantes, à vous de voir si vous voulez les utiliser : **text-align**, **font-size**, **letter-spacing**, **line-height**, **font-weight**

Le texte du titre et le sous-titre
`````` html title="Titre"
<div>
    <h1>Hawaii’s Online Gaming Curse</h1>
    <h2>The island’s physical isolation adds milliseconds of latency to an internet connection. In competitive eSports, milliseconds matter.</h2>
</div>
``````


Voici le texte de l'article divisé en deux parties. La première partie est affiché sur ==deux colonnes== sous le titre de l'article. Dans cette partie il y a un extrait mis en évidence, c'est la section avec la balise **blockquote**.

`````` html title="Première partie texte"
<section>
  <p>It was a Thursday at around 10 p.m., and the weekly <em>League of Legends</em> tournament was underway at PC Gamerz, a gaming cafe in Honolulu, Hawaii. The store was cool and dark inside, lit by the glow of monitors and a neon-green Monster energy drink sign plugged into the wall. Most of the patrons — almost all young men — were fixated on their screens, but occasionally something would happen in a game, and a corner of the room would break out into raucous commentary.</p>

  <p>This tournament was just for fun, but some of the players seemed to harbor quiet ambition to get more serious about the game. <em>League of Legends</em> is the most watched, most played competitive video game in the world, with professional leagues sponsored by the likes of Intel, Geico, and Monster Energy. According to <a href="http://www.esportsearnings.com/games">esportsearnings.com</a>, <em>League of Legends</em> tournaments have awarded $38 million since the game started in 2009. One player attending the weekly tournament, Blaise Lum (handle: Too Tilted), said he plays around 50 hours a week. I asked if he had considered going pro. “I’m nowhere near that good,” he demurred. “Maybe one day, you never know.”</p>

  <p>If Lum wanted to become professional, he’d face an obstacle that’s merely an inconvenience for most <em>League</em> players in Hawaii, but a significant disadvantage for the serious ones. The game’s server is in Chicago. That means if you live in the Midwest, your computer can communicate with it almost instantaneously. If you’re in L.A., it can take roughly 60 milliseconds. But if you’re in Hawaii, it can take 120 milliseconds, with some players reporting as long as 200 milliseconds. And at the highest echelons of competitive video gaming, milliseconds matter.</p>

  <p>We rarely think about the physicality of the internet. In 2006, former Senator Ted Stevens of Alaska was ridiculed for saying the internet was “not a big truck” but rather “a series of tubes.” While Stevens clearly had a limited understanding of the internet, he was right in one sense: The internet is mostly a series of fiberoptic tubes, wrapped in protective layers of steel and plastic, that run above ground and under the sea.</p>

  <p>There are some very specific situations in which the physical limitations of the internet come to the fore. Probably the best-known example is high-frequency trading, in which traders set up shop <a href="https://www.telegraph.co.uk/finance/newsbysector/banksandfinance/10736960/High-frequency-trading-when-milliseconds-mean-millions.html">as close to stock exchanges as possible</a>. These limitations are also a <a href="https://motherboard.vice.com/en_us/article/how-high-speed-communications-networks-are-making-remote-surgery-realistic">big concern</a> for the emerging field of remote surgery, in which a doctor in the U.S. might operate on a patient in France.</p>

  <blockquote class="extrait">
      <hr class="ligne-top"/>
          We rarely think about the physicality of the internet
      <hr class="ligne-bas"/>
  </blockquote>

  <p>High frequency traders, remote surgeons, and competitive eSports players are all worried about the same thing: latency, which is the lag time between when users at different ends of a connection register a piece of data. Another word for this is ping, which refers to a test in which a machine sends a small data packet to another machine and calculates how long it takes to come back. Low ping will make a connection seem faster. High ping will make it seem slower. In reality, the data is traveling at the same speed, it’s just going farther, or making more stops that add small delays along the way.</p>
</section>
``````

!!! Astuce

    Pour disposer le texte sur deux colonnes, utilisez la propriété [column-count](https://www.w3schools.com/css/css3_multiple_columns.asp){target=_blank}

La deuxième partie du texte est simplement affiché dans la colonne de droite

`````` html title="Deuxième partie texte"
<section>
  <p>In <em>League</em> and other eSports games, playing on a high ping is a big disadvantage. The goal of the game is to set up defenses to protect your base while pushing forward to capture the enemy’s base, and there are typically lightning bolts and fireballs and slime-spitting dragons shooting across the screen. Playing on a high ping means players may not see all of the action that happens in a game. “It's harder for us to dodge them,” said Devin Wolery, the owner of PC Gamerz. “Or when we attack, they they can dodge it easier.” Or as Lum said, “Those extra seconds, even like milliseconds, they just make you feel really off.”</p>

  <p>In 2015, Riot Games, which publishes <em>League of Legends</em>, <a href="http://kotaku.com/league-of-legends-pros-arent-happy-about-riots-latest-l-1723450285">moved</a> the game’s servers from Los Angeles to Chicago in order to “improve connection quality for the vast majority of [North American] players.”</p>

  <p>The change evened out latency for players on the east and west coasts, but it doubled latency for Hawaii players overnight.</p>

  <p>Latency can really screw things up for a young eSports scene, said Zack Johnson, who runs gg Circuit, a global tournament provider for gaming centers like PC Gamerz. Players on the mainland sometimes say they don’t want to compete against Hawaii players, he said, because the high ping throws things off.</p>

  <p>“It really is that they’re out on an island all by themselves,” Johnson said. “In basketball, the hoop is always 10 feet. Every field is always the same. In eSports, there is so much difference in latency, it’s very hard to make that playing field even.”</p>

  <p>That’s partly why all the big tournaments — the ones where the winning team gets cash prizes of over $1 million — happen in big stadiums, and in person. It’s not just for the spectacle; it’s because otherwise it would be difficult to guarantee a fair game. “We haven't had any professional players come out of Hawaii since the server change,” Wolery said.</p>

  <p>That doesn’t mean no professional players have come out of Hawaii. Dyrus, birth name Marcus Hill, <a href="https://www.youtube.com/watch?v=3l7TaWNeDvE">played</a> for multiple pro <em>League</em> teams before retiring in 2015 at the ripe age of 23. Matthew Elento, 19, who played as MattLife and now Matt, is a starter for Team Liquid, a well-known eSports organization based in the Netherlands and L.A. that fields teams in multiple games.</p>

  <p>“Any kid playing video games in Hawaii would know the struggles of playing from Hawaii,” Elento, who now lives in L.A., said. “You have latency for everything.”</p>

  <p>Latency doesn’t really matter until you get to the highest levels of competition, Elento added, because top players have extremely quick reaction times. It takes years of training to get good enough to go pro, and for 95 percent of that time, he said, ping wasn’t a factor. But in that last stretch, when he was playing against expert players, it really hurt.</p>

  <p>He had to learn how to “see into the future,” he said, and predict and input moves in advance. Elento likens the scenario to that of a football player, but “instead of being a regular football player, he has to close his eyes for a quarter of a second for every second, and he has to judge all of his decisions based on information he knew before, and he has to just plug in the information for the last quarter of a second.”</p>
</section>
``````

