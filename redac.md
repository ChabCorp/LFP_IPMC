## Analyse descriptive 
Dans un premier temps, nous avons commencé par une analyse des données. Nous avons donc commencé par regarder les données brutes comprises dans un fichier texte dans lequel se trouvait le voltage mesurée dans différentes zones du cerveau en fonction du temps, comme on peut le voir sur la figure 1. 
[...]
Figure 1 : Données brutes du voltage mesuré dans le cortex préfrontal d'une souris en fonction du temps.

Nous avons ensuite, sous les conseils de l'expert en neurologie de l'institut de pharmacologie moléculaire et cellulaire de Nice (IPMC), réaliser une transformée de fourier rapide (FFT) normalisée par la taille de l'échantillon sur les données brutes. Comme on peut le voir .... 
[...]
Figure 2 : FFT des données brutes du voltage mesuré dans le cortex préfrontal d'une souris en fonction du temps.

A la suite de cette transformé nous avons réaliser une analyse du spectre de puissance du signal. Comme on peut le voir sur la figure 3, le spectre de puissance du signal est composé de plusieurs pics. Cela indique que ...... 
[...]
Figure 3 : Spectre de puissance du signal du voltage mesuré dans le cortex préfrontal d'une souris en fonction du temps.

De plus, notre expert nous a conseillé d'analyser la présence des ondes theta (5-12 Hz) et gamma (30 Hz) et de ne pas s'occuper des signaux dont la fréquence excède 120 Hz car ils ne sont pas biologiquement possible. Nous avons donc appliqué un filtre passe bas à 4 Hz sur le signal avec une fenetre de 4 afin de supprimer toutes les ondes d'une fréquence supérieur à ce qui nous a permis de réduire légèrement le bruit du signal. Comme on peut le voir sur la figure 4.a, le spèctre du voltage en fonction du temps est plus épuré. Aussi dans la figure 4.b, on peut voir après application de la transformée de fourier rapide (FFT) normalisée par la taille de l'échantillon sur les données brutes, le spectre de puissance du signal est composé d'une multitude de pics. On observe un pic à 10 Hz qui correspond aux ondes theta en revanche le signal est toujours très bruité.
[...]
Figure 4 : a) Spèctre du voltage en fonction du temps après application d'un filtre passe bas. b) FFT normalisée par la taille de l'échantillon sur les données brutes après application d'un filtre passe bas.

Afin d'avoir une meilleur visualisation de l'ensemble des fréquences présentes dans le signal, nous avons réaliser une heatmap après application d'un algorythme des ondelettes de Morlet comme présenté dans la figure 5.
[3_copie]
Figure 5 : Heatmap de la fréquence en fonction du temps après application d'un algorythme des ondelettes de Morlet.

Ensuite, nous avons réaliser le même type de heatmap mais du PSD en fonction du temps. Comme on peut le voir sur la figure 6.b, on observe une forte proportion de fréquence entre 5 et 12 Hz à la fin de l'enregistrement du signal. 
[7]
Figure 6 : Heatmap du PSD en fonction du temps après application d'un algorythme des ondelettes de Morlet. a) fréquences super lentes (0.1-5 Hz), b) fréquences des ondes théta (5-12 Hz), c) fréquences des ondes gamma (12-30 Hz), d) fréquences des ondes super rapides (> 30 Hz).

## Découpage des données 
### Découpage entre sample et choice
Comme nous avons pu le voir dans la partie précédente, l’analyse des données totales n’a pas été très concluantes. Notre expert nous a alors conseiller de découper nos données en plusieurs fenètre, tout d’abbord nous avons découpé en phase de sample et choice. Comme on peut le voir sur ces deux exemples (figure 7.a et figure 7.b), les résultats sont assez similaires entre eux. On observe sur le plot de la figure 7.c que si l'on superpose les deux phases et que l'on plot les db (µV²/Hz) en fonction du temps, on retrouve plus oiu moins les mêmes résultats. On observe cependant un pic a 100 Hz et une abscence d'ondes de fréquence proche de 50 Hz dans les deux phases d'études. Nous avons alors appliquer un algorithme d'ondelettes de haar afin de voir si les résultats étaient les mêmes. Comme on peut le voir sur la figure 7.d, les résultats sont très similaires l'abscence de pic a 50 Hz à été déplacé a 100 Hz.
[...]
Figure 7 : a) Exemple de découpage des données entre 60 et 600 s dans la phase de sample. b) Exemple de découpage des données entre 5000 et 5540 s dans la phase de choice. c) Plot des db en fonction du temps de la phase de sample et de la phase de choice. d) Plot des db en fonction du temps de la phase de sample et de la phase de choice après application d'un algorithme d'ondelettes de haar.

### Découpage en fenètre de 4 s dans la phase de sample
Nous avons sous les conseils de notre expert, découpé nos données en fenètre de 4 s dans la phase de sample. En effet cela avait pour but de réduire légèrement le bruit dans les données ainsi que nous permettre de déterminer si les signaux changeaient au cours de l'expérience. Nous avons donc réaliser un plot des db en fonction du temps pour chaque fenètre de 4 s (figure 8.a), on retrouve les mêmes résultats que précédent ce qui indique que les signaux ne changent pas ou peut au cours de l'expérimentation. Toujours dans une optique de réduction du bruit du signal, nous avons appliqué un filtre passe haut et passe bas entre 0 et 1.5 Hz nommé superslow(figure 8.b), 5 et 12 Hz nommé theta (figure 8.c), 12 et 30 Hz nommé gamma (figure 8.d) et enfin 30 et 120 Hz nommé super rapide (figure8.e). 
[...] 
Figure 8 : a) Plot des db en fonction du temps pour chaque fenètre de 4 s dans la phase de sample. b) Plot des db en fonction du temps pour chaque fenètre de 4 s dans la phase de sample après application d'un filtre passe haut et passe bas entre 0 et 1.5 Hz. c) Plot des db en fonction du temps pour chaque fenètre de 4 s dans la phase de sample après application d'un filtre passe haut et passe bas entre 5 et 12 Hz. d) Plot des db en fonction du temps pour chaque fenètre de 4 s dans la phase de sample après application d'un filtre passe haut et passe bas entre 12 et 30 Hz. e) Plot des db en fonction du temps pour chaque fenètre de 4 s dans la phase de sample après application d'un filtre passe haut et passe bas entre 30 et 120 Hz. 

Ces résultats ne nous semblais toujours pas concluant, après avoir été conseillé par un mathématicien de ... spécialisé dans l'analyse de signal notamment en biologie. Il nous a été conseillé de ... (Chab)


## Mise en place d'un suivi du chemin de la souris dans le T maze 
Après ces nombreux essais infructueux, notre expert en neurobiologie nous a demandé si il serait possible de mettre en place une méthode afin de suivre les déplacement de la souris au cours de l'expérience. En effet, comme on peut le voir sur la figure 9, les souris testés ont une première phase de sample dans lequel un des bras (aléatoirement choisis) du T-maze est fermé, elle n'ont donc accès qu'a un seul des deux bras contenant de la nourriture. Après cette phase de sample, la souris est placé dans le T-maze et doit choisir entre les deux bras. 
[...]
Figure 9 : Description du T-maze entre la phase de sample et la phase de choice.

Notre expert nous a alors fournis une séquence des déplacement de la souris en fonction de zones établies dans le T-maze (figure 10). Nous avons donc mis en place un algorithme très simple permettant de déterminer les différents chemins, en effet deux règles implicites ont été établies : 
- Si la souris passe de la zone A à la zone B puis C, et que l'on observe un retour dans la zone A, alors la souris à été déplacé par l'expérimenteur et le chemin n'est pas valide.
- Si la souris passe dans la zone F, alors l'expérience est en pause et le chemin correspond à la dernière lettre obtenu avant F. 

Pour cela, nous avons mis en place une fonction permettant de découper les différents trajets de la souris. Pour cela, nous parcourons la liste des zones, si la zone courante est A alors on continue a avancer dans la liste tant que l'on n'observe pas de nouveau un A ce qui correspond à une phase de sample. Ensuite, on reprend notre parcourt de la liste depuis le dernier A trouvé jusqu'a observer un E ou un D ce qui correspond à la phase de choice et on stoque les deux chemins dans une liste de chaine de caractère. 
[...]
Figure 10 : a) Exemple type des 20 premières zones rencontré par la souris dans le T-maze. b) Résultat obtenu par l'algorithme de détermination des chemins sur les 20 premières zones rencontré par la souris.