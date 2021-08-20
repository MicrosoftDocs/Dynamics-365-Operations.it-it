---
title: Creare nuovo ordine di rifornimento spedizione
description: In questo argomento viene illustrato come creare un ordine di rifornimento spedizione in cui è possibile tracciare la consegna prevista da un fornitore nell'inventario di spedizione.
author: sherry-zheng
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: chuzheng
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d18d0bcd5b12548aaf2c9f73afb9ab8766d3dd652bbb444fa7c643913e012b0c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759601"
---
# <a name="create-a-consignment-replenishment-order"></a>Creare nuovo ordine di rifornimento spedizione

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come creare un ordine di rifornimento spedizione in cui è possibile tracciare la consegna prevista da un fornitore nell'inventario di spedizione. Viene inoltre illustrato come registrare un'entrata prodotti in modo da registrare l'inventario di spedizione come scorte disponibili di proprietà del fornitore. Questa procedura viene in genere eseguita da un responsabile approvvigionamenti. È possibile utilizzare questa guida nella società di dati dimostrativi USMF. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.

## <a name="create-a-consignment-replenishment-order"></a>Creare nuovo ordine di rifornimento spedizione
1. Nel pannello di navigazione, andare a **Moduli > Approvvigionamento > Spedizione > Ordini di rifornimento spedizione**.
2. Selezionare **Nuovo**.
3. Nel campo **Conto fornitore**, selezionare il fornitore **US-104** (è necessario selezionare un fornitore che viene registrato come proprietario nella pagina **Proprietari inventario**). 
4. Selezionare **OK**.
5. Selezionare **Aggiungi riga**.
6. Nel campo **Numero articolo**, digitare `M9211CI` (è necessario selezionare un articolo impostato per l'inventario spedizione).
7. Nel campo **Quantità** immettere un numero.
8. Nel campo **Data di consegna richiesta** immettere una data. Le date di richiesta e conferma vengono utilizzate dal motore MRP per l'arrivo previsto delle merci.  
9. Immettere una data nel campo **Data di consegna confermata**.
10. Espandere la sezione **Dettagli riga**.
11. Selezionare la scheda **Dimensioni inventariali**.
12. Per visualizzare il proprietario nel campo **Proprietario dimensioni inventariali**, aggiornare la pagina. Il fornitore US-104 è ora elencato come proprietario.  

## <a name="check-the-inventory-transaction-status"></a>Controllare lo stato delle transazioni di inventario
1. Selezionare **Scorte**.
2. Selezionare **Transazioni**.
3. Nella riga desiderata, da notare che il campo **Entrata** è impostato su **Ordinato**.  
4. Chiudere la pagina.

## <a name="receive-items"></a>Ricevi articoli
1. Selezionare **Entrata prodotti**.
2. Digitare un valore nel campo **Entrata prodotti esterna**.
3. Nel campo **Quantità**, immettere un numero minore del numero riportato. 
4. Selezionare **OK**.

## <a name="check-the-on-hand-inventory"></a>Controllare le scorte disponibili.
1. Selezionare **Scorte**.
2. Seleziona **Disponibilità**.
3. Selezionare **Panoramica**. Gli articoli ricevuti come inventario di spedizione di proprietà del fornitore sono scorte disponibili. La quantità rimanente nell'ordine di rifornimento spedizione è indicata nel campo **Ordinata in totale**.  
4. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]