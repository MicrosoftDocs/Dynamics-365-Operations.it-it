---
title: Riconciliare le spese di trasporto nella gestione del trasporto
description: In questo articolo viene descritto il processo di riconciliazione delle spese di trasporto.
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: ab7d21d7a75e2c954831a254bb339d9cf5746d9d
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017


---

# <a name="reconcile-freight-in-transportation-management"></a>Riconciliare le spese di trasporto nella gestione del trasporto

[!include[banner](../includes/banner.md)]


In questo articolo viene descritto il processo di riconciliazione delle spese di trasporto.

La riconciliazione delle spese di trasporto può essere eseguita manualmente oppure è possibile impostarla affinché venga eseguita automaticamente. Per utilizzare riconciliazione automatica di spese di trasporto, è necessario impostare un master di controllo in cui è possibile definire i criteri che determinano quali fatture di trasporto vengono associate automaticamente.

## <a name="the-freight-reconciliation-process"></a>Processo di riconciliazione spese di trasporto
Le tariffe di trasporto vengono calcolate dal motore tariffe associato con il vettore di spedizione pertinente. Quando un carico viene confermato, viene generata una fattura di trasporto e le tariffe di trasporto vengono trasferite ad essa. Le tariffe di trasporto vengono ripartite come spese varie nel documento di origine pertinente (ordine fornitore, ordine cliente e/o ordine di trasferimento), a seconda dell'impostazione utilizzata per il normale processo di fatturazione. Il processo di riconciliazione delle spese di trasporto (che è noto anche come il processo di abbinamento) può iniziare non appena arriva la fattura di trasporto dal vettore di spedizione. La fattura può essere ricevuta elettronicamente o su carta. Se si riceve la fattura su carta, è possibile generare una fattura elettronica utilizzando la fattura di trasporto come modello. 

[![Processo di riconciliazione spese di trasporto](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Riconciliazione manuale
Se si riconciliano manualmente le spese di trasporto, è necessario abbinare ogni riga della fattura con la riga o le righe della fattura di trasporto del carico da fatturare. A tale scopo, abbinare nella pagina **Abbinamento fatture di trasporto e fatture**. Se l'importo nella riga della fattura non corrisponde all'importo della fattura di trasporto, è necessario selezionare un motivo di riconciliazione per la differenza. Se esistono diversi motivi per la riconciliazione, è possibile ripartire sui vari motivi l'importo non abbinato. Il motivo di riconciliazione determina la modalità di registrazione degli importi di differenza nella contabilità generale. Quando la riconciliazione dell'importo della fattura intera è contabilizzata, viene inviata per l'approvazione e quindi la registrazione. Nell'illustrazione che segue viene mostrato come generare una fattura di trasporto ed eseguire la riconciliazione delle spese di trasporto in Microsoft Dynamics 365 for Finance and Operations. 
[![Attività di riconciliazione delle spese di trasporto in Dynamics AX](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)
## <a name="automatic-reconciliation"></a>Riconciliazione automatica
Per utilizzare la riconciliazione automatica, è necessario specificare la programmazione per la riconciliazione e le fatture e i vettori di spedizione da utilizzare. L'abbinamento delle righe di fattura e delle fatture di trasporto viene effettuato in base all'impostazione del tipo di controllo master e di fattura di trasporto. Dopo aver eseguito la riconciliazione automatica, è necessario gestire tutte le fatture che il sistema non riesce ad abbinare. È quindi necessario elaborare queste fatture manualmente prima di poter registrare tutte le fatture per il pagamento.




