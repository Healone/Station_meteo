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

Séance du 10/02/22 et 11/02/22
- Nous avons recontré deux problématiques concernant la gestion de la girouette:
  - La tension de la batterie ne sera pas constante.
  Solution : Nous récupérons la tension d'alim sur une voie GPIO avec une range de 5V pour ne pas se retrouver la range non gérées pas l'ADC de l'ESP (3V à 3.3V) et                  apporter une précision à deux digit. Avec la tension d'alim on sera en mesure d'apliquer un coefficient sur le calcul de tension resultant du pont divisuer              entre la giroutte et notre résistance fixe de 12k ohm.
  - L'ADC de l' ESP ne gére pas les tensions entre 0V et 0.20 V, et entre 3V et 3.3V.
