---
title: Budget planning justification documents
description: "I documenti di motivazione immettere una descrizione per quelle che invitano un budget di spiegare perché un budget specifico necessario."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: c86d01fec3d8d7c210c7e73a034f4e9e384a0dcf
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-justification-documents"></a>Budget planning justification documents

I documenti di motivazione immettere una descrizione per quelle che invitano un budget di spiegare perché un budget specifico necessario. 

Un modello di piano di budget viene creato dal responsabile budget in Microsoft Word a cui è assegnato il processo di pianificazione del budget corrente. Numero dei proprietari potrà quindi aprire il modello e avere dati inseriti automaticamente in Word basato sulla relativa richiesta di budget. È quindi possibile aggiungere testo aggiuntivo o dati prima del salvataggio e per l'allegato del documento personale di giustificazione al piano di budget.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Componente di Office di Microsoft Dynamics di Microsoft Word

1.  Visualizza un nuovo documento di Microsoft Word.
2.  Fare clic su ** inserimento ** sulla barra multifunzione e fare clic su ** ** punto vendita.
3.  Ricerca di Componente di Office di Microsoft Dynamics e fare clic su ** aggiungere **.
4.  In Word, nel riquadro destro, fare clic su ** aggiungere le informazioni sul server **.
5.  Tipo o incollare il server URL e fare clic su OK ** **.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Consente di impostare il modello di giustificativo in Microsoft Word

1.  Fare clic su ** progettazione ** in Componente di Office di Microsoft Dynamics dopo che è stato associato.
2.  Per informazioni di intestazione, utilizzare ** aggiungere i campi ** il pulsante.
3.  Selezionare l'origine dati dell'entità di BudgetPlanJustification e fare clic su ** dopo **. ** Nota: ** La entità è necessaria per qualsiasi documento di motivazione. Le altre entità possono essere utilizzate ma il caricamento di nuovo a Microsoft Dynamics 365 per le operazioni avrà esito negativo se questa entità non verrà inclusa.
4.  Aggiungere il BudgetPlanName, il BudgetPlanPreparer, il ResponsibilityCenter ed etichette e i valori di DocumentNumber nel documento Word. ** Nota: ** È possibile utilizzare le proprie etichette personalizzati, anziché le etichette standard, se necessario.
5.  Fare clic su ** effettuato ** per completare la sezione di intestazione.
6.  Per il dettaglio livello di riga per gli importi del piano di budget, fare clic su ** aggiungere la tabella **.
7.  Anche in questo caso, selezionare l'origine dati dell'entità di BudgetPlanJustification e fare clic su ** dopo **.
8.  Aggiungere i campi per EffectiveDate, ScenarioName, AccountDisplayValue e AccountingCurrencyExpenseAmount. ** Nota: ** Se i commenti sono disponibili per aggiungere all'interno di un singolo piano di budget, queste righe possono essere aggiunti alla tabella corrispondente.
9.  Aggiunge tutte le istruzioni aggiuntive immettere all'utilizzatore finale ed eseguire qualsiasi formattazione necessaria o la designazione al documento.
10. Salvare il documento nel computer locale e chiudere il file prima di continuare.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>Impostare il processo di pianificazione del budget per utilizzare il modello di giustificativo

1.  In Microsoft Dynamics 365 per le operazioni, spostarsi ** crearlo ** &gt; ** l'impostazione ** &gt; ** pianificazione del budget ** &gt; ** la motivazione aziendale vengono documentati i modelli **.
2.  Fare clic su ** nuovo ** e funzione di visualizzazione nel documento di recente di Microsoft Word.
3.  Immettere un nome visualizzato e una descrizione per il modello. Click **OK**.
4.  Va ** crearlo ** &gt; ** l'impostazione ** &gt; ** budget ** ** pianificazione ** &gt; ** processo di pianificazione del budget **.
5.  Selezionare il processo cui un modello di giustificativo deve essere utilizzato e fare clic su ** ** modifica.
6.  In ** modello di documento di motivazione ** sistemi, selezionare il modello appropriato e salvare.

##### <a name="edit-and-save-personalized-justification-documents"></a>Consente di modificare e salvare i documenti di motivazione personali

1.  In Dynamics 365 per le operazioni, creare un nuovo piano di budget o aprire un piano di budget esistente.
2.  ** Giustificazione ** dal menu a discesa, selezionare ** creare una nuova motivazione **.
3.  Dopo il ricaricamento in dettaglio, selezionare per caricare il documento personale ** motivazione ** dal menu a discesa.



