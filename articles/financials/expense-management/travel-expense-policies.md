---
title: Definire i criteri di spesa
description: In Microsoft Dynamics 365 for Finance and Operations è possibile definire criteri di spesa che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04eaff110fea021ddee32be650be540894eb703b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "342433"
---
# <a name="expense-policies"></a>Criteri di spesa

[!include [banner](../includes/banner.md)]

È possibile definire criteri che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio.         
L'implementazione di criteri di spesa consente di gestire le spese in modo efficiente.         

È ad esempio possibile impostare un criterio per le spese di albergo a New York, secondo il quale non devono superare USD 250 a notte.       
Se un lavoratore invia una nota spese o una richiesta di viaggio in cui il prezzo della camera supera questo importo, riceverà una notifica        
in cui viene indicato che è stato superato l'importo previsto dal criterio per questo tipo di spesa. È possibile configurare il messaggio che il lavoratore riceverà quando        
si definiscono i criteri.      
        
È possibile definire tre tipi di criteri:         
        
- Avviso: consente al lavoratore di inviare una nota spese o una richiesta di viaggio ma la spesa verrà contrassegnata per tutti gli approvatori e        
  per la dichiarazione successiva.        

- Errore: richiede al lavoratore di rivedere la spesa per conformarsi ai criteri prima di inviare la nota spese o la richiesta di viaggio.       
 
  - Motivazione: richiede al lavoratore o a un responsabile di immettere una motivazione per superare l'importo previsto dai criteri prima di inviare la nota spese o la richiesta di viaggio.        
 
  È inoltre possibile impostare un intervallo di date per il quale sono validi i criteri di spesa. Ad esempio, le tariffe aeree per i voli tra la Danimarca      
  e New York possono essere costose durante il periodo di picco della stagione turistica. È possibile definire una regola per le spese aeree in modo da specificare un limite      
  di DKK 5.000 per il costo dei voli diretti a New York e indicare che tale regola deve essere applicata nel periodo compreso tra il 15 marzo e      
  il 15 settembre.
