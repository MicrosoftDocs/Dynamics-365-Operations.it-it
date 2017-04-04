---
title: Pianificazione generale per la copertura a livello di sito, magazzino obbligatorio
description: "In questo argomento viene descritto come viene pianificato un articolo con dimensione sito come copertura. La dimensione magazzino è obbligatoria."
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
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4c595aa9809e37ba752b76f559ef909c071eb303
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Pianificazione generale per la copertura a livello di sito, magazzino obbligatorio

In questo argomento viene descritto come viene pianificato un articolo con dimensione sito come copertura. La dimensione magazzino è obbligatoria.

In questo scenario di pianificazione generale sono previste le seguenti condizioni:

-   La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda. Questa impostazione non può essere modificata.
-   La dimensione magazzino è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.
-   La dimensione sito non è impostata per la pianificazione di copertura. Altre dimensioni possono essere impostate anche per la pianificazione copertura. Tuttavia, non sono interessate dalla funzionalità multisito.
-   La dimensione magazzino non è impostata per la pianificazione di copertura. Di conseguenza, la fornitura e la domanda verranno aggregate in base al sito e, forse, anche in base ad altre dimensioni pianificate per la copertura.

Nella figura riportata di seguito è illustrato il processo di pianificazione generale. I parametri a cui viene fatto riferimento nella figura comprendono:
-   La copertura articoli viene definita per l'articolo. ** Prodotti Fare clic su Gestione informazioni &gt; sul&gt; prodotto rilasciati i prodotti **. Selezionare l'articolo e fare clic su ** progetti &gt; la copertura articoli **.
-   Relazioni di ricaricamento definite per il magazzino. ** Fare clic su Gestione &gt; articoli impostare &gt; i magazzini di suddivisione &gt; scorte **. Nella scheda **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.
-   Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban. ** Prodotti Fare clic su Gestione informazioni &gt; sul&gt; prodotto rilasciati i prodotti **. Selezionare l'articolo e fare clic su ** progetti &gt; le impostazioni di ordine predefinite **. Nel modulo **Impostazioni ordine predefinite** vedere **Tipo di ordine predefinito**.

![Copertura a livello di sito della domanda, magazzino obbligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a>Vedere anche
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Pianificazione generale: copertura a livello di sito magazzino, magazzino obbligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Pianificazione generale - copertura del sito. magazzino obbligatorio master-plan-site-coverage-warehouse-mandatory.md] ()

[Pianificazione generale: copertura a livello di sito magazzino, magazzino non obbligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Pianificazione generale - Come determinare la versione DBA](master-plan-bom-version-determined.md)


