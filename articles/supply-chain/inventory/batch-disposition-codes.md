---
title: Utilizzare i codici smaltimento batch per contrassegnare i batch come disponibili o non disponibili
description: Questo articolo descrive come impostare e utilizzare i codici smaltimento batch per contrassegnare i batch come disponibili o non disponibili per l'uso in pianificazione generale, prenotazione, prelievo e/o spedizione.
author: t-benebo
ms.date: 09/16/2022
ms.topic: article
ms.search.form: PdsDispositionMaster, InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-16
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: cfb0743a573550de93d75063df517e0c143f2568
ms.sourcegitcommit: 20ce54cb40290dd116ab8b157c0a02d6757c13f5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2022
ms.locfileid: "9542471"
---
# <a name="use-batch-disposition-codes-to-mark-batches-as-available-or-unavailable"></a>Utilizzare i codici smaltimento batch per contrassegnare i batch come disponibili o non disponibili

In questo articolo viene descritto come configurare e utilizzare i *codici smaltimento batch*. Lo stato di ogni codice smaltimento batch può essere *Disponibile* o *Non disponibile*. I codici smaltimento batch vengono assegnati ai batch di magazzino per indicare se ogni batch è disponibile per la pianificazione generale, la prenotazione, il prelievo e/o la spedizione.

Per utilizzare i codici smaltimento batch, è necessario impostare i codici e assegnarli ai batch che vuoi gestire.

## <a name="set-up-batch-disposition-codes"></a>Impostare i codici smaltimento batch

È necessario impostare ogni codice smaltimento batch che vuoi utilizzare nel sistema. È possibile creare il numero di codici desiderato. Ad esempio, puoi creare i codici per identificare i diversi motivi per cui un batch può essere disponibile o non disponibile. Tuttavia, avrai spesso solo due codici: uno *disponibile* e uno *non disponibile*. È inoltre possibile creare codici personalizzati che consentono di utilizzare un batch per alcune operazioni ma non per altre.

Attieniti alla seguente procedura per impostare i codici smaltimento batch.

1. Vai a **Gestione articoli \> Impostazioni \> Batch \> Smaltimento batch generale**.
1. La pagina **Smaltimento batch generale** elenca i codici di smaltimento batch correnti e consente di crearli, eliminarli e modificarli. Eseguire uno dei passaggi riportati di seguito.

    - Per modificare un codice esistente, selezionalo nel riquadro elenco.
    - Nel riquadro azioni seleziona **Nuovo** per creare un nuovo codice.

1. Imposta i seguenti campi nell'intestazione del codice nuovo o selezionato:

    - **Codice smaltimento batch** – Immetti il nome visualizzato per il codice.
    - **Descrizione** – Descrivi come deve essere utilizzato il codice.
    - **Stato smaltimento batch** – Seleziona lo stato che si applica ai batch a cui è assegnato il codice:

        - *Non disponibile* – I batch non possono essere utilizzati per la pianificazione generale, la prenotazione, il prelievo o la spedizione. Quando selezioni questo valore, tutte le opzioni **Blocca** nella scheda dettaglio **Impostazioni** sono impostati su *sì*, e tutte le opzioni **Nettificabile** sono impostate su *No*. Tuttavia, puoi modificare alcune di queste impostazioni per aggiungere eccezioni.
        - *Disponibile* – I batch possono essere utilizzati per la pianificazione generale, la prenotazione, il prelievo e/o la spedizione. Quando selezioni questo valore, tutte le opzioni **Blocca** nella scheda dettaglio **Impostazioni** sono impostati su *No*, e tutte le opzioni **Nettificabile** sono impostate su *Sì*. Queste impostazioni saranno di sola lettura mentre il campo **Stato smaltimento batch** è impostato su *Disponibile*.

1. Se imposti il campo **Stato smaltimento batch** su *Non disponibile*, puoi personalizzare lo stato di blocco di ogni operazione (prenotazione, prelievo e spedizione) per ogni tipo di ordine (vendita, trasferimento e produzione). Per gli ordini di produzione, è possibile scegliere di bloccare o sbloccare il giornale di registrazione di prelievo produzione. Puoi anche scegliere di bloccare o sbloccare la pianificazione generale. Usa le opzioni della scheda dettaglio **Impostazioni** per bloccare o sbloccare ogni operazione secondo le tue esigenze. Imposta l'opzione **Nettificabile** su *sì* per abilitare la pianificazione generale o impostala su *No* per bloccare la pianificazione generale.

## <a name="assign-batch-disposition-codes-to-batches"></a>Assegnare i codici smaltimento batch ai batch

Dopo aver definito i codici di smaltimento batch richiesti, attieniti alla seguente procedura per assegnarli ai batch.

1. Vai a **Gestione magazzino \> Impostazioni \> Scorte \> Batch**.
1. Seleziona uno o più batch a cui assegnare un codice smaltimento batch.
1. Nel riquadro azioni, nella scheda **Reimposta**, seleziona **Reimposta codice smaltimento batch**.
1. Nella finestra di dialogo **Modifica le restrizioni sul lotto di magazzino**, imposta il campo **Nuovo codice smaltimento batch** sul nome del codice che vuoi assegnare.
1. Seleziona **OK** per applicare la nuova impostazione e salvare la modifica.

    Sulla pagina **Batch**, i valori nelle colonne **Codice smaltimento batch** e **Stato smaltimento batch** vengono aggiornati in modo che riflettano le nuove impostazioni per i batch selezionati.

## <a name="master-planning-example"></a>Esempio di pianificazione generale

Questo esempio mostra come i codici smaltimento batch possono influire sulla pianificazione generale.

Per questo esempio, i codici smaltimento batch vengono impostati nel modo seguente:

- *P-Disponibile:*

    - **Stato smaltimento batch:** *Disponibile*
    - **Nettificabile:** *Sì*

- *P-Non disponibile:*

    - **Stato smaltimento batch:** *Non disponibile*
    - **Nettificabile:** *No*

C'è un prodotto (*Prodotto-1*) che ha due batch: *Batch-A* e *Batch-B*. Questi batch vengono impostati nel seguente modo:

- *Batch-A:*

    - **Codice smaltimento batch:** *P-Disponibile*
    - **Quantità disponibile:** 1

- *Batch-B:*

    - **Codice smaltimento batch:** *P-Non disponibile*
    - **Quantità disponibile:** 1

C'è un ordine cliente (*SO1*) per una quantità pari a 2 del *Prodotto-1*. La data di consegna è a tre giorni da oggi.

Esegui la pianificazione generale e imposta i seguenti valori rilevanti per questo esempio:

- **Ordine pianificato:** *Ordine fornitore*
- **Strategia di rifornimento:** *fabbisogno*
- **Lead time:** *0*

Come risultato dell'esecuzione della pianificazione, il sistema utilizza il batch disponibile (*Batch-A*) per coprire la quantità di 1 del *Prodotto-1* per l'ordine cliente *SO1*. Tuttavia, non può utilizzare il *Batch-B* perché quel batch è contrassegnato come non disponibile per la pianificazione. Pertanto, per coprire la quantità rimanente, il sistema crea un ordine fornitore pianificato (*PPO1*) per un nuovo batch del *Prodotto-1*.

L'illustrazione seguente mostra una sequenza temporale per il risultato della pianificazione.

![Esempio che mostra come i codici smaltimento batch possono influire sulla pianificazione generale.](media/batch-codes-planning-example.png "Esempio che mostra come i codici smaltimento batch possono influire sulla pianificazione generale")
