---
title: Lavoro di imballaggio per l'imballaggio di contenitori in uscita e l'elaborazione di spedizioni
description: In questo articolo viene descritto il tipo di ordine di lavoro "Imballaggio", che gestisce il lavoro per l'imballaggio di contenitori e supporta spedizioni parziali di contenitori imballati correlati a carichi in cui gli articoli di magazzino rimangono non imballati.
author: perlynne
ms.date: 7/13/2022
ms.topic: article
ms.search.form: WHSPackingWorkLocationSetup, WHSPack, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 34a7087df7e7768d0012ea4f534aa109654af8fa
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220588"
---
# <a name="packing-work-for-packing-outbound-containers-and-processing-shipments"></a>Lavoro di imballaggio per l'imballaggio di contenitori in uscita e l'elaborazione di spedizioni

[!include [banner](../../includes/banner.md)]

In questo articolo viene descritto il tipo di ordine di lavoro *Imballaggio*, che gestisce il lavoro per l'imballaggio di contenitori e supporta spedizioni parziali di contenitori imballati correlati a carichi in cui gli articoli di magazzino rimangono non imballati. Il lavoro di imballaggio ti consente di utilizzare la funzionalità [Conferma e trasferisci](confirm-and-transfer.md) per confermare le spedizioni in uscita associate ai contenitori.

Il lavoro di imballaggio viene creato automaticamente quando gli articoli correlati al lavoro del documento di origine vengono messi nelle ubicazioni di tipo *Ubicazione imballaggio*. Il lavoro consiste di due righe, una per *Preleva* e una per *Inserisci* e viene gestito automaticamente nell'ambito di un processo di chiusura/riapertura dei contenitori.

Per ulteriori informazioni su come configurare e utilizzare il processo di imballaggio di contenitori, vedi [Imballare contenitori per la spedizione](packing-containers.md).

## <a name="turn-on-the-feature"></a>Attivare la funzionalità

Se il sistema in uso non include già le funzionalità descritte in questo articolo, accedi a [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attiva le seguenti funzionalità nel seguente ordine. Entrambe le funzionalità fanno parte del modulo **Gestione magazzino**.

1. *Conferma e trasferimento*
1. *Lavoro di imballaggio per stazioni di imballaggio*

## <a name="set-up-a-location-for-packing-work"></a>Impostare un'ubicazione per il lavoro di imballaggio

Per impostare ubicazioni di imballaggio, attieniti alla seguente procedura. Per ogni ubicazione, puoi indicare se il sistema deve creare automaticamente il lavoro di imballaggio.

1. Vai a **Gestione magazzino \> Impostazioni \> Imballaggio \> Impostazione stazione di imballaggio**.
1. Nel riquadro Azioni seleziona **Nuovo** per aggiungere un record di impostazione di stazione di imballaggio.
1. Nel nuovo record, imposta i seguenti campi:

    - **Magazzino**: seleziona o immetti il magazzino in cui si trova l'ubicazione di imballaggio.
    - **Ubicazione**: seleziona o immetti l'ubicazione di imballaggio. Questa ubicazione deve essere assegnata a un profilo di ubicazione che utilizza il tipo di ubicazione configurato come tipo di ubicazione di imballaggio per la tua azienda nella pagina **Parametri di gestione magazzino**. Per ulteriori informazioni, vedi [Imballare contenitori per la spedizione](packing-containers.md).
    - **Crea lavoro imballaggio**: seleziona questa casella di controllo per creare lavoro di imballaggio ogni volta che gli articoli vengono consegnati all'ubicazione di imballaggio. Il lavoro includerà collegamenti alle righe di carico correlate, di modo che i carichi parziali possano essere imballati e spediti.

## <a name="example-scenario"></a>Scenario di esempio

Questo scenario di esempio mostra come elaborare un flusso di ordini cliente in uscita imballando un contenitore e spedendo un carico parziale.

### <a name="make-sample-data-available"></a>Rendi disponibili i dati di esempio

Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

Puoi anche utilizzare questo scenario come guida all'uso della funzionalità in un sistema di produzione. Tuttavia, in tal caso, devi sostituire i tuoi valori per ciascuna impostazione descritta qui.

### <a name="configure-packing-work-for-warehouse-packing-location"></a>Configurare il lavoro di imballaggio per l'ubicazione di imballaggio del magazzino

Per iniziare, devi configurare il processo di lavoro *Imballaggio* per un magazzino e un'ubicazione specifici.

1. Vai a **Gestione magazzino \> Impostazioni \> Imballaggio \> Impostazione stazione di imballaggio**.
1. Per aggiungere un record di configurazione, seleziona **Nuovo** nel riquadro Azioni.
1. Nel nuovo record, imposta i seguenti valori:

    - **Magazzino:** *62*
    - **Ubicazione:** *Imballaggio*
    - **Crea lavoro imballaggio:** *Sì*

1. Chiudi la pagina **Impostazione stazione di imballaggio**.

### <a name="create-a-load-template-that-allows-partial-shipping"></a>Creare un modello di carico che consenta una spedizione parziale

Per consentire la consegna di un carico in più spedizioni, devi associarlo a un modello di carico che consenta la spedizione parziale. Per creare il modello necessario, attieniti alla procedura seguente.

1. Accedere a **Gestione magazzino \> Impostazioni \> Carico \> Modelli di carico**.
1. Per aggiungere un record di configurazione, seleziona **Nuovo** nel riquadro Azioni.
1. Nel nuovo record, imposta i seguenti valori:

    - **ID modello carico:** *Parziale*
    - **Consenti divisione carico durante la conferma spedizione:** *Sì*

1. Chiudi la pagina **Modelli di carico**.

Per ulteriori informazioni, vedi [Conferma e trasferimento](Confirm-and-transfer.md).

### <a name="process-a-sales-order"></a>Elaborare un ordine cliente

Attieniti alla seguente procedura per elaborare un ordine cliente e spedirlo parzialmente.

1. Completa lo [scenario di esempio](packing-containers.md#scenario) in [Imballare contenitori per la spedizione](packing-containers.md). In tale scenario, creerai un ordine cliente per due pezzi di un articolo. Quindi imballerai solo uno dei pezzi in un contenitore e chiuderai il contenitore. Prendi nota dell'ID spedizione che crei, come indicato nello scenario.
1. Vai a **Gestione magazzino \> Lavoro \> Tutti i lavori**.
1. Nell'area di filtro, seleziona la casella di controllo **Mostra lavoro chiuso**. Quindi immetti l'ID spedizione nel campo **Filtro** e seleziona per filtrare in base al valore **ID spedizione**. Ora dovresti vedere tre intestazioni lavoro. Una per il lavoro di prelievo degli ordini cliente il cui stato è *Chiuso*. Due per il processo di imballaggio: una è relativa al contenitore chiuso, il cui stato è *Chiuso*, e l'altra è relativa all'articolo rimanente non imballato, il cui stato è *Aperto*.
1. Seleziona il valore **ID carico** per una qualsiasi delle intestazioni lavoro per aprire la pagina **Dettagli carico** per il carico.
1. Passa alla visualizzazione **Intestazione**.
1. Nella Scheda dettaglio **Generale**, seleziona il pulsante **Modifica** per il campo **ID modello carico**. Quindi seleziona il modello di carico della spedizione parziale che hai creato per questo scenario (*Parziale*).
1. Nel riquadro Azioni, nella scheda **Spedisci e ricevi**, nel gruppo **Conferma**, seleziona **Spedizione in uscita**.
1. Nella finestra di dialogo **Conferma spedizione**, seleziona l'opzione **Suddividi quantità nel nuovo carico**.
1. Seleziona **OK**.

Ora hai spedito un contenitore correlato al carico originale e il sistema ha creato un nuovo carico per gli articoli rimanenti che devono ancora essere imballati nei contenitori.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
