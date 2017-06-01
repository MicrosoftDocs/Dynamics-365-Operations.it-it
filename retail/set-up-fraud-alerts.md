---
title: Impostare avvisi antifrode
description: "In questo argomento viene illustrato come impostare le regole per avvisare i rappresentanti dell&quot;assistenza clienti di informazioni potenzialmente fraudolente quando gli ordini vengono elaborati. È possibile definire codici specifici da utilizzare per mettere automaticamente o manualmente gli ordini sospetti in attesa."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7255f2b7e49f56a731d0e3745b4752091013668b
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-fraud-alerts"></a>Impostare avvisi antifrode

[!include[banner](includes/banner.md)]


In questo argomento viene illustrato come impostare le regole per avvisare i rappresentanti dell'assistenza clienti di informazioni potenzialmente fraudolente quando gli ordini vengono elaborati. È possibile definire codici specifici da utilizzare per mettere automaticamente o manualmente gli ordini sospetti in attesa. 

Prima di impostare e di utilizzare le regole di verifica delle frodi, è necessario abilitare la verifica delle frodi e definire i valori di base di verifica delle frodi nei parametri per call center. Sono disponibili due tipi di regole su frode:

-   **Regole statiche**: utilizzano un valore specifico, come un numero di telefono che è stato inserito nella black list.
-   **Regole dinamiche**: possono essere composte da variabili e condizioni.

Prima di creare una regola dinamica, è necessario creare le variabili e le condizioni che definiscono a chi viene applicata la regola e quando questa deve essere applicata. Si supponga, ad esempio, di voler creare una regola per richiedere che qualsiasi ordine cliente effettuato dal cliente 1202 del valore di 1.000,00 o più sia sospeso fino a quando non è possibile verificare il pagamento del cliente. In questo caso, le variabili sono il cliente 1202 e un totale dell'ordine di 1.000,00. La condizione specifica che se il cliente 1202 effettua un ordine e l'importo totale dell'ordine è uguale o maggiore di 1.000,00, l'ordine cliente deve sospeso fino a quando non viene verificato il pagamento del cliente.




