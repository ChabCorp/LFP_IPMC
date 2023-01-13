Dans un premier temps, nous avons commencé par une analyse des données. Nous avons donc commencé par regarder les données brutes comprises dans un fichier texte dans lequel se trouvait le voltage mesurée dans différentes zones du cerveau en fonction du temps, comme on peut le voir sur la figure 1. 
[...]
Figure 1 : Données brutes du voltage mesuré dans le cortex préfrontal d'une souris en fonction du temps.

Nous avons ensuite, sous les conseils de l'expert en neurologie de l'institut de pharmacologie moléculaire et cellulaire de Nice (IPMC), réaliser une transformée de fourier rapide (FFT) normalisée par la taille de l'échantillon sur les données brutes. Comme on peut le voir .... 
[...]
Figure 2 : FFT des données brutes du voltage mesuré dans le cortex préfrontal d'une souris en fonction du temps.

A la suite de cette transformé nous avons réaliser une analyse du spectre de puissance du signal. Comme on peut le voir sur la figure 3, le spectre de puissance du signal est composé de plusieurs pics. Cela indique que ...... 
[...]
Figure 3 : Spectre de puissance du signal du voltage mesuré dans le cortex préfrontal d'une souris en fonction du temps.

De plus, notre expert nous a conseillé d'analyser la présence des ondes theta (5-12 Hz) et gamma (30 Hz). Nous avons donc appliqué un filtre passe bas à 4 Hz sur le signal avec une fenetre de 4 afin de supprimer toutes les ondes d'une fréquence supérieur à ce qui nous a permis de réduire légèrement le bruit du signal. Comme on peut le voir sur la figure 4.a, le spèctre du voltage en fonction du temps est plus épuré. Aussi dans la figure 4.b, on peut voir après application de la transformée de fourier rapide (FFT) normalisée par la taille de l'échantillon sur les données brutes, le spectre de puissance du signal est composé d'une multitude de pics. On observe un pic à 10 Hz qui correspond aux ondes theta en revanche le signal est toujours très bruité.
[...]
Figure 4 : a) Spèctre du voltage en fonction du temps après application d'un filtre passe bas. b) FFT normalisée par la taille de l'échantillon sur les données brutes après application d'un filtre passe bas.

Afin d'avoir une meilleur visualisation de l'ensemble des fréquences présentes dans le signal, nous avons réaliser une heatmap après application d'un algorythme des ondelettes de Morlet comme présenté dans la figure 5.
[3_copie]
Figure 5 : Heatmap de la fréquence en fonction du temps après application d'un algorythme des ondelettes de Morlet.

Ensuite, nous avons réaliser le même type de heatmap mais du PSD en fonction du temps. Comme on peut le voir sur la figure 6.b, on observe une forte proportion de fréquence entre 5 et 12 Hz à la fin de l'enregistrement du signal. 
[7]
Figure 6 : Heatmap du PSD en fonction du temps après application d'un algorythme des ondelettes de Morlet. a) fréquences super lentes (0.1-5 Hz), b) fréquences des ondes théta (5-12 Hz), c) fréquences des ondes gamma (12-30 Hz), d) fréquences des ondes super rapides (> 30 Hz).

Après ces nombreux essais, [souris trajectoire] ... Chab 