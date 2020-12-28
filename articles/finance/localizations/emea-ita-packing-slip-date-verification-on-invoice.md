---
title: Verifica della data del documento di trasporto nelle fatture per l'Italia
description: Per l'Italia, la data della fattura è verificata sui documenti di trasporto e sulle proposte di fatturazione. In questo argomento vengono fornite informazioni aggiuntive sulla verifica eseguita.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPackingSlipJournal
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 263824
ms.search.region: Italy
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 549f5a93224ba64781676bc1239254e708fabafa
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408115"
---
# <a name="packing-slip-date-verification-on-invoices-for-italy"></a>Verifica della data del documento di trasporto nelle fatture per l'Italia

[!include [banner](../includes/banner.md)]

Per l'Italia, la data della fattura è verificata sui documenti di trasporto e sulle proposte di fatturazione. In questo argomento vengono fornite informazioni aggiuntive sulla verifica eseguita. 

Per le persone giuridiche il cui indirizzo principale è in Italia è presente un passaggio di verifica della data documento di trasporto per gli utenti che generano fatture di vendita o fatture progetto.

-   I documenti di trasporto che hanno data successiva alla fattura non devono essere inclusi nella quantità di aggiornamento consigliata.
-   Per Gestione progetti e contabilità, quando si crea una proposta di fatturazione, solo i documenti di trasporto del cliente datati anteriore alla proposta di fatturazione vengono inclusi nella proposta. **Nota**: Se la data di input utente per la proposta di fatturazione è vuota, la data di sistema viene utilizzata.




