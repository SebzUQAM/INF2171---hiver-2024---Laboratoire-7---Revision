# INF2171---hiver-2024---Laboratoire-7---Revision
## Question 1 :

 i. Pour déterminer la taille maximale d’un nombre entier **NON SIGNÉ** sur n bits, il faut utiliser la formule suivante : 2^(n-1) - 1.
	 - [ ] vrai
	 - [x] faux<br/>
		 **Réponse :** 2^n - 1

 ii. Je suis un caractère qui représente 4 bits.
	 - [ ] un word
	 - [ ] un code ASCII
	 - [ ] un octet
	 - [x] un chiffre hexadécimal

 iii. Que se passe-t-il lorsque le résultat d’une opération est hors domaine?<br/>
		 **Réponse :** Les bits qui sont hors du comaine sont ignorés.

 iv. Dans quel registre faut-il passer l’argument lorsqu’on utilise printInt ?<br/>
	 **Réponse :** a0

 v. Quelle est l’utilité du registre a7?<br/>
		 **Réponse :** Définir l'appel système à exécuter du ecall. En d'autre mot, dire à ecall ce qu'il doit faire.

 vi. Vous circulez dans un tableau qui contient des caractères ASCII (`.byte`). Vous voulez accéder à 6 éléments plus loin dans le tableau. Quelle valeur allez vous devoir additionner au registre contenant l’adresse du tableau?
	 - [x] 6
	 - [ ] 12
	 - [ ] 24
	 - [ ] 48<br/>
	**Réponse :**  Puisque chaque caractères est de 1 octet, nous n'avons qu'à faire +6 pour 6 caractères.
		 
 vii. Encore avec un tableau contenant des caractères ASCII, quelle instruction devez-vous utiliser pour extraire le caractère de la case dans laquelle vous vous trouvez?
	 - [ ] lb
	 - [x] lbu
	 - [ ] lw
	 - [ ] lwu<br/>
	 **Notez que** lb va fonctionner, mais il va poser problème si nous faisons des calcule arithmétiques avec les chars ensuite.
	 
 iix. `slli` peut être utilisé pour multiplier la valeur d’un registre.
	 - [x] vrai
	 - [ ] faux<br/>
		**Comme expliquer durant les labs**
			- 10100010<sub>2</sub> * 1**0**<sub>2</sub> = 10100010**0**<sub>2</sub>
			- 12345<sub>10</sub> * 1**0**<sub>10</sub> = 12345**0**<sub>10</sub>
			- 12ABC<sub>16</sub> * 1**0**<sub>16</sub> = 12ABC**0**<sub>16</sub>
			- Peux importe la base que tu as, slli avec le nombre de "0".

 ix. À quel bit doit-on se référer pour déterminer si un nombre est positif ou négatif?<br/>
 **Réponse:** Le bit le plus fort, celui qui est totalement à gauche.

 x. Une pseudoinstruction consiste d’une ou plusieurs vraies instructions machines.
	 - [x] vrai
	 - [ ] faux

 xi. On veut définir un tableau de 10 entiers 16 bits signés. Pour garantir que les loads et stores des éléments soient naturellement alignés, l’adresse du tableau devrait être un multiple de combien ?<br/>
	 **Réponse :** Des multiples de 2 car les sauts se font par 8 bits, donc pour avoir un saut de 16 bits il nous faut un saut du double (16/8=2)

 xii. La taille des registres dépends de?<br/>
	**Réponse :** De l'architecture du processeur (selon moi, je peux faire une erreur sur ce point)

## Question 2 :
Dans votre nouvel emploi, on vous demande de créer un programme qui permettra aux utilisateur de transformer des degrés Kelvin en degrés Celsius. Lorsqu’un utilisateur rentre le nombre `0`, on lui retourne -273. Considérant que votre outil utilise des registres de 16 bits, répondez aux questions suivantes en laissant des traces de votre démarche :

 a. Quelle est la représentation en binaire du registre contenant “-273” si on travaille en complément de deux? Écrivez le résultat sur 16 bits.
	<br/>273-1=272
	<br/>0b0000000100010000 = 272
	<br/>On inverse :
	<br/>**Réponse :** 0b1111111011101111

 b. Quelle est sa représentation sous format hexadécimal (toujours sur 16 bits)?
	<br/>0b1111.1110.1110.1111
	<br/>**Réponse :** 0xFEEF
	

 c. Un bug dans le système est survenu et votre programme à imprimé le résultat en binaire. Cependant, il s’agissait d’une donnée très importante et vous devez le convertir en décimal pour vos collègues avant de corriger ce bug. Voici le nombre en question : 0000 0001 0111 0011
	<br/>**Réponse :** 1+2+16+32+64+256=371
	

 d. Vous installez une nouvelle fonctionnalité qui permet d’additionner des registres dans votre programme. Pour le tester, vous décidez d’additionner un registre contenant la valeur 0xCAFE et un autre registre contenant la valeur 0xA15. Quelle est la valeur obtenue en hexadécimale (toujours sur 16 bits) ?
	<br/>**Réponse :**
	<br/>0xCAFE
	<br/>0x0A15 +
	<br/>E+5=13; 13-10=3
	<br/>Donc 3 avec une retenu de 1
	<br/>1+F+1 = 11; 11-10=1
	<br/>Donc 2 avec une retenu de 1
	<br/>1+A+A=15; 15-10=5
	<br/>Donc 5 avec une retenu de 1
	<br/>1+C=D
	<br/>Pour un total de 0xD513

## Question 3 :
a. Décrivez ce que ce programme fait en quelques phrases.
    <br/>**Réponse :** Compte le nombre de lettre majuscule et affiche le nombre quand "!" est entré.

b. Qu'allons nous obtenir si on entre dans ce programme "BONJOUR tout le monde!" ?
    <br/>**Réponse :** 7

## Question 4 :
a. Expliquez ce que fait ce programme (pas besoin des fonctions effacées pour répondre).
    <br/>**Réponse :** Va chercher la plus grande valeur dans le tableau

b. Qu’est-ce que ce programme retourne si l’on prends les données présentes dans tab?
    <br/>**Réponse :** Rien puisqu'il n'est pas fini, mais normalement 800

c. Écrivez les fonctions prochainElement et finProg directement dans le code. Vous devriez avoir 7 nouvelles lignes d’instructions.
<br/>   **Réponse :** 
<br/>   prochainElement:
<br/>       addi s1, s1, 8
<br/>       addi s2, s2, -1
<br/>   finProg: 
<br/>       li a7, printInt
<br/>       mv a0, s0
<br/>       ecall

<br/>       li a7, exit
<br/>       ecall

d. Vous souhaitez passer ceci dans votre programme : tab2: .word 11, 5, -19, 24, 30, -30, 90, -150, 400, -12. Cependant, votre programme se termine avec des erreurs. Pourquoi? Comment peut-on corriger cette erreur?
    <br/>**Réponse :** Le logiciel original gère des dword, mais les nouvelles données sont des word. donc il faut additionner 4 et non 8 dans la fonction prochainElement.