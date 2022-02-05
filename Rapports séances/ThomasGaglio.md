Tâches projet GAGLIO Thomas

Séance du 27/08/2021 :


• Prise de connaissance du travail effectué les années précédentes.
• Prise en main de GitHub et création des différents fichiers et de l'espace de travail.
• Réunion d'informations avec Monsieur Peter afin de bien prendre en main le sujet / Rédaction d'un document synthèse.


Séance du 09/09/2021 :


• Etude de la documentation technique. Récupération du matèriel.
• Découverte du schéma Eagle de la carte électronique
• Début de l'installation du connecteur RJ454 femelle dans le logiciel Eagle (10%)
• Etude de la doc de cablage des capteurs pour savoir comment connecter le RJ45 a ceux-ci.


Séance du 17/09/2021 :

• Etude de la documentation de l'anémomètre, girouette et pluviomètre
• Remplacement sur le schéma électrique (sous Eagle) des connecteurs RJ11 par des connecteur RJ45
• Prise de connaissance du PCB de l'ancien groupe et finition du routage de celui-ci.  

Séance du 23/09/2021 :

• Absent


Séance du 01/10/2021 :

  • Récupération du PCB de notre carte électronique
  • Brasage des composants sur le PCB avec moule + four pour l'avant de la carte, brasage au fer a souder des composants restant au verso de la carte. 
  
  Séance du 22/11/2021 :
  
  • Nous avons terminé le brassage de la carte, tous les composants on étés soudés. 
  • Début des test sur les differents composants de la carte. 
  • A la fin de la séance il semble qu'une LED est déffectueuse. Nous prévoyons de tester la contniuité et de la mettre en tension pour vérifier sa fonctionalité à la prochaine séance.
  
 
  Séance du 12/12/2021 :
  
• La LED présumée defectueuse est confirmée KO après les tets effectués avec un multimètre. Mr Peter prévoit de nous en ramener une la séance prochaine.
• Essai des codes du groupe de l'année dernière sur l'ESP32 pour récupérer des infos avec l'anémomètre sans succès. Tests avec un oscillateur pour vérifier le fonctionnement du l'anémomètre. Résultat OK --> On voit une impulsion à chaque fois que l'anénmomètre effectue un tour. Plus l'anémomètre va touner vite, plus l'impulsion sera rapide et la fréquence entre les impulsions sera petite.

Séance du 07/01/2022
•La led supposée déffectueuse était finalement mal positionée. Ainsi après un débrasage et un rebrasage dans le bon sens, la Led fonctionne.
•Création d'une configuration sur la breadbord permettant de tester le fonctionnement des capteurs BME et TSL. Récupération du code du groupé précedent et amélioration.
•Ajout des capteurs sur la carte PCB (collage avec du scotch car la carte n'a pas été bien dimensionée pour l'ajour de ces capteurs.

Séance du 03/01/2022

•Etude sur le branchement des capteurs TSL et BME sur la carte PCB et récupération de la documentation des brochures des capteurs. (durée 1h45)
•Brasage des deux capteurs sur la carte avec des fils. (durée 1h45)

Séance du 04/01/2022

•Vérification du brasage des capteurs TSL et BME éffectué le 03/01/2022 : Les 2 capteurs ne fonctionnement pas on pense que le problème vient de la carte. A la suite de ce soucis et pour un gain de temps nous allons effectuer tous les test jusqu'à la finalisation sur la breadbord. Ensuite à la fin nous reréaliserons un schéma eagle pour créer une nouvelle carte qui fonctionne et qui répond à nos besoins.
•Brasage de fils sur des RJ11 pour test sur breadbord de nos codes d'anémomètre et pluviometre.
•Test fonctionnels. 

  
  
  

