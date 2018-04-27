--- 
title: Impostare un metodo di pagamento per addebito diretto ISO20022
description: In questa procedura viene illustrato come impostare il metodo di pagamento del cliente per addebito diretto ISO20022 o qualsiasi altro tipo di pagamento mediante la creazione di report elettronici.
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 3a884837ab0b5a1f4211532969619b54206bbef4
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-method-of-payment-for-iso20022-direct-debit"></a>Impostare un metodo di pagamento per addebito diretto ISO20022

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come impostare il metodo di pagamento del cliente per addebito diretto ISO20022 o qualsiasi altro tipo di pagamento mediante la creazione di report elettronici. 



Prima di completare l'attività, è necessario impostare le configurazioni del formato di esportazione e i conti di pagamento.



Questa procedura è stata creata utilizzando la società di dati dimostrativi DEMF.



Si tratta della terza di cinque procedure che illustrano il processo di pagamento cliente utilizzando le configurazioni di creazione di report elettronici.

1. Andare a Contabilità clienti > Impostazione pagamenti > Metodi di pagamento.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, applicare un filtro al campo Metodo di pagamento in base al valore di pagamento elettronico.
3. Fare clic su Modifica.
4. Nel campo Conto pagamenti specificare i valori "DEMF OPER".
5. Espandere la sezione Formati file.
6. Selezionare Sì nel campo Report elettronici generici.
7. Nel campo Esporta configurazione formato immettere o selezionare un valore.
    * Nell'elenco selezionare Addebito diretto ISO20022 (DE).  Se l'elenco è vuoto, significa che la configurazione del formato di esportazione dei pagamenti cliente non è importata e attiva.  
8. Selezionare Sì nel campo Richiedi mandato.
    * Selezionare il parametro Richiedi mandato per i formati di pagamento cliente, che richiedono di includere le informazioni sul mandato nel messaggio di pagamento, come addebito diretto SEPA.  
9. Fare clic su Salva.


