---
title: Utilizzare i file di sostituzione CSS
description: Questo argomento descrive perché, quando e come utilizzare i file di sostituzione CSS (Cascading Style Sheets) in Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3ec43b16b1df07400cffe597378ad4035e4d07e0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413459"
---
# <a name="work-with-css-override-files"></a>Utilizzare i file di sostituzione CSS


[!include [banner](includes/banner.md)]

Questo argomento descrive perché, quando e come utilizzare i file di sostituzione CSS (Cascading Style Sheets) in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Gli stili permanenti del sito dovrebbero generalmente essere gestiti attraverso un tema del sito. I temi forniscono i CSS e le impostazioni di stile fondamentali per i moduli su qualsiasi pagina del tuo sito. I temi vengono creati utilizzando l'SDK online di Dynamics 365 Commerce vengono distribuiti ai siti Web tramite Lifecycle Services (LCS) di Microsoft Dynamics. Le funzionalità di debug dei temi e le configurazioni dell'interfaccia del modulo nell'SDK aiutano gli sviluppatori del sito a creare pacchetti di progettazione del sito personalizzabili e coerenti. Quando questi pacchetti di progettazione vengono distribuiti in un sito, gli autori del sito possono concentrarsi sulla creazione, la modifica e la pubblicazione di contenuti anziché sullo sviluppo del sito.

Dato il normale ciclo di vita di un tema, la dipendenza dagli sviluppatori per apportare modifiche di stile attraverso la pipeline di distribuzione SDK e LCS può essere proibitiva in alcuni scenari. I prototipi o gli aggiornamenti rapidi del sito possono sembrare complicati se l'SDK non è configurato o se non si ha il tempo di attendere una distribuzione LCS.

In questi scenari, i file di sostituzione CSS possono essere di aiuto. Negli strumenti di creazione di Commerce, gli utenti autenticati possono caricare un file CSS, visualizzalo in anteprima e quindi attivalo per sovrascrivere il tema di un sito. Non è richiesto il sovraccarico della distribuzione di SDK o LCS. Le sostituzioni specificate in un file di sostituzione CSS può essere piccolo come una modifica a un singolo stile di testo o ampio come una revisione completa del marchio.

Prima di utilizzare i file di sostituzione CSS, tenere presenti le seguenti limitazioni:

- Su un sito può essere attivo un solo file di sostituzione CSS alla volta. Pertanto, tutte le sostituzioni attive devono essere in un singolo file di sostituzione.
- Sebbene sia possibile visualizzare l'anteprima delle sostituzioni negli strumenti di creazione di Commerce, non esistono funzioni di debug dedicate per identificare eventuali bug introdotti dalle sostituzioni. In altre parole, quando si utilizzano i file di sostituzione CSS, non si dispone dello stesso set di strumenti fornito dall'SDK per la convalida del modulo e della creazione.

Tuttavia, i file di sostituzione CSS forniscono un modo rapido per eseguire il prototipo di un progetto o implementare un aggiornamento rapido prima che venga sviluppato e distribuito un aggiornamento completo del tema.

## <a name="create-a-css-override-file"></a>Creare un file di sostituzione CSS

Per creare un file di sostituzione CSS, è possibile utilizzare qualsiasi ambiente di sviluppo integrato (IDE), editor di testo o editor di codice sorgente. Un approccio tipico consiste nell'utilizzare i debugger Web standard nel browser per identificare selettori di stile, proprietà e valori nel sito esistente. La maggior parte dei browser consente di modificare i valori e visualizzarli in anteprima nel debugger. Dopo aver identificato le modifiche che si desidera apportare, è possibile salvarle nel proprio file CSS.

## <a name="upload-a-css-override-file"></a>Caricare un file di sostituzione CSS

Per caricare un file CSS sul sito in Commerce, effettuare le seguenti operazioni.

1. Negli strumenti di creazione, accedere al sito.
1. Nel riquadro di navigazione a sinistra, selezionare **Progetto**.

    > [!NOTE]
    > A seconda della versione degli strumenti di creazione di Commerce che stai utilizzando, potresti dover espandere **Impostazioni** nel riquadro di navigazione prima di poter selezionare **Progetto**.

1. Nella parte superiore del riquadro di progettazione principale, selezionare la scheda **Sostituzione CSS**, se non è già selezionata.
1. In **Sostituzioni CSS disponibili**, Selezionare **Carica file CSS**. Viene visualizzata una finestra Esplora file.
1. In Esplora file, cercare e selezionare un file CSS, quindi selezionare **Apri**. Il file CSS caricato ora appare sotto **Sostituzioni CSS disponibili**.

## <a name="preview-a-css-override-file"></a>Anteprima di un file di sostituzione CSS

Per visualizzare l'anteprima di un file di sostituzione CSS prima di renderlo attivo sul sito live, effettuare le seguenti operazioni.

1. Nel riquadro di navigazione a sinistra, selezionare **Progetto** e quindi sulla scheda **Sostituzione CSS**, sotto **Sostituzioni CSS disponibili**, trovare il file CSS che si desidera visualizzare in anteprima.
1. Accanto al nome file CSS, selezionare **Anteprima del sito**.
1. Nella finestra di dialogo **Seleziona un URL** selezionare l'URL del sito a cui si desidera applicare la sostituzione, quindi selezionare **OK**.
1. Se esistono più varianti per l'URL selezionato, selezionare la variante desiderata nella finestra di dialogo **Anteprima delle variazioni** visualizzata.

Viene aperta una nuova scheda o finestra del browser, in cui è possibile convalidare le sostituzioni di stile sul sito. È quindi possibile condividere l'URL con altri utenti Commerce autenticati per la revisione e il feedback.

## <a name="activate-a-css-override-file-on-your-live-site"></a>Attivare un file di sostituzione CSS sul sito live

Dopo aver visualizzato in anteprima e approvato il file di sostituzione CSS, è possibile attivarlo sul sito live.

> [!NOTE]
> Sul sito può essere attivo un solo file di sostituzione CSS alla volta. Se si attiva un nuovo file di sostituzione, il precedente file di sostituzione viene disattivato. Pertanto, assicurarsi che tutte le sostituzioni richieste siano presenti in un solo file di sostituzione CSS.

Per attivare un file di sostituzione CSS, effettuare le operazioni seguenti.

1. Nel riquadro di navigazione a sinistra, selezionare **Progetto** e quindi sulla scheda **Sostituzione CSS**, sotto **Sostituzioni CSS disponibili**, trovare il file CSS che si desidera attivare.
1. Sotto il nome file CSS, selezionare **Attiva**. Il file di sostituzione diventa immediatamente attivo sul sito live.

## <a name="deactivate-a-css-override-file-on-your-live-site"></a>Disattivare un file di sostituzione CSS sul sito live

Per disattivare un file di sostituzione CSS sul sito, effettuare le operazioni seguenti.

1. Nel riquadro di navigazione a sinistra, selezionare **Progetto** e quindi sulla scheda **Sostituzione CSS**, sotto **Sostituzioni CSS disponibili**, trovare il file CSS che si desidera disattivare.
1. Sotto il nome file CSS, selezionare **Disattiva**. Il file di sostituzione diventa immediatamente inattivo sul sito live.

> [!TIP]
> Per accedere a opzioni aggiuntive per i file di sostituzione CSS, selezionare i puntini di sospensione ( **...**) accanto al nome del file CSS. Le opzioni **Scarica**, **Rinomina** e **Sostituisci** sono utili per le modifiche rapide a un file di sostituzione CSS esistente.

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere un logo](add-logo.md)

[Selezionare un tema per il sito](select-site-theme.md)

[Utilizzare set di impostazioni di stile](style-presets.md)

[Aggiungere una favicon](add-favicon.md)

[Aggiungere un messaggio di benvenuto](add-welcome-message.md)

[Aggiungere informazioni sul copyright](add-copyright-notice.md)

[Aggiungere lingue al sito](add-languages-to-site.md)

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)
