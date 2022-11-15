---
title: Pianificazione generale per copertura a livello di sito e magazzino, magazzino non obbligatorio
description: In questo articolo viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura. La dimensione magazzino non è impostata come obbligatoria.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4989a05f4647ac836b78692da7f63396dbef788
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741014"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>Pianificazione generale per copertura a livello di sito e magazzino, magazzino non obbligatorio

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come viene pianificato un articolo con sito e magazzino come dimensioni di copertura. La dimensione magazzino non è impostata come obbligatoria.

In questo scenario di pianificazione generale sono previste le seguenti condizioni:

-   La dimensione sito è impostata come obbligatoria e deve essere immessa nella transazione relativa alla domanda. Questa impostazione non può essere modificata.
-   La dimensione magazzino non è impostata come obbligatoria. Il magazzino può essere noto, ma non è utilizzato nel calcolo della pianificazione generale.
-   Le dimensioni sito e magazzino sono impostate per la pianificazione della copertura. Altre dimensioni possono essere impostate anche per la pianificazione copertura. Tuttavia, non sono interessate dalla funzionalità multisito.

Nella figura riportata di seguito è illustrato il processo di pianificazione generale. I parametri a cui viene fatto riferimento nella figura comprendono:
-   Il magazzino è impostato su Manuale. Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini** Nella scheda dettaglio **Pianificazione generale**, vedere il campo **Manuale**.
-   La copertura articoli viene definita per l'articolo. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Seleziona l'articolo, quindi nel riquadro azioni nella scheda **Pianificazione** fai clic su **Copertura articoli**.
-   Relazioni di ricaricamento definite per il magazzino. Fare clic su **Gestione articoli &gt; Impostazioni &gt; Suddivisione scorte &gt; Magazzini** Nella scheda dettaglio **Pianificazione generale** vedere il gruppo di campi **Magazzino principale**.
-   Il tipo di ordine predefinito viene impostato sull'ordine acquisto, di produzione o sul kanban. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Seleziona l'articolo, quindi nel riquadro azioni nella scheda **Pianificazione** fai clic su **Impostazioni ordine predefinite**. Nel modulo **Impostazioni ordine predefinite** vedere **Tipo di ordine predefinito**.

![Domanda di sito e magazzino, magazzino non obbligatorio.](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica pianificazione generale e funzionalità multisito](master-plan-multisite-functionality.md)
- [Pianificazione generale per copertura a livello di sito, magazzino obbligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)
- [Pianificazione generale a livello di sito e magazzino, magazzino obbligatorio](master-plan-site-coverage-warehouse-mandatory.md)
- [Pianificazione generale a livello di sito e magazzino, magazzino non obbligatorio](master-plan-site-coverage-warehouse-not-mandatory.md)
- [Determinare la versione DBA](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]