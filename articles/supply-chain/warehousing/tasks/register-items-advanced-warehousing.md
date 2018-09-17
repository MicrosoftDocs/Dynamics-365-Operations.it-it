--- 
title: Registrare articoli per un articolo abilitato a immagazzinaggio avanzato tramite un giornale di registrazione arrivi
description: Questa procedura mostra come registrare gli articoli utilizzando il giornale di registrazione arrivi articoli quando si utilizzano i processi di gestione avanzata di magazzino.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 050d1fcbc59d9bb3253bfed2433987285423b334
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a>Registrare articoli per un articolo abilitato a immagazzinaggio avanzato tramite un giornale di registrazione arrivi

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come registrare gli articoli utilizzando il giornale di registrazione arrivi articoli quando si utilizzano i processi di gestione avanzata di magazzino. Questa operazione viene generalmente effettuata da un addetto al ricevimento. 

È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. È necessario disporre di un ordine fornitore confermato con una riga ordine fornitore aperta prima di iniziare questa guida. L'articolo nella riga deve essere stoccato e non deve utilizzare le varianti prodotto né avere dimensioni di tracciabilità. E l'articolo deve essere associato a un gruppo di dimensioni di immagazzinamento abilitato da un processo di gestione magazzino. Il magazzino utilizzato deve essere abilitato per i processi di gestione magazzino e l'ubicazione utilizzata per il ricevimento deve essere controllata da targa. Se si utilizza USMF, è possibile utilizzare l'account società 1001, il magazzino 51 e l'articolo M9200 per creare il PO. 

Prendere nota del numero dell'ordine fornitore creato e anche del numero di articolo e del sito utilizzati per la riga ordine fornitore.


## <a name="create-an-item-arrival-journal-header"></a>Creare un'intestazione di giornale di registrazione arrivi articoli
1. Passare a Arrivo articoli.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
    * Se si utilizza USMF, è possibile digitare WHS. Se si utilizzano altri dati, il giornale di registrazione di cui è stato scelto il nome deve avere le proprietà Verifica ubicazione prelievo e Gestione quarantena impostate su No.  
4. Digitare un valore nel campo Numero.
5. Digitare un valore nel campo Sito.
    * Selezionare il sito utilizzato per la riga ordine fornitore. Questo servirà come valore predefinito, per tutte le righe nel giornale di registrazione. Se è stato utilizzato il magazzino 51 in USMF, selezionare il sito 5.  
6. Digitare un valore nel campo Magazzino.
    * Selezionare un magazzino valido per il sito selezionato. Questo servirà come valore predefinito, per tutte le righe nel giornale di registrazione. Se si utilizzano i valori di esempio in USMF, selezionare 51.  
7. Digitare un valore nel campo Ubicazione.
    * Selezionare un'ubicazione valida nel magazzino selezionato. L'ubicazione deve essere associata a un profilo dell'ubicazione, che è controllata da targa. Questo servirà come valore predefinito, per tutte le righe nel giornale di registrazione. Se si utilizzano i valori di esempio in USMF, selezionare Bulk-008.  
8. Fare clic con il pulsante destro del mouse sulla freccia a discesa nel campo Targa e selezionare Visualizza dettagli.
9. Fare clic su Nuovo.
10. Digitare un valore nel campo Targa.
    * Prendere nota del valore.  
11. Fare clic su Salva.
12. Chiudere la pagina.
13. Digitare un valore nel campo Targa.
    * Immettere il valore di targa appena creato. Questo servirà come valore predefinito, per tutte le righe nel giornale di registrazione.  
14. Fare clic su OK.

## <a name="add-a-line"></a>Aggiungere una riga
1. Fare clic su Aggiungi riga.
2. Nel campo Numero articolo, digitare un valore.
    * Immettere il numero di articolo che è stato utilizzato nella riga ordine fornitore.  
3. Nel campo Quantità immettere un numero.
    * Immettere la quantità che si desidera registrare.  
    * Il campo Data determina la data in cui la quantità disponibile dell'articolo verrà registrata in magazzino.  
    * L'ID lotto sarà popolato dal sistema se può essere identificato in modo univoco dalle informazioni fornite. Altrimenti sarà necessario aggiungerlo manualmente. Si tratta di un campo obbligatorio, che collega la registrazione a una riga specifica del documento di origine.  

## <a name="complete-the-registration"></a>Completare la registrazione
1. Fare clic su Convalida.
    * Ciò verifica che il giornale di registrazione è pronto per essere registrato. Se la convalida ha esito negativo sarà necessario correggere gli errori prima di registrare il giornale di registrazione.  
2. Fare clic su OK.
    * Dopo aver fatto clic su OK, controllare il messaggio. Dovrebbe esserci un messaggio che dice che il giornale di registrazione è corretto.  
3. Fare clic su Registra.
4. Fare clic su OK.
    * Dopo aver fatto clic su OK, controllare la barra dei messaggi. Dovrebbe esserci un messaggio che dice che l'operazione è stata completata.  
5. Chiudere la pagina.


