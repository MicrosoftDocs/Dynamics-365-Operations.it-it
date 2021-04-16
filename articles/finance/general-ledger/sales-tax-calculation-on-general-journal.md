---
title: Calcolo dell'IVA nelle righe giornale di registrazione generale
description: Questo argomento spiega come viene calcolata l'IVA per diversi tipi di conti (fornitore, cliente, contabilità generale e progetto) sulle righe del giornale di registrazione generale.
author: EricWang
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: e4d367fe6cb729c9c5658a9bbbac04e53fdf9644
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815334"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a>Calcolo dell'IVA nelle righe giornale di registrazione generale
[!include [banner](../includes/banner.md)]

Questo argomento spiega come viene calcolata l'IVA per diversi tipi di conti (fornitore, cliente, contabilità generale e progetto) sulle righe del giornale di registrazione generale.

Il processo può essere suddiviso in tre passaggi:

- Determinare la direzione dell'IVA.

- Determinare l'importo dell'IVA da archiviare una tabella IVA temporanea.

- Determinare l'importo dell'IVA e il conto sul giustificativo.

## <a name="determine-the-sales-tax-direction"></a>Determinare la direzione dell'IVA

Il modo in cui viene determinata la direzione dell'IVA dipende dal tipo di conto nel giustificativo. La direzione dell'IVA è determinata dalla combinazione di tipo di conto e codice IVA. Nelle seguenti sezioni vengono spiegate le opzioni in modo più dettagliato. 

### <a name="account-type-is-project"></a>Il tipo di conto è Progetto

Se un giustificativo ha riga giornale di registrazione in cui il tipo di conto è **Progetto**, tutte le righe giornale di registrazione del giustificativo applicano la stessa direzione dell'IVA. Nella figura seguente è illustrata la regola. I punti seguenti indicano le possibili direzioni dell'IVA per i conti di progetto.

•   Se il codice IVA è l'imposta di utilizzo, la direzione dell'IVA è Imposta di utilizzo.

•   Se il codice IVA è l'esenzione di imposta, la direzione dell'IVA è Acquisto esentasse.

•   Se il codice IVA è l'IVA intracomunitaria, la direzione dell'IVA è IVA a debito.

•   Se il codice IVA è il reverse charge, la direzione dell'IVA è IVA a debito.

Negli altri casi la direzione dell'IVA è IVA a credito.

Nel diagramma riportato di seguito viene illustrata graficamente la regola.

![Possibilità di direzione dell'IVA per i conti di progetto](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a>Il tipo di conto è Fornitore

Se un giustificativo ha riga giornale di registrazione in cui il tipo di conto è **Fornitore**, tutte le righe giornale di registrazione del giustificativo applicano la stessa direzione dell'IVA. I punti seguenti indicano le possibili direzioni dell'IVA per i conti di fornitore. 

•   Se il codice IVA è l'imposta di utilizzo, la direzione dell'IVA è Imposta di utilizzo.

•   Se il codice IVA è l'esenzione di imposta, la direzione dell'IVA è Acquisto esentasse.

•   Se il codice IVA è l'IVA intracomunitaria, la direzione dell'IVA è IVA a debito.

•   Se il codice IVA è il reverse charge, la direzione dell'IVA è IVA a debito.

Negli altri casi la direzione dell'IVA è IVA a credito.

Nel diagramma riportato di seguito viene illustrata graficamente la regola.

![Possibilità di direzione dell'IVA per i conti di fornitore](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a>Il tipo di conto è Cliente

Se un giustificativo ha riga giornale di registrazione in cui il tipo di conto è **Cliente**, tutte le righe giornale di registrazione del giustificativo applicano la stessa direzione dell'IVA. I punti seguenti indicano le possibili direzioni dell'IVA per i conti di cliente.

•   Se il codice IVA è l'esenzione di imposta, la direzione dell'IVA è Acquisto esentasse.

•   Se il codice IVA è l'IVA intracomunitaria, la direzione dell'IVA è IVA a credito.

•   Se il codice IVA è il reverse charge, la direzione dell'IVA è IVA a credito.

Negli altri casi la direzione dell'IVA è IVA a debito.

Nel diagramma riportato di seguito viene illustrata graficamente la regola.

![Possibilità di direzione dell'IVA per i conti di cliente](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a>Il tipo di conto è Contabilità generale

Nella seguente figura è illustrata la regola che si applica quando in un giustificativo sono presenti solo righe giornale di registrazione in cui il tipo conto è **Contabilità generale**. I punti seguenti indicano le possibili direzioni dell'IVA per i conti di contabilità generale.

•   Se il codice IVA è l'imposta di utilizzo, la direzione dell'IVA è Imposta di utilizzo.

•   Se il codice IVA è l'esenzione di imposta, la direzione dell'IVA è Acquisto esentasse.

Altrimenti, se l'importo giornale di registrazione è un addebito (positivo) la direzione è IVA a credito, se l'importo giornale di registrazione è un credito (negativo) la direzione è IVA a debito.

Nel diagramma riportato di seguito viene illustrata graficamente la regola.

![Possibilità di direzione dell'IVA per i conti di contabilità generale](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a>Sostituire la direzione dell'IVA

È possibile sostituire la direzione dell'IVA quando il giustificativo contiene solo le righe in cui il tipo di conto è **Contabilità generale**.

Passare a **Contabilità generale \> Piano dei conti \> Conti \> Conti principali** e selezionare la scheda dettaglio **Sostituzioni persona giuridica**.

## <a name="determine-the-sales-tax-amount"></a>Determinare l'importo dell'IVA

In questa sezione viene descritto come viene calcolato il segno dell'importo dell'IVA.

![Pagina delle transazioni IVA](media/sales-tax-amount-sign.jpg)

Nella tabella seguente viene illustrata la regola generica per determinare il segno degli importi IVA nella tabella IVA temporanea.

| Importo riga giornale di registrazione | Tipo di IVA  | Segno dell'importo IVA |
|---------------------|----------------------|-----------------------|
| Positivo            | IVA a credito | Positivo              |
| Positivo            | IVA a debito    | Negativo              |
| Negativo            | IVA a credito | Negativo              |
| Negativo            | IVA a debito    | Positivo              |

Esiste una regola speciale per i giustificativi con righe solo righe **Contabilità generale** o **Progetto**, quando una fascia IVA o fascia VAT articoli è selezionata nella riga **Contabilità generale**. Questa regola è controllata dalla funzionalità di abilitazione del calcolo dell'IVA indipendente per i giornali di registrazione generali. Quando questa funzionalità è disattivata, l'importo IVA della riga **Contabilità generale** utilizza la direzione Dare/Avere della riga **Progetto**. Quando la funzionalità è attivata, l'importo IVA della riga **Contabilità generale** utilizza la propria direzione Dare/Avere. Nelle tabelle seguente è illustrata la regola per ogni scenario. 

**Regola quando la funzionalità è attivata**

| Importo riga giornale di registrazione del progetto | Tipo di IVA  | Segno dell'importo IVA |
|--------------------------------|----------------------|-----------------------|
| Positivo                       | IVA a credito | Positivo              |
| Negativo                       | IVA a credito | Negativo              |

**Regola quando la funzionalità è disattivata**

| Importo riga giornale di registrazione della contabilità generale  | Tipo di IVA  | Segno dell'importo IVA |
|--------------------------------|----------------------|-----------------------|
| Positivo                       | IVA a credito | Positivo              |
| Negativo                       | IVA a credito | Negativo              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a>Determinare l'importo dell'IVA e il conto sul giustificativo

Quando si registra l'IVA, il conto principale viene recuperato dal profilo del gruppo di registrazione contabile. Quando l'IVA è a credito, il sistema utilizza il conto IVA a credito specificato nel profilo. Per l'IVA a debito, il sistema utilizza il conto IVA a debito specificato nel profilo.

Nella seguente tabella viene illustrata la regola generale.

| Tipo di IVA  | Segno dell'importo IVA | Conto IVA      | Importo su giustificativo |
|----------------------|-----------------------|------------------------|-------------------|
| IVA a credito | Positivo              | Conto IVA a credito | Positivo (Dare)  |
| IVA a credito | Negativo              | Conto IVA a credito | Negativo (Avere)  |
| IVA a debito    | Positivo              | Conto IVA a debito    | Negativo (Avere)  |
| IVA a debito    | Negativo              | Conto IVA a debito    | Positivo (Dare)  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]