---
title: Panoramica della risoluzione delle discrepanze durante l'abbinamento dei totali fatture
description: È possibile utilizzare l'abbinamento dei totali fatture per garantire che gli importi totali delle fatture non si discostino dagli importi previsti oltre un livello accettabile.
author: abruer
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 63413,  ""intro-internal
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.form: VendTotalPriceTolerance
ms.openlocfilehash: fa248622a21b0571b08c97eff507ee1035daa7f9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268589"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching-overview"></a>Panoramica della risoluzione delle discrepanze durante l'abbinamento dei totali fatture

[!include [banner](../includes/banner.md)]

Un tipo di convalida dell'abbinamento fatture è l'abbinamento dei totali fatture. Per fare in modo che il sistema esegua l'abbinamento dei totali fatture, nella pagina **Parametri contabilità fornitori**, nella scheda **Convalida fattura**, impostare l'opzione **Abbina totali fatture** su **Sì**. 

È possibile utilizzare l'abbinamento dei totali fatture per garantire che gli importi totali delle fatture non si discostino dagli importi previsti oltre un livello accettabile. Nella pagina **Dettagli abbinamento totali fatture** vengono confrontati sei totali. Se uno qualsiasi dei totali devia dal corrispondente totale ordine acquisto previsto, viene segnalata una discrepanza di abbinamento. 

Per esaminare la fattura che presenta le discrepanze nell'abbinamento dei totali, nell'area di lavoro **Inserimento fatture fornitore** fare clic sul riquadro **Fatture in sospeso**. Successivamente, nel riquadro azioni, nella scheda **Revisione**, fare clic su **Dettagli abbinamento**. Se sono state rilevate discrepanze di abbinamento, accanto all'importo fattura vengono visualizzate delle icone di avviso. È possibile visualizzare ulteriori dettagli sui totali visualizzando i dettagli di abbinamento dei totali fatture. 

Dopo aver identificato la discrepanza, potrebbe essere necessario contattare il fornitore se si ritiene che le informazioni riportate nella fattura non siano corrette. A seconda dell'accordo risultante con il fornitore, sarà possibile effettuare una delle seguenti operazioni:

-   Accettare la differenza di prezzo e registrare la fattura che presenta discrepanze di abbinamento. È possibile che il sistema sia impostato in modo da richiedere l'approvazione prima della registrazione in presenza di discrepanze di abbinamento. In questo caso, è necessario approvare la discrepanza di abbinamento e facoltativamente si può scegliere di immettere un commento di approvazione. Successivamente si può scegliere di registrare la fattura.
-   Modificare l'importo della fattura in modo che corrisponda a quello previsto e registrare la fattura.
-   Richiedere al fornitore un credito totale e una nuova fattura corretta.

Per ulteriori informazioni, vedere [Cercare/Risolvere eccezioni](tasks/research-resolve-exceptions.md).




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
