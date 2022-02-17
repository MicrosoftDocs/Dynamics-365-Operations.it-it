---
title: Utilizzare i frammenti
description: In questo argomento viene descritto perché, quando e come utilizzare frammenti in Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 02/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 98cb1fba158ea99427d2068ca49b257cb5290de3
ms.sourcegitcommit: 1eef00796f7c5511f432b01800cdf8920992d7d5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2022
ms.locfileid: "8090746"
---
# <a name="work-with-fragments"></a>Utilizzare i frammenti 

[!include [banner](includes/banner.md)]

In questo argomento viene descritto perché, quando e come utilizzare frammenti in Microsoft Dynamics 365 Commerce.

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

![Figura che mostra come utilizzare i frammenti per centralizzare la creazione di configurazioni di modulo condivise in un sito di e-Commerce.](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a>Creare un frammento

È possibile creare un nuovo frammento o salvare una configurazione di modulo esistente come frammento.

### <a name="save-an-existing-module-configuration-as-a-fragment"></a>Salvare una configurazione di modulo esistente come frammento

Per convertire un modulo configurato precedentemente in un frammento riutilizzabile in Creazione di siti Web di Commerce, effettuare le seguenti operazioni.

1. Aprire una pagina o un modello che contiene il modulo da convertire in frammento.
1. Nel riquadro struttura a sinistra o direttamente nel generatore di pagine visivo, selezionare il modulo precedentemente configurato.
1. Selezionare i puntini di sospensione (**...**) accanto al nome del modulo nel riquadro struttura o nella barra degli strumenti del modulo nel generatore di pagine visivo. 
1. Selezionare **Condividi come frammento**. 
1. Nella finestra di dialogo **Salva come frammento** immettere un nome per il frammento.
1. Selezionare **OK** per salvare la configurazione di modulo come frammento che è possibile aggiungere ad altre pagine.
<!-- The following image shows how to save a module configuration as a fragment.-->
<!--![A screen capture of how to save a module configuration as a fragment.](./media/save-as-fragment.png)-->

### <a name="create-a-new-fragment"></a>Crea un nuovo frammento

Per creare un nuovo frammento in Creazione di siti Web di Commerce, seguire questi passaggi.

1. Selezionare **Frammenti** nel pannello di navigazione a sinistra.
1. Selezionare **Nuovo**. Viene visualizzata una finestra di dialogo **Nuovo frammento** contenente tutti i tipi di modulo disponibili. Come indicato in precedenza, i frammenti possono essere creati da qualsiasi tipo di modulo.
1. Selezionare un tipo di modulo per il frammento.

<!-- The following image shows where to create a new fragment.-->
<!-- ![A screen capture of where to create a new fragment.](./media/fragment-nav-menu.png)-->
> [!TIP]
> Se si seleziona un tipo di modulo contenitore generico, si avrà a disposizione la massima flessibilità quando si dovrà aggiornare e configurare il frammento in seguito.

## <a name="add-remove-or-edit-fragments-on-a-page"></a>Aggiungere, rimuovere o modificare frammenti in una pagina

Nelle procedure riportate di seguito viene descritto come aggiungere, rimuovere e modificare frammenti.

### <a name="add-a-fragment"></a>Aggiungere un frammento

Per aggiungere un frammento a una pagina in Creazione di siti Web di Commerce, seguire questi passaggi.

1. Nel riquadro a sinistra o direttamente nel generatore di pagine visivo, selezionare un contenitore o uno slot a cui i moduli figlio possono essere aggiunti.
1. Selezionare i puntini di sospensione (**...**) accanto al nome del contenitore o dello slot.  In alternativa, se si utilizza il generatore di pagine visivo, selezionare il simbolo più (**+**).  
1. Selezionare **Aggiungi frammento**.
    <!-- ![A screen capture of how to add an existing fragment to a slot or container.](./media/add-fragment.png)-->
 
    > [!NOTE]
    > Se il contenitore o lo slot non supporta nuovi moduli figlio, l'opzione **Aggiungi frammento** non è disponibile.
    
1. Nella finestra di dialogo **Seleziona frammento**, cercare e selezionare un frammento da aggiungere. Se non sono elencati frammenti disponibili, è necessario dapprima creare un frammento da un tipo di modulo che lo slot o il contenitore supporta.
1. Selezionare il frammento desiderato per aggiungerlo al contenitore o allo slot nella pagina.
<!--    ![A screen capture of the fragment picker modal window.](./media/fragment-picker.png)-->

> [!NOTE]
> I moduli consentiti in un contenitore o in uno slot sono definiti in base al modello della pagina o alle definizioni dei moduli.

### <a name="remove-a-fragment"></a>Rimuovere un frammento

Per rimuovere un frammento da uno slot o un contenitore in una pagina di Creazione di siti Web di Commerce, seguire questi passaggi.

1. Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione (**...**) accanto al nome del frammento da rimuovere e quindi selezionare il simbolo del cestino.  In alternativa, è possibile selezionare il frammento nel generatore di pagine visivo e selezionare il simbolo del cestino nella barra degli strumenti del frammento.
1. Quando viene richiesto di confermare la rimozione del frammento, selezionare **OK**.

> [!NOTE]
> Quando si rimuove un frammento da una pagina, si rimuove solo il riferimento allo stesso da quella pagina. **Non** si elimina il frammento dal sito. Per eliminare frammenti dal sito, è necessario utilizzare l'interfaccia utente del controllo frammenti. È possibile eliminare frammenti da un sito solo se si fa riferimento agli stessi con un qualsiasi modello, pagina o altro frammento.

### <a name="edit-a-fragment"></a>Modificare un frammento

Per modificare i frammenti, è necessario utilizzare l'interfaccia utente dell'editor di frammenti. Questa restrizione è dovuta alla struttura. Impedisce agli autori di confondere il processo di modifica dei moduli per una pagina specifica con il processo di modifica di frammenti che potrebbero essere condivisi da più pagine.

Per modificare un frammento in Creazione di siti Web di Commerce, seguire questi passaggi.

1. Selezionare **Frammenti** nel pannello di navigazione a sinistra.
1. In **Frammenti**, selezionare il frammento da modificare.
1. Modificare le proprietà del modulo del frammento e la struttura come necessario. Il processo è analogo a quello per modificare i moduli nella visualizzazione dell'editor di pagine.

È anche possibile modificare un frammento selezionandolo in una pagina, in un modello o in un frammento padre e quindi selezionando **Modifica frammento** nel riquadro delle proprietà a destra.

### <a name="rename-a-fragment"></a>Rinominare un frammento

Per rinominare un frammento esistente in Generatore di siti Web di Commerce, segui questi passaggi.

1. Nel pannello di navigazione a sinistra, seleziona **Frammenti**.
1. Selezionare il nome del frammento che vuoi rinominare.
1. Selezionare **Modifica** per iniziare a modificare il frammento. Tieni presente che non puoi modificare un frammento se qualcun altro sta già modificando il frammento.
1. Nel riquadro delle proprietà del frammento, seleziona il simbolo della penna accanto al nome del frammento.
1. Modificare il nome del frammento, se necessario.
1. Selezionare il segno di spunta per confermare la modifica del nome.
1. Selezionare **Fine modifica**.

Puoi rinominare un frammento dopo che è stato creato modificandolo e selezionando il simbolo della penna accanto al nome della frammento nel riquadro delle proprietà.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica modelli e layout](templates-layouts-overview.md)

[Utilizzare i modelli](work-with-templates.md)

[Utilizzare i layout preimpostati](work-with-layouts.md)

[Utilizzare i gruppi di pubblicazione](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
