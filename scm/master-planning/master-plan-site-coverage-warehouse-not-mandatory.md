---
title: Pianificazione generale per la copertura a livello di sito, magazzino non obbligatorio
description: In questo argomento viene descritto come viene pianificato un articolo con dimensione sito impostata per la copertura.
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c04fee4b08e95e9a642375c661c06a4351e22b7e
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017

---

# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a>Pianificazione generale per la copertura a livello di sito, magazzino non obbligatorio

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come viene pianificato un articolo con dimensione sito impostata per la copertura.

In questo scenario di pianificazione generale sono previste le seguenti condizioni:

-   La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.
-   La dimensione magazzino non è impostata come obbligatoria. Il magazzino può essere noto, ma non è utilizzato nel calcolo della pianificazione generale.
-   La dimensione sito non è impostata per la pianificazione di copertura.
-   La dimensione magazzino non è impostata per la pianificazione di copertura. Di conseguenza, la fornitura e la domanda verranno aggregate in base al sito e, forse, anche in base ad altre dimensioni pianificate per la copertura.

Nella figura riportata di seguito è illustrato il processo di pianificazione generale. I parametri a cui viene fatto riferimento nella figura comprendono:
-   La copertura articoli viene definita per l'articolo. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Selezionare l'articolo, quindi fare clic su **Pianifica &gt;  Copertura articoli**.
-   Relazioni di ricaricamento definite per il magazzino. Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini** Nella scheda **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.
-   Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Selezionare l'articolo, quindi fare clic su **Pianifica &gt; Impostazioni ordine predefinite**. Nel modulo **Impostazioni ordine predefinite** vedere il campo **Tipo di ordine predefinito**.

![Copertura a livello di sito della domanda, magazzino non obbligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="see-also"></a>Vedere anche
--------

[Pianificazione generale e funzionalità multisito](master-plan-multisite-functionality.md)

[Pianificazione generale: copertura a livello di sito, magazzino obbligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Pianificazione generale: copertura a livello di sito magazzino, magazzino non obbligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Pianificazione generale: copertura a livello di sito magazzino, magazzino obbligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Pianificazione generale - Come determinare la versione DBA](master-plan-bom-version-determined.md)




