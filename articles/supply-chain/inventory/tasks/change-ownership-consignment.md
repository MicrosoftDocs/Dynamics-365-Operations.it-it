--- 
title: "Modificare la proprietà dell'inventario spedizione in base alla domanda di produzione"
description: "In questa procedura viene illustrato come modificare il proprietario dell'inventario di spedizione dal fornitore alla persona giuridica quando c'è domanda di inventario nella produzione."
author: perlynne
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5925f5423d596adc4326dfff4734de2afd80b5a8
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a>Modificare la proprietà dell'inventario spedizione in base alla domanda di produzione

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come modificare il proprietario dell'inventario di spedizione dal fornitore alla persona giuridica quando c'è domanda di inventario nella produzione. Questo cambio di proprietà viene eseguito creando e registrando un giornale di registrazione modifiche proprietà inventario. Le righe del giornale di registrazione modifiche proprietà possono essere create manualmente oppure, come illustrato nella registrazione corrente, in base alla domanda di produzione esistente. In genere, un supervisore dello shop floor esegue questa attività. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure sui propri dati. Se si utilizzano i propri dati, verificare che siano presenti i seguenti prerequisiti: un nome di giornale di registrazione inventario impostato per la modifica di proprietà di inventario, gli articoli registrati di proprietà del fornitore fisicamente disponibili e una o più righe di ordine di produzione per il materiale. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations, versione 1611.


## <a name="create-an-inventory-ownership-journal"></a>Creare un giornale di registrazione proprietà inventario
1. Passare a Gestione inventario > Inserimenti nel giornale di registrazione > Articoli > Modifica proprietà inventario.
2. Fare clic su Nuovo.
    * Il giornale di registrazione modifiche proprietà inventario viene utilizzato per cambiare il proprietario dell'inventario di spedizione dal fornitore alla persona giuridica corrente. Questo cambio di proprietà viene effettuato mediante il rilascio delle scorte disponibili di proprietà del fornitore e la ricezione di inventario nella persona giuridica corrente.  
3. Nel campo Nome immettere o selezionare un valore.
    * È possibile selezionare soltanto i nomi di giornale di registrazione inventario con un tipo di giornale di registrazione Modifica proprietà.  
4. Fare clic su OK.
5. Fare clic su Funzioni.
6. Fare clic su Creare righe del giornale di registrazione dagli ordini di produzione.
    * È possibile avviare il processo di cambio di proprietà eseguendo una query su tutte le righe di produzione con domanda di consumo di materie prime.  
7. Nel campo Stati uscita inventario da includere, selezionare un'opzione.
    * Questa opzione consente di filtrare in base allo stato dell'uscita delle transazioni di inventario. Ad esempio, è possibile creare righe del giornale di registrazione per l'inventario con gli stati Prelevato e Fisico prenotato.  
8. Espandere la sezione Record da includere.
    * Questa sezione consente di applicare filtri aggiuntivi. Ad esempio, è possibile selezionare una data specifica per le materie prime.  
9. Fare clic su OK.

## <a name="post-the-inventory-ownership-change-journal"></a>Registrare il giornale di registrazione modifiche proprietà inventario
1. Fare clic su Registra.
    * Quando il giornale viene registrato, l'inventario di proprietà del fornitore viene rilasciato mediante un riferimento "Modifica proprietà". L'inventario verrà ricevuto come scorte disponibili utilizzando una transazione di inventario che viene aggiornata con un'entrata prodotti ordine fornitore. Tenere presente che solo le transazioni relative al giornale registrato vengono create. Non vengono create transazioni di inventario previste.  
2. Fare clic su OK.
3. Chiudere la pagina.


