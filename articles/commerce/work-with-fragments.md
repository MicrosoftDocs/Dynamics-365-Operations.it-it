---
title: Utilizzare i frammenti
description: In questo argomento viene descritto perché, quando e come utilizzare frammenti in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f29046ded47ed9c49a2cc841aa7c1f6492b49aec
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124361"
---
# <a name="work-with-fragments"></a>Utilizzare i frammenti 


[!include [banner](includes/banner.md)]

In questo argomento viene descritto perché, quando e come utilizzare frammenti in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

I frammenti consentono un'esperienza di creazione centralizzata per le configurazioni di moduli che devono essere riutilizzate in tutto il sito. Ad esempio, intestazioni, piè di pagina e banner sono spesso configurati come frammenti, in quanto sono condivisi da molte pagine. È possibile considerare i frammenti come pagine Web in miniatura inseribili in altre pagine del sito. I frammenti hanno un ciclo di vita proprio. In altre parole, vengono creati, utilizzati come riferimento, aggiornati ed eliminati come entità indipendenti negli strumenti di creazione.

Dopo che i frammenti sono stati configurati, possono essere utilizzati in tutte le aree della struttura del sito in cui l'uso dei moduli è consentito. È possibile fare riferimento ai moduli in pagine, layout, modelli e altri frammenti.

> [!NOTE]
> I frammenti possono essere nidificati fino a sette livelli di profondità in altri frammenti.

Ad esempio, se si desidera promuovere un evento promozionale in molte pagine del sito, è possibile utilizzare un frammento. Il primo passaggio del processo di creazione di un nuovo frammento consiste nel selezionare il tipo di modulo da cui iniziare. Per questo esempio, genereremo un frammento da un modulo Hero.

> [!NOTE]
> I frammenti possono essere creati da qualsiasi tipo di modulo.

È quindi possibile configurare il frammento hero con lo specifico contenuto promozionale. È anche possibile localizzarlo come necessario. Il nuovo frammento hero autonomo può quindi essere utilizzato come modulo preconfigurato in tutto il sito. È possibile aggiungerlo facilmente a modelli, pagine specifiche o altri frammenti che possono contenere moduli Hero.

Tutte le posizioni in cui il frammento viene aggiunto sono riferimenti al frammento hero centrale creato. Se si pubblicano modifiche al frammento, queste vengono immediatamente riflesse in tutte le posizioni in cui si fa riferimento al frammento nel sito. Di conseguenza, i frammenti sono un modo potente ed efficiente di riutilizzare e gestire centralmente le configurazioni di moduli in un sito. Un uso efficiente dei frammenti consente di aumentare notevolmente l'agilità e contribuisce a ridurre i costi associati alla gestione del contenuto del sito.

Nella figura seguente viene illustrato come è possibile utilizzare i frammenti per centralizzare la creazione di configurazioni di modulo condivise in un sito di e-Commerce.

![Figura che mostra come utilizzare i frammenti per centralizzare la creazione di configurazioni di modulo condivise in un sito di e-Commerce](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a>Creare un frammento

È possibile creare un nuovo frammento o salvare una configurazione di modulo esistente come frammento.

### <a name="save-an-existing-module-configuration-as-a-fragment"></a>Salvare una configurazione di modulo esistente come frammento

Per convertire un modulo configurato precedentemente in un frammento riutilizzabile, effettuare le seguenti operazioni.

1. Aprire una pagina o un modello che contiene il modulo da convertire in frammento.
1. Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione (**...**) accanto al nome del modulo. 
1. Selezionare **Condividi come frammento**. 
1. Viene visualizzata una finestra di dialogo. Immettere un nome e i metadati per il frammento.
1. Selezionare **OK** per salvare la configurazione di modulo come frammento che è possibile aggiungere ad altre pagine.

L'immagine seguente mostra come salvare una configurazione di modulo come frammento.

![Schermata di come salvare una configurazione di modulo come frammento](./media/save-as-fragment.png)

### <a name="create-a-new-fragment"></a>Creare un nuovo frammento

Per creare un nuovo frammento, completare i passaggi seguenti.

1. Selezionare **Frammenti** nel pannello di navigazione a sinistra.
1. Selezionare **Nuovo frammento pagina**. Viene visualizzata una finestra di dialogo contenente tutti i tipi di modulo disponibili. Come indicato in precedenza, i frammenti possono essere creati da qualsiasi tipo di modulo.
1. Selezionare un tipo di modulo per il frammento.

L'immagine seguente mostra dove creare un nuovo frammento.

![Una schermata di dove creare un nuovo frammento](./media/fragment-nav-menu.png)

> [!TIP]
> Se si seleziona un tipo di modulo contenitore generico, si avrà a disposizione la massima flessibilità quando si dovrà aggiornare e configurare il frammento in seguito.

## <a name="add-remove-or-edit-fragments-on-a-page"></a>Aggiungere, rimuovere o modificare frammenti in una pagina

Nelle procedure riportate di seguito viene descritto come aggiungere, rimuovere e modificare frammenti.

### <a name="add-a-fragment"></a>Aggiungere un frammento

Per aggiungere un frammento a una pagina, effettuare le operazioni indicate di seguito.

1. Nella riquadro a sinistra, selezionare un contenitore o uno slot a cui è possibile aggiungere moduli figlio.
1. Selezionare il pulsante con i puntini di sospensione al nome del contenitore o dello slot, quindi selezionare **Aggiungi frammento**. Viene visualizzata una finestra di dialogo.

    ![Una schermata di come aggiungere un frammento esistente a uno slot o contenitore](./media/add-fragment.png)
 
    > [!NOTE]
    > Se il contenitore o lo slot non supporta nuovi moduli figlio, l'opzione **Aggiungi frammento** non è disponibile.
    
1. Nella finestra di dialogo, cercare e selezionare un frammento da aggiungere. Se non sono elencati frammenti disponibili, è necessario dapprima creare un frammento da un tipo di modulo che lo slot o il contenitore supporta.
1. Selezionare il frammento desiderato per aggiungerlo al contenitore o allo slot nella pagina.

    ![Schermata della finestra modale del selettore di frammenti](./media/fragment-picker.png)

> [!NOTE]
> I moduli consentiti in un contenitore o in uno slot sono definiti in base al modello della pagina o alle definizioni dei moduli.

### <a name="remove-a-fragment"></a>Rimuovere un frammento

Per rimuovere un frammento da uno slot o un contenitore in una pagina, effettuare le seguenti operazioni.

1. Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione accanto al nome del frammento da rimuovere e quindi selezionare il pulsante Cestino.
1. Quando viene richiesto di confermare la rimozione del frammento, selezionare **OK**.

> [!NOTE]
> Quando si rimuove un frammento da una pagina, si rimuove solo il riferimento allo stesso da quella pagina. **Non** si elimina il frammento dal sito. Per eliminare frammenti dal sito, è necessario utilizzare l'interfaccia utente del controllo frammenti. È possibile eliminare frammenti da un sito solo se si fa riferimento agli stessi con un qualsiasi modello, pagina o altro frammento.

### <a name="edit-a-fragment"></a>Modificare un frammento

Per modificare i frammenti, è necessario utilizzare l'interfaccia utente dell'editor di frammenti. Questa restrizione è dovuta alla struttura. Impedisce agli autori di confondere il processo di modifica dei moduli per una pagina specifica con il processo di modifica di frammenti che potrebbero essere condivisi da più pagine.

Per modificare un frammento, completare i passaggi seguenti.

1. Selezionare **Frammenti** nel pannello di navigazione a sinistra.
1. In **Frammenti**, selezionare il frammento da modificare.
1. Modificare le proprietà del modulo del frammento e la struttura come necessario. Il processo è analogo a quello per modificare i moduli nella visualizzazione dell'editor di pagine.

È anche possibile modificare un frammento selezionandolo in una pagina, in un modello o in un frammento padre e quindi selezionando **Modifica frammento** nel riquadro delle proprietà a destra.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica modelli e layout](templates-layouts-overview.md)

[Utilizzare i modelli](work-with-templates.md)

[Utilizzare i layout preimpostati](work-with-layouts.md)

[Utilizzare i gruppi di pubblicazione](publish-groups.md)
