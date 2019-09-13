---
title: Configurare i parametri di vendita al dettaglio che influiscono sui rendiconti della vendita al dettaglio
description: In questo argomento sono illustrate le configurazioni per i parametri di vendita al dettaglio che interessano la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9a0386a4d61395903e82d988244dd131c1febaf
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867273"
---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a>Configurare i parametri di vendita al dettaglio che influiscono sui rendiconti della vendita al dettaglio

[!include[task guide banner](../includes/task-guide-banner.md)]

In questo argomento sono illustrate le configurazioni per i parametri di vendita al dettaglio che interessano la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio. Questa procedura utilizza la società dimostrativa USRT.

1. Nel pannello di navigazione, andare a **Moduli > Vendita al dettaglio e commercio > Impostazione sedi centrali > Parametri > Parametri di vendita al dettaglio.**
2. Selezionare la scheda **Registrazione**.
    - Selezionare **Sì** se si desidera registrare gli importi di sconto periodici in modo specifico.  
    - Selezionare **Standard** per utilizzare i conti predefiniti o selezionare **Periodico** per definire il conto da utilizzare per ciascuno sconto periodico.  
      - Selezionare **Riepilogo** se le righe di scorte devono essere aggregate ove possibile.  
      - Selezionare **Sì** se le fatture e pagamenti devono essere automaticamente liquidati durante il processo di registrazione rendiconti.  
      - Selezionare **Sì** se le transazioni deposito in cassaforte devono essere aggregate.  
      - Selezionare **Sì** se le transazioni deposito bancario devono essere aggregate.  
      - Selezionare **Sì** per attivare l'aggregazione per la registrazione rendiconti.  
      - Selezionare **Sì** per creare ed elaborare gli ordini in parallelo quando i rendiconti vengono registrati.  
      - Immettere il numero massimo di ordini da elaborare in ogni attività di processo batch.  
3. Selezionare **Salva**.

