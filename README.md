# Traitement-de-signal-tp1
Représentation temporelle et fréquentielle 

Considérons un signal périodique x(t) constitué d’une somme de trois sinusoïdes de fréquences 440Hz, 550Hz, 2500Hz.
 𝐱(𝐭) = 𝟏. 𝟐𝐜𝐨𝐬 (𝟐𝐩𝐢𝟒𝟒𝟎𝐭 + 𝟏. 𝟐) + 𝟑𝐜𝐨𝐬(𝟐𝐩𝐢𝟓𝟓𝟎𝐭) + 𝟎. 𝟔𝐜𝐨𝐬(𝟐𝐩𝐢𝟐𝟓𝟎𝟎𝐭)

1.	On représente le signal continu dans le temps x(t)par un signal discret dans le temps, qui peut être traité numériquement (convenable dans notre cas d’étude sur Matlab qui est essentiellement un outil d’analyse numérique contrairement à Maple ou Maxima qui sont des outils d’analyse symbolique).
 Pour cela on a défini une fréquence d'échantillonnage fe=1e4 Hz et un nombre d’échantillons N=10000. On note que plus N est grand plus le signal ressemble à un signal continu, ceci s’explique par le pas de discrétisation qui tend vers 0 quand N tend vers l’infini d’après la formule Δf= fe/N (fe étant la fréquence d’échantillonnage)

![1](https://user-images.githubusercontent.com/86806375/209026780-8d850bef-dc57-4b3d-87b7-c29e538e0b7b.JPG)


2.	Pour une discrétisation du signal dans le domaine fréquentiel on a recours à la transformée de fourrier discrète du signal x(t) en utilisant la commande fft.
Les 6 pics obtenus dans le spectre sont identiques deux à deux par rapport à 5000. C’est une symétrie conjuguée centrée sur fe/2. Les pics prennent les valeurs 440,550 et 2500 correspondant aux fréquences dans l’expression du signal x(t)

![2](https://user-images.githubusercontent.com/86806375/209026802-3d7fad7e-3070-453f-8fb3-b18995797344.JPG)


3.	Vu qu’on se retrouve face à une symétrie conjuguée du spectre par rapport à fe/2, il faut effectuer un décalage circulaire centré sur 0 pour mieux visualiser le contenu fréquentiel du signal en utilisant La commande fftshift

![3](https://user-images.githubusercontent.com/86806375/209026823-5652e4ac-fdd6-4768-89b2-fc0c62a2e923.JPG)


4.	On génère maintenant un signal stationnaire qui va nous servir de bruit, à l’aide de la loi normale centrée réduite de moyenne 0 et d’écart type 1. Ce type de bruit s’appelle bruit Gaussien. La fonction `randn` de MATLAB qui génère des nombres aléatoires suivant une distribution normale nous permet de créer un bruit Gaussien sans devoir passer par les calculs 

![4](https://user-images.githubusercontent.com/86806375/209026835-3b110d3e-df08-4de3-88f6-99d09c607d24.JPG)


5.	 On utilise la commande sound pour écouter le signal et puis le signal bruité

6.	On affiche le signal bruité en combinant le bruit et le spectre du signal x dans un même plot

Le bruit qui est par définition un signal a pics de basses fréquences, détériore le signal utile mais ce dernier est toujours visible dans le spectre et toujours audible également, un filtrage basse fréquence peut permettre dans ce cas à récupérer le signal initial

![5](https://user-images.githubusercontent.com/86806375/209026867-da98ea03-7efc-4238-80de-d474e0036364.JPG)


7.	Apres amplification du bruit le signal utile est quasi-totalement perdu. Pas de possibilité de filtrage dans ce cas

![6](https://user-images.githubusercontent.com/86806375/209026887-7fcf00b4-1e4a-40e6-87b5-0a18980b543a.JPG)


