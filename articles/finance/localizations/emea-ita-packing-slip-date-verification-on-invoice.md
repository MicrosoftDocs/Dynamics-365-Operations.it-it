---
title: Verifica della data del documento di trasporto nelle fatture per l'Italia
description: Per l'Italia, la data della fattura è verificata sui documenti di trasporto e sulle proposte di fatturazione. In questo articolo vengono fornite informazioni aggiuntive sulla verifica eseguita.
author: AdamTrukawka
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 263824
ms.search.form: CustPackingSlipJournal
ms.openlocfilehash: ac6bf37b0e5a7d32836fa4c43d6e95242f8639ff
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292267"
---
# <a name="packing-slip-date-verification-on-invoices-for-italy"></a>Verifica della data del documento di trasporto nelle fatture per l'Italia

[!include [banner](../includes/banner.md)]

Per l'Italia, la data della fattura è verificata sui documenti di trasporto e sulle proposte di fatturazione. In questo articolo vengono fornite informazioni aggiuntive sulla verifica eseguita. 

Per le persone giuridiche il cui indirizzo principale è in Italia è presente un passaggio di verifica della data documento di trasporto per gli utenti che generano fatture di vendita o fatture progetto.

-   I documenti di trasporto che hanno data successiva alla fattura non devono essere inclusi nella quantità di aggiornamento consigliata.
-   Per Gestione progetti e contabilità, quando si crea una proposta di fatturazione, solo i documenti di trasporto del cliente datati anteriore alla proposta di fatturazione vengono inclusi nella proposta. **Nota**: Se la data di input utente per la proposta di fatturazione è vuota, la data di sistema viene utilizzata.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
