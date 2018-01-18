---
title: Definire i criteri di spesa
description: "In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition è possibile definire criteri di spesa che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio."
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 9a5ce1a3b6519b510c9f5aa5618ab91f77a2d91a
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="expense-policies"></a>Criteri di spesa

[!include[banner](../includes/banner.md)]

È possibile definire criteri che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio. L'implementazione di criteri di spesa consente di gestire le spese in modo efficiente. 

È ad esempio possibile impostare un criterio per le spese di albergo a New York, secondo il quale non devono superare USD 250 a notte. Se un lavoratore invia una nota spese o una richiesta di viaggio in cui la tariffa per la stanza d'albergo supera quell'importo, il lavoratore riceverà una notifica in cui viene indicato che l'importo previsto dal criterio per questo tipo di spesa è stato superato. È possibile configurare il messaggio che il lavoratore riceverà quando si definiscono i criteri. 

È possibile definire tre tipi di criteri: 

 - Avviso: consente al lavoratore di inviare una nota spese o una richiesta di viaggio ma la spesa verrà contrassegnata per tutti gli approvatori e  
 per la dichiarazione successiva. 
 - Errore: richiede al lavoratore di rivedere la spesa per conformarsi ai criteri prima di inviare la nota spese o la richiesta di viaggio. 
 - Motivazione: richiede al lavoratore o a un responsabile di immettere una motivazione per superare l'importo previsto dai criteri prima di inviare la nota spese o la richiesta di viaggio. 

È inoltre possibile impostare un intervallo di date per il quale sono validi i criteri di spesa. Le tariffe aeree per i voli tra la Danimarca e New York ad esempio possono essere costose durante il periodo di picco della stagione turistica. È possibile definire una regola per le spese aeree in modo da specificare un limite di DKK 5.000 per il costo dei voli diretti a New York e indicare che tale regola deve essere applicata nel periodo compreso tra il 15 marzo e il 15 settembre. 

