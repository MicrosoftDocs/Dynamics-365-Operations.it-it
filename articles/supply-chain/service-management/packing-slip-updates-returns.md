---
title: Aggiornamenti dei documenti di trasporto per i resi
description: Affinché i resi possano essere ricevuti nel magazzino, è necessario aggiornare il documento di trasporto relativo all'ordine a cui essi si riferiscono.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c82e43beddb8bae0a56b0894ce484ca7605b42e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006718"
---
# <a name="packing-slip-updates-for-returns"></a>Aggiornamenti dei documenti di trasporto per i resi  

[!include [banner](../includes/banner.md)]


Affinché i resi possano essere ricevuti nel magazzino, è necessario aggiornare il documento di trasporto relativo all'ordine a cui essi si riferiscono. Come il processo di aggiornamento della fattura rappresenta l'aggiornamento per la transazione finanziaria, il processo di aggiornamento del documento di trasporto rappresenta l'aggiornamento fisico del record di magazzino. In altre parole, consente di eseguire il commit delle modifiche nel magazzino. Nel caso dei resi, i passaggi assegnati all'azione di smaltimento vengono implementati durante l'aggiornamento del documento di trasporto.

L'aggiornamento del documento di trasporto può essere elaborato nel giornale di registrazione arrivi articoli o nell'ordine di reso.

Durante il processo di registrazione del documento di trasporto, è possibile associare il numero di riferimento del documento di trasporto indicato nei documenti di spedizione del cliente alle righe dell'ordine. Questa associazione facoltativa serve solo a scopo di riferimento e non comporta l'esecuzione di aggiornamenti transazionali.

Se non sono arrivati tutti i resi previsti, includere solo la quantità ricevuta nell'aggiornamento del documento di trasporto e lasciare gli articoli rimanenti nell'ordine fino a quando non arriverà la restante parte della spedizione dei resi.

Se un articolo viene rinviato dalla quarantena al reparto addetto alle spedizioni e ai ricevimenti, ad esempio quando l'addetto alle ispezioni della quarantena non sa dove posizionare l'articolo nel magazzino, è necessario aggiornare il documento di trasporto corrispondente per registrare correttamente il codice smaltimento specificato a causa della quarantena ed eseguire un'azione appropriata.

Quando si aggiorna un documento di trasporto per un reso che deriva da un contratto di vendita, l'impegno del contratto di vendita per tale articolo viene aggiornato automaticamente per riflettere la modifica nella quantità o nell'importo. 

## <a name="see-also"></a>Vedere anche

[Eseguire aggiornamenti di fatture per i resi](perform-invoice-updates-for-returns.md)

  


