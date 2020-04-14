---
title: Configurare i parametri che influiscono sui rendiconti della vendita al dettaglio
description: In questo argomento sono illustrate le configurazioni per i parametri di Commerce che interessano la modalità di creazione e registrazione dei rendiconti.
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
ms.openlocfilehash: 7892a216d836ebcc297a5b7eb87bc996dd9b91bf
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140839"
---
# <a name="configure-parameters-that-affect-retail-statements"></a>Configurare i parametri che influiscono sui rendiconti della vendita al dettaglio

[!include [banner](../includes/banner.md)]

In questo argomento sono illustrate le configurazioni per i parametri di Commerce che interessano la modalità di creazione e registrazione dei rendiconti. Questa procedura utilizza la società dimostrativa USRT.

1. Nel pannello di navigazione, andare a **Moduli > Retail e Commerce > Impostazione sedi centrali > Parametri > Parametri di commercio**.
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

