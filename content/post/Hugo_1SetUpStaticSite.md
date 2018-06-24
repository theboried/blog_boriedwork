---
title: "HUGO - 1. Generare un sito statico"
date: 2018-06-23T14:25:53+02:00
categories:
- Tutorial per nabbi (come me)
tags:
- hugo
- web
- siti-statici
- guida
keywords:
- hugo
- sito
- statico
- guida
- manuale
- tutorial
#thumbnailImage: //example.com/image.jpg
---

<!--more-->
## Eseguire il setup di un sito statico (e qualche nozione preliminare)

Se aprendo questo mio blog, sei stato in qualche modo colpito (magari un amico burlone è passato per il 'coppino' di rituale proprio in quel momento), o se hai pensato "cavolo, bello! Ma chissà quanto tempo c'avrà messo a sviluppare un sito del genere", ho una buona notizia per te caro lettore: la risposta è un paio d'ore.

![star eyes](https://i.ytimg.com/vi/YVTXdhTd4VM/maxresdefault.jpg "Start eyes")


Bada bene, un paio d'ore perché non sono pratico con **git** né con la piattaforma **github** che mi sono ripromesso di approffondire.
Non voglio correre troppo, ma in locale avevo già un'anteprima del sito fatto e finito dopo 20 minuti di lavoro.

Vuoi sapere come ho fatto? Presto detto...

... ma prima lasciami descriverti cos'è un sito statico. Se non t'interessa puoi comunque skippare questo piccolo cenno teorico.

Intanto partirei con una piccola definizione di 

<br />

### SITO STATICO:

    Il Web statico è un paradigma di progettazione e pubblicazione web caratterizzata, dal punto di vista comunicativo, in un'interazione sostanzialmente unilaterale: l'utente può visualizzare i contenuti forniti dall'autore di un sito, ma non può modificare lo stato né le informazioni. Da un punto di vista tecnico i contenuti, siano essi testuali, strutturati e formattati in documenti e fogli di stile, principalmente utilizzando nell'ordine i formati di marcatura HTML e CSS, o audiovisivi, sono memorizzati dal server e non vengono manipolati né da quel lato, prima della trasmissione al browser, né dall'altro, al momento della loro visualizzazione o riproduzione per l'utente. 

Grazie wikipedia (https://it.wikipedia.org/wiki/Web_statico).  
Detto in parole povere, tu lettore ti becchi il sito così per com'è fatto e se non ti stà bene cambia canale. 

Vediamo dunque, che questo tipo di soluzione può andar benone per:

* Siti al solo fine informativo
* Blog (sì come questo)
* Portfolio

Quindi applicazioni per cui si vuole mostrare qualcosa ad una persona senza che questa abbia la possibilità di fare azioni che richiederebbero un lavoro di *backend* (Es: comprare la lattiera del gatto online, chattare con l'amante, controllare se il treno per Roma sia in ritado (\*spoiler\*: sì lo è), etc)

Detto ciò, c'è da precisare il fatto che non siamo più nel Medioevo, in cui gli scribacchini si mettevano a copiare e incollare codice HTML su ogni singola pagina del proprio sito; ma siamo nel 2018 (ma guarda un po'!) e al giorno d'oggi esistono software che in un quattro e quattr'otto **generano** il nostro sito statico.

<br />

### GENERATORE DI SITO STATICO
Un generatore di siti statici è sostanzialmente un wrapper che dati in pasto una serie di cartelle e file, genera per l'appunto il sito. 

Andando nel dettaglio possiamo dire che un software di questo tipo si differenzia per:
* Linguaggio di programmazione
* Templates
* Plugins che possono essere utilizzati (abilitazione dei commenti dei post per esempio)

Esiste una lista bella corposa di generatori che ti linko qui: [Lista generatori siti statici](https://www.staticgen.com/)

Vogliamo cominciare? Allora, avvia il cronometro che ora ci diamo dentro.

Innanzitutto, precisiamo che la mia guida si baserà su **HUGO** un generatore scritto in **GO**. 

![HugoNotUgo](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQcb2KAMziebDCADblAZuVlZcspvof2IbbezYpQqMACq4GbP-yE "HugoNotUgo")
##### HUGO, non Ugo!
<br /> 

### 1. INSTALLAZIONE HUGO


Vai sulla pagina ufficiale d'installazione di **GOHUGO**: https://gohugo.io/getting-started/installing
e segui a menadito la procedura d'installazione per il tuo sistema operativo. Almeno che tu non sia su Linux basato su Debian, in questo caso (per esperienza personale) ti consiglierei di scaricarti e di installarti direttamente il deb della versione desiderata di Hugo da qui https://github.com/gohugoio/hugo/releases.
Scusa, non ti volevo spaventare, ma a quanto pare con **apt** (almeno, per ora) viene scaricata una versione di Hugo abbastanza vecchiotta, che mi ha fatto dannare per il tema che volevo utilizzare.

Lo dichiarano pure loro:

    Debian and Ubuntu provide a hugo version via apt-get:

    sudo apt-get install hugo

    Pros

        Native Debian/Ubuntu package maintained by Debian Developers
        Pre-installed bash completion script and man pages

    Cons

        Might not be the latest version, especially if you are using an older, stable version (e.g., Ubuntu 16.04 LTS). Until backports and PPA are available, you may consider installing the Hugo snap package to get the latest version of Hugo.

Quando hai finito, per essere sicuro di aver completato correttamente la procedura, lancia:

> hugo version

    Hugo Static Site Generator v0.25.1 linux/amd64 BuildDate: 2017-07-10T08:58:07+02:00
<br />

### 2. CREAZIONE DEL SITO

Qui non mi dilungherò. Solo la nota che per l'esempio ho usato la ~ che sta per la directory di HOME. 

<br />

1. Crea la cartella del sito con il comando di HUGO<br />

    > hugo new site ~/mySite<br />

    >
            Congratulations! Your new Hugo site is created in /tmp/mySite.
            Just a few more steps and you're ready to go:
            1. Download a theme into the same-named folder.
            Choose a theme from https://themes.gohugo.io/, or
            create your own with the "hugo new theme <THEMENAME>" command.
            2. Perhaps you want to add some content. You can add single files
            with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
            3. Start the built-in live server via "hugo server".
            
            Visit https://gohugo.io/ for quickstart guide and full documentation.

    <br />

2.  Posizionati nella cartella<br />


    > cd ~/mySite && ll<br />


    >
            total 64
            drwxr-xr-x  8 boried boried  4096 Jun 23 22:21 ./
            drwxrwxrwt 25 root     root     28672 Jun 23 22:21 ../
            drwxr-xr-x  2 boried boried  4096 Jun 23 22:21 archetypes/
            -rw-r--r--  1 boried boried    82 Jun 23 22:21 config.toml
            drwxr-xr-x  2 boried boried  4096 Jun 23 22:21 content/
            drwxr-xr-x  2 boried boried  4096 Jun 23 22:21 data/
            drwxr-xr-x  2 boried boried  4096 Jun 23 22:21 layouts/
            drwxr-xr-x  2 boried boried  4096 Jun 23 22:21 static/
            drwxr-xr-x  2 boried boried  4096 Jun 23 22:21 themes/

    <br />

3. Non c'è nessun punto 3. Abbiamo fatto; non ci resta che installare il tema.

<br />

### 3. INSTALLAZIONE E CONFIGURAZIONE DEL TEMA

La parte più piacevole e difficoltosa allo stesso tempo. Possiamo paragornare questa esperienza alla scelta del nickname del nostro personaggio ad un nuovo RPG. 

Da questa lista che ti linko https://themes.gohugo.io/, trovi tutti i temi che sono compatibili con **hugo**, scegli quello che più si addice a te e a quello che vuoi farne del tuo sito, tenendo conto che nella maggior parte dei casi colori e immagini sono customizzabili.

Ora, apri la repository del tema, clonalo nella cartella del sito creato nel punto 2, con:
> git clone https://github.com/kakawait/hugo-tranquilpeak-theme themes/traquilpeak 

(Questo è quello che ho usato io). 

Ora segui la procedura di configurazione descritta dall'autore del tema sulla pagina di github, che ti illustrerà come aggiornare il tuo file **config.toml** per poter usare il nuovo tema. Se ti potesse essere d'aiuto di lascio la mia configurazione per il tema https://github.com/kakawait/hugo-tranquilpeak-theme

>
    baseurl = "http://blog.boriedwork.space/"
    languageCode = "it-it"
    defaultContentLanguage = "it-it"
    title = "Boried Workspace"
    theme = "tranquilpeak"

    # googleAnalytics = "UA-123-45"
    paginate = 7
    canonifyurls = true

    [permalinks]
    post = "/:year/:month/:slug/"

    [taxonomies]
    tag = "tags"
    category = "categories"
    archive = "archives"

    [author]
    name = "Boried"
    bio = "Programmatore per lavoro e per passione.  Cerco sempre qualcosa di nuovo da imparare e voglio usare questo blog per mantenere traccia delle nuove nozioni con la possibilità di poterle condividere."
    job = "Sviluppatore software"
    location = "Italia"
    # Your Gravatar email. Overwrite `author.picture` everywhere in the blog
    gravatarEmail = "theboried@gmail.com"
    # Your profile picture
    # Overwritten by your gravatar image if `author.gravatarEmail` is filled
    picture = "theboried.theboried@gmail.com"
    # Your Twitter username without the @. E.g : thibaudlepretre
    # twitter = "thibaudlepretre"
    # Your google plus profile id. E.g : +ThibaudLepretre or 114625208755123718311
    # googlePlus = "+ThibaudLepretre"

    # Menu Configuration
    [[menu.main]]
    weight = 1
    identifier = "home"
    name = "Home"
    pre = "<i class=\"sidebar-button-icon fa fa-lg fa-home\"></i>"
    url = "/"
    [[menu.main]]
    weight = 2
    identifier = "categories"
    name = "Categories"
    pre = "<i class=\"sidebar-button-icon fa fa-lg fa-bookmark\"></i>"
    url = "/categories"
    [[menu.main]]
    weight = 3
    identifier = "tags"
    name = "Tags"
    pre = "<i class=\"sidebar-button-icon fa fa-lg fa-tags\"></i>"
    url = "/tags"
    [[menu.main]]
    weight = 4
    identifier = "archives"
    name = "Archives"
    pre = "<i class=\"sidebar-button-icon fa fa-lg fa-archive\"></i>"
    url = "/archives"
    [[menu.main]]
    weight = 5
    identifier = "about"
    name = "About"
    pre = "<i class=\"sidebar-button-icon fa fa-lg fa-question\"></i>"
    url = "/#about"

    [[menu.links]]
    weight = 1
    identifier = "github"
    name = "GitHub"
    pre = "<i class=\"sidebar-button-icon fa fa-lg fa-github\"></i>"
    url = "https://github.com/theboried"
    #[[menu.links]]
    #  weight = 2
    #  identifier = "stackoverflow"
    #  name = "Stack Overflow"
    #  pre = "<i class=\"sidebar-button-icon fa fa-lg fa-stack-overflow\"></i>"
    #  url = "https://stackoverflow.com/users/636472/kakawait"

    [[menu.misc]]
    weight = 1
    identifier = "rss"
    name = "RSS"
    pre = "<i class=\"sidebar-button-icon fa fa-lg fa-rss\"></i>"
    url = "/index.xml"

    [params]
    # Customize date format use to render blog post date, categories and other
    # You must use date format used by Go Time package https://golang.org/pkg/time/
    # Months (not work with short month like "jan", "feb", etc) are translated if translation exists on i18n folders
    # Default format is: January 2, 2006 
    dateFormat = "2 January 2006"

    # Global keywords configuration. Following keywords will be add to every pages
    # keywords = ["development", "next-gen"]

    # Syntax highlighter, possible choice between: "highlight.js" (recommanded) and "prism.js" (experimental)
    # You can comment it to disable syntax highlighting
    syntaxHighlighter = "highlight.js"

    # Hide sidebar on all article page to let article take full width to improve reading, and enjoy wide images and cover images. (true: enable, false: disable)
    clearReading = true

    # Define categories will create hierarchy between parents: `categories = ["foo", "bar"]` will consider "bar" a sub-category of "foo". 
    # If false it will flat categories.
    hierarchicalCategories = true

    description = "Hugo tranquilpeak theme demo"

    # Customization
    # Define the behavior of the sidebar
    # 1: Display extra large sidebar on extra large screen, large sidebar on large screen,
    #    medium sidebar on medium screen and header bar on small screen and
    # extra large sidebar is swiped on extra large screen and large sidebar on all lower screen (default)
    # 2: Display large sidebar on large screen, medium sidebar on medium screen and
    #    header bar on small screen and large sidebar is swiped
    # 3: Display medium sidebar on large and medium screen and header bar on small screen and
    #    medium sidebar is swiped
    # 4: Display header bar on all screens, extra large sidebar is swiped on extra large screen and
    #    large sidebar is swiped on all lower screens
    # 5: Display header bar on all screens and large sidebar is swiped on large screen
    # 6: Display header bar on all screens and medium sidebar is swiped
    sidebarBehavior = 1

    # Your blog cover picture. I STRONGLY recommend you to use a CDN to speed up loading of pages.
    # There is many free CDN like Cloudinary or you can also use indirectly
    # by using services like Google Photos.
    # Current image is on AWS S3 and delivered by AWS CloudFront.
    # Otherwise put your image in folder `static/_images/` (development)  or in `source/assets/images/` if you can't or don't want to build the theme,
    # and use relative url : `your-image.png`
    coverImage = "cover.jpg"

    # Display an image gallery at the end of a post which have photos variables (false: disabled, true: enabled)
    imageGallery = true

    # Display thumbnail image of each post on index pages (false: disabled, true: enabled)
    thumbnailImage = true
    # Display thumbnail image at the right of title in index pages (`right`, `left` or `bottom`)
    # Set this value to `right` if you have old posts to keep the old style on them
    # and define `thumbnailImagePosition` on a post to overwrite this setting
    thumbnailImagePosition = "bottom"
    # Automatically select the cover image or the first photo from the gallery of a post if there is no thumbnail image as the thumbnail image
    # Set this value to `true` if you have old posts that use the cover image or the first photo as the thumbnail image
    # and set `autoThumbnailImage` to `false` on a post to overwrite this setting
    autoThumbnailImage = true

    # Your favicon path, default is "/favicon.png"
    # favicon = "/favicon.png"

    # Header configuration
    # The link at the right of the header is customizable
    # You can add a link (as an icon) at the right of the header instead of the author's gravatar image or author's picture.
    # By default, author's gravatar or author's picture is displayed.
    #     url: /#search
    #     icon: search
    #     class: st-search-show-outputs

    # Custom CSS. Put here your custom CSS files. They are loaded after the theme CSS;
    # they have to be referred from static root. Example
    # [[params.customCSS]]
    #   href = "css/mystyle.css"

    # Custom JS. Put here your custom JS files. They are loaded after the theme JS;
    # they have to be referred from static root. Example
    # [[params.customJS]]
    #   src = "js/myscript.js"

    # Display `Next` on left side of the pagination, and `Prev` on right side one.
    # If you set this value to `true`, these positions swap.
    # swapPaginator = true

    # Sharing options
    # Comment and uncomment to enable or disable sharing options
    # If you wanna add a sharing option, read user documentation :
    # Tranquilpeak configuration > Theme configuration > sharing-options
    [[params.sharingOptions]]
        name = "Facebook"
        icon = "fa-facebook-official"
        url = "https://www.facebook.com/sharer/sharer.php?u=%s"

    [[params.sharingOptions]]
        name = "Twitter"
        icon = "fa-twitter"
        url = "https://twitter.com/intent/tweet?text=%s"

    [[params.sharingOptions]]
        name = "Google+"
        icon = "fa-google-plus"
        url = "https://plus.google.com/share?url=%s"

    [params.header.rightLink]
        class = ""
        icon = ""
        url = "/#about"

    # Customize link of author avatar in sidebar
    # [params.sidebar.profile]
    #   url = "/#about"

    # Customize copyright value "© 2017 <CUSTOMIZATION>. All Rights Reserved"
    # [params.footer]
    # copyright = "<a href=\"https://github.com/kakawait\">kakawait</a>"

### 4. TEST
Ora che abbiamo installato sito e tema non ci resta che controllare il risultato. Per farlo usa il comando dalla cartella del sito:

> hugo server -D

    Started building sites ...
    Built site for language en:
    0 draft content
    0 future content
    0 expired content
    0 regular pages created
    6 other pages created
    0 non-page files copied
    0 paginator pages created
    0 tags created
    0 categories created
    total in 6 ms
    Watching for changes in /tmp/mySite/{data,content,layouts,static}
    Serving pages from memory
    Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
    Press Ctrl+C to stop

Ora da browser sulla porta **1313** risponderà il nostro sito. Spero vivamente di essere stato d'aiuto.

Nella prossima guida vediamo come pubblicare il sito sull'internet, così tra una guida e l'altra puoi munirti di dominio. 

A presto! 