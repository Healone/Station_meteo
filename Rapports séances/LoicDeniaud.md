Rapport de projet semaine 1

Découverte du projet et création du GitHub. Prise de connaissance du travail effectué les années précédentes. Prise de connaissance du travail à faire pour la mise en oeuvre du projet. Réunion d'information avec le client dans le but de créer un cahier des charges.

Rapport de projet semaine 2

Etude de la documentation technique. Découverte du schéma Eagle de la carte électronique. Installation du connecteur RJ45 femelle dans le logiciel Eagle (10%). Appréhension des besoins du client pour le cahier des charges.

Rapport de projet semaine 3

/**/

Rapport de projet semaine 4

séance du 3/1/22
- Récupération des quantités de pluie sur ESP + modif du layout EAGLE.
- Amélioration du code en général et rapatriement de petit bout de code 

Séance du 4/1/22
- Récupération de la vitesse du vent sur ESP.
- Début d'intégration de la girouette, avec prise en compte de la plage d'acq analogique de l'ESP.

Séances du 10/02/22 et 11/02/22
- Nous avons recontré deux problématiques concernant la gestion de la girouette:
  - La tension de la batterie ne sera pas constante.
  Solution : Nous récupérons la tension d'alim sur une voie GPIO avec une range de 5V pour ne pas se retrouver la range non gérées pas l'ADC de l'ESP (3V à 3.3V) et                apporter une précision à deux digit. Avec la tension d'alim on sera en mesure d'apliquer un coefficient sur le calcul de tension resultant du pont                    divisuer entre la giroutte et notre résistance fixe de 12k ohm.
  - L'ADC de l' ESP ne gére pas les tensions entre 0V et 0.20 V, et entre 3V et 3.3V.
  Solution : Nous avons réduit la range de tension en sortie du pont divisuer girouette avec des résistances qui nous permettent de "supprimer" les tensions basses                (0-0.5V) et les tensions hautes (2.5-3.3V), ce qui va nous permettre d'établir un nouveau tableau des correspondanes entre les tensions resultantes
             et la position de la girouette (N,WE,S, etc).
- La prochaine étape sera d'établir ce nouveau tableau, de maniere précise, mettre dans le code les seuils correspondants, et enfin l'intégrer au code déja fonctionnelle.
- Travailler en parrallele sur la communication avec le module LORA (Quentin Gaglio), et pouvoir réunir l'ensemble. 

Séances du 03/03/22 et 04/03/22
- La girouette est mise en place, opérationnelle et fonctionnelle, qu'elle soit alimentée en 3V ou 3.6V (range de tension de la batterie)
  Nous avons d'abord fixé une tension "cible" de 3.3V, rajouter des resistances talon permettant d'éliminer les tensions non prises en charg par l'ADC de l'ESP32.
  L'ajout de resistances de 1k ohm en amont et en aval du montage pont diviseur nous a permis "d'éliminer" ces tensions.
  Une fois ces resistances installées, nous avons établi un nouveau tableau des correpondance ou chaque tension en sortie du pont représente une direction du vent.
  => Comme nous récupérons de facon précise la tension d'alimentation de l'ESP32, il nous suffit juste d'appliquer un coeff (tension d'alim/3.3) pour avoir la bonne        valeur en fonction du tableau de correspondance.
- Intégration du code girouette dans le code principal, ce qui nous permet maintenant d'avoir toutes les valeurs centralisés.
- Debut des test concernant la communication LORA avec la gateway, mais nous avons rencontré dans problêmes de cablage sur breadboard avec le module LORA durant la     deuxieme partie du cours du 4/03, ce qui nous a fait prendre du retard, mais sera très propablement réglé lors de la prochaine séance.

Séance du 11/03/22
- Modification du code afin de recuperer les interruptions du pluviometre pendant le sleep de l'ESP32.
- Câblage et test du module LORA sur la breadboard et essayer de transmettre les " vraies " donnés, celles issues des différents capteurs.

Séance du 29/03/22
- Synchronisation entre notre format d'envoi et le format de réception (multiplier un float par 100 pour une double précision, qui sera ensuite diviser par     100 lors de la réception, et pour les entiers on envoie sur 1 ou 2 octets en fonction de la taille de la donnée).
  -  
