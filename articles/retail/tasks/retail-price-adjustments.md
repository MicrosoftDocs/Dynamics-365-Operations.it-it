---
title: " Rettifiche prezzi di vendita al dettaglio"
description: In questa procedura vengono descritti i passaggi per creare una rettifica prezzo di vendita al dettaglio.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailDiscountPriceGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9427d3955e5442e301c416e2960e071ca5d85a3c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550023"
---
# <a name="retail-price-adjustments"></a> Rettifiche prezzi di vendita al dettaglio

[!include[task guide banner](../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per creare una rettifica prezzo di vendita al dettaglio. Con una rettifica prezzo di vendita al dettaglio si può impostare direttamente il prezzo di vendita di un articolo o modificare il prezzo di vendita di base o il prezzo di vendita dell'accordo commerciale. Questa procedura utilizza la società di dati dimostrativi USRT.

1. Fare clic su Gestione prezzi e sconti.
2. Fare clic sulla scheda Rettifiche prezzi.
3. Fare clic su Nuovo.
    * A questo punto è possibile creare tutte le regole di sconto e di prezzo più utilizzate, incluse le regole di sconti vendita al dettaglio, rettifiche di prezzo, giornali di registrazione accordi commerciali e prezzi di categoria.  
4. Fare clic su Rettifica prezzo.
5. Digitare un valore nel campo Nome.
6. Espandere la sezione Righe.
7. Scegliere Aggiungi.
    * Per questo esempio, immettere '81126' nel campo Prodotto.    Poi, nel campo Percentuale sconto, immettere '10,0'.  
    * Una rettifica prezzo di tipo di percentuale sconto riduce il prezzo di vendita di base o il prezzo di vendita dell'accordo commerciale.  
8. Scegliere Aggiungi.
    * Per questo esempio, immettere '81125' nel campo Prodotto.    Quindi, selezionare 'Importo sconto di cassa' nel campo Metodo di sconto.    Infine, impostare '5,0' nel campo Importo sconto di cassa.  
    * Il tipo di sconto Importo sconto di cassa è un importo detratto dal prezzo di base o dal prezzo dell'accordo commerciale.  
9. Fare clic su Gruppi di prezzi.
    * Selezionare 'RP-Houston' nel campo Gruppo di prezzi.  
    * In tal modo la rettifica prezzo viene associata al punto vendita Houston.  
10. Fare clic su Salva.
11. Chiudere la pagina.
12. Nel campo Stato, selezionare 'Abilitato'.
13. Fare clic su Salva.
14. Chiudere la pagina.
15. Aggiorna la pagina.

