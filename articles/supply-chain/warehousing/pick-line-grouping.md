---
title: Raggruppamento righe prelievo
description: In questo argomento viene fornita una panoramica del raggruppamento delle righe prelievo.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b3497d43a500898207ed5154721ee0e3a327fb93
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017738"
---
# <a name="pick-line-grouping"></a>Raggruppamento righe prelievo

[!include [banner](../includes/banner.md)]

Nel raggruppamento delle righe di prelievo, è possibile combinare più righe di lavoro con lo stesso articolo e posizione in un unico prelievo che viene presentato all'utente su un dispositivo mobile. Pertanto, gli addetti al magazzino possono ricevere le istruzioni più efficienti possibili, ma viene mantenuta anche la necessaria separazione delle righe di lavoro nel sistema (ad esempio, per diversi contenitori e ordini).

## <a name="set-up-pick-line-grouping"></a>Configurare il raggruppamento delle righe prelievo

### <a name="create-a-mobile-device-menu-item"></a>Creare una voce di menu per dispositivo mobile

1. Andare a **Gestione magazzino \>Impostazione \>Dispositivo mobile \>Voci di menu del dispositivo mobile** e creare una nuova voce di menu denominata **Prelievo riga gruppo di vendita - Utente diretto**.
2. In **Voci di menu del dispositivo mobile** , impostare i valori seguenti:

    - Nel campo **Nome voce di menu** , immettere **Prelievo vendite - Riga gruppo**.
    - Nel campo **Titolo** , immetti **Prelievo vendite - Riga gruppo**.
    - Selezionare **Lavoro** nel campo **Modalità**.
    - Impostare l'opzione **Utilizza lavoro esistente** su **Sì**.

3. Nella scheda Dettagli **Generale** , è possibile impostare i seguenti valori:

    - Nel campo **Diretto da** , selezionare **Diretto dall'utente**.
    - Impostare l'opzione **Genera targa** su **Sì**.
    - Impostare l'opzione **Prelievo gruppo** su **Sì**.

4. Nella Scheda dettagli **Classi di lavoro** , seguire questi passaggi per configurare le classi di lavoro valide per la voce di menu del dispositivo mobile:

    1. Selezionare **Nuovo**.
    2. Nel campo **ID classe di lavoro** , selezionare **Vendite** o **Prelievo SO** , a seconda del magazzino che verrà utilizzato.
    3. Nel campo **Tipo ordine di lavoro** selezionare **Ordini cliente**.

### <a name="set-up-a-mobile-device-menu"></a>Configurare un menu per dispositivo mobile

1. Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**. 
1. Aggiungere la voce di menu appena creata al menu desiderato.

### <a name="set-up-a-work-template"></a>Configurare un modello di lavoro

1. Accedere a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Trovare il modello di lavoro da utilizzare con questa funzione. Per questo esempio, selezionare il modello di lavoro Contoso **51 prelievi da approntare** standard.
1. Nel menu, selezionare **Modifica query**.
1. Nella scheda **Ordinamento** , selezionare **Aggiungi** e quindi impostare i seguenti valori:

    - Nel campo **Tabella** selezionare **Transazioni lavoro temporanee**.
    - Nel campo **Tabella derivata** selezionare **Transazioni lavoro temporanee**.
    - Nel campo **Campo** selezionare **Numero articolo**.
    - Nel campo **Direzione di ricerca** , selezionare **Crescente**.

> [!NOTE]
> Affinché la funzionalità di raggruppamento delle righe di prelievo funzioni, le righe di lavoro devono essere ordinate per ID articolo. Se le righe che hanno gli stessi articoli non sono in sequenza una dopo l'altra, non verranno raggruppate.

## <a name="example"></a>Esempio

### <a name="create-picking-work"></a>Creare il lavoro di prelievo

Prima di poter impostare il raggruppamento delle righe di prelievo, è necessario creare del lavoro in uscita idoneo.

1. Accedere a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
2. Selezionare **Nuovo** per creare un ordine cliente. 
3. Nel campo **Conto cliente** selezionare qualsiasi cliente. 
4. Nel campo **Magazzino** della Scheda dettaglio **Generale** , selezionare **51**. Selezionare **OK**.
5. In **Righe ordine cliente** , aggiungere le sei righe seguenti:

    - **Riga 1:** nel campo **Numero articolo** selezionare **M9200**. Nel campo **Quantità** immettere **3**
    - **Riga 2:** nel campo **Numero articolo** selezionare **M9201**. Nel campo **Quantità** immettere **3** 
    - **Riga 3:** nel campo **Numero articolo** selezionare **M9202**. Nel campo **Quantità** immettere **2** 
    - **Riga 4:** nel campo **Numero articolo** selezionare **M9200**. Nel campo **Quantità** immettere **1** 
    - **Riga 5:** nel campo **Numero articolo** selezionare **M9200**. Nel campo **Quantità** immettere **3**
    - **Riga 6:** nel campo **Numero articolo** selezionare **M9202**. Nel campo **Quantità** immettere **7** 

    Ecco un riepilogo delle quantità totali per ciascun articolo:

    - **Articolo M9200:** 7 ciascuno
    - **Articolo M9201:** 3 ciascuno
    - **Articolo M9202:** 9 ciascuno

6. Prima di rilasciare gli ordini al magazzino, è necessario assicurarsi che le posizioni di prelievo dispongano di scorte sufficienti per tutti gli articoli di tutti gli ordini. Rivedere l'impostazione **Direttiva ubicazione** per determinare quali ubicazioni di prelievo vengono utilizzate per il prelievo dell'ordine cliente.
7. Prenotare le scorte e rilasciarle al magazzino. Viene creato un ID lavoro con sei righe. Le righe sono ordinate per numero articolo.

### <a name="run-the-mobile-device-flow"></a>Eseguire il flussi del dispositivo mobile

1. Sul dispositivo mobile, selezionare il menu che include la nuova voce di menu del dispositivo mobile.
1. Selezionare la voce di menu **Prelievo vendite - Riga gruppo** e avviare il prelievo.

    Dopo aver selezionato il menu e inserito l'ID lavoro, viene visualizzato il passaggio di prelievo in cui sono raggruppate tutte le righe di prelievo per l'articolo M9200. Si riceve quindi l'istruzione per prelevare scegliere 7 quantità dell'articolo M9200.

1. Confermare il passaggio di prelievo. 
1. Passare alla schermata client del lavoro in corso e prendere nota che tutte e tre le righe di prelievo per l'articolo M9200 sono state chiuse contemporaneamente.

    Viene presentata la riga di lavoro 4.

1. Confermare il passaggio di prelievo.

    L'ultimo passaggio di prelievo sul dispositivo mobile aggrega le ultime due righe di prelievo dall'ordine di lavoro.

1. Completare il passaggio di prelievo per 9 ciascuno dell'articolo M9202.
1. Confermare il passaggio di inserimento e tutte le coppie di prelievo/inserimento aggiuntive per completare il lavoro.

> [!NOTE]
> - Le righe di lavoro possono essere raggruppate solo se sono in sequenza.
> - Sono supportate le seguenti funzionalità:
>
>    - Articoli a peso variabile. Se sul lavoro sono presenti articoli a peso variabile, riceverai un messaggio di errore prima di iniziare il prelievo.
>    - Prelievo di pezzi.
>    - Righe di lavoro che includono lavori di rifornimento incompiuti.
>    - Prelievo eccessivo.
>    - Prelievo breve con riallocazione articolo
