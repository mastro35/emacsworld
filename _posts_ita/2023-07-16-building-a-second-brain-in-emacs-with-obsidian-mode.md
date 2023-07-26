---
title: Building a Second Brain in Emacs with Obsidian Mode
tags: productivity "second brain" emacs
category: productivity
author: mastro35
share: true
layout: post
---

Vi piacerebbe poter impostare il vostro sistema personale di gestione della conoscenza in modo tale che sia facilmente utilizzabile e consultabile sia tramite Emacs che tramite una comoda app mobile? Beh, allora questo articolo potrebbe fare al caso vostro... :)

![brain](https://imgs.xkcd.com/comics/brain.png) {: .align-left} 

## La base teorica: il secondo cervello ed il metodo Zettelkasten 

Tutto nasce dallo [Zettelkasten](https://en.wikipedia.org/wiki/Zettelkasten), un sistema di gestione della conoscenza personale nato nel secolo scorso dalla prolifica mente del sociologo tedesco [Niklas Luhmann](https://en.wikipedia.org/wiki/Niklas_Luhmann). Da questo metodo nascerà poi (in particolar modo da [Tiago Forte](https://fortelabs.com)) una teoria più ampia di gestione di un sistema di informazioni digitale che permette di creare un repository navigabile di appunti in cui le singole note possano essere messe in relazione fra di loro.

Se vi sembra un concetto complicato o troppo astratto siete sulla strada giusta perchè probabilmente state cercando di immaginare qualcosa di rivoluzionario mentre invece tutto quello di cui stiamo parlando è un sistema di appunti in cui ad una nota si possano collegare altre note. Se quanto vi sto dicendo vi ricorda qualcosa meglio noto come "Wikipedia", siete sulla strada giusta. Di fatto stiamo parlando di creare una "Wikipedia" che abbia come base dati i vostri appunti personali.

Lo so, sto banalizzando il concetto presentandovi quello che viene ultimamente venduto come qualcosa di "rivoluzionario" come un semplice ipertesto dei vostri appunti, nulla di veramente rivoluzionario dato che il concetto di ipertesto come lo conosciamo oggi è un concetto nato nella prima metà del secolo scorso. 

Eppure, sebbene il concetto sia super semplice, spesso ci troviamo a prendere appunti su agende che poi finiscono su scaffali polverosi o su supporti non facilmente consultabili e sui quali non è possibile creare collegamenti fra le note. Perchè allora non provare a costruire un "secondo cervello" utilizzando strumenti pratici e moderni per la gestione della nostra conoscenza personale?

## Partiamo: la scelta degli strumenti

La prima cosa da fare per iniziare a costruire il proprio secondo cervello è capire con quali strumenti vogliamo crearlo. Nel capitolo precedente abbiamo parlato di ipertesti e di note in "stile Wikipedia", quindi potrebbe venirci l'idea di impostare il nostro sistema utilizzando l'HTML, giusto? Beh, io a dire il vero non sarei particolarmente emozionato al pensiero di dover scrivere i miei appunti in HTML... ma tutto sommato la direzione è quella corretta perchè l'HTML ha sicuramente un paio di caratteristiche molto interessanti: anzitutto permette di creare link ipertestuali e poi si basa su semplici file di testo, l'unico formato che è realistico pensare si potrà leggere anche tra 20 anni, a prescindere dai progressi che avverranno nel mondo informatico. 

Se solo ci fosse la possibilità di utilizzare un linguaggio di markup *simile* all'HTML ma più semplice e sempre basato su file di testo linkabili fra di loro... Beh, ma un formato simile esiste, anzi, ne esistono due che sono di fatto in concorrenza fra di loro: [Org](https://en.wikipedia.org/wiki/Org-mode) e [Markdown](https://en.wikipedia.org/wiki/Markdown).

Ora, questo è un sito che parla di Emacs, quindi vi attenderete che il formato scelto sia Org, giusto? 

Sbagliato.

Intendiamoci, Org è un formato di markup che non ha nulla da invidiare a Markdown, che supporta molte più funzionalità e con un Emacs mode (org-mode appunto) che lo rende veramente potentissimo e molto più versatile di Markdown. Inoltre grazie ad [Org Roam](https://www.orgroam.com) l'implementazione di un sistema di gestione della conoscenza personale è una questione di minuti, quindi per quale motivo dovremmo preferirgli Markdown? Per un semplicissimo motivo: Markdown è di gran lunga più conosciuto e a mio modo di vedere uno standard "de facto" per chi vuole utilizzare un linguaggio di markup plain text per produrre contenuto, mentre al di fuori della bolla di Emacs praticamente nessuno utilizza Org. 

Il fatto che Markdown sia così utilizzato ha reso possibile la nascita di numerosi strumenti per poterlo gestire per qualsiasi piattaforma e qualsiasi dispositivo. Esistono editor Markdown per Windows, Linux, MacOS, iOS, Android, FreeBSD e chi più ne ha più ne metta. Inoltre, su Markdown è basata un'app mobile che negli ultimi anni ha veramente cambiato il panorama degli strumenti con cui si può creare e gestire un secondo cervello: [Obsidian](https://obsidian.md). La caratteristica più interessante di Obsidian è che il suo utilizzo base prevede semplicemnete l'esistenza di una directory contenente files in markdown linkati fra di loro. Null'altro. E in più dispone di un'applicazione multipiattaforma molto potente e ben fatta. Ok, Obsidian sembra essere un'ottimo punto di partenza. L'unico problema di Obsidian è che... non è Emacs, giusto? Voglio dire, che Emacs sia di gran lunga lo strumento migliore per poter editare files di testo mi sembra scontato, non sarebbe fantastico poter utilizzare Emacs per lavorare sui nostri file Obsidian quando siamo davanti ad un computer? Beh, tutto questo in realtà è possibile grazie ad un pacchetto che si chiama [obsidian.el](https://github.com/licht1stein/obsidian.el) ed al suo creatore [Mykhaylo Bilyanskyy](Mykhaylo Bilyanskyy). 









