---
title: Risolvere le discrepanze durante l'abbinamento dei totali fatture
description: È possibile utilizzare l'abbinamento dei totali fatture per garantire che gli importi totali delle fatture non si discostino dagli importi previsti oltre un livello accettabile.
author: abruer
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63f4747c13d70d45404069a200124336d6f54947
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1512317"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching"></a>Risolvere le discrepanze durante l'abbinamento dei totali fatture

[!include [banner](../includes/banner.md)]

Un tipo di convalida dell'abbinamento fatture è l'abbinamento dei totali fatture. Per fare in modo che il sistema esegua l'abbinamento dei totali fatture, nella pagina **Parametri contabilità fornitori**, nella scheda **Convalida fattura**, impostare l'opzione **Abbina totali fatture** su **Sì**. 

È possibile utilizzare l'abbinamento dei totali fatture per garantire che gli importi totali delle fatture non si discostino dagli importi previsti oltre un livello accettabile. Nella pagina **Dettagli abbinamento totali fatture** vengono confrontati sei totali. Se uno qualsiasi dei totali devia dal corrispondente totale ordine acquisto previsto, viene segnalata una discrepanza di abbinamento. 

Per esaminare la fattura che presenta le discrepanze nell'abbinamento dei totali, nell'area di lavoro **Inserimento fatture fornitore** fare clic sul riquadro **Fatture in sospeso**. Successivamente, nel riquadro azioni, nella scheda **Revisione**, fare clic su **Dettagli abbinamento**. Se sono state rilevate discrepanze di abbinamento, accanto all'importo fattura vengono visualizzate delle icone di avviso. È possibile visualizzare ulteriori dettagli sui totali visualizzando i dettagli di abbinamento dei totali fatture. 

Dopo aver identificato la discrepanza, potrebbe essere necessario contattare il fornitore se si ritiene che le informazioni riportate nella fattura non siano corrette. A seconda dell'accordo risultante con il fornitore, sarà possibile effettuare una delle seguenti operazioni:

-   Accettare la differenza di prezzo e registrare la fattura che presenta discrepanze di abbinamento. È possibile che il sistema sia impostato in modo da richiedere l'approvazione prima della registrazione in presenza di discrepanze di abbinamento. In questo caso, è necessario approvare la discrepanza di abbinamento e facoltativamente si può scegliere di immettere un commento di approvazione. Successivamente si può scegliere di registrare la fattura.
-   Modificare l'importo della fattura in modo che corrisponda a quello previsto e registrare la fattura.
-   Richiedere al fornitore un credito totale e una nuova fattura corretta.

Per ulteriori informazioni, vedere [Cercare o risolvere eccezioni](tasks/research-resolve-exceptions.md).


