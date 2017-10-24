--- 
title: " Configurare un lavoratore"
description: Questa procedura dimostra come configurare un lavoratore di vendita al dettaglio come rappresentante che ha diritto alla provvigione sulle vendite nel POS.
author: jblucher
manager: AnnBe
ms.date: 02/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 09c5d263f3ad0bade6b7dd8f099dd3f62a1ddf5d
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="configure-a-worker"></a> Configurare un lavoratore

[!include[task guide banner](../includes/task-guide-banner.md)]

Questa procedura dimostra come configurare un lavoratore di vendita al dettaglio come rappresentante che ha diritto alla provvigione sulle vendite nel POS. Questa procedura utilizza la società di dati dimostrativi USRT.


## <a name="create-a-commission-sales-group-for-the-worker"></a>Creare un gruppo di vendite con provvigione per il lavoratore
1. Andare a Vendite e marketing > Provvigioni > Gruppi vendite.
    * I lavoratori possono essere assegnati a uno o più gruppi di vendite. In POS, è possibile scegliere qualsiasi gruppo di vendite contenente i lavoratori dalla rubrica del punto vendita.  
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Gruppo.
4. Digitare un valore nel campo Nome.
5. Fare clic su Salva.
6. Nel riquadro azioni fare clic su Generale.
7. Fare clic su Rappres.
    * Un gruppo di vendite può contenere più di un lavoratore. Le provvigioni possono essere suddivise tra i lavoratori in base alla modalità di definizione della quota di provvigione.  
8. Nel campo Nome immettere o selezionare un valore.
9. Nel campo Quota provvigione immettere un numero.
10. Fare clic su Salva.
11. Chiudere la pagina.
12. Chiudere la pagina.

## <a name="assign-the-workers-default-sales-group"></a>Assegnare i lavoratori al gruppo di vendite predefinito
1. Passare a Vendita al dettaglio e commercio > Dipendenti > Lavoratori.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Fare clic sulla scheda Vendita al dettaglio.
    * Un lavoratore può essere assegnato a un gruppo di vendite predefinito. Il gruppo di vendite predefinito viene aggiunto automaticamente alle righe di vendita nel POS se l'opzione è abilitata nel profilo funzionalità per il punto vendita.  
5. Fare clic su Modifica.
6. Nel campo Gruppo predefinito, immettere o selezionare un valore.
7. Fare clic su Salva.


