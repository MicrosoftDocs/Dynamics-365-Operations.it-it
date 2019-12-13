---
title: Utilizzare i moduli
description: In questo argomento viene descritto come e quando utilizzare moduli in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 06a26e5dfd35bf229e67ed27213210d0da726bdf
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698075"
---
# <a name="work-with-modules"></a>Utilizzare i moduli

In questo argomento viene descritto come e quando utilizzare moduli in Microsoft Dynamics 365 Commerce.

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

## <a name="overview"></a>Panoramica

I moduli sono blocchi predefiniti logici che costituiscono la struttura della pagina e hanno scopi e finalità. Alcuni moduli sono contenitori di alto livello e il loro solo scopo è di contenere e organizzare altri moduli (moduli figlio). Altri moduli, ad esempio un modulo Posizionamento immagine semplice, hanno uno scopo molto specifico. Altri moduli, come il modulo Sequenza, non rientrano in nessuna di queste due categorie.

Per impostazione predefinita, il sito di Dynamics 365 Commerce include una libreria di moduli dello starter kit che consente di ottenere la maggior parte degli scenari di e-Commere di base. Dovrebbe essere possibile poter creare un sito di e-Commerce end-to-end utilizzando questi moduli. Tuttavia, è anche possibile che si intenda personalizzare tali moduli o creare nuovi moduli personalizzati per specifiche esigenze. Se si desidera creare moduli personalizzati, un kit SDK di progettazione di moduli è disponibile per creare una libreria di moduli personalizzati.

## <a name="container-modules-and-slots"></a>Moduli contenitore e slot

Come indicato in precedenza, alcuni moduli sono progettati per contenere moduli figlio. Questi moduli sono noti come *contenitori* e consentono l'utilizzo di gerarchie di moduli nidificati. I moduli contenitore includono *slot*. Gli slot sono utilizzati per gestire il layout e lo scopo dei moduli figlio nel contenitore. Un esempio è un modulo contenitore pagina di base (un modulo di livello superiore per qualsiasi pagina) che definisce vari slot importanti:

- Uno slot di intestazione
- Uno slot corpo
- Uno slot piè di pagina

Lo sviluppatore del modulo definisce tali slot e determina quali e quanti moduli figlio possono essere inseriti direttamente all'interno di tale modulo. Ad esempio, lo slot intestazione potrebbe supportare solo un modulo di tipo **modulo Intestazione**, mentre lo slot corpo potrebbe supportare un numero illimitato di moduli di qualsiasi tipo (tranne altri moduli contenitore pagina).

Negli strumenti di creazione, gli autori di pagine non devono sapere in anticipo quali moduli possono e non possono essere inseriti in ogni slot. Quando gli autori di pagine selezionano uno slot e quindi tentano di selezionare un modulo da aggiungere allo slot, vedono una visualizzazione filtrata dei tipi di modulo supportati per quello slot.

## <a name="content-modules"></a>Moduli contenuto

I moduli contenuto contengono contenuto ed elementi multimediali, come testo (ad esempio, titoli, paragrafi e collegamenti) o riferimenti ad asset (ad esempio, immagini, video e PDF). Esempi di tipi di modulo contenuto tipici sono **Hero**, **Funzionalità** e **Banner**. I moduli di questi tre tipi possono contenere testo o elementi multimediali e non richiedono moduli figlio per rendere qualcosa visibile in una pagina.

La maggior parte delle attività di creazione di pagine e contenuto quotidiane tipiche comporta moduli contenuto, in particolare perché questi moduli definiscono il contenuto effettivo di cui viene eseguito il rendering nei moduli contenitore padre. Molti moduli contenuto sono disponibili e questi moduli sono in genere gli ultimi pezzi che saranno aggiunti alla gerarchia di moduli nidificati di una pagina.

Nella figura seguente viene illustrato come i moduli sono nidificati negli slot di moduli contenitore padre.

![Moduli nidificati](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Aggiungere o rimuovere moduli

Nelle procedure riportate di seguito viene descritto come aggiungere e rimuovere moduli.

### <a name="add-a-module"></a>Aggiungere un modulo

Per aggiungere un modulo a uno slot o contenitore in una pagina, effettuare le seguenti operazioni.

1. Nel riquadro a sinistra, selezionare un contenitore o uno slot a cui un modulo figlio può essere aggiunto.

    > [!NOTE]
    > Lo strumento di progettazione di moduli definisce l'elenco dei tipi di modulo che possono essere aggiunti a uno slot di modulo specifico. Gli autori di modelli possono quindi affinare le opzioni per moduli consentite per garantire un'ottimizzazione del motore di ricerca coerente e l'efficacia di creazione per tutte le pagine generate da un modello specifico.

1. Selezionare il pulsante con i puntini di sospensione (**...**) e quindi selezionare **Aggiungi modulo**. Viene visualizzata la finestra di dialogo **Aggiungi modulo**. Questa finestra di dialogo viene automaticamente filtrata in modo da visualizzare solo i moduli che sono supportati nel contenitore o nello slot selezionato. L'elenco di moduli viene determinato dal modello della pagina o dalla definizione del modulo contenitore.

    > [!NOTE]
    > Se un contenitore o uno slot non supporta nuovi moduli figlio, l'opzione **Aggiungi modulo** non è disponibile.

1. Nella finestra di dialogo, cercare e selezionare un modulo da aggiungere alla pagina.

    > [!TIP]
    > **Funzionalità** e **Hero** sono tipi di modulo ottimi per gli utenti inesperti.

1. Selezionare **OK** per aggiungere il modulo selezionato al contenitore o allo slot selezionato nella pagina.

### <a name="remove-a-module"></a>Rimuovere un modulo

Per rimuovere un modulo da uno slot o un contenitore in una pagina, effettuare le seguenti operazioni.

1. Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione accanto al nome del modulo da rimuovere e quindi selezionare il pulsante Cestino.
1. Quando viene richiesto di confermare la rimozione del modulo, selezionare **OK**.

## <a name="configure-modules"></a>Configurare moduli

Nelle procedure riportate di seguito viene descritto come configurare moduli contenuto e contenitore.

### <a name="configure-a-content-module"></a>Configurare un modulo contenuto

Per configurare un modulo contenuto in una pagina, effettuare le seguenti operazioni.

1. Nella riquadro a sinistra, selezionare un tipo di modulo contenuto (ad esempio **Funzionalità**, **Hero** o **Banner**).
1. Nel riquadro delle proprietà a destra, espandere i controlli nidificati selezionando le intestazioni e impostare tutti i valori di controllo necessari.
1. Se il riquadro delle proprietà include una sezione **Configurazione dati**, selezionarla per espanderla. Altrimenti, andare al passaggio 5.
1. Se è presente un pulsante **Aggiungi origine dati**, selezionarlo e quindi selezionare gli elementi contenuto da aggiungere.
1. Immettere le impostazioni per qualsiasi controllo di modulo necessario o desiderato.
1. Selezionare **Salva**.

### <a name="configure-a-container-module"></a>Configurare un modulo contenitore

Per configurare un modulo contenitore in una pagina, effettuare le seguenti operazioni.

1. Selezionare un modulo contenitore nella pagina (ad esempio un modulo contenitore fluido o Sequenza).
1. Nel riquadro delle proprietà a destra, espandere i controlli nidificati selezionando le intestazioni e impostare tutti i valori di controllo necessari.
1. Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione accanto al nome del contenitore o di qualsiasi slot nel contenitore e quindi selezionare **Aggiungi modulo**. Aggiungere quindi i moduli figlio al contenitore selezionato. Per ulteriori informazioni, vedere la procedura [Aggiungere un modulo](#add-a-module) descritta precedentemente in questo argomento.
1. Se molteplici moduli figlio esistono come elementi di pari livello in un contenitore padre, è possibile modificarne l'ordine di visualizzazione nel contenitore padre. Selezionare il pulsante con i puntini di sospensione per un modulo e quindi utilizzare i tasti freccia GIÙ o SU.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica modelli e layout](templates-layouts-overview.md)

[Utilizzare i modelli](work-with-templates.md)

[Utilizzare i layout preimpostati](work-with-layouts.md)

[Utilizzare i frammenti](work-with-fragments.md)

[Aggiungere un modulo contenitore a una pagina](add-container-module.md)

[Aggiungere moduli Posizionamento contenuti a una pagina](add-content-placement-modules.md)

