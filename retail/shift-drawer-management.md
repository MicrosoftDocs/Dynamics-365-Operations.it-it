---
title: Gestione turni e cassetto della cassa
description: "In questo articolo viene descritto come impostare e utilizzare i due tipi di turni al dettaglio di (POS) del POS - condivisi e autonomi. I turni condivisi possono essere utilizzati da più utenti in più posizioni, mentre i turni autonomi possono essere utilizzati da un solo lavoratore alla volta."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 09c7fce1fa83d6a8d6391db667b7260d2a199390
ms.lasthandoff: 03/31/2017


---

# <a name="shift-and-cash-drawer-management"></a>Gestione turni e cassetto della cassa

In questo articolo viene descritto come impostare e utilizzare i due tipi di turni al dettaglio di (POS) del POS - condivisi e autonomi. I turni condivisi possono essere utilizzati da più utenti in più posizioni, mentre i turni autonomi possono essere utilizzati da un solo lavoratore alla volta.

Esistono due tipi di turni POS al dettaglio: autonomo e condiviso. I turni autonomi sono utilizzabili da un solo lavoratore alla volta. I turni condivisi possono essere utilizzati da più utenti in più posizioni. Pertanto, creano in modo efficace un turno singolo per più lavoratori in un punto vendita.

## <a name="standalone-shifts"></a>Turni autonomi
I turni autonomi vengono utilizzati in uno scenario POS fisso tradizionale, in cui la cassa è riconciliata in modo indipendente per ogni registratore di cassa POS. Ad esempio, in un negozio di alimentari, in genere esistono più registratori di cassa POS fissi e un cassiere viene assegnato a ciascun registratore. In questo caso, ciascun registratore probabilmente utilizza un turno autonomo e il cassiere è responsabile per il cassetto o la cassa fisica di quel registratore di cassa. Un turno autonomo include tutte le attività su tale registratore di cassa durante il turno di lavoro del cassiere. Le attività possono includere l'importo di apertura che viene depositato nel cassetto, tutte le rimozioni e le aggiunte di contanti tramite operazioni quali depositi bancari e immissioni fondo di cassa, e il riepilogo degli incassi alla fine del turno.

### <a name="set-up-a-stand-alone-shift"></a>Impostare un turno autonomo

Un turno autonomo viene definito a livello di cassetto della cassa. Questa procedura illustra come impostare un turno autonomo su un registratore di cassa POS.

1.  ** Fare clic su Retail e il commercio ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** il POS profili ** &gt; ** profili hardware **.
2.  Selezionare il profilo dhardware a utilizzare per il turno autonomo.
3.  Nella scheda dettaglio **Cassetto**, verificare che l'opzione **Cassetto turno condiviso** sia impostata su **No**.
4.  Click **Save**.
5.  ** Fare clic su Retail e il commercio ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** registrare **.
6.  Selezionare il registratore di cassa che richiede un turno autonomo e quindi fare clic su **Modifica**.
7.  Nel campoa **Profilo hardware** selezionare il profilo hardware selezionato nel passaggio 2.
8.  Click **Save**.
9.  ** Fare clic su Retail e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazione di distribuzione **.
10. Selezionare la programmazione di distribuzione **1090** e quindi fare clic su **Esegui adesso** per sincronizzare le modifiche nel POS.

### <a name="use-a-stand-alone-shift"></a>Utilizzare turno autonomo

1.  Accedere al POS.
2.  Se nessun turno è aperto, selezionare **Apri un nuovo turno**.
3.  Vai all'operazione **Dichiara importo iniziale** e specificare l'importo di contanti aggiunto al cassetto per iniziare la giornata di lavoro.
4.  Eseguire alcune transazioni.
5.  Alla fine del giorno, selezionare **Dichiara metodo di pagamento** per dichiarare l'importo di contanti che rimane nel cassetto della cassa.
6.  Immettere l'importo di contanti quindi fare clic su **Salva** per salvare il riepilogo incassi.
7.  Selezionare **Chiudi turno** per chiudere il turno.

**Nota:** sono disponibili altre operazioni durante il turno, a seconda dei processi aziendali implementati. Le operazioni **Deposito in cassaforte**, **Deposito bancario**, e **Rimozione metodo di pagamento** possono essere utilizzate per rimuovere denaro dal cassetto durante il giorno o prima della chiusura del turno. Se un cassetto non ha contanti sufficienti, l'operazione **Immissione fondo cassa** può essere utilizzata per aggiungere contanti alla cassa.

## <a name="shared-shifts"></a>Turni condivisi
Un turno condiviso viene utilizzato in un ambiente in cui più cassieri condividono un cassetto o un insieme di cassetti di registratori di cassa nel corso della giornata di lavoro. In genere, un turno condiviso viene utilizzato in ambienti di POS mobili. In un ambiente mobile, ogni cassiere non è assegnato né responsabile di un singolo cassetto della cassa. Invece tutti i cassieri devono poter gestire una vendita e aggiungere contanti a qualsiasi cassetto della cassa sia più vicino. In questo scenario, i cassetti della cassa che vengono condivisi tra i cassieri sono inclusi in un turno condiviso. Tutti i cassetti della cassa in un turno condiviso sono inclusi nello stesso turno per le attività correlate alla gestione di cassa per il turno. Pertanto, l'importo iniziale del turno deve includere la somma di tutti i contanti in tutti i cassetti inclusi nel turno condiviso. Analogamente, il riepilogo incassi sarà la somma di tutti i contanti in tutti i cassetti inclusi nel turno condiviso. ** Nota: ** Solo un turno condivisa può essere aperto alla volta in ogni punto vendita. I turni condivisi e autonomi possono essere utilizzati nello stesso punto vendita.

### <a name="set-up-a-shared-shift"></a>Impostare un turno condiviso

1.  ** Fare clic su Retail e il commercio ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** il POS profili ** &gt; ** profili hardware **.
2.  Selezionare il profilo dhardware da utilizzare per il turno condiviso.
3.  Nella scheda dettaglio **Cassetto**, impostare l'opzione **Cassetto turno condiviso** su **Sì**.
4.  Click **Save**.
5.  ** Fare clic su Retail e il commercio ** &gt; ** Manica impostato ** &gt; ** POS configurato ** &gt; ** registrare **.
6.  Selezionare il registratore di cassa che richiede un turno condiviso e quindi fare clic su **Modifica**.
7.  Nel campoa **Profilo hardware** selezionare il profilo hardware selezionato nel passaggio 2.
8.  Click **Save**.
9.  ** Fare clic su Retail e il commercio ** &gt; ** IT al dettaglio ** &gt; ** programmazione di distribuzione **.
10. Selezionare la programmazione di distribuzione **1090** e quindi fare clic su **Esegui adesso** per sincronizzare le modifiche nel POS.

### <a name="use-a-shared-shift"></a>Utilizzare un turno condiviso

1.  Accedere al POS.
2.  Se il POS non è ancora connesso a una stazione hardware, selezionare **Operazione non relativa a cassetto**, quindi selezionare l'operazione **Seleziona stazione hardware** per attivare una stazione hardware per il turno condiviso. Questo passaggio è necessario solo la prima volta che viene aggiunto un registratore di cassa in un ambiente di turno condiviso.
3.  Uscire dal POS, e quindi accedere di nuovo.
4.  Selezionare **Crea un nuovo turno**.
5.  Selezionare **Dichiara importo iniziale**.
6.  Immettere l'importo iniziale di tutti i registratori di cassa nel punto vendita che fanno parte del turno condiviso e quindi fare clic su **Salva**.
    -   Per aggiungere una parte dell'importo iniziale a ogni successivo cassetto della cassa, utilizzare l'operazione **Seleziona stazione hardware **per rendere attiva la stazione hardware.
    -   Per aggiungere un cassetto a un cassetto della cassa specifico, utilizzare l'operazione **Apri cassetto**.
    -   Continuare fino a quando tutti i cassetti della cassa nel turno condiviso hanno la propria parte dell'importo iniziale.

7.  Alla fine del giorno, aprire ogni cassetto della cassa e rimuovere i contanti.
8.  Dopo aver rimosso il denaro dal cassetto della cassa ultimo, contare tutti i contanti da tutti i cassetti della cassa.
9.  Utilizzare l'operazione **Dichiara metodo di pagamento** per dichiarare l'importo totale di contanti di tutti i cassetti inclusi nel turno condiviso.
10. Utilizzare l'operazione **Chiudi turno** per chiudere il turno condiviso.


