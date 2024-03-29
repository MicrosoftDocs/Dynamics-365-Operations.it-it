---
title: Creare un budget da conti transazioni e conti totali
description: Questo articolo fornisce una panoramica del processo per creare budget basati sui conti totali. Illustra inoltre come attivare il controllo del budget per i conti totali, se il controllo del budget è necessario.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: kfend
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33f7e49c56a5780644023b6b4fdcbc0937f7f90b
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714399"
---
# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a>Creare un budget da conti transazioni e conti totali

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una panoramica del processo per creare budget basati sui conti totali. Illustra inoltre come attivare il controllo del budget per i conti totali, se il controllo del budget è necessario.

Il piano di budget e i documenti della voce del registro di budget consentono l'impostazione del budget sui conti principali di tipo **Totale**. I valori effettivi possono essere registrati solo sul conti principali transazionali. 

Per il processo periodico **Genera piano di budget da contabilità generale**, sulla scheda **Origine**, è possibile specificare il tipo di conto principale **Totale** come criterio. In questo caso, ogni conto principale totale verrà incluso nel piano di budget di destinazione e l'importo sarà pari all'importo totale dell'intervallo di conti principali selezionati. 

È possibile attivare il controllo del budget per i conti principali di tipo **Totale**. Questa funzionalità è supportata tramite l'utilizzo dei gruppi di budget. Per ciascun conto principale totale, il budget da controllare per un gruppo di budget deve essere creato nella pagina **Configurazione controllo del budget**. I criteri specificati devono includere il conto principale totale e l'intervallo di conti. Per rendere più rapido il processo di creazione di gruppi di budget, è possibile usufruire dell'entità di dati Gruppi di controllo del budget. 

Quando un budget viene utilizzato nella creazione di report, ad esempio in un rendiconto finanziario, la somma del budget per il conto totale è costituita dai seguenti importi:

-   I budget creati da ciascun conto CoGe per transazioni nell'intervallo del conto totale.
-   L'importo del budget immesso direttamente nel conto totale.

Pertanto, è possibile creare budget distinti per i conti transazioni più significativi nell'intervallo del conto totale e quindi aggiungere l'importo del budget disponibile al conto totale.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
