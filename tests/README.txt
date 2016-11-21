
Ce repertoire contient des fichiers pour le test du projet 
"Circuits et Architecture"

Pour executer les tests existants:
---------------------------------
1) Dans un terminal, definir la variable d'environnement 'logisim'
   par exemple, en bash

	export logisim="java -jar logisim.jar"

   ou mettre un alias dans .bashrc

2) Dans ce terminal, lancer le script 'do-tests.sh'

	do-tests.sh <user name> <solution LC3-sim>.circ [<dir>]

   L'argument <dir> indique le repertoire source des tests et
   il est optionnel. Par defaut, tous les repertoires sont 
   consideres.


Pour ajouter des tests:
-----------------------
1) Ecrire le test sous forme d'une liste d'instructions LC-3
   dans le repertoire 'perso'. Par exemple,
	cat > perso/testADD-1.asm
	.ORIG x300
	AND R0, R0, 0
	ADD R0, R0, 4

2) Generer le fichier .mem en utilisant lc3-as. Par exemple,
	lc3-as perso/testADD-1.asm perso/testADD-1.mem

3) Ecrire un fichier avec le resultat attendu dans le
   registre R0 sous la forme d'une suite de 16 bits avec
   groupement de 4 bits separes par ':', par exemple
	0000:0000:0000:0010
   pour la valeur attendue 2.

4) Lancer le script 'do-tests.sh'

