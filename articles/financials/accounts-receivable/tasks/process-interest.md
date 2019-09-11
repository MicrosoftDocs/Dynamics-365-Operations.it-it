---
title: Elaborare interessi
description: Questa procedura indica come creare, stampare e registrare le note d'interesse.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7170a7a14237058064ed3091e9437cae312e6bd5
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916278"
---
# <a name="process-interest"></a>Elaborare interessi

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura indica come creare, stampare e registrare le note d'interesse. In questa attività viene utilizzata la società dimostrativa USMF.


## <a name="set-up-interest-on-the-posting-profile"></a>Impostare l'interesse nel profilo di registrazione.
1. Nel **pannello di navigazione**, andare a **Moduli > Crediti e riscossioni > Impostazione > Profili di registrazione cliente**.
2. Fare clic su **Modifica**.
3. Nella **Scheda dettaglio Impostazione**, nel campo **Codice interessi**, selezionare un codice interessi dall'elenco a discesa. Se non si desidera che l'interesse venga calcolato per le transazioni utilizzando tale profilo registrazione, lasciare vuoto il campo. La Scheda dettaglio **Restrizioni tabella** consente di modificare la modalità di elaborazione dell'interesse. Se questo campo è impostato su Sì, l'interesse verrà calcolato per il profilo registrazione.  

## <a name="calculate-interest"></a>Calcola interessi
1. Nel **pannello di navigazione**, andare a **Moduli > Crediti e riscossioni > Interessi > Crea note d'interesse**.
2. È necessario selezionare i tipi di transazione per cui verrà calcolato l'interesse. Tutte le transazioni aperte per questi tipi verranno incluse nel calcolo.  
3. Se si imposta **Interesse** su "Sì", verrà calcolato l'interesse sull'interesse. È consigliabile controllare le normative che regolano il calcolo degli interessi sugli interessi prima di includere le transazioni.  
4. Nel campo **Dal** immettere una data di inizio per il calcolo degli interessi. Se non si specifica **Dal**, tutte le note d'interesse non registrate verranno annullate e l'interesse verrà ricalcolato a partire dalla data della transazione.
5. Nel campo **Al** immettere una data di fine per il calcolo degli interessi.
6. Nel campo **Utilizza profilo registrazione da**, selezionare un'opzione. Sono disponibili tre opzioni di profilo di registrazione:
    - Conto: consente di utilizzare il profilo di registrazione assegnato al conto cliente per ogni nota d'interesse. 
    - Seleziona: consente di utilizzare il profilo di registrazione selezionato nel campo Profilo registrazione.
    - Transazione: consente di utilizzare il singolo profilo di registrazione delle transazioni in cui vengono calcolati gli interessi per ciascuna nota d'interesse. Per le transazioni a cui non è assegnato un profilo di registrazione verrà utilizzato il profilo di registrazione specificato nella Contabilità generale e nell'area IVA del modulo Parametri contabilità clienti.  
7. Espandere la Scheda dettaglio **Record da includere**.
8. Fare clic su **Filtro**.
9. Nel campo **Criteri**, immettere un ID cliente. Ad esempio, immettere "US-001".
6. Fare clic su **OK**.
7. Fare clic su **OK**.

## <a name="print-interest-notes"></a>Stampa le note d'interesse
1. Nel **pannello di navigazione**, andare a **Moduli > Crediti e riscossioni > Interessi > Esamina ed elabora note d'interesse**.
2. Nel campo **Stato** selezionare "Creata".
3. Nel campo **Stampata** selezionare "Non stampata".
4. Fare clic su **Stampa**.
5. Espandere la Scheda dettaglio **Record da includere**.
6. Fare clic su **OK**.
7. Chiudere la pagina.

## <a name="post-the-interest-note"></a>Registrare la nota d'interesse
1. Selezionare una nota d'interesse pronta per la registrazione (lo stato è Creata).
2. Fare clic su **Registra**.
3. Immettere la data di registrazione per la nota d'interesse. Selezionare Sì per creare una transazione di contabilità generale per ciascuna nota d'interesse. Se non si seleziona Sì, gli interessi indicati su tutte le note d'interesse destinate al cliente verranno cumulati e registrati nella contabilità generale in un'unica transazione.  
4. Espandere la Scheda dettaglio **Record da includere**.
5. Fare clic su **OK**.
6. Nel campo **Stato** selezionare "Registrata".

