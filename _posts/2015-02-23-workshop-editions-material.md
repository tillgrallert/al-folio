---
layout: post
title: "Überlegungen und Material für den Editionsworkshop im März 2015 am OIB"
author: Till Grallert
date: 2015-02-23
categories:
- blog
tags:
- digital humanities
- digital editions
- workshop
- tei
- xml
excerpt_separator: <!--more-->
---

# Technische Aspekte, oder: the D in Digital Humanities

## Grundsätze

+ **wenige** und **simple** Formate / Programmiersprachen, die mit einfachsten Texteditoren bearbeitet werden können, damit sie von den Nutzer_innen, und das sind in der Regel Geistes- und Sozialwissenschaftler_innen, gebraucht werden können. D.h. im besten Fall wird ein einziges Format und eine einzige Sprache für den gesamten Editions-/ Publikationsprozess verwandt.
+ Formate / Programmiersprachen müssen **menschen- und maschinenlesbar** sein. Damit wird sichergestellt, dass sogar ein plain-text-Ausdruck auf Papier prinzipiell verständlich ist, auch wenn dabei natürlich viel, wenn nicht gar sämtliche, Funktionalität verloren geht. 
+ Sämtliche Sprachen und Programme sollten **open source** und **etabliert** sein, mit einer großen Community. Das verhindert einen lock-in und Abhängigkeit von einem einzelnen Abieter.
+ Sprachen sollten im **Publikationsgewerbe** und **Editionsprojekten** weit verbreitet  sein.
<!--more-->

## Evaluation aktueller Stand am OIB

Die **aktuell** von uns (OIB) benutzten Formate und Programme **erfüllen die technischen Grundsätze alle nicht**!

* Viele Produktionsprozesse finden innerhalb von **Microsoft Office** statt und setzen auf Microsoft Dateiformate. Die älteren dieser Formate (.doc, .xls, .ppt ...) sind prinzipiell weder dokumentiert noch offen und ohne Lizenz benutzbar. Obwohl seit 2007 Microsoft XML-basierte Formate benutzt (.docx, .xslx, .pptx ...), sind diese nicht dokumentiert und müssen, wenn sie außerhalb von Microsoftprodukten benutzt werden sollen, *reverse engineered* werden.
* Unser digitaler Output ist häufig ein **PDF**. Dieses ist ein proprietäres Adobe Format und nicht dokumentiert. Sollen PDFs auf einem professionellen Level erstellt werden, sind sehr teure Lizenzen für Adobeanwendungen notwendig. Während es die Darstellung auf allen Anzeigegeräten stabil hält indem es sich nicht oder nur sehr schwer bearbeiten lässt, verhindert es genau dadurch ein gemeinsames Arbeiten an einem Quelltext. Außerdem ist PDF ausschließlich auf die *optische Präsentation* und nicht die *logische Organisation* der Inhalte ausgerichtet. Es ist fast unmöglich auch aus einem "guten" PDF wieder eine bearbeitbare Datei zu erzeugen ohne wesentliche Aspekte eines Textes zu verlieren. Für webbasierte Anwendungen ist es prinzipiell nicht gemacht oder geeignet (da es z.B. nicht sequentiell geladen werden kann und damit enorme Bandbreiten verschlingt).
    
## Technische Vorschläge: XML

Viele Editionsprojekte und Verlage setzen daher auf **XML** und die damit verbundenen Spezifikationen / Techniken, die sämtlich offene Standards oder Recommendations des W3C Konsortiums sind. XML **erfüllt alle oben angeführte Grundsätze**. Um einen Eindruck von den Möglichkeiten zu bekommen, ist es sinnvoll sich unten stehende, beispielhafte Editionsprojekte und -werkzeuge anzuschauen.

Um [Stefan Müllers Fazit](http://mws.hypotheses.org/1571) zu zitieren: "Geisteswissenschaftler sollen mit XML umgehen können, weil der Umgang mit Texten, Textstruktur und Textsemantik zum Kernbereich der Geisteswissenschaft gehört, weil die dabei anfallenden Entscheidungen auch nur der Fachwissenschaftler, kein hilfreich herbeieilender Techniker treffen kann und weil der Umgang mit XML auch gar nicht so schwierig ist wie die wirklich harten Probleme ‒ die sind bei einer Edition stets philologischer Natur. Wenn man von der XML-Frage verallgemeinernd absieht, wird der Impetus ein aufklärerischer: Es geht dann um den Ausgang des Geisteswissenschaftlers aus einer selbstverschuldeten Unmündigkeit, was Datenverarbeitung angeht. Besteht diese Unmündigkeit? Und ist sie selbstverschuldet ‒ aus denselben Ursachen, die Kants berühmter Aufsatz nennt? Hier liegt ein Problem, das unangenehmer ist als etwa das vergleichsweise harmlose Ansinnen, die Geisteswissenschaften im Social Web zu verankern."

* **XML** (Extensible Markup Language): [Spezifikationen]( http://www.w3.org/TR/xml11), [Wikipedia](https://en.wikipedia.org/wiki/XML). XML ist eine strikt hierarchische Markup-Sprache in der prinzipiell zwischen funktionalem Markup und Inhalt unterschieden wird. Da XML sehr ausführlich/ wortreich ist und sämtliche Dinge explizit beschrieben werden müssen, ist XML menschenlesbar. XML unterstützt Unicode und LnR-Sprachen, wie Arabisch. Die eigentlichen Regeln für das Markup einer Datei weden in sogenannten Schemata festgelegt, über die jedes Projekt selbst entscheiden kann. XML ist international und in Deutschland sowohl für Editionsprojekte als auch im Publikationsgewerbe weit verbreitet (siehe Beispiele unten). Außerdem sind viele von uns allen täglich benutzte Dateiformate XML-Varianten, z.B. sämtliche aktuelle Microsoft Office Formate (enden auf "x", wie z.B. ".docx"). Allerdings sind nicht alle dieser Schemata und Spezifikationen offen und gut dokumentiert (auch hier ist wieder Microsoft Office zu nennen).
    * **XSLT** (Extensible Stylesheet Language Transformations): [Spezifikation](http://www.w3.org/TR/xslt20/), [Wikipedia](https://en.wikipedia.org/wiki/XSLT). Deklarative Sprache um XML Dokumente in andere XML Dokumente (inklusiver anderer Markup-sprachen, wie z.B. HTML) zu transformieren. Die Sprache selbst wird in XML geschrieben.
    * **XPath**: data model, [Spezifikationen](http://www.w3.org/TR/xpath-datamodel/.), [Wikipedia](https://en.wikipedia.org/wiki/XPath). Mit XPath können die einzelnen Elemente innerhalb einer XML-Datei adressiert werden und simple Operationen vorgenommen werden. XPath ist ein subset von XQuery.
    * **XQuery**: [Spezifikationen](http://www.w3.org/XML/Query/), [Wikipedia](https://en.wikipedia.org/wiki/XQuery)
+ **[TEI P5 XML](http://www.tei-c.org/index.xml)**: Die aktuelle Fassung des XML Schemas der Text Encoding Initiative (TEI). Hierbei handelt es sich um einen quasi-Standard, der ursprünglich für die digitale Abbildung und Beschreibung (i.e. Edition) analoger Quelltexte entwickelt worden ist. Allerdings wird TEI auch zunehmend für born-digital Texte verwandt.
+ **XML Datenbanken**: auf der Grundlage von XML Datenbanken wie z.B. [eXist DB](http://exist-db.org/exist/apps/homepage/index.html) können komplette, dynamische Onlinelösungen in XML und XQuery geschrieben werden. Ein gutes Beispiel ist hierbei die Webseite des [Office of the Historian of the United States](http://history.state.gov/).
   * [MyCoRe repository framework](http://sourceforge.net/projects/mycore/): ein Dokumentenserver; open source, benutzt Java, XML und "different database backends". Dieses System wird für Herrn Leders Projekt einer "Encyclopaedia of Islamic Political Thought" eingesetzt. Andere Nutzer sind unter anderem das Projekt zur Katalogisierung und Digitalisierung aller [Islamischer Handschriften der Universitätsbibliothek Leipzig](http://www.islamic-manuscripts.net/content/below/index.xml).

# Beispiele und konkrete Vorschläge

Damit alle Teilnehmer_innen gebrauch von der folgenden Liste machen können, ist diese vornehmlich in englisch verfasst.

- Tools / Research environments:
    <!-- + **[TextGrid](http://www.textgrid.de/en/)**: eine virtuelle Forschungsumgebung, die sowohl Repositorien als auch Werkzeuge für textbasierte Forschung bietet. Entwickelt u.a. von Berlin-Brandenburgische Akademie der Wissenschaften (BBAW), Georg-August-Universität Göttingen, Niedersächsische Staats- und Universitätsbibliothek Göttingen (Projektleitung), Institut für Deutsche Sprache Mannheim, Julius-Maximilians-Universität Würzburg, Max-Planck-Institut für Wissenschaftsgeschichte Berlin, Technische Universität Berlin, Technische Universität Darmstadt.-->
    + **[TextGrid](http://www.textgrid.de/en/)**: a virtual research environment, providing a repository for digital texts as well as various editing tools; developed by the [Berlin-Brandenburgische Akademie der Wissenschaften (BBAW)](http://www.bbaw.de), Georg-August-Universität Göttingen, Niedersächsische Staats- und Universitätsbibliothek Göttingen (Projektleitung), Institut für Deutsche Sprache Mannheim, Julius-Maximilians-Universität Würzburg, Max-Planck-Institut für Wissenschaftsgeschichte Berlin, Technische Universität Berlin, Technische Universität Darmstadt.
    <!-- + **[Ediarum](http://www.bbaw.de/telota/software/ediarum)**: eine virtuelle Forshungsumgebung, entwickelt von der BBAW. Basiert auf XML, TEI P5, eXist DB, XQuery etc. und kann sowohl Webauftritt als auch Printeditionen produzieren. Ein Erfahrungsbericht des [Schleiermacher Projektes](http://www.bbaw.de/forschung/alphabetisch/schleiermacher_II) mit dieser Software findet sich [hier](http://digiversity.net/2012/digitale-arbeitsumgebung-fur-das-editionsvorhaben-schleiermacher-in-berlin-1808-1834/). -->
    + **[Ediarium](http://www.bbaw.de/telota/software/ediarum):** a virtual research environment developed by the BBAW. It is based on XML, TEI P5, eXist DB, XQuery etc. and can be used to generate websites as well as printed editions. The [Schleiermacher Projekt](http://www.bbaw.de/forschung/alphabetisch/schleiermacher_II) provides a [report](http://digiversity.net/2012/digitale-arbeitsumgebung-fur-das-editionsvorhaben-schleiermacher-in-berlin-1808-1834/) on their experiences with this software.
    + **[Archiv Editor](http://www.bbaw.de/en/telota/projectcollection/archiv-editor)**. XML-editor, developed by the BBAW.
    + **[DFG-Viewer](http://dfg-viewer.de/ueber-das-projekt/)**: Plattform zur Anzeige von Digitalisaten mit einer METS/MODS und METS/TEI XML Schnittstelle.
    + **[Classical Text Editor](http://cte.oeaw.ac.at//)**: Ziemlich altes Windows-only Programm zur Edition von Texten, dass nicht mehr aktiv weiterentwickelt wird (es gab in den letzten 5 Jahren nur ein winziges Update), produziert TEI XML und HTML. Wird/ wurde am OIB bereits benutzt.
        *  **UPDATE** CTE is under active development and version 9 was just released (20 Feb 2015) --- some 6 years after v8.
    + [**T-Pen** (transcription for paleographical and editorial notation)](http://t-pen.org/TPEN/): Werkzeug zur Transkription von Digitalisaten, erlaubt den Export von XML Dateien.
    <!-- + **[tranScriptorium](http://transcriptorium.eu)**: Ein Projekten zur Entwicklung von Transkriptionswerkzeugen für historische Dokumente, inklusive sogenannter HandwrittenText Recognition (HTR) Werkzeuge. Der Fokus liegt auf europäischen Sprachen, aber der Ansatz ist für Arabisch durchaus interessant. Das Projekt bietet eine   [online Demonstration](http://transcriptorium.eu/demots/htr/index.php) an. -->
    + **[tranScriptorium](http://transcriptorium.eu)**: a project for the development of transcription tools for historical documents, inluding so-called Handwritten Text Recognition (HTR) tools. The project focusses on European languages, but their approach might be interesting for Arabic and other L-to-R scripts as well. They provide a functional [online demo](http://transcriptorium.eu/demots/htr/index.php).
    <!-- + **DENQ** (Digitale Editionen neuzeitlicher Quellen): Vom DHI in Rom und London entwickelte Editions- und Publikationsumgebung. Setzt auf einer eXistDB Datenbank und TEI XML auf ist allerdings kein offenes Projekt. Es existiert keine Dokumentation vage Beschreibungen sind vier bis sechs Jahre alt.[^1] -->
    + **DENQ** (Digitale Editionen neuzeitlicher Quellen): editing and publishing tool. Based on eXist DB and TEI XML. Under development by the DHI Rome and London. A rather vague and old description, dating to 2008(!), can be found [here](http://digiversity.net/2010/denq/) and [here](http://www.roman-repertories.net/fileadmin/user_upload/pdf-dateien/Online-Publikationen/Dresden_Histtag/Hist_Grundlagenforschung_Mittelalter_Neuzeit.pdf). The project is not open and there is no publicly accessible documentation.
    + **[Juxta](http://www.juxtasoftware.org/)**: open-source tool for comparing and collating multiple witnesses to a single textual work; XML.
    + [**EVT** (Edition Visualization Technology)](http://sourceforge.net/projects/evt-project/): a set of interdependent XSLT stylesheets to publish digital editions marked-up in TEI P5 to a website. EVT was developed for the [Vercelli Book Digitale beta edition](http://vbd.humnet.unipi.it/beta/) and a description was published in [JTEI (Rosselli et al. 2014)](http://jtei.revues.org/1077).
    + [**DTA** (Deutsches Text Archiv)](http://deutschestextarchiv.de): they, inter alia, developed the DTABf (DTA-Basisformat) as a strict subset of TEI P5 to ensure a very high level of interoperability for their large corpus of German texts between the 17th-19th centuries. They also supply an oXygen framework. A description was published in [JTEI (Haaf et al. 2014)](http://jtei.revues.org/1114).
     

- Digital editions
    + [First Folio](http://firstfolio.bodleian.ox.ac.uk/): digital Shakespeare edition. Based on TEI XML.
    + Das [Deutsche Text Archiv, DTA](http://www.deutschestextarchiv.de/doku/workflow), XML basiert. Benutzt TEI und eigene Erweiterungen.
    + [Schleiermacher Projekt](http://www.bbaw.de/forschung/alphabetisch/schleiermacher_II). Briefedition auf Basis von TEI XML.
    <!-- + [Refaiya Library](http://www.refaiya.uni-leipzig.de), Leipzig: Katalogisierung und Digitalisate von Manuskripten der Rifāʾiyya Bibliothek. XML basierter Dokumentenserver. Die bibliographischen Metadaten sind in METS/TEI bzw. in METS/MODS erfasst. Die Digitalisate werden über den DFG-Viewer ausgegeben. -->
    + **[Refaiya Library](http://www.refaiya.uni-leipzig.de)**, Leipzig: an XML-based document server providing a catalogue and digitized manuscripts from the Rifāʾiyya library. Bibliographic meta data is recorded in METS/TEI or METS/MODS. Digitised items are served online through the DFG-Viewer software.
    + [The Leipzig Open Fragmentary Texts Series (LOFTS)](http://www.dh.uni-leipzig.de/wo/projects/open-greek-and-latin-project/the-leipzig-open-fragmentary-texts-series-lofts/): Producing open editions of ancient works that survive only through quotations and re-uses in later texts, including Arabic translations; TEI, XML, RDF.
    + [Briefe und Texte aus dem intellektuellen Berlin um 1800](http://tei.ibi.hu-berlin.de/berliner-intellektuelle/). Texteditionen auf Basis von TEI XML.
    + [Perseus Digital Library](http://www.perseus.tufts.edu/hopper/): Bietet unter anderem eine TEI basierte Onlineversion von [Lane's Arabic Dictionary](http://www.perseus.tufts.edu/hopper/text?doc=Perseus%3atext%3a2002.02.0015).
    + [The Digital Walters](http://www.thedigitalwalters.org/01_ACCESS_WALTERS_MANUSCRIPTS.html): u.a. Bilddigitalisate von Koranmanuskripten und anderen arabischen Handschriften des Walters Art Museum, die Facsimiles werden über TEI XML erschlossen. 
    
- Further projects and initiative
    + **[DiXit](http://dixit.uni-koeln.de/home.html)**: Digital Scholarly Editions, Initial Training Network
    + [**IDE** (Institut für Dokumentologie und Editorik)](http://www.i-d-e.de/): <!-- Publizieren u.a. Listen mit hilfreichen Werkzeugen, eine Schriftenreihe und den [Review of of digital editions (RIDE)](http://ride.i-d-e.de). --> network of researchers involved in the development of tools and practices for digital editions. They organise workshops and spring/summer schools. They also publish a book series and a [Review of digital editions (RIDE)](http://ride.i-d-e.de).
    <!-- + [Wellcome Arabic Manuscript Cataloguing Project](http://wamcp.bibalex.org/home): Entwicklung eines XML Schemas zur Beschreibung arabischer Manuskripte basierend auf TEI/ENRICH XML model. Die Webseite bietet Zugang zu Bilddigitalisaten der Manuskripte. -->
    + **[Wellcome Arabic Manuscript Cataloguing Project](http://wamcp.bibalex.org/home)**: Developed an XML schema for the description of Arabic manuscripts based on the TEI/ENRICH XML model. The website also provides access to digitised images of the manuscripts.
    + **[Fihrist](http://www.fihrist.org.uk/home)**: <!-- Unionskatalog arabischer Manuskripte, basiert auf TEI XML.--> union catalogue of Arabic manuscripts. Based on TEI XML.

# Literature / Links

- Haaf, Susanne, Alexander Geyken, and Frank Wiegand. "[The DTA 'Base Format': A TEI Subset for the Compilation of a Large Reference Corpus of Printed Text From Multiple Sources](http://jtei.revues.org/1114)." *Journal of the Text Encoding Initiative* 8: Selected Papers from the 2013 TEI Conference (2015)
- Hedges, Mark, Heike Neuroth, et al. "[TextGrid, TEXTvre, and DARIAH: Sustainability of Infrastructures for Textual Scholarship](http://jtei.revues.org/774)." *Journal of the Text Encoding Initiative* 5: TEI Infrastructures (2013): doi:10.4000/jtei.774
- Hudrisier, Henri, Rachid Zghibi, et al. *[Promoting the Linguistic Diversity of TEI in the Maghreb and the Arab Region](http://digilab2.let.uniroma1.it/teiconf2013/wp-content/uploads/2013/09/book-abstracts.pdf#page=65).* Presentation at TEI Conference and Members Meeting 2013. The Linked TEI: Text Encoding in the Web. Rome, 2013. <!-- http://digilab2.let.uniroma1.it/teiconf2013/wp-content/uploads/2013/09/book-abstracts.pdf#page=65 (accessed October 29, 2014)-->
- Müller, Stefan. "[Der Veſte Buchſtab. Digitale Editionen, Ihre Erstellung und Darbietung](http://mws.hypotheses.org/1571)." Wissen in Verbindung. Bericht über das Arbeitstreffen „digital humanities. Wissenschaftliche Datenbanken und Editionsprojekte“ der Max Weber Stiftung, 29-30 Nov. 2012. <!-- http://mws.hypotheses.org/1571 (accessed December 11, 2014) -->
- Pearce, Sarah. "[Notes from the Life of a Medievalist: Textual Corpora and the Digital Islamic Humanities, Day 1](http://meshalim.blogspot.co.uk/2014/10/textual-corpora-and-digital-islamic.html)." <!-- http://meshalim.blogspot.co.uk/2014/10/textual-corpora-and-digital-islamic.html (accessed December 18, 2014). -->
- Pearce, Sarah. "[Notes from the Life of a Medievalist: Textual Corpora and the Digital Islamic Humanities, Day 2](http://meshalim.blogspot.co.uk/2014/10/textual-corpora-and-digital-islamic_18.html)." <!-- http://meshalim.blogspot.co.uk/2014/10/textual-corpora-and-digital-islamic_18.html (accessed December 18, 2014).-->
- Rosselli Del Turco, Roberto, Giancarlo Buomprisco, et al. "[Edition Visualization Technology: A Simple Tool to Visualize TEI-based Digital Editions](http://jtei.revues.org/1077)." *Journal of the Text Encoding Initiative* 8: Selected Papers from the 2013 TEI Conference (2014)
- Soualah, Mohammed Ourabah and Mohamed Hassoun. "[A TEI P5 Manuscript Description Adaptation for Cataloguing Digitized Arabic Manuscripts](http://jtei.revues.org/398)." *Journal of the Text Encoding Initiative* 2 (2012): doi:10.4000/jtei.398

# Resources
    
- [http://svnextern.dl.uni-leipzig.de/viewsvn/](http://svnextern.dl.uni-leipzig.de/viewsvn/) providing code for IslamHS and various other projects, including the Refaiya
- [overleaf](https://www.overleaf.com/): commercial (?) colaborative publishing platform. Based on LaTeX.
