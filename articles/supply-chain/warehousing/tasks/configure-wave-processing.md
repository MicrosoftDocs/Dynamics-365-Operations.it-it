---
title: Configurare l'elaborazione di cicli di esempio
description: Questo argomento fornisce un esempio di come impostare i criteri che determinano quale lavoro viene generato per un magazzino quando viene elaborata un'ondata e se le ondate vengono elaborate manualmente o automaticamente.
author: Mirzaab
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSParameters, ProdParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39c3fecf9250ee89c22003d5dff4ea662c3042e3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572987"
---
# <a name="configure-wave-processing-example"></a>Configurare l'elaborazione di cicli di esempio

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce un esempio di come impostare i criteri che determinano quale lavoro viene generato per un magazzino quando viene elaborata un'ondata e se le ondate vengono elaborate manualmente o automaticamente. I criteri vengono specificati impostando i modelli ondata e le query che corrispondono a un'ondata con le righe rilasciate negli ordini cliente, negli ordini di produzione o negli ordini kanban.

## <a name="enable-sample-data"></a>Abilitare dati di esempio

Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i dati dimostrativi standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

## <a name="example-scenario-configure-wave-processing"></a>Scenario di esempio: configurare l'elaborazione di cicli

Questo scenario di esempio illustra molte delle diverse impostazioni che influiscono sul modo in cui i cicli vengono creati, popolati, elaborati e rilasciati.

1. Passare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Ondate > Modelli ondata**.
1. Selezionare **Nuovo**.
1. Digitare un valore nel campo **Nome modello ondata**. Quando si imposta un modello di ondata, si specifica la sequenza in cui i modelli verranno associati alle righe rilasciate negli ordini cliente, negli ordini di produzione o sui kanban. Quando una riga viene rilasciata al magazzino o alla produzione, viene utilizzato il primo modello di ondata che soddisfa i criteri. Si consiglia di inserire i modelli con i criteri più specifici in cima all'elenco. Più ampi sono i criteri, maggiore è la possibilità che una riga soddisfi i criteri e ciò potrebbe comportare che le righe vengano assegnate a un'ondata errata.  
1. Nel campo **Descrizione modello ondata** immettere un valore.
1. Nel campo **Sito** immettere o selezionare un valore. Se si utilizza USMF, è possibile selezionare il sito 2.  
1. Nel campo **Magazzino** immettere o selezionare un valore. Se si utilizza USMF, è possibile selezionare il magazzino 24.  
1. Impostare il campo **Automatizza creazione ondata** su **Sì**. Selezionare questa opzione per creare un'ondata quando viene rilasciato un ordine cliente, un ordine di produzione, un kanban al magazzino.  
1. Impostare l'opzione **Elabora ondata al rilascio in magazzino** su **Sì**. Selezionare questa opzione per elaborare automaticamente l'ondata e creare il lavoro quando una riga viene rilasciata nel magazzino.  
1. Impostare l'opzione **Automatizza rilascio ondata** su **Sì**. Selezionare questa opzione per rilasciare automaticamente l'ondata. Il lavoro di prelievo viene creato e reso disponibile sui dispositivi mobili.  
1. Impostare l'opzione **Assegna a ondate aperte** su **Sì**. Le righe vengono assegnate a ondate sul filtro di query per il modello ondata.  
1. Impostare l'opzione **Elabora ondata automaticamente alla soglia** su **Sì**. Selezionare questa opzione per elaborare automaticamente l'ondata quando i relativi valori raggiungono le soglie di peso, la spedizione e le righe specificate nel gruppo di campi **Soglie ciclo**. Questa opzione è disponibile solo se nel campo **Tipo di modello ciclo** è selezionata l'opzione **Spedizione**.  
1. Impostare l'opzione **Automatizza rilascio lavoro di rifornimento** su **Sì**. Selezionare questa opzione per creare lavoro di rifornimento basato sulla domanda e per rilasciarlo automaticamente. È necessario aggiungere il metodo ciclo di rifornimento al modello di ciclo e creare un modello rifornimento di tipo **Domanda ciclo**.  
1. Usa le impostazioni nel gruppo di file **Valori standard** per assegnare gli attributi ciclo. Gli attributi di ondata fungono da filtri per limitare il tipo di articoli che possono utilizzare l'ondata. Ad esempio, è possibile specificare un gruppo di articoli.  
1. Espandi la sezione **Metodi** e imposta le azioni intraprese dal modello ciclo. I metodi del modello di ondata consentono di controllare la sequenza di attività cui ogni ondata viene sottoposta quando è elaborata. Ad esempio, potrebbe essere disponibile un metodo per il rifornimento per ondata. Quando si aggiunge un metodo, viene automaticamente elencato nella posizione appropriata nella sequenza delle fasi. Se è stata impostata l'opzione **Automatizza rilascio lavoro di rifornimento** su **Sì**, è necessario aggiungere qui il metodo di rifornimento.  
1. Selezionare **Salva**.
1. Chiudere la pagina.
1. Andare a **Gestione magazzino > Impostazioni > Parametri di gestione magazzino**.
1. Espandere la sezione **Elaborazione ondata**.
1. Nel campo **Gruppo batch elaborazione ondata** immettere o selezionare un valore.
1. Impostare l'opzione **Elabora ondate in batch** su **Sì**.
1. Nel campo **Attesa blocco (ms)** immettere un numero. Immettere il tempo, espresso in millisecondi, in cui un passaggio di allocazione aspetterà una risorsa di sistema bloccata da un altro passaggio di allocazione. Quando il tempo viene superato, l'ondata non viene elaborata e viene visualizzato un messaggio di errore.  
1. Selezionare **Salva**.
1. Chiudere la pagina.
1. Passare a **Pannello di navigazione > Moduli > Controllo produzione > Impostazioni  Parametri controllo di produzione**.
1. Nel campo **Rilascia in magazzino** selezionare un'opzione.

    Per gli ordini cliente e gli ordini di kanban, l'inventario deve essere prenotato prima che l'ordine venga rilasciato al magazzino. In caso contrario, gli articoli o le righe di allocazione non possono essere elaborati in un'ondata. Per gli ordini di produzione, è anche possibile scegliere **Consenti prenotazione parziale**. Ad esempio, questo è utile se hai i materiali necessari per avviare una produzione e quindi puoi attendere fino a quando i materiali aggiuntivi diventano disponibili per terminare il processo. Se si seleziona questa opzione, è necessario ripetere manualmente il rilascio al processo di magazzino quando i materiali aggiuntivi diventano disponibili.
1. Chiudere la pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Creazione ed elaborazione dei cicli](../wave-processing.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
