---
title: " Rettifiche prezzi di vendita al dettaglio"
description: In questa procedura vengono descritti i passaggi per creare una rettifica prezzo di commercio.
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
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7443f69473c0aad478d47f80f284b1156bad9c24
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962987"
---
# <a name="retail-price-adjustments"></a> Rettifiche prezzi di vendita al dettaglio

[!include [banner](../includes/banner.md)]

In questa procedura vengono descritti i passaggi per creare una rettifica prezzo di commercio. Con una rettifica prezzo si può impostare direttamente il prezzo di vendita di un articolo o modificare il prezzo di vendita di base o il prezzo di vendita dell'accordo commerciale. Questa procedura utilizza la società di dati dimostrativi USRT.

1. Fare clic su Gestione prezzi e sconti.
2. Fare clic sulla scheda Rettifiche prezzi.
3. Fare clic su Nuovo.
    * A questo punto è possibile creare tutte le regole di sconto e di prezzo più utilizzate, incluse le regole di sconti, rettifiche di prezzo, giornali di registrazione accordi commerciali e prezzi di categoria.  
4. Fare clic su Rettifica prezzo.
5. Digitare un valore nel campo Nome.
6. Espandere la sezione Righe.
7. Scegliere Aggiungi.
    * Per questo esempio, immettere '81126' nel campo Prodotto. Poi, nel campo Percentuale sconto, immettere '10,0'.  
    * Una rettifica prezzo di tipo di percentuale sconto riduce il prezzo di vendita di base o il prezzo di vendita dell'accordo commerciale.  
8. Scegliere Aggiungi.
    * Per questo esempio, immettere '81125' nel campo Prodotto. Quindi, selezionare 'Importo sconto di cassa' nel campo Metodo di sconto.    Infine, impostare '5,0' nel campo Importo sconto di cassa.  
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]