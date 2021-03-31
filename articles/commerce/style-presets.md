---
title: Utilizzare le impostazioni predefinite degli stili
description: In questo argomento viene descritto come utilizzare set di impostazioni di stile in Creazione di siti Web di Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 55d333c3ae94b17dabaef3c697c698f068a06543
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226593"
---
# <a name="work-with-style-presets"></a>Utilizzare le impostazioni predefinite degli stili

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come utilizzare set di impostazioni di stile in Creazione di siti Web di Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un set di impostazioni di stile è un insieme memorizzato di tutti i valori di stile modificabili nel tema di un sito. Può essere utilizzato per modificare immediatamente l'aspetto di un sito tramite Creazione di siti Web. I set di impostazioni di stile consentono ai creatori di Creazione di siti Web di modificare, visualizzare in anteprima e attivare rapidamente un insieme di valori di stile nel proprio sito, senza dover utilizzare Cascading Style Sheets (CSS) o distribuire temi. Stili di caratteri, stili di pulsanti e colori di sito sono esempi tipici di variabili di stile che possono essere gestite tramite set di impostazioni di stile.

L'insieme delle variabili di stile disponibili in un sito è determinato dalla libreria di temi e moduli distribuita al tenant di un sito. Il kit SDK online di Dynamics 365 Commerce consente agli sviluppatori di implementare tutte le variabili di stile modificabili necessarie per un determinato tema. Abilitando più variabili di stile, uno sviluppatore di temi può consentire ai creatori di siti di prendere le decisioni finali relative agli stili da utilizzare per i siti. Pertanto, i non sviluppatori possono aggiornare e visualizzare in anteprima gli stili di sito utilizzando il set di strumenti. La funzionalità è utile anche per qualsiasi scenario in cui le modifiche dirette a temi o CSS causerà spese inutili.

I temi in cui sono abilitate le variabili di stile modificabili richiedono un set di impostazioni di stile predefinito. Questi possono facoltativamente includere ulteriori opzioni preimpostate come parte di un pacchetto di temi distribuito. Ad esempio, è possibile distribuire un tema che ha un unico set di impostazioni di stile "modern light" predefinito. In alternativa, potrebbe includere ulteriori opzioni di set di impostazioni di stile oltre al set predefinito, come  "modern dark", "vintage light" o "vintage dark". Questi set di impostazioni di tema incoporati sono creati dagli sviluppatori e possono essere utilizzati come punto di partenza per la progettazione di nuovi siti.

In Creazione di siti Web, i creatori possono selezionare set di impostazioni incorporati di un tema oppure creare set di impostazioni e personalizzazioni utilizzando le variabili di stile abilitate. Un set di impostazioni di stile può essere visualizzato in anteprima in Creazione di siti Web prima che venga attivato sul sito live. Dopo aver esaminato le modifiche allo stile del creatore, è possibile impostare il set di impostazioni su "attiva" per il sito live.

## <a name="preview-a-style-preset"></a>Visualizzare in anteprima un set di impostazioni di stile

Per visualizzare in anteprima un set di impostazioni di stile nel proprio sito in Creazione di siti Web seguire questi passaggi.

1. Nel riquadro di navigazione sinistro del sito, andare a **Impostazioni sito \> Progettazione**.
1. Nella scheda **Set di impostazioni di stile** nella parte superiore dell'editor di progettazione, nell'elenco **Set di impostazioni di stile disponibili**, selezionare un set di impostazioni, quindi selezionare **Visualizza** per accedere all'editor di set di impostazioni.

    Se al momento non ci sono set di impostazioni nell'elenco **Set di impostazioni disponibili**, vedere [Creare un set di impostazioni di stile personalizzato](#create-a-custom-style-preset) per informazioni su come creare un set di impostazioni di stile personalizzato.

    > [!NOTE]
    > I set di impostazioni già presenti nel tema sono indicate con **Incorporato**. Questi set di impostazioni incorporati sono di sola lettura. Per copiare un set di impostazioni incorporato come nuovo set di impostazioni personalizzabile, selezionare il pulsante con i puntini di sospensione (**...**) per il set di impostazioni, quindi selezionare **Salva con nome**.

1. Nella barra dei comandi, selezionare **Anteprima**.
1. Selezionare un URL nel sito da utilizzare per visualizzare in anteprima il set di impostazioni di stile, quindi selezionare **OK**.
1. Selezionare la variante URL specifica del canale e delle impostazioni locali da visualizzare in anteprima selezionando il nome della variante. Viene aperta una nuova finestra del browser di anteprima, in cui il set di impostazioni di stile selezionato viene applicato alla pagina specificata.

> [!NOTE]
> L'URL di anteprima è persistente e autenticato. Pertanto, è possibile copiarlo, incollarlo e inviarlo ad altri colleghi autenticati per la revisione prima di impostarlo su "attivo" sul sito live. L'URL di anteprima è utile anche per controllare gli stili in diversi dispositivi, browser e schermate.

> [!TIP]
> Quando si modifica un set di impostazioni di stile, potrebbe rivelarsi utile lasciare aperta la finestra del browser di anteprima in una finestra del browser separata, in modo da poter convalidare rapidamente le modifiche. Dopo aver salvato le modifiche a un set di impostazioni, aggiornare la finestra del browser di anteprima aperta per convalidare l'esperienza dell'utente.

## <a name="create-a-custom-style-preset"></a>Creare un set di impostazioni di stile personalizzato

Per creare un set di impostazioni di stile personalizzato in Creazione di siti Web seguire questi passaggi.

1. Nel riquadro di navigazione sinistro del sito, andare a **Impostazioni sito \> Progettazione**.
1. Nella barra dei comandi della scheda **Set di impostazioni di stile** nella parte superiore dell'editor di progettazione, selezionare **Nuovo set di impostazioni**.
1. Immettere un nome e una descrizione per il nuovo set di impostazioni e selezionare **Salva**. Viene creato un nuovo set di impostazioni personalizzabile che utilizza i valori predefiniti del tema come punto di partenza.

> [!NOTE]
> È anche possibile creare un nuovo set di impostazioni di stile personalizzato a partire da qualsiasi set di impostazioni esistente selezionando il pulsante con i puntini di sospensione (**...**) per quel set di impostazioni e quindi selezionando **Salva con nome**. In alternativa, selezionare **Salva con nome** nella barra dei comandi dell'editor di set di impostazioni.

## <a name="modify-global-and-module-type-style-values"></a>Modificare i valori di stile del tipo di modulo e globali

Alcune delle variabili di stile di un tema sono condivise tra più tipi di modulo. Queste variabili di stile sono note come variabili di stile *globali*. Gli esempi includono i colori principali del sito, gli stili di carattere predefiniti e gli stili dei pulsanti. Impostando le variabili globali, è possibile modificare l'aspetto di molti tipi di modulo differenti.

Alcuni valori di stile possono essere univoci per un tipo di modulo oppure è possibile che debbano eventualmente sostituire un valore globale predefinito. Se il tema di un sito ha implementato variabili di stile del tipo di modulo, i creatori di Creazione di siti Web possono personalizzare lo stile di un tipo di modulo indipendentemente dalle impostazioni globali. Le variabili del tipo di modulo possono aumentare o sovrascrivere le variabili di stile globali in un tema.

> [!NOTE]
> La gerarchia dei valori di stile in un sito si comporta nel modo seguente. I valori di stile che appaiono più a destra sovrascrivono i valori di stile a sinistra degli stessi.
>
> Valori predefiniti del tema \<Valori di stile globali \< Valori di stile del tipo di modulo \< Sostituisci CSS

Per modificare i valori globali o del tipo di modulo di un set di impostazioni di stile in Creazione di siti Web, attenersi alla seguente procedura.

1. Nel riquadro di navigazione sinistro del sito, andare a **Impostazioni sito \> Progettazione**.
1. Nella scheda **Set di impostazioni di stile** nella parte superiore dell'editor di progettazione, selezionare **Visualizza** per qualsiasi set di impostazioni di stile per accedere all'editor di set di impostazioni.
1. Selezionare **Anteprima**, quindi seguire i passaggi di selezione dell'URL per aprire un'anteprima del set di impostazioni in una finestra del browser. Lasciare aperta questa finestra di anteprima del browser.
1. Nell'editor di set di impostazioni, selezionare **Modifica** in alto a destra.
1. Utilizzare i controlli delle variabili di stile nell'editor per modificare alcuni valori di stile globali.
1. Nella parte superiore dell'editor, nella scheda **Moduli** a destra della scheda **Globale**, selezionare un tipo di modulo a cui deve essere applicato uno stile.
1. Utilizzare i controlli di stile per modificare alcuni valori per il tipo di modulo.
1. Quando si è pronti per visualizzare in anteprima le modifiche, selezionare **Salva** nella barra dei comandi.
1. Tornare alla finestra di anteprima del browser aperta e aggiornarla. L'anteprima nella finestra del browser è utile per controllare le modifiche allo stile in differenti punti di interruzione della visualizzazione, browser e piattaforme di dispositivi.
1. Quando tutte le modifiche sono state completate e convalidate, selezionare **Fine modifica** in alto a destra nell'editor.

> [!NOTE]
> Se si sta modificando il set di impostazioni di stile attualmente attivo nel sito, verrà visualizzato un badge blu **Attivo** nell'editor. Questo badge indica che il set di impostazioni è attualmente attivo sul sito web. Se si modifica il set di impostazioni attivo, selezionare **Pubblica** per inviare tali modifiche al sito live.

## <a name="make-a-new-style-preset-active-on-your-live-site"></a>Rendere un nuovo set di impostazioni attivo nel sito live

Per impostare un set di impostazioni di stile come nuovo set di impostazioni di stile nel sito, seguire questi passaggi.

- Selezionare il pulsante **Imposta come attivo** in una di queste posizioni:

    - La barra dei comandi nell'editor del set di impostazioni di stile
    - Il menu con i puntini di sospensione (**...**) per tutti i set di impostazioni disponibili nella visualizzazione principale nella scheda **Set di impostazioni di stile** in **Impostazioni sito \> Progettazione**

I valori di stile del set di impostazioni diventano attivi nel sito Web visibile al pubblico.

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere un logo](add-logo.md)

[Selezionare un tema per il sito](select-site-theme.md)

[Utilizzare i file di sostituzione CSS](css-override-files.md)

[Aggiungere una favicon](add-favicon.md)

[Aggiungere un messaggio di benvenuto](add-welcome-message.md)

[Aggiungere informazioni sul copyright](add-copyright-notice.md)

[Aggiungere lingue al sito](add-languages-to-site.md)

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]