---
title: Contratti fornitore Retribuisci su retribuzione
description: "Questo articolo descrive le condizioni del metodo Retribuisci su retribuzione per i contratti fornitore. Le condizioni del metodo Retribuisci su retribuzione consentono di sospendere parzialmente o completamente il pagamento a un fornitore finché il cliente del progetto non paga. Questo articolo fornisce anche un esempio reale per mostrare come utilizzare le condizioni di tale metodo per un progetto."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectsListPage
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23131
ms.assetid: 20bf1d7f-8813-4c69-9cd7-576884a7e169
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7b21d4e93ec22715d530b75f75f3ba475e561f62
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="pay-when-paid-vendor-agreements"></a>Contratti fornitore Retribuisci su retribuzione

[!include[banner](../includes/banner.md)]


Questo articolo descrive le condizioni del metodo Retribuisci su retribuzione per i contratti fornitore. Le condizioni del metodo Retribuisci su retribuzione consentono di sospendere parzialmente o completamente il pagamento a un fornitore finché il cliente del progetto non paga. Questo articolo fornisce anche un esempio reale per mostrare come utilizzare le condizioni di tale metodo per un progetto.

Quando si approva un fornitore per lavorare su un progetto come terzista, è possibile trattenere il pagamento al fornitore o al terzista fino a che non si viene pagati dal cliente per il progetto. Per trattenere il pagamento a un fornitore vengono impostati i termini dell'opzione Retribuisci su retribuzione quando si imposta un ordine fornitore con il fornitore. Quando si crea un ordine fornitore per il fornitore e si assegna un ID progetto all'ordine fornitore, i termini dell'opzione Retribuisci su retribuzione vengono associati all'ordine fornitore e al fornitore. Nella pagina **Fatture fornitore con Retribuisci su retribuzione** è possibile visualizzare un elenco di fatture fornitore non pagate per un ordine fornitore e le fatture cliente associate. Utilizzare questo modulo per determinare se e quanto pagare un fornitore. Ad esempio, quando un cliente paga un importo di una fattura di progetto, è possibile rilasciare parte o tutte le fatture fornitore correlate per il pagamento. È possibile impostare le condizioni di Retribuisci su retribuzione per specificare che un fornitore venga pagato dopo aver ricevuto una percentuale specifica del pagamento correlato da un cliente. Quando si riceve il pagamento parziale da un cliente, è possibile rilasciare manualmente alcune fatture fornitore correlate per il pagamento. Nell'esempio riportato di seguito viene illustrato come è possibile utilizzare i termini dell'opzione Retribuisci su retribuzione per trattenere il pagamento a un fornitore o al terzista fino a che non si viene pagati dal cliente. L'organizzazione stipula un contratto con un cliente per fornire 100 computer in cui viene installato il software richiesto dal cliente. Il prezzo concordato con il cliente è pari a 150,00 per ogni computer. Vengono richiesti i servizi di un fornitore di terze parti per fornire i computer all'utente. Il cliente desidera approvare la qualità dei computer prima che l'organizzazione venga pagata. I criteri dell'organizzazione prevedono il trattenimento del pagamento a un fornitore di terze parti fino a quando non si viene pagati dal cliente per un progetto. Di conseguenza, impostare il progetto con una percentuale di Retribuisci su retribuzione del 100%, in modo che vangano trattenuti tutti i pagamenti al fornitore finché non si riceve il pagamento completo della fattura cliente. Il fornitore addebita 100,00 per ogni computer. Quando il fornitore invia i computer, la spedizione include una fattura di 10.000,00 per 100 computer. Poiché il progetto è stato impostato con i termini dell'opzione Retribuisci su retribuzione, non pagare il fornitore. Dopo aver ricevuto i computer dal fornitore, installare il software richiesto sui computer. Quando si inviano i computer al cliente, viene inviata al cliente anche una fattura di 15.000,00. Il cliente controlla i computer e approva la qualità il prodotto. Il cliente paga quindi all'organizzazione l'intero importo della fattura di progetto. Dopo aver ricevuto il pagamento completo dal cliente, pagare al fornitore l'intero importo della fattura fornitore, 10.000,00.




