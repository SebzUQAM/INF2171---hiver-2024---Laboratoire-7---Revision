# INF2171---hiver-2024---Laboratoire-7---Revision
## Question 1 :

 1. Pour déterminer la taille maximale d’un nombre entier **NON SIGNÉ** sur n bits, il faut utiliser la formule suivante : 2^(n-1) - 1.
	 - [ ] vrai
	 - [x] faux
		 **Réponse :** 2^n - 1

 2. Je suis un caractère qui représente 4 bits.
	 - [ ] un word
	 - [ ] un code ASCII
	 - [ ] un octet
	 - [x] un chiffre hexadécimal

 3. Que se passe-t-il lorsque le résultat d’une opération est hors domaine?
		 **Réponse :** Les bits qui sont hors du comaine sont ignorés.

 4. Dans quel registre faut-il passer l’argument lorsqu’on utilise printInt ?
	 **Réponse :** a0

 5. Quelle est l’utilité du registre a7?
		 **Réponse :** Définir l'appel système à exécuter du ecall. En d'autre mot, dire à ecall ce qu'il doit faire.

 6. Vous circulez dans un tableau qui contient des caractères ASCII (`.byte`). Vous voulez accéder à 6 éléments plus loin dans le tableau. Quelle valeur allez vous devoir additionner au registre contenant l’adresse du tableau?
	 - [x] 6
	 - [ ] 12
	 - [ ] 24
	 - [ ] 48
	**Réponse :**  Puisque chaque caractères est de 1 octet, nous n'avons qu'à faire +6 pour 6 caractères.
		 
 7. Encore avec un tableau contenant des caractères ASCII, quelle instruction devez-vous utiliser pour extraire le caractère de la case dans laquelle vous vous trouvez?
	 - [ ] lb
	 - [x] lbu
	 - [ ] lw
	 - [ ] lwu
	 **Notez que** lb va fonctionner, mais il va poser problème si nous faisons des calcule arithmétiques avec les chars ensuite.
	 
 8. `slli` peut être utilisé pour multiplier la valeur d’un registre.
	 - [x] vrai
	 - [ ] faux
		**Comme expliquer durant les labs**
			- 10100010<sub>2</sub> * 1**0**<sub>2</sub> = 10100010**0**<sub>2</sub>
			- 12345<sub>10</sub> * 1**0**<sub>10</sub> = 12345**0**<sub>10</sub>
			- 12ABC<sub>16</sub> * 1**0**<sub>16</sub> = 12ABC**0**<sub>16</sub>
			- Peux importe la base que tu as, slli avec le nombre de "0".

 9. À quel bit doit-on se référer pour déterminer si un nombre est positif ou négatif?
 **Réponse:** Le bit le plus fort, celui qui est totalement à gauche.

 10. Une pseudoinstruction consiste d’une ou plusieurs vraies instructions machines.
	 - [x] vrai
	 - [ ] faux

 11. On veut définir un tableau de 10 entiers 16 bits signés. Pour garantir que les loads et stores des éléments soient naturellement alignés, l’adresse du tableau devrait être un multiple de combien ?
	 **Réponse :** Des multiples de 2 car les sauts se font par 8 bits, donc pour avoir un saut de 16 bits il nous faut un saut du double (16/8=2)

 12. La taille des registres dépends de?
	Réponse : De l'architecture du processeur (selon moi, je peux faire une erreur sur ce point)

