---
title: Pianificazione generale per copertura a livello di sito e magazzino, magazzino obbligatorio
description: In questo argomento viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura. La dimensione magazzino è obbligatoria.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11720b70697112085ac612fc9eded8292a68ab2d
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815090"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a>Pianificazione generale per copertura a livello di sito e magazzino, magazzino obbligatorio

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura. La dimensione magazzino è obbligatoria.

In questo scenario di pianificazione generale sono previste le seguenti condizioni:

-   La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.
-   La dimensione magazzino è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda.
-   Le dimensioni sito e magazzino sono impostate per la pianificazione della copertura. Altre dimensioni possono essere impostate anche per la pianificazione copertura. Tuttavia, non sono interessate dalla funzionalità multisito.

Nella figura riportata di seguito è illustrato il processo di pianificazione generale. I parametri a cui viene fatto riferimento nella figura comprendono:
-   Il magazzino è impostato su **Manuale**. Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini** Nella scheda dettaglio **Pianificazione generale**, vedere il campo **Manuale**.
-   La copertura articoli viene definita per l'articolo. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Selezionare l'articolo, quindi nel riquadro azioni nella scheda **Pianificazione** fare clic su **Copertura articoli**.
-   Relazioni di ricaricamento definite per il magazzino. Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini** Nella scheda dettaglio **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.
-   Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Selezionare l'articolo, quindi nel riquadro azioni nella scheda **Pianificazione** fare clic su **Impostazioni ordine predefinite**. Nel modulo **Impostazioni ordine predefinite** vedere **Tipo di ordine predefinito**.

![Copertura a livello di sito e magazzino della domanda, magazzino obbligatorio](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a>Risorse aggiuntive
--------

[Panoramica pianificazione generale e funzionalità multisito](master-plan-multisite-functionality.md)

[Pianificazione generale per copertura a livello di sito, magazzino obbligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Pianificazione generale per copertura a livello di sito, magazzino non obbligatorio](master-plan-site-coverage-warehouse-not-mandatory.md)

[Pianificazione generale a livello di sito e magazzino, magazzino non obbligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Determinare la versione DBA](master-plan-bom-version-determined.md)



