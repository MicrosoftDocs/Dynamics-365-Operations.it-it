---
title: Impostare un metodo di pagamento per bonifico ISO20022
description: In questa procedura viene illustrato come impostare il metodo di pagamento del fornitore per bonifico ISO20022 o qualsiasi altro tipo di pagamento mediante la creazione di report elettronici per generare un file.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 643be31db625d0db12f1df18b9e797013da98ece
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832474"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a>Impostare un metodo di pagamento per bonifico ISO20022

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come impostare il metodo di pagamento del fornitore per bonifico ISO20022 o qualsiasi altro tipo di pagamento mediante la creazione di report elettronici per generare un file. 

Prima di completare l'attività, è necessario esportare le configurazioni del formato impostare i conti di pagamento.

Questa attività è stata creata utilizzando la società di dati dimostrativi DEMF.

Si tratta della terza procedura di cinque, che illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.

1. Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, applicare un filtro al campo Metodo di pagamento in base al valore "SEPA CT".
3. Fare clic su Modifica.
4. Nel campo Periodo selezionare "Totale".
5. Nel campo Tipo di pagamento selezionare "Pagamento elettronico".
6. Espandere la sezione Formati file.
7. Selezionare Sì nel campo Report elettronici generici.
8. Nel campo Esporta configurazione formato immettere o selezionare un valore.
    * Nell'elenco selezionare il valore di bonifico ISO20022 (DE). Se l'elenco è vuoto, significa che la configurazione del formato di esportazione dei pagamenti fornitore non è importata e attiva.  
9. Nel campo Tipo di conto selezionare "Banca".
10. Nel campo Conto pagamenti specificare i valori "DEMF OPER".
11. Fare clic su Salva.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]