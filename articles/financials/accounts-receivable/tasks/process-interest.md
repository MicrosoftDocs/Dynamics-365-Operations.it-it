---
title: Elaborare interessi
description: Questa procedura indica come creare, stampare e registrare le note d'interesse.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5652a38684061914f895d7f8b82999c9840fd63
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549608"
---
# <a name="process-interest"></a>Elaborare interessi

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura indica come creare, stampare e registrare le note d'interesse. In questa attività viene utilizzata la società dimostrativa USMF.


## <a name="set-up-interest-on-the-posting-profile"></a>Impostare l'interesse nel profilo di registrazione.
1. Andare a Crediti e riscossioni > Impostazioni > Profili di registrazione cliente.
2. Fare clic su Modifica.
    * Selezionare un codice interessi dall'elenco a discesa. Se non si desidera che l'interesse venga calcolato per le transazioni utilizzando tale profilo registrazione, lasciare vuoto il campo.  
    * La scheda Restrizioni tabella consente di modificare la modalità di elaborazione dell'interesse. Se questo campo è impostato su Sì, l'interesse verrà calcolato per il profilo registrazione.  

## <a name="calculate-interest"></a>Calcola interessi
1. Andare a Crediti e riscossioni > Interessi > Crea note d'interesse.
    * È necessario selezionare i tipi di transazione per cui verrà calcolato l'interesse. Tutte le transazioni aperte per questi tipi verranno incluse nel calcolo.  
    * Se si seleziona Interesse, verrà calcolato l'interesse sull'interesse. È consigliabile controllare le normative che regolano il calcolo degli interessi sugli interessi prima di includere le transazioni.  
    * Gli interessi verranno calcolati a partire da questa data fino alla "Data finale". Se non si specifica la "Data iniziale" tutte le note d'interesse non registrate verranno annullate e l'interesse verrà ricalcolato a partire dalla data della transazione.  
2. Immettere la data della nota d'interesse.
    * Sono disponibili tre opzioni di profilo registrazione. Conto: consente di utilizzare il profilo registrazione assegnato al conto cliente per ogni nota d'interesse.   Seleziona: consente di utilizzare il profilo di registrazione selezionato nel campo Profilo registrazione.   Transazione: consente di utilizzare il singolo profilo di registrazione delle transazioni in cui vengono calcolati gli interessi per ciascuna nota d'interesse. Per le transazioni a cui non è assegnato un profilo di registrazione verrà utilizzato il profilo di registrazione specificato nella Contabilità generale e nell'area IVA del modulo Parametri contabilità clienti.  
    * Selezionare un profilo registrazione qui se "Utilizza profilo registrazione da" è stato modificato in "Seleziona".  
3. Espandere o comprimere la sezione Record da includere.
4. Fare clic su Filtro.
5. Nel campo Criteri, immettere un ID cliente. Ad esempio, immettere "US-001".
6. Fare clic su OK.
7. Fare clic su OK.

## <a name="print-interest-notes"></a>Stampa le note d'interesse
1. Andare a Crediti e riscossioni > Interessi > Esamina ed elabora note d'interesse.
2. Nel campo Stato selezionare "Creata".
3. Nel campo Stampata selezionare "Non stampata".
4. Fare clic su Stampa.
5. Espandere o comprimere la sezione Record da includere.
6. Fare clic su OK.
7. Chiudere la pagina.

## <a name="post-the-interest-note"></a>Registrare la nota d'interesse
1. Selezionare una nota d'interesse pronta per la registrazione (lo stato è Creata).
2. Fare clic su Registra.
3. Immettere la data di registrazione per la nota d'interesse.
    * Selezionare Sì per creare una transazione di contabilità generale per ciascuna nota d'interesse.     Se non si seleziona Sì, gli interessi indicati su tutte le note d'interesse destinate al cliente verranno cumulati e registrati nella contabilità generale in un'unica transazione.  
4. Espandere o comprimere la sezione Record da includere.
5. Fare clic su OK.
6. Nel campo Stato selezionare "Registrata".

