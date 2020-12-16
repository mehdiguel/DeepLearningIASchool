		Présentation de la compétition & objectifs

Le Deepfake prend une ampleur de plus en plus considérable avec l'avancée permanente de l'IA. Les vidéos générées 
sont de plus en plus réalistes et deviennent difficiles à distinguer du vrai. Cela pose en effet un problème majeur 
dans la mesure ils peuvent etre utilisés à des fins malvaillantes comme sources de désinformation, de manipulation, 
d'harcelement et de persuasion. Les technologies Deepfake peuvent aussi porter atteinte à la qualité du discours 
public et bien au dela.

L'object de la compétition DEEPFAKE DETECTION CHALLENGE, serait d'inciter les chercheurs du monde entier à créer de
nouvelles technologie qui peuvent aider à detecter les deepfakes et les medias manipulés.

                Les données

- 1 dossier test_videos contenant toutes 400 videos de test .mp4 pour tester le modele
- 1 dossier train_sample_videos contenant 400 les videos d'entrainement .mp4 qui serviront à entrainer
  le ou les modeles
- 1 fichier .csv de 400 lignes et 2 colonnes la premiere ( les lignes correspondent aux noms des 400 videos test) et 
  la deuxieme colonne contient que des 0.

                Premièr notebook(5eme place)
		
° Extraction des visages: 
	*chaque nième trame passe par le model MTCNN.
 	*Les coordonnées de la boîte englobante sont ensuite utilisées pour définir 	un masque dans un tableau 3D.
	*Enfin, extraction d'une boîte englobant l'ensemble du visage dans le temps 	et creation d'une vidéo à partir de cette région d'intérêt, en incluant 		chaque image.
° 3D CNN:4 architectures différentes (I3D, 3D ResNet34, MC3 & R2+1D) et 2 résolutions différentes (224 x 224 & 112 x 112). + Utilisation d'une pixel-level augmentation
° Cutmix: Stratégie de régularisation pour former des classificateurs forts avec des caractéristiques localisables
° AdamW : a 1-cycle learning rate scheduler.
° 2D CNN: Choix du SE-ResNeXT50 pour le model final, tout en essayant plusieurs autres, dont Xceptions et EfficientNets.



                Deuxieme notebook(12 eme place)
 
les difficultés rencontrées par le compétiteur :
° MesoNet, RNN - sous-ajustement sur les données de train
° De fortes augmentations (par exemple, découpe, saturation de la teinte, rotation 90)
° Empilement de modèles empilés - semblait surpasser, mais pas trop
° FaceForensics ++ - le maximum que j'ai réussi à tirer de cette chose est de 0,68 LB public

