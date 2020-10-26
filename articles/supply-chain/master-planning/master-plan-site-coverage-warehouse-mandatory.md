---
title: Pianificazione generale per copertura a livello di sito, magazzino obbligatorio
description: In questo argomento viene descritto come viene pianificato un articolo con dimensione sito come copertura. La dimensione magazzino è obbligatoria.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b1890f14351734c26952511f6245efe4cce5f3e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3987144"
---
# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Pianificazione generale per copertura a livello di sito, magazzino obbligatorio

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come viene pianificato un articolo con dimensione sito come copertura. La dimensione magazzino è obbligatoria.

In questo scenario di pianificazione generale sono previste le seguenti condizioni:

-   La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda. Questa impostazione non può essere modificata.
-   La dimensione magazzino è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.
-   La dimensione sito non è impostata per la pianificazione di copertura. Altre dimensioni possono essere impostate anche per la pianificazione copertura. Tuttavia, non sono interessate dalla funzionalità multisito.
-   La dimensione magazzino non è impostata per la pianificazione di copertura. Di conseguenza, la fornitura e la domanda verranno aggregate in base al sito e, forse, anche in base ad altre dimensioni pianificate per la copertura.

Nella figura riportata di seguito è illustrato il processo di pianificazione generale. I parametri a cui viene fatto riferimento nella figura comprendono:
-   La copertura articoli viene definita per l'articolo. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Selezionare l'articolo, quindi fare clic su **Pianifica &gt;  Copertura articoli**.
-   Relazioni di ricaricamento definite per il magazzino. Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini** Nella scheda **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.
-   Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Selezionare l'articolo, quindi fare clic su **Pianifica &gt; Impostazioni ordine predefinite**. Nel modulo **Impostazioni ordine predefinite** vedere **Tipo di ordine predefinito**.

![Copertura a livello di sito della domanda, magazzino obbligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a>Risorse aggiuntive
--------

[Panoramica pianificazione generale e funzionalità multisito](master-plan-multisite-functionality.md)

[Pianificazione generale a livello di sito e magazzino, magazzino obbligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Pianificazione generale per copertura a livello di sito, magazzino obbligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Pianificazione generale a livello di sito e magazzino, magazzino non obbligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Determinare la versione DBA](master-plan-bom-version-determined.md)



