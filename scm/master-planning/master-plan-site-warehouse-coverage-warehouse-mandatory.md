---
title: La pianificazione generale per la copertura a livello di sito e magazzino, magazzino non disponibile
description: "In questo argomento viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura. La dimensione magazzino è obbligatoria."
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
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: a0931d88f84544160803e42466575c02f47588a4
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a>La pianificazione generale per la copertura a livello di sito e magazzino, magazzino non disponibile

In questo argomento viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura. La dimensione magazzino è obbligatoria.

In questo scenario di pianificazione generale sono previste le seguenti condizioni:

-   La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.
-   La dimensione magazzino è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.
-   Le dimensioni sito e magazzino sono impostate per la pianificazione della copertura. Altre dimensioni possono essere impostate anche per la pianificazione copertura. Tuttavia, non sono interessate dalla funzionalità multisito.

Nella figura riportata di seguito è illustrato il processo di pianificazione generale. I parametri a cui viene fatto riferimento nella figura comprendono:
-   The warehouse is set to **Manual**. ** Fare clic su Gestione &gt; articoli impostare &gt; i magazzini di suddivisione &gt; scorte **. Nella scheda dettaglio **Pianificazione generale**, vedere il campo **Manuale**.
-   La copertura articoli viene definita per l'articolo. ** Prodotti Fare clic su Gestione informazioni &gt; sul&gt; prodotto rilasciati i prodotti **. Selezionare l'articolo, quindi nel riquadro azioni, ** piano ** nella scheda, fare clic su ** copertura articoli **.
-   Relazioni di ricaricamento definite per il magazzino. ** Fare clic su Gestione &gt; articoli impostare &gt; i magazzini di suddivisione &gt; scorte **. Nella scheda dettaglio **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.
-   Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban. ** Prodotti Fare clic su Gestione informazioni &gt; sul&gt; prodotto rilasciati i prodotti **. Selezionare l'articolo, quindi nel riquadro azioni, ** piano ** nella scheda, fare clic su ** delle impostazioni ordine **. Nel modulo **Impostazioni ordine predefinite** vedere **Tipo di ordine predefinito**.

![Copertura a livello di sito e magazzino della domanda, magazzino obbligatorio](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="see-also"></a>Vedere anche
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Pianificazione generale: copertura a livello di sito, magazzino obbligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Pianificazione generale: copertura a livello di sito, magazzino non obbligatorio](master-plan-site-coverage-warehouse-not-mandatory.md)

[Pianificazione generale: copertura a livello di sito magazzino, magazzino non obbligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Pianificazione generale - Come determinare la versione DBA](master-plan-bom-version-determined.md)


