---
title: Panoramica dei ratei
description: Questo argomento descrive i ratei e fornisce informazioni su come impostarli e su come creare le transazioni.
author: aprilolson
ms.date: 01/11/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "14131"
- intro-internal
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62b56e698d3d9eeec08824eb799d74a8c6792ea7
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735234"
---
# <a name="accruals-overview"></a>Panoramica dei ratei

[!include [banner](../includes/banner.md)]

Questo argomento descrive i ratei e fornisce informazioni su come impostarli e su come creare le transazioni.

I ratei vengono utilizzati nella contabilità per competenza per tenere traccia dei ricavi riconosciuti nel periodo in cui vengono incassati, non quando il pagamento viene ricevuto, e per tenere traccia delle spese (costi) riconosciute quando si verificano, non quando viene effettuato il pagamento.

## <a name="accrual-schemes"></a>Schemi di attribuzione per competenza
Gli schemi di attribuzione per competenza vengono utilizzati per impostare i ricavi e i costi posticipati e lo stesso schema di attribuzione per competenza può essere utilizzato per i ricavi e per i costi. I ratei nella contabilità generale consentono di ridistribuire i costi o i ricavi di una riga del giornale di registrazione in modo che i costi e i ricavi vengano riconosciuti nei periodi appropriati. Nella pagina **Schema di attribuzione per competenza**, si specificano i conti per gli importi dare e avere che verranno utilizzati quando lo schema di attribuzione per competenza viene applicato.

-   **Dare** - Il conto principale definito sostituirà il conto principale per gli importi dare nella riga del giustificativo del giornale di registrazione. Questo conto verrà utilizzato anche per lo storno dell'operazione posticipata, in base alle transazioni di attribuzione per competenza nella contabilità generale.
-   **Avere** - Il conto principale definito sostituirà il conto principale per gli importi avere nella riga del giustificativo del giornale di registrazione. Questo conto verrà utilizzato anche per lo storno dell'operazione posticipata, in base alle transazioni di attribuzione per competenza nella contabilità generale.

Dopo aver determinato quali conti utilizzare, è possibile specificare la modalità di creazione del numero di giustificativo quando le transazioni di attribuzione per competenza vengono create. È inoltre possibile specificare la frequenza con cui le transazioni si verificano, il numero di volte in cui le transazioni vengono create e quando le transazioni vengono registrate. Una volta creato lo schema di attribuzione per competenza, è possibile utilizzarlo in alcuni dei giornali di registrazione tramite la funzione Ratei in contabilità generale.

## <a name="ledger-accruals"></a>Ratei in contabilità generale
Quando si immette un giornale di registrazione, è possibile fare clic su **Ratei in contabilità generale** sul menu **Funzioni**. Quindi, quando si seleziona lo schema di attribuzione per competenza, verrà visualizzato l'imponibile dal giornale di registrazione che verrà distribuito sul periodo, come determinato dallo schema di attribuzione per competenza. Ad esempio, se si paga l'assicurazione di un dipendente per l'intero anno a gennaio e l'importo è 12.000, è necessario riconoscere tale spesa ogni mese. È possibile selezionare la data di inizio. È inoltre possibile specificare se l'importo attribuito è basato sul conto o sul conto di contropartita. Dopo aver fatto le selezioni, fare clic su **Transazioni** per visualizzare tutte le transazioni create in base allo schema di attribuzione per competenza. Ad esempio, se si distribuiscono i 12.000 delle spese di assicurazione nel corso dell'anno, si vedrà 1.000 per ogni mese. Dopo la registrazione del giornale di registrazione, è possibile visualizzare le transazioni utilizzando la pagina di richiesta informazioni **Transazioni giustificativo**. Se uno schema di attribuzione per competenza non può essere applicato (ad esempio, nel caso di una fattura di ordine cliente o una fattura di ordine fornitore), è possibile accreditare l'importo pagato anticipatamente e addebitare l'importo della spesa. È possibile quindi selezionare **Contropartita** quando si applica lo schema di attribuzione per competenza.


Per ulteriori informazioni, vedere [Creare schemi di attribuzione per competenza](tasks/create-accrual-schemes.md) e [Creare transazioni di attribuzione per competenza in contabilità generale](tasks/create-ledger-accrual-transactions.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
