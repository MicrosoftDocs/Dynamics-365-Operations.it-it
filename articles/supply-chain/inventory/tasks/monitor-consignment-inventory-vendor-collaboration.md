---
title: Verificare l'inventario spedizione tramite la collaborazione fornitore
description: In questa procedura viene illustrato come utilizzare la collaborazione fornitore per visualizzare le informazioni sul livello scorte di un prodotto che è stato inserito in spedizione a un cliente.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0d194728805cd1eee741069538352b497867981
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571835"
---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Verificare l'inventario spedizione tramite la collaborazione fornitore

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come utilizzare la collaborazione fornitore per visualizzare le informazioni sul livello scorte di un prodotto che è stato inserito in spedizione a un cliente. È inoltre possibile monitorare il consumo delle scorte quando il cliente assume la proprietà dell'inventario. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="view-consumed-inventory"></a>Visualizzare l'inventario consumato
1. Andare a Collaborazione fornitore > Inventario spedizione > Prodotti entrati da inventario spedizione.
    * Nell'elenco verranno visualizzate le righe entrata prodotti generate quando la proprietà dell'inventario di spedizione è stata modificata dal fornitore al cliente. Può essere necessario scorrere a destra per visualizzare le quantità e altre informazioni. È possibile utilizzare le informazioni contenute in questo elenco per generare le fatture per il cliente. È inoltre possibile esportare i dati in Microsoft Excel.   
2. Fare clic su Visualizza ordine fornitore.
3. Espandere la sezione Dettagli riga.
    * La riga viene contrassegnata come Spedizione e la sezione di intestazione indica che l'ordine fornitore ha stato Ricevuto.  
4. Chiudere la pagina.

## <a name="view-on-hand-inventory"></a>Visualizzare le scorte disponibili
1. Andare a Collaborazione fornitore > Inventario spedizione > Inventario spedizione disponibile.
    * La pagina Inventario spedizione disponibile mostra le scorte di proprietà nel magazzino del cliente. È possibile visualizzare ulteriori dimensioni, ad esempio sito e magazzino, facendo clic sulla scheda Visualizza dimensioni.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]