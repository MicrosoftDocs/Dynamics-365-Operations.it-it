--- 
title: " Configurazioni dei parametri per rendiconti di vendita al dettaglio"
description: "In questa procedura sono illustrate le configurazioni per i parametri di vendita al dettaglio che interessano la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: ba3b528f8739e4e84ffdbeea5d0af5817f2d9c10
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="parameter-configurations-for-retail-statements"></a> Configurazioni dei parametri per rendiconti di vendita al dettaglio

[!include[task guide banner](../includes/task-guide-banner.md)]

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


