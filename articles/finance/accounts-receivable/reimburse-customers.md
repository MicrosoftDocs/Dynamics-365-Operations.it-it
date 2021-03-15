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
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae6a3078743fc9cd43c71bc1d4531c0553ee53bb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012141"
---
# <a name="reimburse-customers"></a>Rimborsare i clienti

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come creare transazioni di rimborso per un gruppo di clienti. Se un cliente dispone di un saldo in Avere, è possibile rimborsare il cliente per l'importo del saldo. 

Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.

| Prerequisito                                                            | Descrizione |
|-------------------------------------------------------------------------|-------------|
| Specificare l'importo minimo di rimborso per la persona giuridica.          | Nella pagina **Parametri contabilità clienti**, nell'area **Generale**, nel campo **Rimborso minimo**, immettere l'importo minimo rimborsabile per le eccedenze di pagamento del cliente. |
| Facoltativo: aggiungere un conto fornitore a ciascun cliente che può essere rimborsato. | Nella pagina **Clienti**, nella scheda dettaglio **Dettagli vari**, nel campo **Conto fornitore**, selezionare il conto fornitore per il cliente. |

Quando si creano le transazioni di rimborso, viene creata una fattura fornitore per l'importo del saldo in Avere. Il processo di rimborso rimuove il saldo in Avere per il conto cliente e crea un saldo esigibile per il conto fornitore corrispondente al cliente.

1. In Contabilità clienti, esegui il processo **Rimborso** (**Contabilità clienti \> Attività periodiche \> Rimborso**).
2. Per raggruppare tutte le transazioni, indipendentemente dalle dimensioni del libro mastro, imposta l'opzione **Riepiloga cliente** su **Sì**. Per raggruppare solo transazioni con dimensioni contabili simili, imposta l'opzione su **No**.
3. Seleziona **Includi clienti con transazioni di addebito in sospeso** per selezionare i clienti che hanno importi di addebito non liquidati.
4. Per rimborsare conti di clienti specifici, nella scheda dettaglio **Record da includere**, elezionare **Filtro** e quindi specificare i conti del cliente nella query.

    Gli importi in Avere verranno trasferiti nei conti fornitore dei clienti ed elaborati come normali pagamenti. Se un cliente non dispone di conto fornitore, verrà creato automaticamente un conto fornitore occasionale per il cliente.

5. Per visualizzare le transazioni di rimborso create, utilizza il report **Rimborso** (**Contabilità clienti \> Richieste di informazioni e report \> Report di rimborso**).
6. In Contabilità fornitori, creare un pagamento per le fatture fornitore create dal processo di rimborso. Per informazioni su come pagare i fornitori, vedi [Panoramica dei pagamenti del fornitore](../accounts-payable/Vendor-payments-workspace.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]