UD_Old_French-PROFITEROLE
=========================

Attention: the main development of this treebank happens on the [GitLab of the Profiterole
Project](https://gitlab.huma-num.fr/profiterole/srcmf-ud), please file bug reports and requests
there.

## Summary

UD_Old_French-PROFITEROLE is an expansion of the previous UD_Old_French-SRCMF (which was a
conversion of (part of) the SRCMF corpus (Syntactic Reference Corpus of Medieval French
[srcmf.org](http://srcmf.org/)).

UD_Old_French-PROFITEROLE includes the texts of the previous UD_Old_French-SRCMF, plus Old French
texts that were annotated in the frame of the PROFITEROLE funded project (Projet
[ANR-16-CE38-0010](https://www.lattice.cnrs.fr/projets/projets-passes/projets-anr/projet-anr-profiterole),
2017-2022, supervised by Sophie Prévost) Texts were automatically annotated with part-of-speech and
dependencies, which are currently running a process of correction. Texs will be released in UD as
they are corrected. Middle French texts that were annotated in the PROFITEROLE project are to be
found in
[UD_Middle_French-PROFITEROLE](https://github.com/UniversalDependencies/UD_Old_French-PROFITEROLE).

## Introduction

UD_Old_French-PROFITEROLE consists in 12 texts spanning from 9th to 13th century. It includes 19765
sentences and 227137 tokens.

Sentences are annotated with the following metadata:

- `sent_id` : a unique id for each sentence in the treebank
- `text` : the sentence
- `newdoc id` : a unique id for each of the texts. This id can be split on underscores to get back :
  - name of the text
  - date
  - form : verse and/or prose

The following table lists the texts used in this treebank:

| ID                            | Name of the text       |       Author        | Tokens | Trees |
| :---------------------------- | :--------------------- | :-----------------: | -----: | ----: |
| Strasbourg_842_prose          | Serments de Strasbourg |      anonymous      |    131 |     3 |
| StEulalie_900_verse            | Séquence de Sainte Eulalie | anonymous      |    212 |    21 |
| StLegier_1000_verse           | Vie de saint Léger     |      anonymous      |   1665 |   189 |
| StAlexis_1050_verse           | Vie de saint Alexis    |      anonymous      |   5662 |   572 |
| Roland_1100_verse             | Chanson de Roland      |      anonymous      |  34803 |  3890 |
| Lapidaire_mid12_prose         | Lapidaire en prose     |      anonymous      |   5494 |   524 |
| QuatreLivresReis_late12_prose | Quatre livres des reis |      anonymous      |  15030 |  1509 |
| BeroulTristan_late12_verse    | Tristan de Beroul      |       Beroul        |  32596 |  3310 |
| TroyesYvain_1180_verse        | Yvain de Chrestien     | Chrestien de Troyes |  47964 |  3880 |
| Aucassin_early13_verse_prose  | Aucassin et Nicolet    |      anonymous      |  11639 |  1038 |
| Graal_1225_prose              | Queste del Saint Graal |      anonymous      |  44715 |  3114 |
| ClariConstantinople_1300_prose | Conqueste de COnstantinople | Robert de Clari | 27226 | 1715 |

 Total                          |                        |                     | 227137 | 19765 |

## Structure

In both of the SRCMF and PROFITEROLE projects, documents with less than about 40 000 words were
entirely annotated, while texts with more than 40 000 words were sampled in three parts (beginning,
middle and end of the text) to reach a total amount of about 40000 words.

As a result, UD_Old_French-PROFITEROLE includes 10 full texts (Strasbourg, StEulalie, StLegier,
StAlexis, Roland, Lapidaire, BeroulTristan, TroyesYvain, Aucassin, ClariConstantinople) and 2
sampled ones (QuatreLivresReis and Graal). It should be noticed that ClariConstantinople presently
includes only 27226 words. The remaining part will be released in May 2024.

The treebank is split as follows (in number of tokens) :

| ID                             |  Train |  Test |   Dev |
| :----------------------------- | -----: | ----: | ----: |
| Strasbourg_842_prose           |    131 |     0 |     0 |
| StEulalie_900_verse            |    212 |     0 |     0 |
| StLegier_1000_verse            |   1665 |     0 |     0 |
| StAlexis_1050_verse            |   5662 |     0 |     0 |
| Roland_1100_verse              |  22593 |  6080 |  6130 |
| Lapidaire_mid12_prose          |      0 |  2802 |  2692 |
| QuatreLivresReis_late12_prose  |  15024 |     6 |     0 |
| BeroulTristan_late12_verse     |  20404 |  6060 |  6132 |
| TroyesYvain_1180_verse         |  47964 |     0 |     0 |
| Aucassin_early13_verse_prose   |  11639 |     0 |     0 |
| Graal_1225_prose               |  33538 |  5578 |  5599 |
| ClariConstantinople_1300_prose |  21058 |  2993 |  3175 |
| Total                          | 179890 | 23519 | 23728 |

Note that most of Dev and Test data is taken from texts that also exist in Training data, but these
are large texts, so it does not make the testing too easy… One text (Lapidaire) is represented only
in Dev/Test but not in train. Pre-1100 texts are only in Train, because they seem too small to
reserve anything for testing. The rest of the data is for Train corpus.

## Deviations from UD

We added some more specific relations (subtypes), either to specify a relation, or in the case of
tokens entering a double dependency relation (typically : relative pronouns and  contracted forms) :

- `acl:relcl` : relative clause
- `advmod:obl` : contracted `advmod` + `obl` (e.g. _sin_ = _si_ + _en_)
- `aux:pass` : passive auxiliary
- `case:det` : contracted `case` + `det` (e.g. _del_ = _de_ + _le_)
- `cc:nc` : non coordinating conjunction (e.g. _et_ at the beginning of a sentence)
- `mark:advmod` : `mark` and `advmod` (e.g. _coment_ at the beginning of a subordinate clause)
- `nsubj:advmod` : contracted `nsubj` + `advmod` (e.g. _jon_ = _jo_ + _en_)
- `nsubj:obj` : contracted `nsubj` + `obj` (e.g. _quil_ = _qui_ + _le_)
- `obj:advmod` : contracted `advmod` + `obj` (e.g. _sis_ = _si_ + _les_)
- `obj:advneg` : contracted `negation` + `obj` (e.g. _nes_ = _ne_ + _les_)
- `obj:obl` : contracted `obl` + `obj` (e.g. _oul_ = _ou_ + _le_)
- `obl:advmod` : the double labelling accounts for the difficulty to decide between obl and advmod
  relations (`en` and `i`).

Consult [the language specific documentation](http://universaldependencies.org/fro/dep/index.html)
for further details.

## Acknowledgments

UD_Old_French-PROFITEROLE results from the UD_Old_French-SRCMF as well as from the automatic
annotation (PROFITEROLE project, 2017-2022) of other Old French texts (with the SRCMF corpus being
used as a training corpus), which were/are then manually corrected along with the UD guidelines. The
contributors to the syntactic part of the PROFITEROLE project were: Prévost, Sophie; Villemonte de
la Clergerie, Eric; Regnault, Mathilde; Grobol, Loïc; Crabbé, Benoît; Dehouck, Mathieu; Lavrentiev,
Alexei.

UD_Old_French-SRCMF resulted from the conversion of (part of) the SRCMF corpus (Syntactic Reference
Corpus of Medieval French [srcmf.org](srcmf.org)). The SRCMF corpus resulted from the SRCMF project
which took place in 2008-2012, funded by the ANR (France) and the DFG (Germany), and supervised by
Sophie Prévost and Achim Stein.

The SRCMF project consisted in the manual syntactic annotation of 15 texts (251,000 tokens) from the
9th to 13th C. Part-of-speech tags were for most of them retrieved from the already existing tagging
of the texts (stemming from: Base de Français Medieval, Lyon, ENS de Lyon, IHRIM Laboratory
[http://txm.bfm-corpus.org]([http://txm.bfm-corpus.org]), and the Nouveau Corpus d'Amsterdam
[http://www.uni-stuttgart.de/lingrom/stein/corpus#nca]([http://www.uni-stuttgart.de/lingrom/stein/corpus#nca]))

The contributors to the SRCMF project were: Stein, Achim; Prévost, Sophie; Rainsford, Tom;
Mazziotta, Nicolas;  Bischoff Béatrice; Glikman, Julie; Lavrentiev, Alexei; Heiden, Serge;
Guillot-Barbance, Céline; Marchello-Nizia, Christiane.

The whole SRCMF corpus (251,000 tokens) was converted into UD dependencies, but only 172,000 tokens
had undergone a significant checking.

The conversion from the original SRCMF annotation to the SRCMF-UD annotation was done automatically
both for the POS and the syntactic relations, thanks to a set of elaborated rules. Some 1,200
syntactic relations left unlabelled were then manually annotated (Sophie Prévost), and significant
spot-checking occurred, focusing on potential difficulties (e.g. conj relation).

This conversion was achieved by Aurélie Collomb, during an internship funded by lab Lattice (Paris,
CNRS, ENS & Université Sorbonne Nouvelle Paris 3, PSL & USPC), and supervised by Sophie Prévost,
Isabelle Tellier and Kim Gerdes. Marine Courtin achieved the deposit of the files, and especially
took in charge the validation of the corpus through the successive steps of the process.

A significant review of this initial release has been done on the occasion of the UD 2.6 release by
Loïc Grobol and Sophie Prévost in the frame of the [ANR PROFITEROLE
project](https://www.lattice.cnrs.fr/projets/projet-anr-profiterole) in order to improve the
compliance of the corpus to UD guidelines. This includes both automatic correction and extensive
manual corrections.

A significant import of data from the *Base de français medieval* has been done by Loïc Grobol,
Alexei Lavrentiev and Sophie Prévost on the occasion of the UD 2.9 release. Most notably, this
release adds punctuation tokens for most trees as well as around 350 new trees, consisting mostly of
averbal sentences and fixes a number of conformity bugs with the UD guidelines. See the full changes
in the [upstream repository](https://gitlab.huma-num.fr/profiterole/srcmf-ud/-/releases/v2.9.0)

## References

- Prévost, Sophie, Mathieu Dehouck, Alexei Lavrentiev, Serge Heiden et Loïc Grobol. To appear.
  ['Profiterole : un corpus morpho-syntaxique et syntaxique de français médiéval'], Corpus
- Stein, Achim, and Sophie Prévost. 2013. [‘Syntactic Annotation of Medieval Texts: The Syntactic
  Reference Corpus of Medieval French
  (SRCMF)’](https://halshs.archives-ouvertes.fr/halshs-01122079). In *New Methods in Historical
  Corpora*, edited by Paul Bennett, Martin Durrell, Silke Scheible, and Richard J. Whitt, 275–82.
  Corpus Linguistics and International Perspectives on Language. Gunter Narr Verlag.

## Changelog

- 2022-10-31 v2.13
  - Adds StEulalie and ClariConstantinople
  - See the [upstream release](https://gitlab.huma-num.fr/profiterole/srcmf-ud/-/releases/v2.13.0)
    for more details
  - Treebank renamed from UD\_Old\_French-SRCMF to UD\_Old\_French-PROFITEROLE.
- 2021-10-29 v2.9
  - Significant bugfix and data addition
  - Trees now have punctuation
  - See the [upstream release](https://gitlab.huma-num.fr/profiterole/srcmf-ud/-/releases/v2.9.0)
    for more details
  - **Punctuation addition HAS a significant impact on automatic performances in most settings**,
    please take this into account when comparing the results of parsers on this release with older
    releases
- 2020-05-15 v2.6
  - Significant bugfix release (more than 9k changed tokens)
- 2018-04-15 v2.2
  - Initial release

<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.2
License: CC BY-NC-SA 3.0
Includes text: yes
Genre: nonfiction legal poetry
Lemmas: not available
UPOS: converted with corrections
XPOS: manual native
Features: automatic
Relations: automatic with corrections
Contributors: Prévost, Sophie; Collomb, Aurélie; Gerdes, Kim; Tellier, Isabelle; Courtin, Marine; Lavrentiev, Alexei; Guillot-Barbance, Céline; Grobol, Loïc ; Regnault, Mathilde
Contributing: elsewhere
Contact: sophie.prevost@ens.psl.eu
===============================================================================
</pre>
