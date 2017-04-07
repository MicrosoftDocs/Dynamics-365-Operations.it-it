---
title: La pianificazione generale per la copertura a livello di sito e magazzino, disponibile non obbligatorio
description: "In questo argomento viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura. La dimensione magazzino non è impostata come obbligatoria."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 3671024dc097c94638b1579d7cacc8447c49e97b
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>La pianificazione generale per la copertura a livello di sito e magazzino, disponibile non obbligatorio

In questo argomento viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura. La dimensione magazzino non è impostata come obbligatoria.

In questo scenario di pianificazione generale sono previste le seguenti condizioni:

-   La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda. Questa impostazione non può essere modificata.
-   La dimensione magazzino non è impostata come obbligatoria. Il magazzino può essere noto, ma non è utilizzato nel calcolo della pianificazione generale.
-   Le dimensioni sito e magazzino sono impostate per la pianificazione della copertura. Altre dimensioni possono essere impostate anche per la pianificazione copertura. Tuttavia, non sono interessate dalla funzionalità multisito.

Nella figura riportata di seguito è illustrato il processo di pianificazione generale. I parametri a cui viene fatto riferimento nella figura comprendono:
-   Il magazzino è impostato su Manuale. ** Fare clic su Gestione &gt; articoli impostare &gt; i magazzini di suddivisione &gt; scorte **. Nella scheda dettaglio **Pianificazione generale**, vedere il campo **Manuale**.
-   La copertura articoli viene definita per l'articolo. ** Prodotti Fare clic su Gestione informazioni &gt; sul&gt; prodotto rilasciati i prodotti **. Selezionare l'articolo, quindi nel riquadro azioni, ** piano ** nella scheda, fare clic su ** copertura articoli **.
-   Relazioni di ricaricamento definite per il magazzino. ** Fare clic su Gestione &gt; articoli impostare &gt; i magazzini di suddivisione &gt; scorte **. Nella scheda dettaglio **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.
-   Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban. ** Prodotti Fare clic su Gestione informazioni &gt; sul&gt; prodotto rilasciati i prodotti **. Selezionare l'articolo, quindi nel riquadro azioni, ** piano ** nella scheda, fare clic su ** delle impostazioni ordine **. Nel modulo **Impostazioni ordine predefinite** vedere **Tipo di ordine predefinito**.

![Domanda di sito e magazzino, magazzino non obbligatorio](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)

 
-



<a name="see-also"></a>Vedere anche
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Pianificazione generale: copertura a livello di sito magazzino, magazzino obbligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Pianificazione generale: copertura a livello di sito, magazzino obbligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Pianificazione generale: copertura a livello di sito, magazzino non obbligatorio](master-plan-site-coverage-warehouse-not-mandatory.md)

[Pianificazione generale - Come determinare la versione DBA](master-plan-bom-version-determined.md)


