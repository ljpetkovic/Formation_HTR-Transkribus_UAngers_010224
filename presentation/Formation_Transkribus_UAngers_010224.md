---
marp: true
theme: default
markdown.marp.enableHtml: true
paginate: true
extra: true
footer: "Formation OCR · HTR et Transkribus, M2 « Bibliothèques et archives de l'UA », 01/02/2024, Ljudmila PETKOVIC"
html: true



---

  <style type="text/css">
  section {
    background-color: white;
    color: black;
    font-family: system-ui !important;
  }





@import url('//maxcdn.bootstrapcdn.com/font-awesome/4.2.0/css/font-awesome.min.css');

td {
  text-align: center;
}

h1 {
    color: DarkBlue;
  }

  

  h2 {
    color: DarkBlue;
  }

  h3 {
    color: DarkBlue;
  }

  h4 {
    color: DarkBlue;
  }

  h5 {
    color: DarkBlue;
  }

  h6 {
    color: DarkBlue;
    font-size: 30px;
    font-weight:normal;
  }

  blockquote {
    background: #ffedcc;
    border-left: 10px solid #d1bf9d;
    margin: 1.5em 10px;
    padding: 0.5em 10px;
  }
  blockquote:before{
    content: unset;
  }

  blockquote:after{
    content: unset;
  }

  medium-text {
      font-size: 0.9rem;
    }

  small-text {
      font-size: 0.7rem;
    }

  smaller-text {
      font-size: 0.5rem;
    }

  .center {
   display: block;
     margin-left: auto;
   margin-right: auto;
     width: 50%;
  }

.container {
  display: grid;
  grid-template-columns: 0.68fr 0.90fr;
}

.container-side {
  display: inline-flex;
  text-align: center;
}

    #content {
          position: relative;
      }
      #content img {
          position: absolute;
          top: -600px;
          right: 0px;
      }

.info-msg,
.success-msg,
.warning-msg,
.error-msg {
  margin: 5px 0;
  margin-bottom: 20px;
  padding: 10px;
  border-radius: 5px 5px 5px 5px;
  border: 2px solid transparent;
  border-color: transparent;
}
.info-msg {
  color: #059;
  background-color: #BEF;
}
.success-msg {
  color: #270;
  background-color: #DFF2BF;
}
.warning-msg {
  color: #9F6000;
  background-color: #FEEFB3;
}
.error-msg {
  color: #D8000C;
  background-color: #FFBABA;
}



  </style>





  <!-- _class: lead -->

# *HTR* en théorie et en pratique : *Transkribus*

  ###### Ljudmila PETKOVIC

<span style="font-size: 70%; line-height: 30px; display:block">Sorbonne Université, Faculté des Lettres, UFR Littératures françaises et comparée<br>Centre d’étude de la langue et des littératures françaises (CELLF), UMR 8599<br>Observatoire des textes, des idées et des corpus (ObTIC)</span>

<small-text><a href="mailto:ljudmila.petkovic@sorbonne-universite.fr">`ljudmila.petkovic@sorbonne-universite.fr`</a></small-text>

  <br>

  ![bg left:50% 50% width:130pt height:80pt](https://upload.wikimedia.org/wikipedia/fr/b/b9/Universit%C3%A9_d%27Angers_%28logo%29.svg) 


  ![bg left:25% 60% width:110pt height:110pt background-size: cover;](https://eveille.hypotheses.org/files/2022/09/transkribus.jpg) 

<span style="color:navy; font-size: 90%; line-height: 35px; display:block">Formation OCR · HTR et Transkribus
M2 « Bibliothèques et archives de l'univ. d'Angers »
Angers, le 1 février 2024, année 2023-2024</span>

---

## Petite enquête

* Avez-vous entendu parler de la méthode d'**OCR** (ou bien d'**HTR**) ? 

* Qu'en savez-vous ?

* Envisagez-vous d'utiliser ces méthodes dans le cadre de vos recherches ?

N'hésitez pas à noter vos idées et commentaires dans ce [Framapad](https://annuel2.framapad.org/p/formation-ocr--htr-uangers-a5pm?lang=fr).

---

## Objectif de cette formation

0️⃣ (re)découverte des notions principales en lien avec cette formation

1️⃣ sensibilisation à la question de la transcription automatique de textes (OCR · HTR)

2️⃣ découverte d'un outil d'HTR : Transkribus 

3️⃣ transcription automatique d'un corpus-test

4️⃣ aperçu des projets d'HTR menés par des *GLAM*<sup>1</sup>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<sup>1</sup> angl. ***G**alleries, **L**ibraries, **A**rchives* and ***M**useums* : institutions patrimoniales 

---

## Matériel

Le matériel de cette formation (diapositives et corpus jouet) se trouve sur le [dépôt GitHub](https://github.com/ljpetkovic/Formation_HTR-Transkribus_UAngers_010224), ainsi que sur Moodle.

---

# 0️⃣ Concepts de base

---

## Archivage

<div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #8a6d3b;; background-color: #fcf8e3; border-color: #faebcc;">
Processus de collection, d’organisation, de description, de préservation, de diffusion et d’accès aux archives (collections de documents anciens, classés à des fins historiques).
</div>

<span style="float:right; font-size: 18px">([Lepron, 2023](https://www.abantiquo.fr/stockage-archives/))

* les archives sont définies, collectées, triées et classées selon une logique rationnelle et informationnelle, selon une visée a priori plus fonctionnelle

* mise en jeu des valeurs d’information, juridiques, et secondairement historiques

  <span style="float:right; font-size: 18px">([Davalon, 2014](https://shs.hal.science/halshs-01220537/document))

---

## Patrimonialisation

<div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #3c763d; background-color: #dff0d8; border-color: #d6e9c6;">
Processus de création, de fabrication de patrimoine (héritage du passé existant aujourd'hui), reconnu en tant que bien collectif. Le phénomène s’est développé en France au XIX<sup>e</sup> siècle, notamment pour la sauvegarde des monuments historiques. → valorisation patrimoniale. 
</div>

<span style="float:right; font-size: 18px">([Ressources de géographie pour les enseignants, 2019](http://geoconfluences.ens-lyon.fr/glossaire/patrimonialisation/@@download_pdf?id=patrimonialisation&uid=43fd7cf20c194f3aa9466668df4b34e5))

* concerne des objets qui se trouvent être encore présents tandis que leurs homologues ont disparu 

* le choix de les patrimonialiser suppose un intérêt social pour eux

* mise en jeu des valeurs cognitives, sociales, voire identitaires 

* nouvel usage des archives : patrimonialisation numérique

  <span style="float:right; font-size: 18px">([Davalon, 2014](https://shs.hal.science/halshs-01220537/document))

---

## Archives *numérisées*

  <div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; font-size: 25px; border-radius: 4px; color: #31708f; background-color: #d9edf7; border-color: #bce8f1;">L’archive <b style="color:red">numérisée</b>, à l’inverse de l’archive numérique, n’est pas nativement  électronique. Il s’agit du résultat de la reproduction d’une archive  initialement physique au moyen d’un outil numérique, tel qu’un scanner  ou un appareil photo. 
  </div>

<span style="font-size: 18px; float:right;">([Barbier & Mandret-Degeilh, 2018](https://www.cairn.info/le-travail-sur-archives--9782200621056-page-195.htm))

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/rousseau.png" width="200">
</p>

<p style="text-align:center; font-size: 70%">Exemple d'une page au format PDF issue de <a href="https://gallica.bnf.fr/ark:/12148/bpt6k5564953b">Gallica</a>.</p>

---

## Dématérialisation (rétro-conversion)

* convertir les documents papier dans un format logique pivot les rendant de nouveau rééditables et donc réutilisables

* au-delà de la simple transcription automatique de textes

* réhabilitation de la structure interne du document, la plus proche possible de celle qu’il avait à l ’origine

  <span style="font-size: 18px; float:right;">([Toumit *et al.*, 2000](https://books.google.fr/books?hl=en&lr=&id=s2INxlR0guEC&oi=fnd&pg=PA319&dq=Le+texte+math%C3%A9matique+:+du+document+papier...+%C3%A0+la+version+html&ots=DiQjaFP_hC&sig=k7XJoDpHe-5-d5rBhnZtyMWKM3c&redir_esc=y#v=onepage&q=Le%20texte%20math%C3%A9matique%20%3A%20du%20document%20papier...%20%C3%A0%20la%20version%20html&f=false))

---

## Archives *numériques*

<div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #31708f; background-color: #d9edf7; border-color: #bce8f1; font-size: 25px;">[...] tout type de document produit aujourd’hui sous une forme électronique et dématérialisée. [...] toute archive  « nativement » (c’est-à-dire dès sa création) <b style="color:green">numérique</b>. Cette archive  est faite à la fois de <i>données</i> (le contenu du document à proprement  parler) et de <i>métadonnées</i> (les informations sur le document, telles que  sa date de création, son auteur, etc.).</div>

<span style="font-size: 18px; float:right;">([Barbier & Mandret-Degeilh, 2018](https://www.cairn.info/le-travail-sur-archives--9782200621056-page-195.htm))

* exemples :
  * archives numériques conservées par les Archives nationales
  * contenu généré par l'utilisateur·trice (angl. *user-generated content, UGC*)  
    * issu des réseaux de communication (Internet, email, réseaux sociaux)

---

## Algorithme

* ensemble de règles indiquant à l'ordinateur comment effectuer une tâche

  * <small-text>algorithme d'OCR : « *diviser l'image d'un caractère de texte en sections et distinguer les régions vides et non vides. En fonction de la police ou du type d'écriture utilisé pour la lettre, la somme de contrôle de la matrice résultante est ensuite étiquetée (initialement par une personne) comme correspondant au caractère de l'image* ».</small-text>

  <p align="center" alt="drawing">
      <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/algorithme.png" width="600">
  </p>

  <p style="text-align:center; font-size: 70%">Illustration d'un algorithme d'OCR (<a href="https://www.itransition.com/blog/ocr-algorithm">Anderson, 2021</a>).</p>

---

## Intelligence artificielle (IA)

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/ia-ml-dl.svg" width="1000">
</p>

<p style="text-align:center; font-size: 70%">Relations entre les termes « IA », « apprentissage automatique » et « apprentissage profond » (adapté de <a href="https://www.researchgate.net/figure/Representation-des-relations-entre-intelligence-artificielle-apprentissage-automatique_fig18_349180505">Cendre, 2021</a>).</p>

---

## Principes de l'apprentissage profond

* résoudre un problème en le divisant en plusieurs tâches

* tâches distribuées à des algorithmes de ML, organisés en **couches** successives 

* les couches contiennent des neurones et aident à faire circuler l’information

* chaque couche travaille sur le résultat de la précédente → <span style="color:navy"><b>réseau de neurones</b></span>

  <p align="center" alt="drawing">
      <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/reseau.png" width="460">
  </p>

  <p style="text-align:center; font-size: 70%">Structure d'un réseau de neurones pour la tâche de classification (<a href="https://www.edureka.co/blog/what-is-a-neural-network/">Lateef, 2023</a>).</p>

---

## Réseau de neurones artificiel profond

* algorithmes produisant une donnée de sortie à partir des données d’entrée
  1. <span style="color:red"><b>*</b></span> couche d'entreé (accepte les données d'entrée : images, documents...)
  2. &nbsp;&nbsp;&nbsp;couche cachée (effectue des calculs nécessaires pour produire la sortie)
  3. <span style="color:red"><b>*</b></span> couche de sortie (prédit une donnée de sortie : classe, caractère...)

<small-text>❇ Types de réseaux : classiques, convolutifs, récurrents etc.</small-text>

<!--les couches cachées contribuent à optimiser et à affiner la précision des résultats (elles prennent les données de sortie des précédents  neurones en entrée, calculent de nouvelles données de sortie et les  transmettent à des couches successives)-->

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/reseau.png" width="410">
</p>

<p style="text-align:center; font-size: 70%">Structure d'un réseau de neurones pour la tâche de classification (<a href="https://www.edureka.co/blog/what-is-a-neural-network/">Lateef, 2023</a>).</p>

---

## Apprentissage profond

* cas de figure : reconnaissance de visages

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/dl.png" width="480">
</p>

<p style="text-align:center; font-size: 70%">L'illustration du mécanisme du réseau de neurones pour la tâche de reconnaissance de visage (<a href="https://www.researchgate.net/figure/An-illustration-of-deep-learning-As-a-deep-network-of-neurons-is-trained-to-recognize_fig1_273395781">Lehman & Clune, 2014</a>).</p>

---

## Apprentissage profond : reconnaissance de caractères

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/dl_digits.png" width="850">
</p>

<p style="text-align:center; font-size: 70%">L'illustration du mécanisme du réseau de neurones pour la tâche de reconnaissance de caractères (<a href="https://db-blog.web.cern.ch/index.php/blog/luca-canali/2016-07-neural-network-scoring-engine-plsql-recognizing-handwritten-digits">Canali, 2016</a>).</p>

---

## Les projets en humanités numériques

Quatre principales étapes :

---

## Les projets en humanités numériques

Quatre principales étapes :

:one: Acquisition d'un objet d’étude

---

## Les projets en humanités numériques

Quatre principales étapes :

:one: Acquisition d'un objet d’étude

:two: Traitement d'un objet d’étude

---

## Les projets en humanités numériques

Quatre principales étapes :

:one: Acquisition d'un objet d’étude

:two: Traitement d'un objet d’étude

:three: Exploitation d'un objet d’étude

---

## Les projets en humanités numériques

Quatre principales étapes :

:one: Acquisition d'un objet d’étude

:two: Traitement d'un objet d’étude

:three: Exploitation d'un objet d’étude

:four: Publication des résultats

---

## Les projets en humanités numériques

Quatre principales étapes :

:one: Acquisition d'un objet d’étude

:two: Traitement d'un objet d’étude

:three: Exploitation d'un objet d’étude

:four: Publication des résultats

<div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #8a6d3b;; background-color: #fcf8e3; border-color: #faebcc;">
    <strong>&#9888; <i>NB</i> :<br/></strong> Les frontières entre ces étapes sont très poreuses et l’ordre des opérations ne respecte pas toujours cette progression logique.
</div>

---

## Les projets en humanités numériques

Quatre principales étapes :

:one: **Acquisition d'un objet d’étude**

:two: Traitement d'un objet d’étude

:three: Exploitation d'un objet d’étude

:four: Publication des résultats

<div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #8a6d3b;; background-color: #fcf8e3; border-color: #faebcc;">
    <strong>&#9888; <i>NB</i> :<br/></strong> Les frontières entre ces étapes sont très poreuses et l’ordre des opérations ne respecte pas toujours cette progression logique.
</div>

---

# 1️⃣ Transcription automatique de textes

---

## Enjeux de l'acquisition de données

<div class="warning-msg">
  <i class="fa fa-warning"></i>
  Format natif ➙ format numériquement et pleinement exploitable
</div>


* texte lisible, analysable et requêtable par la machine
* utilisation de la puissance des ordinateurs pour effectuer la transcription

* traitement des documents en masse, redistribution au format numérique

* éviter la transcription manuelle et chronophage de documents volumineux

  ≠ projets de production participative (angl. *crowdsourcing*) : 

  * <small-text>[From The Page](https://fromthepage.com/landing), [Transcribathon](https://transcribathon.eu/), [Transcrire](http://transcrire.huma-num.fr/), [T-PEN](http://t-pen.org/TPEN/) etc.</small-text>

---

## Méthodes de transcription automatique de textes

La transcription automatique de textes comprend les méthodes suivantes :

1. OCR (angl. *optical character recognition*)
2. HTR (angl. *handwritten text recognition*)

<small-text>Ces méthodes sont parfois regroupées sous le nom d'ATR (angl. *automatic text recognition*) ([Scheithauer, 2023](https://www.theses.fr/s381671))</small-text>

---

## OCR

* <span style="color:darkblue">reconnaissance optique de caractères</span>

* technique généralement appliquée aux textes **dactylographiés**

  > Processus qui consiste à convertir un ensemble de signes graphiques, le plus souvent alphanumériques (mais aussi les ponctuations, espacements...), encodés sous la forme d'une image, en mode texte. L'OCR désigne à la fois un <span style="color:green">**processus**</span> (d'OCR) et un <span style="color:green">**logiciel**</span> (d'OCR).

<span style="float:right; font-size:18px">([Camps & Perreaux, 2021](https://outils.lamop.fr/lamop/mp3/E-Ndp/JBC-NP_e-NDP_OCR-et-HTR.pdf))</span>

---

## OCR

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/ocr_augm.svg" width="500">
</p>

<p style="text-align:center; font-size: 70%">Mécanisme de l'OCR (adapté de <a href="https://datascience.unige.ch/application/files/2316/3248/7621/3.3._Simon_Gabay__Jean-Luc_Falcone.pdf">Gabay & SciCoS, 2021</a>).</p>

---

## HTR

* <span style="color:darkblue">reconnaissance de l’écriture manuscrite (angl. *handwritten text recognition*)</span>

* technique applicable aux textes **manuscrits**, mais aussi **dactylographiés** 

  <div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #a94442; background-color: #f2dede; border-color: #ebccd1;">
  Comment peut-on segmenter les caractères en écritures cursives, étant donné que les mêmes sont écrits attachés de manière fluide ? Dans ce cas, la segmentation au niveau des caractères s'avère impossible.
  </div>

  <span style="float:right; font-size:18px">(adapté de [Gabay & SciCoS, 2021](https://datascience.unige.ch/application/files/2316/3248/7621/3.3._Simon_Gabay__Jean-Luc_Falcone.pdf))</span>

  <br>

  <p align="center" alt="drawing">
      <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img//htr.png" width="900">
  <small-text><a href="https://comedie-francaise.bibli.fr/index.php?lvl=notice_display&id=65726"><br><i>Registre du Comité d'administration du Théâtre français de S. M. l'Empereur et Roi</i></a>, par Nicolas Bernard.</small-text>
  </p>

---

## Cas de figure

1. ###### On part de zéro

   * créer (ou collecter) des données d'entraînement 
   * entraîner un ou des modèles de segmentation et/ou de transcription
   * appliquer le(s) modèle(s) entraîné(s) aux images

2. ###### On a déjà un modèle de segmentation et/ou de transcription

   * appliquer le(s) modèle(s) existant(s) aux images et vérifier le résultat

   * on vise l'exhaustivité, sans pour autant attendre une transcription parfaite

   * si le modèle n'est pas suffisamment performant, on bascule dans le 1.

     * ré-entraînement du modèle

     <span style="float:right; font-size:18px">([Chagué, 2021](https://mate-shs.cnrs.fr/wp-content/uploads/2021/03/Tuto33_Chague_slide.pdf))</span>

     

---

## 1. Entraîner un modèle

* créer des <span style="color:navy">données d'entraînement</span> (« vérité terrain », angl. *ground truth*)

  * transcriptions obtenues par l'annotation manuelle d'un échantillon de différentes pages de documents

* entraîner un modèle sur les pages annotées

* appliquer le modèle aux pages non vues lors de l'entraînement (<span style="color:navy">données de test</span>)

  <ul style="font-size:22px">
      <li><i>in‑domain</i> : données provenant des mêmes données que celles présentes dans les données d'entraînement (p. ex. d'autres lignes d'un même document imprimé)</li>
      <li><i>out‑of‑domain</i> : données provenant d'une source différente de celles présentes dans les données d'entraînement (p. ex. d'autres lignes d'un autre document imprimé)
  </li>
  </ul><span style="float:right; font-size:18px">(<a href="https://github.com/gabays/Cours_2020_01_Strasbourg/blob/master/OCR_pratique.pdf">Gabay, 2020</a>)<br>

* détecter les lignes de textes et effectuer une transcription automatique

---

## 2. *Workflow* (*pipeline*) classique d'HTR 

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/workflow.svg" width="1100">
</p>

<p align="center" alt="drawing">
<small-text>Chaîne de traitement d'HTR adaptée de <a href="https://programminghistorian.org/fr/lecons/transcription-automatisee-graphies-non-latines#pipeline-classique-dun-ocrhtr">Vidal-Gorène (2023)</a>.</small-text>
</p>

---

### 2.1 Acquisition des données

* téléchargement des documents disponibles en ligne (format PDF, JPG, PNG...)

* numérisation des documents non disponibles en ligne (idéalement, scans PDF)

* import des documents (avec ou sans pré-traitement d'images)

  <p align="center" alt="drawing">
      <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/pretraitement.png" width="1100">
  </p>

  <p align="left" alt="drawing">
  <small-text>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Image originale.&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Image pré-traitée (binarisation).</small-text>
  </p>

---

### 2.2 Analyse de la mise en page

* <span style="color:red"><b>*</b></span> ligne de base (angl. *baseline*) : polyligne sous la ligne de texte manuscrite
* &nbsp;&nbsp;&nbsp;zones (régions) de texte

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/segmentation_zoom.png" width="750">
</p>

---

### 2.3 Reconnaissance de texte

* le résultat de la transcription automatique de texte n'est pas parfait

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/transcription_work.png" width="450">
</p>

---

### 2.3 Résultat de transcription

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/transcription.png" width="1100">
</p>

---

## Logiciels OCR · HTR

* [Transkribus](https://readcoop.eu)

* [Kraken](https://github.com/mittagessen/kraken) + interfaces eScriptorium

* [Tesseract](https://github.com/tesseract-ocr/tesseract)

* [Calamari](https://github.com/Calamari-OCR/calamari)

* [ocular](https://github.com/tberg12/ocular)

  ...

*Cf.* la [liste](https://github.com/kba/awesome-ocr?tab=readme-ov-file) exhaustive des outils de transcription de textes créée par `awesome-OCR`.

---

# 2️⃣ Transkribus

---

## Transkribus

[`page web`](https://readcoop.eu/transkribus/)

* outil d'IA pour la reconnaissance automatique de texte et l’édition numérique des documents d’archives (documents historiques)

* potentiel tant pour la recherche que pour l'archivage

  <table class="center" style="width:100%; font-size: 28px">
   <tr>
     <th align="center">Transkribus Lite</th>
     <th align="center">Transkribus Expert Client</th>
   </tr>
   <tr>
     <td>interface intuitive (navigateur web)</td>
     <td>téléchargement requis</td>
   </tr>
   <tr>
     <td>fonctionnalités de base</td>
     <td>fonctionnalités avancées</td>
   </tr>
   <tr>
     <td>interface en différentes langues (dont français)</td>
     <td>interface en anglais</td>
   </tr>
  </table> 



<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-b5ek{border-color:#ffffff;color:#010066;font-size:26px;font-weight:bold;text-align:right;vertical-align:top}
.tg .tg-eb5l{border-color:#ffffff;color:#010066;font-size:26px;font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-1v90{border-color:#ffffff;font-size:24px;text-align:right;vertical-align:top}
.tg .tg-r1ff{border-color:#ffffff;color:#000000;font-size:24px;text-align:left;vertical-align:top}
.tg .tg-tz00{border-color:#ffffff;color:#000000;font-size:24px;text-align:right;vertical-align:top}
.tg .tg-unof{border-color:#ffffff;font-size:24px;text-align:left;vertical-align:top}
</style>
<table class="center">
<thead>
  <tr>
    <th class="tg-eb5l" style="color: darkblue;">Transkribus Lite</th>
    <th class="tg-b5ek">Transkribus Expert Client</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-r1ff" style='width:100%'><span style="font-weight:400;font-style:normal">interface simple et ergonomique (navigateur web)</span></td>
    <td class="tg-tz00">installation requise</td>
  </tr>
  <tr>
    <td class="tg-unof"><span style="font-weight:400;font-style:normal">destiné à un public non spécialisé en informatique</span></td>
    <td class="tg-1v90">beaucoup plus de fonctionnalités</td>
  </tr>
</tbody>
</table>




---

## Envergure du logiciel

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/transkribus_bus.png" width="700">
</p>





<p align="center" alt="drawing">
<small-text>Illustration reprise de <a href="https://hal.science/hal-03692413/document">Gautier <i>et al.</i> (2022)</a>.</small-text>
</p>

---

## Choix du modèle de transcription

 <div class="container">
  <div class="column">
     <p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/modeles.png" width="400" height="550"><br>
</p></div>
  <div class="column">Recherche du <a href="https://readcoop.eu/transkribus/public-models/">modèle</a> publique de Transkribus :
     <ul>
         <li>120 modèles</li>
         <li>20 langues</li>
         <li>XI<sup>e</sup>-XXI<sup>e</sup> siècle</li>
     	 <li>imprimés, manuscrits ou dactylographiés</li>
         <li>26 alphabets</li>
         <li><i>CER</i> (angl. <i>character error rate</i>) : 0% – 13%</li>&nbsp;<small-text>→ taux d'erreur de caractère </small-text><br><small-text>🚩 combien de % des caractères avaient été mal transcrits ?</small-text>
      </ul>
         </div>

---

# 3️⃣ Mise en pratique

---

## Étapes d'utilisation de Transkribus 

0. créer un compte sur READ-COOP <span style="color:darkred"><b>(pré-requis)</b></span>
1. importer des documents 
2. effectuer des analyses de mise en page
3. transcrire automatiquement des documents à l'aide de modèles existants
4. entraîner un modèle spécifique pour vos documents <span style="color:darkred"><b>(vérité terrain nécessaire)</b></span> 
5. exporter des transcriptions dans différents formats

---

# Capsules vidéo 

## ▶️ [`playlist YouTube`](https://www.youtube.com/playlist?list=PLKM25d1uzpLhuHKRGsreV-c5-5ZPorrS2)

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/playlist.png" width="700">
</p>

---

## 0. Créer un compte sur READ-COOP ▶️ [`lien YouTube`](https://www.youtube.com/watch?v=JqYPCIF32uk)

* inscription et connexion sur le [site web](https://readcoop.eu/) de READ-COOP 

  <p align="center" alt="drawing">
      <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/inscription.png" width="850">
  </p>


---

## ✳️ Télécharger un document de Gallica ▶️ [`lien YouTube`](https://www.youtube.com/watch?v=uxjiVnYVdk4)

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/hist_grece.png" width="1000">
</p>

---

## 1. Importer des documents ▶️ [`lien YouTube`](https://youtu.be/LJZnHJlV1yg)

<div class="container-side">
  <figure>
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/collection.png" width="600" height="250" alt="">
    <figcaption>
      Créer une collection.
    </figcaption>
  </figure>
    <figure>
<img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/import.png" width="600" height="250" alt="">
<figcaption>
  Y importer les documents.
</figcaption>
</figure>




---

## 2-3. Analyse de mise en page + transcription automatique ▶️ [`lien YouTube`](https://youtu.be/Rhk98bgUWj8)

<div class="container-side">
  <figure>
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/module_trans.png" width="600" height="250" alt="">
    <figcaption>
      Module de transcription.
    </figcaption>
  </figure>
    <figure>
<img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/segm_trans.png" width="600" height="250" alt="">
<figcaption>
  Segmentation et transcription.
</figcaption>
</figure>

---

### 2.3 Liste des processus

💡 Pensez à rafraîchir la page pour voir si la transcription s'est terminée.

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/jobs.png" width="1000">
</p>

---

## 5. Export des transcriptions ▶️ [`lien YouTube`](https://youtu.be/wqz1PKrcOi4)

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/export.png" width="1000">
</p>

---

## 6. Recherche et comptage des mots ▶️ [`lien YouTube`](https://youtu.be/eWV0TfY5nc4)

* ces fonctionnalités ne sont pas disponibles dans Transkribus lite
* pour une utilisation plus avancée, télécharger Transkribus Expert Client

---

## Une alternative à Transkribus : *eScriptorium*

[`code source`](https://gitlab.com/scripta/escriptorium/)

Plusieurs instances :

* [SCAI](https://escriptorium.isir.upmc.fr/) (*Sorbonne Center for Artificial Intelligence*) de Sorbonne Université 
* [FoNDUE](https://test2.fondue.unige.ch/) (Université de Genève)
* [Inria](https://escriptorium.paris.inria.fr/) Paris

etc.

<small-text>*NB* : Pour accéder à l'interface eScriptorium, il faut disposer d'un compte individuel.</small-text> 

---

## Étape(s) suivante(s)

La transcription automatique de textes n'est pas une fin en soi.

* édition numérique

* fouille de textes (analyse stylistique, modélisation de sujets, etc.)

* établissement d'un moteur de recherche

  ...

---

# :four: Projets d'HTR

---

## Patrimonialisation numérique

Acteurs majeurs de patrimonialisation numérique dans le domaine d'HTR : 

* institutions patrimoniales (les *GLAM*) : BnF, Archives nationales, Bodmer Lab...

* institutions d'ESR : ENS, EPHE, École des Chartes, INRIA...

  <span style="float:right; font-size:18px">([Gautier <i>et al.</i>, 2022](https://hal.science/hal-03692413/document))

---

## Gallica

<span style="color:green"><b>Bibliothèque nationale de France (BnF)</b></span> transcrit systématiquement ses contenus imprimés et les rend disponibles dans sa bibliothèque numérique <a href="https://gallica.bnf.fr/ark:/12148/bpt6k317962c/f11.item.r=histoire%20de%20la%20gr%C3%A8ce">**Gallica**</a>. 

<p align="center" alt="drawing">
    <img src="/home/ljudmila/Dropbox/Bureau/formation_Transkribus_Uni_Angers/presentation/img/grece.png" width="650">
</p>

<p style="text-align:center; font-size: 70%">Interface de Gallica, <a href="https://gallica.bnf.fr/ark:/12148/bpt6k317962c/f11.item.r=histoire%20gr%C3%A8ce">exemple d'un document historique OCRisé</a>.</p>

---

## Projets et infrastructures

* [OCR-D](https://ocr-d.de/en/project.html) OCR pour les documents historiques imprimés en allemand

* [Archives municipales de Belfort](https://teklia.com/fr/blog/202211-belfort-en/) OCR · HTR en collaboration avec [TEKLIA](https://teklia.com/)

* [HIMANIS](https://himanis.hypotheses.org/) angl. ***HI**storical **MAN**uscript **I**ndexing for user-controlled **S**earch*

* [LECTAUREP](https://lectaurep.hypotheses.org/) **LECT**ure **A**utomatique de **REP**ertoires

* [CREMMA](https://inria.hal.science/hal-03541887/document) **C**onsortium **R**econnaissance d’**E**critures **M**anuscrites des **M**atériaux **A**nciens

* [FoNDUE](https://www.unige.ch/lettres/humanites-numeriques/recherche/projets-de-la-chaire/fondue) **FO**rmes **N**umerisees et **D**etection **U**nifiee des **E**critures

  ...

---

# ❓

# Questions et discussion libre

---

## Références 

<ul style="font-size: 20px">
    <li><b>Anderson, M.</b> (2021). <a href="https://www.itransition.com/blog/ocr-algorithm">« OCR algorithms: a complete guide »</a>. itransition.</li>
    <li><b>Barbier, J., & Mandret-Degeilh, A.</b> (2018). <a href="https://www.cairn.info/le-travail-sur-archives--9782200621056-page-195.htm">8. Les archives numériques et numériséeS.</a> Dans <i>Le travail sur archives.</i></li>
    <li><b>Camps, J.-B. & Perreaux, N.</b> (2021). <a href="https://outils.lamop.fr/lamop/mp3/E-Ndp/JBC-NP_e-NDP_OCR-et-HTR.pdf">Reconnaissance optique des caractères et des écritures manuscrites</a>. Projet E-NDP [<i>diapositives</i>].</li>
    <li><b>Chagué, A.</b> (2021). <a href="https://mate-shs.cnrs.fr/wp-content/uploads/2021/03/Tuto33_Chague_slide.pdf">« Comment faire lire des gribouillis à mon ordinateur ? »</a> [<i>diapositives</i>]. Inria Paris (ALMAnaCH).</li>
    <li><b>Canali, L.</b> (2016). <a href="https://db-blog.web.cern.ch/index.php/blog/luca-canali/2016-07-neural-network-scoring-engine-plsql-recognizing-handwritten-digits">A neural network scoring engine in PL/SQL for recognizing handwritten digits</a> [<i>blog</i>]. CERN Database Services. </li>
    <li><b>Cendre, R.</b> (2021). <a href="https://www.researchgate.net/figure/Representation-des-relations-entre-intelligence-artificielle-apprentissage-automatique_fig18_349180505">Classification par méthodes d’apprentissage supervisé et faiblement supervisé d’images multimodales pour l’aide au diagnostic du lentigo malin en dermatologie</a> [<i>thèse</i>]. Université de Bourgogne.</li>
    <li><b>Davalon, J.</b> (2014). <a href="https://shs.hal.science/halshs-01220537/document">Une patrimonialisation des archives ?</a>. Dans <i>L'archive dans quinze ans.</i></li>
            <li><b>Gabay et SciCoS</b> (2021). <a href="https://datascience.unige.ch/application/files/2316/3248/7621/3.3._Simon_Gabay__Jean-Luc_Falcone.pdf">FoNDUE (FOrmes Numerisees et Detection Unifiee des Ecritures) · An Handwritting Text Recognition infrastructure for Geneva.</a> Université de Genève.
    </li>
    <li><b>Gabay, S.</b> (2020). <a href="https://github.com/gabays/Cours_2020_01_Strasbourg/blob/master/OCR_pratique.pdf">« OCR »</a>. Formation OCR/<i>GROBID-dictionaries</i> 2020, Strasbourg.</li>
    <li><b>Lateef, Z.</b> (2023). <a href="https://www.edureka.co/blog/what-is-a-neural-network/">« What Is A Neural Network? Introduction To Artificial Neural Networks ».</a> edureka!.</li>
    <li><b>Lehman, J. & Clune, J.</b> (2014). <a href="https://www.researchgate.net/figure/An-illustration-of-deep-learning-As-a-deep-network-of-neurons-is-trained-to-recognize_fig1_273395781">An Anarchy of Methods: Current Trends in How Intelligence Is Abstracted in AI</a>. <i>Intelligent Systems, IEEE 29(6): 56-62</i>.</li>
    <li><b>Lepron, S.</b> (2023). <a href="https://www.abantiquo.fr/stockage-archives/">« Archivage, stockage, quelles différences ? »</a>. Ab Antiquo.</li>
</ul>

---

## Références II

  <ul style="font-size: 20px">
          <li><b>Galleron, I.</b> (2021). « Introduction aux humanités numériques (L1HN001) [<i>diapositives en interne</i>]. Sorbonne Nouvelle.</li>
      <li><b>Gautier, D., Huguet, A., Massot, M.-L., Tricoche, A., Carlin, M., Moreux, J.-P., & Rostaing, A.</b> <a href="https://hal.science/hal-03692413/document">Compte-rendu de la journée d’étude « Point HTR 2022 » Transkribus / eScriptorium : Transcrire, annoter et éditer numériquement des documents d’archives</a> [<i>rapport de recherche</i>]. Bibliothèque nationale de France – Site François-Mitterrand. CAPHES - UMS 3610 CNRS/ENS; AOROC.</li>
<li><b>Moufflet, J.-F.</b> (2021). <a href="https://www.bnf.fr/sites/default/files/2022-01/futurs_fantastiques_moufflet.pdf">5 ans d’expérimentation de la technologie HTR aux Archives nationales · Quels usages pour le futur ?</a>. Futurs Fantastiques – BnF.
      </li>
      <li><b>Ressources de géographie pour les enseignants.</b> (2019). <a href="http://geoconfluences.ens-lyon.fr/glossaire/patrimonialisation">« Patrimonialisation »</a>. Géoconfluences, ENS-Lyon.</li>
<li><b>Scheithauer, H.</b> (2023). <a href="https://www.theses.fr/s381671">Acquisition, intégration et redistribution de données structurées dans les GLAM : harmonisation des pratiques</a>. [<i>thèse</i>] PSL · EPHE.
            <li><b>Toumit, J. Y., Emptoz, H., Jean-Michel, R. O. Y., & Drézen, F.</b> (2000). <a href="https://books.google.fr/books?hl=en&lr=&id=s2INxlR0guEC&oi=fnd&pg=PA319&dq=Le+texte+math%C3%A9matique+:+du+document+papier...+%C3%A0+la+version+html&ots=DiQjaFP_hC&sig=k7XJoDpHe-5-d5rBhnZtyMWKM3c&redir_esc=y#v=onepage&q=Le%20texte%20math%C3%A9matique%20%3A%20du%20document%20papier...%20%C3%A0%20la%20version%20html&f=false">Le texte mathématique : Du document papier... à la version HTML.</a> Dans <i>CIFED'2000 : colloque international francophone sur l'écrit et le document</i> (p. 319). PPUR presses polytechniques.</li>
      <li><b>Vidal-Gorène, C.</b> (2023). <a href="https://programminghistorian.org/fr/lecons/transcription-automatisee-graphies-non-latines#pipeline-classique-dun-ocrhtr">La reconnaissance automatique d'écriture à l'épreuve des langues peu dotées</a>. Programming Historian.</li>
</ul>

<ul style="font-size: 20px">

</ul>
