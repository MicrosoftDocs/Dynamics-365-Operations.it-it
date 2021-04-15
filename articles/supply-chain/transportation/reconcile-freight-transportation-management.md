---
title: Riconciliare le spese di trasporto nella gestione del trasporto
description: In questo argomento viene descritto il processo di riconciliazione delle spese di trasporto.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d523af235d645bd282af07d6a1f617bca5fba2dc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809088"
---
# <a name="reconcile-freight-in-transportation-management"></a>Riconciliare le spese di trasporto nella gestione del trasporto

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto il processo di riconciliazione delle spese di trasporto.

La riconciliazione delle spese di trasporto può essere eseguita manualmente oppure è possibile impostarla affinché venga eseguita automaticamente. Per utilizzare riconciliazione automatica di spese di trasporto, è necessario impostare un master di controllo in cui è possibile definire i criteri che determinano quali fatture di trasporto vengono associate automaticamente.

## <a name="the-freight-reconciliation-process"></a>Processo di riconciliazione spese di trasporto

Le tariffe di trasporto vengono calcolate dal motore tariffe associato con il vettore di spedizione pertinente. Quando un carico viene confermato, viene generata una fattura di trasporto e le tariffe di trasporto vengono trasferite ad essa. Le tariffe di trasporto vengono ripartite come spese varie nel documento di origine pertinente (ordine fornitore, ordine cliente e/o ordine di trasferimento), a seconda dell'impostazione utilizzata per il normale processo di fatturazione. Il processo di riconciliazione delle spese di trasporto (che è noto anche come il processo di abbinamento) può iniziare non appena arriva la fattura di trasporto dal vettore di spedizione. La fattura può essere ricevuta elettronicamente o su carta. Se si riceve la fattura su carta, è possibile generare una fattura elettronica utilizzando la fattura di trasporto come modello.

[![Processo di riconciliazione spese di trasporto](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Riconciliazione manuale

Se si riconciliano manualmente le spese di trasporto, è necessario abbinare ogni riga della fattura con la riga o le righe della fattura di trasporto del carico da fatturare. A tale scopo, abbinare nella pagina **Abbinamento fatture di trasporto e fatture**. Se l'importo nella riga della fattura non corrisponde all'importo della fattura di trasporto, è necessario selezionare un motivo di riconciliazione per la differenza. Se esistono diversi motivi per la riconciliazione, è possibile ripartire sui vari motivi l'importo non abbinato. Il motivo di riconciliazione determina la modalità di registrazione degli importi di differenza nella contabilità generale. Quando la riconciliazione dell'importo della fattura intera è contabilizzata, viene inviata per l'approvazione e quindi la registrazione. Nell'illustrazione che segue viene mostrato come generare una fattura di trasporto ed eseguire la riconciliazione delle spese di trasporto.

[![Attività di riconciliazione trasporto](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)

## <a name="automatic-reconciliation"></a>Riconciliazione automatica

Per utilizzare la riconciliazione automatica, è necessario specificare la programmazione per la riconciliazione e le fatture e i vettori di spedizione da utilizzare. L'abbinamento delle righe di fattura e delle fatture di trasporto viene effettuato in base all'impostazione del tipo di controllo master e di fattura di trasporto. Dopo aver eseguito la riconciliazione automatica, è necessario gestire tutte le fatture che il sistema non riesce ad abbinare. È quindi necessario elaborare queste fatture manualmente prima di poter registrare tutte le fatture per il pagamento.

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a>Effettuare la corrispondenza tra bolle di trasporto e fatture di trasporto utilizzando la riconciliazione automatica o manuale

La *corrispondenza* è il processo di ricerca delle bolle di trasporto che corrispondono a ciascuna fattura di trasporto. Questo può essere fatto effettuando la corrispondenza tra le righe della fattura una alla volta (corrispondenza manuale) o effettuando la corrispondenza tra tutte le fatture disponibili contemporaneamente (corrispondenza automatica).

### <a name="auto-matching"></a>Corrispondenza automatica

Quando si effettua la corrispondenza tra più fatture di trasporto alla stessa bolla di trasporto, il processo per la corrispondenza automatica funziona come segue:

1. Tutte le fatture di trasporto senza corrispondenza vengono ordinate per importo, con l'importo maggiore per primo.
1. La corrispondenza tra le fatture di trasporto viene effettuata una alla volta, fino a quando la bolla di trasporto non ha un importo positivo residuo.
1. A seconda dell'impostazione dell'audit principale e dell'importo rimanente nelle fatture di trasporto, viene impostato l'importo rimanente.

### <a name="manual-matching"></a>Corrispondenza manuale

Tutte le bolle di trasporto con importi positivi saranno disponibili per la corrispondenza. Analogamente alla corrispondenza automatica, l'utente potrà effettuare la corrispondenza solo delle fatture di trasporto con importi negativi con bolle di trasporto senza una corrispondenza completa.

### <a name="example"></a>Esempio

Supponiamo di avere una bolla di trasporto per un importo di 1500 e di aver creato tre fatture di trasporto per la bolla di trasporto con una riga di fattura per ciascuna fattura con le seguenti impostazioni:

- Bolla di trasporto originale: importo 1500
- Fattura 1 (Inv1): importo 1000
- Fattura 2 (Inv2): importo 600
- Fattura 3 (Inv3): importo -100

#### <a name="automatic-matching-result"></a>Risultato della corrispondenza automatica

La corrispondenza automatica verrà eseguita nel seguente ordine:

1. Ordina tutte le fatture di trasporto decrescente per importo: Inv1 -> Inv2 -> Inv3.
1. Corrispondenza di Inv1 con bolla di trasporto. Inv1 ha 1000 corrispondenze e la bolla di trasporto ne ha 500 rimanenti, quindi lo stato è impostato su *Corrispondenza parziale*.
1. Corrispondenza di Inv2 con bolla di trasporto. Inv2 ha 500 corrispondenze e la bolla di trasporto ne ha 0 rimanenti, quindi lo stato è impostato su *Corrispondenza completa*.
1. In virtù della corrispondenza completa della bolla di trasporto, Inv3 non verrà elaborato.

#### <a name="manual-matching-result"></a>Risultato della corrispondenza manuale

Per la corrispondenza manuale, i risultati variano a seconda dell'ordine della corrispondenza, come illustrato nei seguenti casi di esempio.

##### <a name="manual-matching-case-1"></a>Caso di corrispondenza manuale 1

Un modo per eseguire la corrispondenza manuale per questo esempio è procedere come segue:

1. Corrispondenza della bolla di trasporto con Inv1. La bolla di trasporto ne ha 500 rimanenti, quindi lo stato è impostato su *Corrispondenza parziale*.
1. Corrispondenza di Inv2 con bolla di trasporto. Inv2 ha 500 corrispondenze e la bolla di trasporto ne ha 0 rimanenti, quindi lo stato è impostato su *Corrispondenza completa*.
1. Quando si effettua manualmente la corrispondenza con Inv3, non si trovano bolle di trasporto senza corrispondenza.

Questo caso è essenzialmente lo stesso della corrispondenza automatica

##### <a name="manual-matching-case-2"></a>Caso di corrispondenza manuale 2

Un altro modo per eseguire la corrispondenza manuale per questo esempio è procedere come segue:

1. Corrispondenza di Inv3 con la bolla di trasporto. Ora la bolla di trasporto ha la quantità rimanente 1600, che equivale a sottrarre 100 negativi sopra 1500. Sia la bolla di trasporto che Inv3 hanno una quantità corrispondente di -100.
1. Corrispondenza di Inv1 e Inv 2 con una bolla di trasporto dopo l'altra. Corrispondenza completa della bolla di trasporto.

Come mostra questo esempio, la corrispondenza delle fatture di trasporto con importi negativi deve essere eseguito solo manualmente. Ciò garantirà che sia sempre possibile effettuare la corrispondenza delle fatture di trasporto con importi negativi a una bolla di trasporto senza corrispondenza completa perché ciò consente di controllare la sequenza di corrispondenza.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]