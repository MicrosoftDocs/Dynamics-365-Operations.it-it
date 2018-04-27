--- 
title: " Configurazioni dei parametri per rendiconti di vendita al dettaglio"
description: "In questa procedura sono illustrate le configurazioni per i parametri di vendita al dettaglio che interessano la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 0c93633e92221264cc6a67c74d62edaa59bdbd2f
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---
# <a name="parameter-configurations-for-retail-statements"></a> Configurazioni dei parametri per rendiconti di vendita al dettaglio

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

In questa procedura sono illustrate le configurazioni per i parametri di vendita al dettaglio che interessano la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio. Questa procedura utilizza la società dimostrativa USRT.

1. Andare a Vendita al dettaglio e commercio > Impostazione sedi centrali > Parametri > Parametri di vendita al dettaglio.
2. Fare clic sulla scheda Registrazione.
    * Selezionare "Sì" se si desidera registrare gli importi di sconto periodici in modo specifico.  
    * Selezionare "Standard" per utilizzare i conti predefiniti o selezionare "Periodico" per definire il conto da utilizzare per ciascuno sconto periodico.  
    * Selezionare "Riepilogo" se le righe di scorte devono essere aggregate ove possibile.  
    * Selezionare "Sì" se le fatture e pagamenti devono essere automaticamente liquidati durante il processo di registrazione rendiconti.  
    * Selezionare "Sì" se le transazioni deposito in cassaforte devono essere aggregate.  
    * Selezionare "Sì" se le transazioni deposito bancario devono essere aggregate.  
    * Selezionare "Sì" per attivare l'aggregazione per la registrazione rendiconti.  
    * Selezionare "Sì" per creare ed elaborare gli ordini in parallelo quando i rendiconti vengono registrati.  
    * Immettere il numero massimo di ordini da elaborare in ogni attività di processo batch.  
3. Fare clic su Salva.


