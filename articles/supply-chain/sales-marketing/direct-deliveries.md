---
title: Consegne dirette
description: Vengono fornite le informazioni sulle consegne dirette, ovvero le consegne di articoli direttamente dal fornitore al cliente.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchCreateFromSalesOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 9704
ms.assetid: 64c51384-8a4e-45d0-83c1-12cea22902f9
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4550270e87121db4012c273b63576db113a2fbf1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998530"
---
# <a name="direct-deliveries"></a>Consegne dirette

[!include [banner](../includes/banner.md)]

Vengono fornite le informazioni sulle consegne dirette, ovvero le consegne di articoli direttamente dal fornitore al cliente.

Le consegne dirette consentono di ridurre i tempi e i costi associati alla gestione del magazzino, dato che i prodotti non vengono trattenuti nel magazzino prima della spedizione al cliente.  

Dalla pagina **Ordine cliente** è possibile creare consegne dirette. Creare innanzitutto un ordine cliente e le righe ordine. Nella scheda **Ordine cliente** del Riquadro azioni selezionare quindi **Consegna diretta**. Specificare infine le righe da gestire come consegna diretta. Verrà creato un collegamento tra le righe ordine cliente per la consegna diretta e le righe ordine fornitore corrispondenti.  

**Nota:** se una parte della quantità ordinata è già stata consegnata, è necessario dividere la quantità rimanente. Creare una nuova riga per la quantità che deve essere consegnata direttamente e sottrarre tale quantità dalla quantità sulla riga originale. Ad esempio, se la quantità originale è 15 e cinque sono stati consegnati, è necessario creare una nuova riga per la quantità rimanente di 10 e quindi ridurre la quantità originale in base a tale quantità.  

Dopo aver creato il collegamento di consegna diretta tra le righe dell'ordine cliente e quelle dell'ordine fornitore, è possibile aggiornare l'ordine cliente utilizzando un documento di trasporto. Eseguire un aggiornamento del documento di trasporto o della fattura dall'ordine fornitore. È necessario aggiornare la fattura dell'ordine cliente nella pagina **Ordine cliente**. Non è possibile aggiornare una fattura in modo che abbia la quantità dell'ordine cliente superiore rispetto a quella registrata come ricevuta. Si supponga, ad esempio, che una riga ordine cliente abbia 10 pezzi, ma che solo cinque pezzi siano stati aggiornati utilizzando un documento di trasporto. Se si seleziona **Tutto** nell'elenco **Quantità** quando si esegue l'aggiornamento della fattura dell'ordine cliente, viene aggiornata la fattura solo per gli articoli ricevuti fisicamente o aggiornati tramite un documento di trasporto. Non viene aggiornata l'intera riga ordine cliente.

## <a name="delivery-date"></a>Data di consegna
Quando si aggiorna il campo **Data di ricevimento richiesta** nella riga dell'ordine cliente, anche il campo **Data di consegna** nella riga dell'ordine fornitore corrispondente viene aggiornato di conseguenza. In modo analogo, quando si aggiorna il campo **Confermata** nella riga ordine fornitore, vengono aggiornati anche i campi **Data di entrata confermata** e **Data di spedizione confermata** nella riga ordine cliente corrispondente.

## <a name="delivery-address"></a>Indirizzo di consegna
In genere, l'indirizzo di consegna per un ordine fornitore corrisponde all'indirizzo della società. Tuttavia, quando si crea una consegna diretta, l'indirizzo di consegna viene immesso come indirizzo del cliente. Se si modifica l'indirizzo di consegna per una riga ordine fornitore di tipo **Consegna diretta**, verrà aggiornato anche l'indirizzo di consegna per la riga ordine cliente corrispondente. Analogamente, se si modifica l'indirizzo di consegna nella riga ordine cliente, verrà aggiornato anche l'indirizzo di consegna nella riga ordine fornitore.

## <a name="deleting-order-lines"></a>Eliminazione di righe ordine
Se si tenta di eliminare una riga ordine cliente di tipo **Consegna diretta**, verrà visualizzato un messaggio per indicare che alla riga in questione sono collegate righe ordine fornitore. Se la riga ordine cliente è stata parzialmente consegnata, non sarà possibile eliminare tale riga né le righe ordine fornitore collegate.

## <a name="warehouse"></a>Magazzino
Quando si crea una consegna diretta, gli articoli venduti non arrivano mai nel proprio magazzino. Tuttavia, è necessario specificare un magazzino nella riga ordine cliente. In modo analogo, è possibile specificare i requisiti per il prelievo nel gruppo di modelli di articoli per l'articolo. Tuttavia, poiché gli articoli non arrivano mai fisicamente nel magazzino, tali requisiti vengono ignorati quando l'ordine cliente è una consegna diretta.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]