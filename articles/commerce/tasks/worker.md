---
title: " Configurare un lavoratore"
description: Questa procedura dimostra come configurare un lavoratore come rappresentante che ha diritto alla provvigione sulle vendite nel POS.
author: jblucher
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a21d5f2d5963db2a92b653e8e520f96f11ba1bf6acbb238812211154d5b39fc0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726385"
---
# <a name="configure-a-worker"></a> Configurare un lavoratore

[!include [banner](../includes/banner.md)]

Questa procedura dimostra come configurare un lavoratore come rappresentante che ha diritto alla provvigione sulle vendite nel POS. Questa procedura utilizza la società di dati dimostrativi USRT.


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
1. Passare a Retail e Commerce > Dipendenti > Lavoratori.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Fare clic sulla scheda Commerce.
    * Un lavoratore può essere assegnato a un gruppo di vendite predefinito. Il gruppo di vendite predefinito viene aggiunto automaticamente alle righe di vendita nel POS se l'opzione è abilitata nel profilo funzionalità per il punto vendita.  
5. Fare clic su Modifica.
6. Nel campo Gruppo predefinito, immettere o selezionare un valore.
7. Fare clic su Salva.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]