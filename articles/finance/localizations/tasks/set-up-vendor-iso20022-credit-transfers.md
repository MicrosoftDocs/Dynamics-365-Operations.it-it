---
title: Impostare i fornitori e i conti bancari dei fornitori per i bonifici ISO20022
description: Questa procedura descrive come impostare le informazioni sul fornitore e sul conto bancario specifico del fornitore necessarie per la generazione del bonifico ISO20022 o di qualsiasi altro file di pagamento fornitore.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab8c52b9b457505c2cf2bfca46cb938e73c0142e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174922"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a>Impostare i fornitori e i conti bancari dei fornitori per i bonifici ISO20022

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura descrive come impostare le informazioni sul fornitore e sul conto bancario specifico del fornitore necessarie per la generazione del bonifico ISO20022 o di qualsiasi altro file di pagamento fornitore. 

La società di dati dimostrativi utilizzata per creare questa procedura è DEMF.
Si tratta della quarta procedura di cinque, che illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="set-up-bank-details"></a>Impostare i dettagli della banca
1. Andare a Contabilità fornitori > Fornitori > Tutti i fornitori.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, applicare un filtro al Conto fornitore in base al valore "DE-001".
3. Fare clic su DE-001 per aprire i dettagli del fornitore.
4. Nel riquadro azioni, fare clic su Fornitore.
5. Fare clic su Conti bancari.
6. Fare clic su Modifica.
    * Se non è disponibile alcun conto bancario, è necessario crearne uno nuovo.  
7. Nel campo Codice SWIFT digitare "COBADEFFXXX".
8. Nel campo IBAN digitare "DE36200400000628808808".
9. Chiudere la pagina.

## <a name="set-up-a-method-of-payment-for-the-vendor"></a>Impostare un metodo di pagamento per il fornitore
1. Fare clic su Modifica.
2. Espandere o comprimere la sezione Pagamento.
3. Nel campo Metodo fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco fare clic sul collegamento nella riga SEPA CT.
5. Fare clic su Salva.
