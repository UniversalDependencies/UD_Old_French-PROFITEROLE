# Summary

UD_Old_French-SRCMF is a conversion of (part of) the SRCMF corpus(Syntactic Reference Corpus of Medieval French [srcmf.org](http://srcmf.org/)).   

# Introduction

UD_Old_French-SRCMF consists in 10 texts spanning from 9th to 13th century.  

It includes XX sentences and 172 530 tokens.
Sentences are annotated with the following metadata :
+ sent_id : a unique id for each sentence in the treebank
+ text : the sentence which is analysed
+ newdoc id : a unique id for each of the texts. This id can be split on underscores to get back :
    + text
    + date
    + form : verse and/or prose


The following table lists the texts used in this treebank :

| ID | Author | Name of the text | Number of tokens |
| ------ | ------ | ------ | ------ |
| Strasbourg_842_prose | anonymous | Serments de Strasbourg | 115 |
| StLegier_1000_verse | anonymous | Vie de saint Léger | 1,388 |
| StAlexis_1050_verse | anonymous | Vie de saint Alexis | 4,868 |
| Roland_1100_verse | anonymous | Chanson de Roland | 28,997 |
| Lapidaire_mid12_prose | anonymous | Lapidaire en prose | 4,765 |
| QuatreLivresReis_late12_prose | anonymous | Quatre livres des reis | 13,061 |
| BeroulTristan_late12_verse | Beroul, Tristan | Tristan de Beroul  | 27,052 |
| TroyesYvain_1180_verse | Chrestien de Troyes, Yvain | Yvain de Chretien de Troyes | 41,702 |
| Aucassin_early13_verse-prose | anonymous | Aucassin et Nicolet | 9,946 |
| Graal_1225_prose | anonymous | Queste del Saint Graal | 40,636 |


# Structure

The corpus results from a conversion from the SRCMF corpus.
In the SRCMF projet, texts with less than about 40,000 words were entirely annotated, while texts with more than 40,000 words were sampled in three parts (beginning, middle and end of the text) to reach a total amount of about 40000 words.
As a result, UD_Old_French-SRCMF includes 8 full texts (Strasbourg, StLegier, StAlexis, Roland, Lapidaire, BeroulTristan, TroyesYvain, Aucassin) and 2 sampled ones (QuatreLivresReis and Graal).

# Deviations from UD

We added some more specific relations (subtypes) in the case of tokens entering a double dependency relation (typically : relative pronouns and  contracted forms) :  
+ mark:nsubj
+ mark:obl
+ mark:obj
+ advmod:obj
+ advmod:comp: in this case, the double labelling accounts for the difficulty to decide between advmod and obl relations.

Consult [the language specific documentation](http://universaldependencies.org/fro/dep/index.html) for further details concerning subtypes.


# Acknowledgments


UD_Old_French-SRCMF results from the conversion of (part of) the SRCMF corpus (Syntactic Reference Corpus of Medieval French [srcmf.org](srcmf.org)).

This conversion was achieved by Aurélie Collomb, in the frame of a internship funded by lab Lattice (Paris, CNRS, ENS & Université Sorbonne Nouvelle Paris 3, PSL & USPC), and supervised by Sophie Prévost, Isabelle Tellier and Kim Gerdes. Marine Courtin achieved the deposit of the files, and especially took in charge the validation of the corpus through the successive steps of the process.
The SRCMF corpus results from the SRCMF project which took place in 2008-2012, funded by the ANR (France) and the DFG (Germany), and supervised by Sophie Prévost and Achim Stein.
The SRCMF project consisted in the manual syntactic annotation of 15 texts (251,000 tokens) from the 9th to 13th C. Part-of-speech tags were for most of them retrieved from the already existing tagging of the texts (stemming from: Base de Français Medieval, Lyon, ENS de Lyon, IHRIM Laboratory [http://txm.bfm-corpus.org]([http://txm.bfm-corpus.org]), and the Nouveau Corpus d'Amsterdam [http://www.uni-stuttgart.de/lingrom/stein/corpus#nca]([http://www.uni-stuttgart.de/lingrom/stein/corpus#nca]))  
The contributors to the SRCMF project were: Stein, Achim; Prévost, Sophie; Rainsford, Tom; Mazziotta, Nicolas;  Bischoff Béatrice; Glikman, Julie; Lavrentiev, Alexei; Heiden, Serge; Guillot-Barbance, Céline.

The conversion from the original SRCMF annotation to the SRCMF-UD annotation was done automatically both for the POS and the syntactic relations, thanks to a set of elaborated rules.
Some 1,200 syntactic relations left unlabelled were then manually annotated (Sophie Prévost), and significant spot-checking occurred, focusing on potential difficulties (eg. conj relation).

The whole SRCMF corpus (251,000 tokens) was actually automatically converted into UD dependencies, but only 172,000 tokens have so far undergone a significant checking: the remaining 80,000 tokens will be added to UD_Old_French-SRCMF for the next release.


## References

* (citation)

# Changelog

* 2018-03-26 v2.2
  * Initial release

<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.2
License: CC BY-NC-SA License
Includes text: yes
Genre: literary, religious, historical, juridic, didactic
Lemmas: not available
UPOS: converted with corrections
XPOS: manual native
Features: automatic
Relations: automatic with corrections
Contributors: Prévost Sophie; Collomb, Aurélie; Gerdes, Kim; Tellier, Isabelle, Courtin, Marine; Lavrentiev Alexei; Guillot-Barbance, Céline.
Contributing: here source
Contact: sophie.prevost@ens.fr
===============================================================================
</pre>
