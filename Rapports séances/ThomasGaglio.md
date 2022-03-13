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

Semaine du 11/01/2022 : 

• Cablage et code de la girouette sur notre breadboard. Nous avons rencontré un pbroblème car la récupération de tension (Analog read) sur l'es32 n'est pas linéaire. La courbe de tension de celui ci est écrétée en basse tension à 0,1V et en haute tension à 3V. Une des solutions consiste à ne travailler que dans la plage linéaire de la courbe en adaptant les résistances (Rtest et Rgirouette) de notre pont diviseur ou bien en rajoutant des résistances talon si la première option n'est pas possible. Nous avons effecuté des test et des mesures de tensions et il semble que l'ajout de resistances talon ne soient pas nécessaires. Nous prévoyons de terminer le code la semaine suivante pour avoir une girouette opérationnelle. 

•Test de la carte récitifiée de M. PETER. N'est pas fonctionelle avec le code que nous avons écrit pour la breadboard. Nous devons nous renseigner auprès de M. PETER la semaine suivante pour éclaircir ce point. 



Séance du 03-04/2022 : 

Les objectifs de cette séance étaient de finaliser le code/faire fonctionner la girouette et tester le bon fonctionement de notre carte remaniée par Mr Peter. Les codes et bon fonctionnement des autres capteurs et élements de la station météo étant deja réalisés. 
Le problème étant que la récupération de la tension sur L'esp32 avec la fonction analagoREAD() n'est pas linéaire. Entre 0-0.15V et 3-3.3V l'esp ne peut pas différencier les valeurs. 

Avec Loic Deniaud nous avons procédé à différents test de mesures en changeant la résistance de notre pont diviseur de tension pour la girouette. Cela n'était pas suffisant et nous dépassions toujours les seuil haut et bas de tension. Etant bloqués et en dificulté, nous avons donc sur les conseils de notre enseignant ajouté des résistances "talon" en série avec les 2 résitances du Pont divieur de la girouette et refait nos test en reportant les valeurs sur un tableur excel. Nous avons trouvé des valeurs de résitance acceptables (12K pour la résistance du pont diviseur et 1K pour chaque "talon"). Nous avons ensuite codé et implémenté la partie girouette au reste de notre code de récupération des infos météos.

D'un autre coté j'ai questionné Mr.Peter sur le fonctionnement de notre carte éléctronique. En effet, je l'ai testée en téléversant un simple code de scan d'équipement I2C pour vérifier que l'esp discutait bien avec nos capteurs, sans résultat. Mr.Peter m'a expliqué qu'un transistor connecté a une PIN de l'esp bloquait la tension vers les capteurs. Le but étant de reveiller ceux-ci seulement lors d'une requete d'envoi de données. Pour comuniquer avec nos capteurs nous devions simplement passer la valeur de la PIN à 1 pour débloquer le transistor et donc la tension. Après tets, j'ai bien retrouvé mes capteurs et leur adresses I2C grâce au scan. 

L'objectif de la prochaine séance est de réfléchir et concevoir une nouvelle carte avec les modfifications de resistances et de condensateurs testés sur la breadboard. Nous devons également nous pencher sur l'envoi de nos données avec le LORA. 



Séance du 11-04/2022 : 

Présentation tâches individuellesen 1ère partie de séance.

Approche des concepts du Lora et de la trame avec Quentin lors de la deuxième partie de séance. Nous avons rencontré des difficultés a récupérer des valeurs hexadécimales pour l'adresse MAC dans l'envoi de trame, mais finalement réussi après des recherches sur internet. Nous devons avancer sur la mise en commmun de la trame avec l'envoi de nos données de station météo la séance prochaine et faire un point avec M.Peter sur les éléments à corriger sur notre carte électronique. 
