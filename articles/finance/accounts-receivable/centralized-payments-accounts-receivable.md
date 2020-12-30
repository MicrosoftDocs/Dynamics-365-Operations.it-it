---
title: Pagamenti centralizzati per contabilità clienti
description: Le organizzazioni che includono più persone giuridiche possono creare e gestire i pagamenti utilizzando una sola persona giuridica che gestisca tutti i pagamenti. Di conseguenza, la stessa transazione non deve essere immessa in più persone giuridiche. Questo articolo fornisce esempi che indicano come gestire la registrazione dei pagamenti centralizzati in diversi scenari.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 78c72bb9632d3501638d528822a3c30b05686796
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444755"
---
# <a name="centralized-payments-for-accounts-receivable"></a>Pagamenti centralizzati per contabilità clienti

[!include [banner](../includes/banner.md)]

Le organizzazioni che includono più persone giuridiche possono creare e gestire i pagamenti utilizzando una sola persona giuridica che gestisca tutti i pagamenti. Di conseguenza, la stessa transazione non deve essere immessa in più persone giuridiche. Questo articolo fornisce esempi che indicano come gestire la registrazione dei pagamenti centralizzati in diversi scenari.

Le organizzazioni che includono più persone giuridiche possono creare e gestire i pagamenti utilizzando una persona giuridica che gestisca tutti i pagamenti. Di conseguenza, la stessa transazione non deve essere immessa in più persone giuridiche. Inoltre, l'organizzazione risparmia tempo, poiché i processi per le proposte di pagamento, le liquidazioni e la modifica di transazioni aperte e chiuse per i pagamenti centralizzati vengono semplificati. 

In un'organizzazione di pagamento centralizzata sono presenti numerose persone giuridiche per le operazioni e ciascuna persona giuridica operativa gestisce le proprie informazioni in merito alle fatture a credito. I pagamenti per tutte le persone giuridiche operative vengono ricevuti da una singola persona giuridica, definita persona giuridica del pagamento. Durante il processo di liquidazione, vengono generate le transazioni relative a importi da versare e da ricevere. È possibile specificare quale persona giuridica dell'organizzazione riceverà le transazioni di profitto realizzato o di perdita realizzata e la modalità di gestione delle transazioni di sconto di cassa correlate a un pagamento centralizzato. Nella riga del giornale di registrazione pagamenti centralizzato, **Tipo di conto** deve essere impostato su Cliente. **Tipo di conto di contropartita** deve essere impostato su Banca o Contabilità generale. Il conto bancario deve essere nella società corrente. 

Negli esempi riportati di seguito viene illustrata la modalità di gestione della registrazione in diversi scenari. Per tutti gli esempi si presuppone la seguente configurazione:

-   Le persone giuridiche sono Fabrikam, Fabrikam East e Fabrikam West. I pagamenti clienti vengono immessi in Fabrikam.
-   Il campo **Registra sconto di cassa** nella pagina **Contabilità interaziendale** è impostato su **Persona giuridica della fattura**.
-   Il campo **Registra profitto o perdita su cambio valutario** nella pagina **Contabilità interaziendale** è impostato su **Persona giuridica del pagamento**.
-   Il cliente Northwind Traders è impostato come cliente in ogni persona giuridica. I clienti da varie persone giuridiche vengono identificati come lo stesso cliente perché condividono lo stesso ID Rubrica globale.

| ID Rubrica | Conto cliente | Nome              | Persona giuridica  |
|-----------------|------------------|-------------------|---------------|
| 4050            | 4000             | Northwind Traders | Fabrikam      |
| 4050            | 4000             | Northwind Traders | Fabrikam East |
| 4050            | 10000            | Northwind Traders | Fabrikam West |

## <a name="example-1-customer-payment-of-invoice-from-another-legal-entity"></a>Esempio 1: pagamento cliente di una fattura di un'altra persona giuridica
Fabrikam riceve un pagamento di 600,00 per il conto cliente 4000, Northwind Traders, di Fabrikam. Il pagamento viene liquidato con una fattura aperta per l'account cliente 4000 in Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-customer-4000"></a>Fattura registrata in Fabrikam East per il cliente 4000

| Conto                             | Importo in Dare | Importo in Avere |
|-------------------------------------|--------------|---------------|
| Contabilità clienti (Fabrikam East) | 600,00       |               |
| Vendite (Fabrikam East)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>Pagamento ricevuto e registrato in Fabrikam per il cliente 4000

| Conto                        | Importo in Dare | Importo in Avere |
|--------------------------------|--------------|---------------|
| Cassa (Fabrikam)                | 600,00       |               |
| Contabilità clienti (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Pagamento Fabrikam liquidato con fattura Fabrikam East

**Registrazione Fabrikam**

| Conto                         | Importo in Dare | Importo in Avere |
|---------------------------------|--------------|---------------|
| Contabilità clienti (Fabrikam)  | 600,00       |               |
| Dovuto a Fabrikam East (Fabrikam) |              | 600,00        |

**Registrazione Fabrikam East**

| Conto                             | Importo in Dare | Importo in Avere |
|-------------------------------------|--------------|---------------|
| Dovuto da Fabrikam (Fabrikam East)   | 600,00       |               |
| Contabilità clienti (Fabrikam East) |              | 600,00        |

## <a name="example-2-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Esempio 2: pagamento cliente di una fattura di un'altra persona giuridica con sconto di cassa
Fabrikam riceve un pagamento di 580,00 per il cliente 4000, Northwind Traders, di Fabrikam. Fabrikam East ha una fattura aperta per il cliente 4000. Per la fattura è disponibile uno sconto di cassa di 20,00. Il pagamento viene liquidato con le fatture aperte di Fabrikam East. Lo sconto di cassa verrà registrato nella persona giuridica della fattura: Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>Fattura registrata in Fabrikam East per il cliente 4000 di Fabrikam East

| Conto                             | Importo in Dare | Importo in Avere |
|-------------------------------------|--------------|---------------|
| Contabilità clienti (Fabrikam East) | 580.00       |               |
| Vendite (Fabrikam East)               |              | 580.00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Pagamento ricevuto e registrato in Fabrikam per il cliente 4000 di Fabrikam

| Conto                        | Importo in Dare | Importo in Avere |
|--------------------------------|--------------|---------------|
| Cassa (Fabrikam)                | 600,00       |               |
| Contabilità clienti (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Pagamento Fabrikam liquidato con fattura Fabrikam East

**Registrazione Fabrikam**

| Conto                         | Importo in Dare | Importo in Avere |
|---------------------------------|--------------|---------------|
| Contabilità clienti (Fabrikam)  | 580,00       |               |
| Dovuto a Fabrikam East (Fabrikam) |              | 580,00        |

**Registrazione Fabrikam East**

| Conto                             | Importo in Dare | Importo in Avere |
|-------------------------------------|--------------|---------------|
| Dovuto da Fabrikam (Fabrikam East)   | 580,00       |               |
| Contabilità clienti (Fabrikam East) |              | 580,00        |
| Sconto di cassa (Fabrikam East)       | 20,00        |               |
| Contabilità clienti (Fabrikam East) |              | 20,00         |

## <a name="example-3-customer-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-gain"></a>Esempio 3: pagamento cliente di una fattura di un'altra persona giuridica con profitti realizzati sul tasso di cambio
Fabrikam riceve un pagamento di 600,00 Euro (EUR) per il conto cliente 4000, Northwind Traders. Il pagamento viene liquidato con una fattura aperta per il cliente 4000 in Fabrikam East. Durante il processo di liquidazione viene generata una transazione di profitto sul tasso di cambio.

-   Tasso di cambio da EUR a USD alla data della fattura: 1,2062
-   Tasso di cambio da EUR a USD alla data del pagamento: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>Fattura registrata in Fabrikam East per il cliente 4000 di Fabrikam East

| Conto                             | Importo in Dare            | Importo in Avere           |
|-------------------------------------|-------------------------|-------------------------|
| Contabilità clienti (Fabrikam East) | 600,00 EUR / 723,72 USD |                         |
| Vendite (Fabrikam East)               |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Pagamento ricevuto e registrato in Fabrikam per il cliente 4000 di Fabrikam

| Conto                        | Importo in Dare            | Importo in Avere           |
|--------------------------------|-------------------------|-------------------------|
| Cassa (Fabrikam)                | 600,00 EUR / 736,62 USD |                         |
| Contabilità clienti (Fabrikam) |                         | 600,00 EUR / 736,62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Pagamento Fabrikam liquidato con fattura Fabrikam East

**Registrazione Fabrikam**

| Conto                         | Importo in Dare            | Importo in Avere           |
|---------------------------------|-------------------------|-------------------------|
| Contabilità clienti (Fabrikam)  | 600,00 EUR / 736,62 USD |                         |
| Dovuto a Fabrikam East (Fabrikam) |                         | 600,00 EUR / 736,62 USD |
| Dovuto a Fabrikam East (Fabrikam) | 0,00 EUR / 12,90 USD    |                         |
| Profitto realizzato (Fabrikam)        |                         | 0,00 EUR / 12,90 USD    |

**Registrazione Fabrikam East**

| Conto                             | Importo in Dare            | Importo in Avere           |
|-------------------------------------|-------------------------|-------------------------|
| Dovuto da Fabrikam (Fabrikam East)   | 600,00 EUR / 736,62 USD |                         |
| Contabilità clienti (Fabrikam East) |                         | 600,00 EUR / 736,62 USD |
| Contabilità clienti (Fabrikam East) | 0,00 EUR / 12,90 USD    |                         |
| Dovuto da Fabrikam (Fabrikam East)   |                         | 0,00 EUR / 12,90 USD    |

## <a name="example-4-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-gain"></a>Esempio 4: pagamento cliente di una fattura di un'altra persona giuridica con sconto di cassa e profitto realizzato sul tasso di cambio
Fabrikam registra un pagamento per il cliente 4000, Northwind Traders, di Fabrikam per una fattura aperta in Fabrikam East. Per la fattura è disponibile uno sconto di cassa e viene generata una transazione IVA. Il pagamento viene liquidato con la fattura aperta di Fabrikam East. Durante il processo di liquidazione viene generata una transazione di profitto sul tasso di cambio. Lo sconto di cassa viene registrato nella persona giuridica di fatturazione (Fabrikam East) e i profitti sul tasso di cambio vengono registrati nella persona giuridica di pagamento (Fabrikam).

-   Tasso di cambio da EUR a USD alla data della fattura: 1,2062
-   Tasso di cambio da EUR a USD alla data del pagamento: 1,2277

### <a name="free-text-invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-customer-4000"></a>Fattura a testo libero registrata e transazione IVA generata in Fabrikam East per il cliente 4000

| Conto                             | Importo in Dare            | Importo in Avere           |
|-------------------------------------|-------------------------|-------------------------|
| Contabilità clienti (Fabrikam East) | 638,22 EUR / 769,82 USD |                         |
| Vendite (Fabrikam East)               |                         | 600,00 EUR / 723,72 USD |
| IVA (Fabrikam East)           |                         | 38,22 EUR / 46,10 USD   |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>Pagamento ricevuto e registrato in Fabrikam per il cliente 4000

| Conto                        | Importo in Dare            | Importo in Avere           |
|--------------------------------|-------------------------|-------------------------|
| Cassa (Fabrikam)                | 626,22 EUR / 768,81 USD |                         |
| Contabilità clienti (Fabrikam) |                         | 626,22 EUR / 768,81 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Pagamento Fabrikam liquidato con fattura Fabrikam East

**Registrazione Fabrikam**

| Conto                         | Importo in Dare            | Importo in Avere           |
|---------------------------------|-------------------------|-------------------------|
| Contabilità clienti (Fabrikam)  | 626,22 EUR / 768,81 USD |                         |
| Dovuto a Fabrikam East (Fabrikam) |                         | 626,22 EUR / 768,81 USD |
| Dovuto a Fabrikam East (Fabrikam) | 0,00 EUR / 13,46 USD    |                         |
| Profitto realizzato (Fabrikam)        |                         | 0,00 EUR / 13,46 USD    |

**Registrazione Fabrikam East**

| Conto                             | Importo in Dare            | Importo in Avere           |
|-------------------------------------|-------------------------|-------------------------|
| Dovuto da Fabrikam (Fabrikam East)   | 626,22 EUR / 768,81 USD |                         |
| Contabilità clienti (Fabrikam East) |                         | 626,22 EUR / 768,81 USD |
| Contabilità clienti (Fabrikam East)  | 0,00 EUR / 13,46 USD    |                         |
| Dovuto da Fabrikam (Fabrikam East)   |                         | 0,00 EUR / 13,46 USD    |
| Sconto di cassa (Fabrikam East)       | 12,00 EUR / 14,47 USD   |                         |
| Contabilità clienti (Fabrikam East) |                         | 12,00 EUR / 14,47 USD   |

## <a name="example-5-customer-credit-note-with-primary-payment"></a>Esempio 5: nota di accredito cliente con pagamento primario
Fabrikam riceve un pagamento di 75,00 dal cliente 4000, Northwind Traders. Il pagamento viene liquidato con una fattura aperta per il cliente 10000 di Fabrikam West e una nota di accredito aperta per il cliente 4000 di Fabrikam East. Il pagamento viene selezionato come pagamento primario nella pagina **Liquida transazioni**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>Fattura registrata in Fabrikam West per il cliente 10000

| Conto                             | Importo in Dare | Importo in Avere |
|-------------------------------------|--------------|---------------|
| Contabilità clienti (Fabrikam West) | 100,00       |               |
| Vendite (Fabrikam West)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Nota di accredito registrata in Fabrikam East per il fornitore 4000

| Conto                             | Importo in Dare | Importo in Avere |
|-------------------------------------|--------------|---------------|
| Resi su vendite (Fabrikam East)       | 25,00        |               |
| Contabilità clienti (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Pagamento registrato in Fabrikam per il cliente 4000

| Conto                        | Importo in Dare | Importo in Avere |
|--------------------------------|--------------|---------------|
| Cassa (Fabrikam)                | 75,00        |               |
| Contabilità clienti (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Pagamento Fabrikam liquidato con fattura Fabrikam West e nota di accredito Fabrikam East

**Registrazione Fabrikam**

| Conto                           | Importo in Dare | Importo in Avere |
|-----------------------------------|--------------|---------------|
| Dovuto da Fabrikam East (Fabrikam) | 25,00        |               |
| Contabilità clienti (Fabrikam)    |              | 25,00         |
| Contabilità clienti (Fabrikam)    | 100,00       |               |
| Dovuto a Fabrikam West (Fabrikam)   |              | 100,00        |

**Registrazione Fabrikam East**

| Conto                             | Importo in Dare | Importo in Avere |
|-------------------------------------|--------------|---------------|
| Contabilità clienti (Fabrikam East) | 25,00        |               |
| Dovuto a Fabrikam (Fabrikam East)     |              | 25,00         |

**Registrazione Fabrikam West**

| Conto                             | Importo in Dare | Importo in Avere |
|-------------------------------------|--------------|---------------|
| Dovuto da Fabrikam (Fabrikam West)   | 100,00       |               |
| Contabilità clienti (Fabrikam West) |              | 100,00        |

## <a name="example-6-customer-credit-note-without-primary-payment"></a>Esempio 6: nota di accredito cliente senza pagamento primario
Fabrikam riceve un pagamento di 75,00 dal cliente 4000, Northwind Traders. Il pagamento viene liquidato con una fattura aperta per il cliente 10000 di Fabrikam West e una nota di accredito aperta per il cliente 4000 di Fabrikam East. Il pagamento non viene selezionato come pagamento primario nella pagina **Liquida transazioni**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>Fattura registrata in Fabrikam West per il cliente 10000

| Conto                             | Importo in Dare | Importo in Avere |
|-------------------------------------|--------------|---------------|
| Contabilità clienti (Fabrikam West) | 100,00       |               |
| Vendite (Fabrikam West)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Nota di accredito registrata in Fabrikam East per il fornitore 4000

| Conto                             | Importo in Dare | Importo in Avere |
|-------------------------------------|--------------|---------------|
| Resi su vendite (Fabrikam East)       | 25,00        |               |
| Contabilità clienti (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Pagamento registrato in Fabrikam per il cliente 4000

| Conto                        | Importo in Dare | Importo in Avere |
|--------------------------------|--------------|---------------|
| Cassa (Fabrikam)                | 75,00        |               |
| Contabilità clienti (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Pagamento Fabrikam liquidato con fattura Fabrikam West e nota di accredito Fabrikam East

**Registrazione Fabrikam**

| Conto                         | Importo in Dare | Importo in Avere |
|---------------------------------|--------------|---------------|
| Contabilità clienti (Fabrikam)  | 75,00        |               |
| Dovuto a Fabrikam West (Fabrikam) |              | 75,00         |

**Registrazione Fabrikam East**

| Conto                              | Importo in Dare | Importo in Avere |
|--------------------------------------|--------------|---------------|
| Contabilità clienti (Fabrikam East)  | 25,00        |               |
| Dovuto a Fabrikam West (Fabrikam East) |              | 25,00         |

**Registrazione Fabrikam West**

| Conto                                | Importo in Dare | Importo in Avere |
|----------------------------------------|--------------|---------------|
| Dovuto da Fabrikam (Fabrikam West)      | 75,00        |               |
| Contabilità clienti (Fabrikam West)    |              | 75,00         |
| Dovuto da Fabrikam East (Fabrikam West) | 25,00        |               |
| Contabilità clienti (Fabrikam West)    |              | 25,00         |
