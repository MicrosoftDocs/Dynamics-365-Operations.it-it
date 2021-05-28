---
title: Parametri di magazzino per l'elaborazione ciclo
description: In questo argomento viene descritto come impostare i parametri di magazzino per l'elaborazione ciclo. È possibile utilizzare l'elaborazione ciclo per raggruppare il lavoro di prelievo per più ordini di lavoro in un singolo ciclo.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: b120c24ad3289f5f46119d70c8cb7124546e41b1
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019180"
---
# <a name="warehouse-parameters-for-wave-processing"></a>Parametri di magazzino per l'elaborazione ciclo

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come impostare i parametri di magazzino per l'elaborazione ciclo. È possibile utilizzare l'elaborazione ciclo per raggruppare il lavoro di prelievo per più ordini di lavoro in un singolo ciclo.

Per utilizzare l'elaborazione ciclo, specifica quanto segue nella pagina **Parametri di gestione magazzino**:

- Se è possibile elaborare i cicli utilizzando un processo batch.
- Se si raccolgono le informazioni in un file di registro quando vengono elaborati i cicli.

## <a name="set-up-warehouse-management-parameters-for-wave-processing"></a>Impostare i parametri di gestione magazzino per l'elaborazione ciclo

Per impostare i parametri di magazzino per l'elaborazione ciclo, effettua le operazioni seguenti:

1. Vai a **Gestione magazzino** \> **Impostazioni** \> **Parametri di gestione magazzino**.

1. Nella Scheda dettaglio **Elaborazione ciclo** effettua le seguenti impostazioni:

    - **Gruppo batch elaborazione ciclo** - Seleziona il gruppo batch da utilizzare quando si elaborano cicli utilizzando processi batch. Il gruppo batch specifica il server su cui verranno eseguiti i processi batch.
    - **Elabora cicli in batch** - Scegli se abilitare l'elaborazione automatica dei cicli da un processo batch. Devi impostarlo su *Sì* per utilizzare l'elaborazione parallela. Il processo batch viene impostato nella pagina **Elabora cicli**. (Vedi anche la nota alla fine di questo elenco.)
    - **Crea registro stato ciclo** - Scegli se il sistema deve generare un record di registro ogni volta che inizia e finisce l'allocazione di un articolo e le sue dimensioni. Devi abilitare questo registro solo quando necessario, ad esempio durante il test iniziale o per la risoluzione dei problemi. - Per ulteriori informazioni, vedi [Allocazione del ciclo](wave-allocation-method.md).
    - **Crea un registro cronologia elaborazione ciclo** - Scegli se salvare automaticamente le informazioni su un ciclo in un file di registro dopo che il ciclo è stato elaborato anche durante l'elaborazione parallela delle allocazioni in sospeso. In genere dovresti abilitarlo solo durante la risoluzione dei problemi perché aggiunge un sovraccarico extra. Per visualizzare il registro, vai a **Gestione magazzino \> Cicli in uscita \> Registro cronologia elaborazione ciclo**. Per ulteriori informazioni, vedi [Creazione ed elaborazione di cicli](wave-processing.md).
    - **Crea registro cronologia containerizzazione** - Scegli se salvare automaticamente le informazioni sulla containerizzazione per un ciclo in un file di registro dopo che il ciclo è stato elaborato. Per visualizzare il registro, vai a **Gestione magazzino \> Imballaggio e containerizzazione \> Storico containerizzazione**.
    - **Attesa blocco (ms)** - Immetti il tempo, espresso in millisecondi, in cui un passaggio di allocazione aspetterà una risorsa di sistema bloccata da un altro passaggio di allocazione. Quando il tempo viene superato, l'ondata non viene elaborata e viene visualizzato un messaggio di errore.

1. Nella scheda dettaglio **Rilascio in magazzino** effettua la seguente impostazione:

    - **Errore in caso di batch non riuscito** - Scegli se generare un errore quando un processo batch di rilascio nel magazzino non riesce. Se questa opzione è abilitata, i processi non riusciti termineranno con uno stato di *Errore*. Se questa opzione è disabilitata, i processi non riusciti termineranno con uno stato di *Finito*.

> [!NOTE]
> Nel modello ondata utilizzato per elaborare l'ondata, è possibile specificare le impostazioni che automatizzano l'elaborazione ondata. Se si imposta una programmazione per il processo batch, è necessario coordinare l'intervallo con le impostazioni per l'automazione nel modello ondata. Per ulteriori informazioni, vedere [Creazione di un modello di ciclo](wave-templates.md).
>
> Se usi *Gestione trasporto* e *Gestione magazzino avanzata*, puoi specificare se consolidare i carichi quando elabori un ciclo. Ad esempio, questo è utile quando vari piccoli carichi possono essere spediti contemporaneamente. Per consolidare i carichi quando si elabora un ciclo, nella scheda **Carichi** seleziona la casella di controllo **Consolida carichi durante elaborazione ciclo**.</P>

## <a name="set-up-full-or-partial-reservation-for-production-waves"></a>Impostare la prenotazione completa o parziale per i cicli di produzione

Per gli ordini cliente e gli ordini di kanban, l'inventario deve essere prenotato prima che l'ordine venga rilasciato al magazzino. In caso contrario, gli articoli o le righe di allocazione non possono essere elaborati in un'ondata. Tuttavia, gli ordini di produzione sono leggermente più flessibili. Per gli ordini di produzione, è possibile specificare quanto riportato di seguito:

- Consenti agli ordini di produzione di essere rilasciati al magazzino anche se non possono essere prenotati tutti i materiali. Se si seleziona questa opzione, è necessario ripetere manualmente il rilascio al processo di magazzino quando i materiali aggiuntivi diventano disponibili. Ad esempio, questo è utile se hai i materiali necessari per avviare una produzione e puoi attendere fino a quando i materiali aggiuntivi diventano disponibili.
- Richiedi che tutti i materiali siano prenotati prima di poter rilasciare un ordine al magazzino.

Per richiedere la prenotazione completa o per consentire la prenotazione parziale, effettua le operazioni seguenti:

1. Vai a **Controllo produzione** \> **Impostazioni** \> **Parametri di controllo produzione**.
1. Nella scheda **Generale** nel campo **Rilascia in magazzino** seleziona l'impostazione predefinita.
