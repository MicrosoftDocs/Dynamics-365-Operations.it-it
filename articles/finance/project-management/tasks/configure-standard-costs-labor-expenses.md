---
title: Configurare i costi standard di manodopera e spese
description: In questo argomento viene illustrato come impostare i costi standard per la manodopera e le spese per un progetto.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60ab8eb94d4a8a0fb2c1e732ec7b25bfd5e7611e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185407"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Configurare i costi standard di manodopera e spese

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questo argomento viene illustrato come impostare i costi standard per la manodopera e le spese per un progetto. Questa attività utilizza il set di dati dimostrativi USSI.

1. Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di costo (ora)**.
2. Selezionare **Nuovo**.
3. Nel campo **Data di validità**, immettere una data.
4. Immettere un numero nel campo **Prezzo di costo**. È possibile impostare un prezzo di costo standard in base alla categoria del progetto oppure prezzi di costo per numero lavoratore, numero progetto, categoria, data o una qualsiasi combinazione di questi elementi. Il prezzo di costo applicato corrisponderà a quello associato al livello di dettaglio più alto.  
5. Selezionare **Salva**.
6. Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di vendita (ora)**.
7. Selezionare **Nuovo**.
8. Nel campo **Data di validità**, immettere una data.
9. Selezionare un'opzione nel campo **Valido per**.
10. Immettere un numero nel campo **Determinazione prezzo**. È possibile impostare un prezzo di vendita standard per transazioni orarie o per una categoria di progetto. Inoltre è possibile impostare i prezzi di vendita in base al numero del lavoratore, al numero del progetto, alla categoria, alla data della transazione oppure a una combinazione di questi elementi. Il prezzo di vendita effettivo, che viene applicato quando un lavoratore immette una transazione nel giornale di registrazione ore, è il prezzo di vendita con il livello di dettagli più alto. Se vengono impostati, ad esempio, un prezzo di vendita generale e un prezzo di vendita specifico per un lavoratore, verrà utilizzato automaticamente quello specifico per il lavoratore.  
11. Selezionare **Salva**.
12. Chiudere la pagina.
13. Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di costo (spesa)**.
14. Selezionare **Nuovo**.
15. Nel campo **Data di validità**, immettere una data.
16. Immettere un numero nel campo **Prezzo di costo**. Più campi possono essere completati, ma questo è il minimo necessario per salvare il record.  
17. Selezionare **Salva**.
18. Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di vendita (spesa)**.
19. Selezionare **Nuovo**.
20. Nel campo **Data di validità**, immettere una data.
21. Selezionare un'opzione nel campo **Valido per**.
22. Immettere un numero nel campo **Determinazione prezzo**. Il prezzo di vendita effettivo, applicato quando un lavoratore immette una transazione in un giornale di registrazione spese, corrisponde al prezzo di vendita con il più alto livello di dettaglio. Se vengono impostati, ad esempio, un prezzo di vendita generale e un prezzo di vendita specifico per un lavoratore, verrà selezionato automaticamente quello specifico per il lavoratore.  
23. Selezionare **Salva**.

