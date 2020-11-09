---
title: Rimborsare i clienti
description: In questo articolo viene illustrato come creare transazioni di rimborso per un gruppo di clienti. Se un cliente dispone di un saldo in Avere, è possibile rimborsare il cliente per l'importo del saldo.
author: JodiChristiansen
manager: AnnBe
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bceeaf99437f6ef66bd3b4e1710b469c262e693e
ms.sourcegitcommit: 9e7ceb5604472f3088f611aa0360bd6a716db32b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4022545"
---
# <a name="reimburse-customers"></a>Rimborsare i clienti

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come creare transazioni di rimborso per un gruppo di clienti. Se un cliente dispone di un saldo in Avere, è possibile rimborsare il cliente per l'importo del saldo. 

Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.

| Prerequisito                                                            | Descrizione                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Specificare l'importo minimo di rimborso per la persona giuridica.          | Nella pagina **Parametri contabilità clienti** , nell'area **Generale** , nel campo **Rimborso minimo** , immettere l'importo minimo rimborsabile per le eccedenze di pagamento del cliente. |
| Facoltativo: aggiungere un conto fornitore a ciascun cliente che può essere rimborsato. | Nella pagina **Clienti** , nella scheda dettaglio **Dettagli vari** , nel campo **Conto fornitore** , selezionare il conto fornitore per il cliente.                                           |

Quando si creano le transazioni di rimborso, viene creata una fattura fornitore per l'importo del saldo in Avere. Il processo di rimborso rimuove il saldo in Avere per il conto cliente e crea un saldo esigibile per il conto fornitore corrispondente al cliente.

1.  In Contabilità clienti, eseguire il processo **Rimborso**.
2.  Eseguire uno dei passaggi riportati di seguito.
    -   Per effettuare il rimborso su specifici conti cliente, fare clic su **Seleziona** , quindi specificare i conti cliente nella query.
    -   Per effettuare il rimborso su tutti i conti cliente, scegliere **OK**.

    Gli importi in Avere verranno trasferiti nei conti fornitore dei clienti ed elaborati come normali pagamenti. Se un cliente non dispone di conto fornitore, verrà creato automaticamente un conto fornitore occasionale per il cliente.
3.  Per visualizzare le transazioni di rimborso create, utilizzare la pagina **Rimborso**.
4.  In Contabilità fornitori, creare un pagamento per le fatture fornitore create dal processo di rimborso.




