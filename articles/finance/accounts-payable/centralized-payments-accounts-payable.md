---
title: Pagamenti centralizzati per la contabilità fornitori
description: Le organizzazioni che includono più persone giuridiche possono creare e gestire i pagamenti utilizzando una sola persona giuridica che gestisca tutti i pagamenti. Di conseguenza, gli stessi pagamenti non devono essere immessi in più persone giuridiche. Questo articolo fornisce esempi che indicano come gestire la registrazione dei pagamenti centralizzati in diversi scenari.
author: abruer
manager: AnnBe
ms.date: 02/12/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14341
ms.assetid: 7bd02e32-2416-4ac6-8a60-85525267fdb7
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f63d38464a78091a32777707c0df76d05cfd190a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213020"
---
# <a name="centralized-payments-for-accounts-payable"></a>Pagamenti centralizzati per la contabilità fornitori

[!include [banner](../includes/banner.md)]

Le organizzazioni che includono più persone giuridiche possono creare e gestire i pagamenti utilizzando una sola persona giuridica che gestisca tutti i pagamenti. Di conseguenza, gli stessi pagamenti non devono essere immessi in più persone giuridiche. Questo articolo fornisce esempi che indicano come gestire la registrazione dei pagamenti centralizzati in diversi scenari.

Le organizzazioni che includono più persone giuridiche possono creare e gestire i pagamenti utilizzando una persona giuridica che gestisca tutti i pagamenti. Di conseguenza, gli stessi pagamenti non devono essere immessi in più persone giuridiche. Inoltre, l'organizzazione risparmia tempo, poiché il processo di pagamento viene semplificato.

In un'organizzazione di pagamento centralizzata sono presenti numerose persone giuridiche per le operazioni e ciascuna persona giuridica operativa gestisce le proprie fatture fornitore. I pagamenti per tutte le persone giuridiche operative vengono generati da una singola persona giuridica, nota come persona giuridica del pagamento. Durante il processo di liquidazione, vengono generate le transazioni relative a importi da versare e da ricevere. È possibile specificare quale persona giuridica dell'organizzazione riceve le transazioni di profitto realizzato o di perdita realizzata e la modalità di gestione delle transazioni di sconto di cassa correlate a un pagamento interaziendale. Nella riga del giornale di registrazione pagamenti centralizzato, **Tipo di conto** deve essere impostato su Fornitore. **Tipo di conto di contropartita** deve essere impostato su Banca o Contabilità generale. Il conto bancario deve essere nella società corrente. 

Negli esempi riportati di seguito viene illustrata la modalità di gestione della registrazione in diversi scenari. Per tutti gli esempi si presuppone la seguente configurazione:

-   Le persone giuridiche sono Fabrikam, Fabrikam East e Fabrikam West. I pagamenti vengono effettuati attraverso Fabrikam.
-   Il campo **Registra sconto di cassa** nella pagina **Contabilità interaziendale** è impostato su **Persona giuridica della fattura**.
-   Il campo **Registra profitto o perdita su cambio valutario** nella pagina **Contabilità interaziendale** è impostato su **Persona giuridica del pagamento**.
-   Il fornitore Fourth Coffee è impostato come fornitore in ogni persona giuridica. I fornitori di varie persone giuridiche vengono identificati come lo stesso fornitore perché condividono lo stesso ID rubrica globale.

| ID Rubrica | Account fornitore | Nome          | Persona giuridica  |
|--------------|----------------|---------------|---------------|
| 1050         | 3004           | Fourth coffee | Fabrikam      |
| 1050         | 100            | Fourth coffee | Fabrikam East |
| 1050         | 3004           | Fourth coffee | Fabrikam West |

## <a name="example-1-vendor-payment-of-invoice-from-another-legal-entity"></a>Esempio 1: pagamento fornitore di una fattura di un'altra persona giuridica
Fabrikam East ha una fattura aperta per il conto fornitore 100, Fourth Coffee. Fabrikam immette e registra un pagamento nel conto fornitore 3004 di Fabrikam, Fourth Coffee. Il pagamento viene liquidato con la fattura aperta.

### <a name="invoice-is-posted-in-fabrikam-east-for-vendor-100"></a>Fattura registrata in Fabrikam East per il fornitore 100

| Conto                          | Importo in Dare | Importo in Avere |
|----------------------------------|--------------|---------------|
| Spese (Fabrikam East)          | 600,00       |               |
| Contabilità fornitori (Fabrikam East) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>Pagamento generato e registrato in Fabrikam per il fornitore 3004

| Conto                     | Importo in Dare | Importo in Avere |
|-----------------------------|--------------|---------------|
| Contabilità fornitori (Fabrikam) | 600,00       |               |
| Cassa (Fabrikam)             |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Pagamento Fabrikam liquidato con fattura Fabrikam East

**Registrazione Fabrikam**

| Conto                           | Importo in Dare | Importo in Avere |
|-----------------------------------|--------------|---------------|
| Dovuto da Fabrikam East (Fabrikam) | 600,00       |               |
| Contabilità fornitori (Fabrikam)       |              | 600,00        |

**Registrazione Fabrikam East**

| Conto                          | Importo in Dare | Importo in Avere |
|----------------------------------|--------------|---------------|
| Contabilità fornitori (Fabrikam East) | 600,00       |               |
| Dovuto a Fabrikam (Fabrikam East)  |              | 600,00        |

## <a name="example-2-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Esempio 2: pagamento fornitore di una fattura di un'altra persona giuridica con sconto di cassa
Fabrikam East ha una fattura aperta per il fornitore 100, Fourth Coffee. Per la fattura è disponibile uno sconto di cassa di 20,00. Fabrikam immette e registra un pagamento di 580,00 per il fornitore 3004 di Fabrikam, Fourth Coffee. Il pagamento viene liquidato con le fatture aperte di Fabrikam East. Lo sconto di cassa verrà registrato nella persona giuridica della fattura: Fabrikam East.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>Fattura registrata in Fabrikam East per il fornitore 100 di Fabrikam East

| Conto                          | Importo in Dare | Importo in Avere |
|----------------------------------|--------------|---------------|
| Spese (Fabrikam East)          | 600,00       |               |
| Contabilità fornitori (Fabrikam East) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>Pagamento generato e registrato in Fabrikam per il fornitore 3004 di Fabrikam

| Conto                     | Importo in Dare | Importo in Avere |
|-----------------------------|--------------|---------------|
| Contabilità fornitori (Fabrikam) | 580,00       |               |
| Cassa (Fabrikam)             |              | 580,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Pagamento Fabrikam liquidato con fattura Fabrikam East

**Registrazione Fabrikam**

| Conto                           | Importo in Dare | Importo in Avere |
|-----------------------------------|--------------|---------------|
| Dovuto da Fabrikam East (Fabrikam) | 580,00       |               |
| Contabilità fornitori (Fabrikam)       |              | 580,00        |

**Registrazione Fabrikam East**

| Conto                          | Importo in Dare | Importo in Avere |
|----------------------------------|--------------|---------------|
| Contabilità fornitori (Fabrikam East) | 580,00       |               |
| Dovuto a Fabrikam (Fabrikam East)  |              | 580,00        |
| Contabilità fornitori (Fabrikam East) | 20,00        |               |
| Sconto di cassa (Fabrikam East)    |              | 20,00         |

## <a name="example-3-vendor-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-loss"></a>Esempio 3: pagamento fornitore di una fattura di un'altra persona giuridica con perdite realizzate sul tasso di cambio valutario
Fabrikam East ha una fattura aperta per il fornitore 100, Fourth Coffee. Fabrikam immette e registra un pagamento per il fornitore 3004 di Fabrikam, Fourth Coffee. Il pagamento viene liquidato con la fattura aperta di Fabrikam East. Durante il processo di liquidazione viene generata una transazione di perdita sul tasso di cambio valutario.

-   Tasso di cambio da euro (EUR) a dollari statunitensi (USD) alla data della fattura: 1,2062
-   Tasso di cambio da EUR a USD alla data del pagamento: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>Fattura registrata in Fabrikam East per il fornitore 100 di Fabrikam East

| Conto                          | Importo in Dare            | Importo in Avere           |
|----------------------------------|-------------------------|-------------------------|
| Spese (Fabrikam East)          | 600,00 EUR / 723,72 USD |                         |
| Contabilità fornitori (Fabrikam East) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>Pagamento generato e registrato in Fabrikam per il fornitore 3004 di Fabrikam

| Conto                     | Importo in Dare            | Importo in Avere           |
|-----------------------------|-------------------------|-------------------------|
| Contabilità fornitori (Fabrikam) | 600,00 EUR / 736,62 USD |                         |
| Cassa (Fabrikam)             |                         | 600,00 EUR / 736,62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Pagamento Fabrikam liquidato con fattura Fabrikam East

**Registrazione Fabrikam**

| Conto                           | Importo in Dare            | Importo in Avere           |
|-----------------------------------|-------------------------|-------------------------|
| Dovuto da Fabrikam East (Fabrikam) | 600,00 EUR / 736,62 USD |                         |
| Contabilità fornitori (Fabrikam)       |                         | 600,00 EUR / 736,62 USD |
| Perdita realizzata (Fabrikam)          | 0,00 EUR / 12,90 USD    |                         |
| Dovuto da Fabrikam East (Fabrikam) |                         | 0,00 EUR / 12,90 USD    |

**Registrazione Fabrikam East**

| Conto                          | Importo in Dare            | Importo in Avere           |
|----------------------------------|-------------------------|-------------------------|
| Contabilità fornitori (Fabrikam East) | 600,00 EUR / 736,62 USD |                         |
| Dovuto a Fabrikam (Fabrikam East)  |                         | 600,00 EUR / 736,62 USD |
| Dovuto a Fabrikam (Fabrikam East)  | 0,00 EUR / 12,90 USD    |                         |
| Contabilità fornitori (Fabrikam East) |                         | 0,00 EUR / 12,90 USD    |

## <a name="example-4-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-loss"></a>Esempio 4: pagamento fornitore di una fattura di un'altra persona giuridica con sconto di cassa e perdite realizzate sul tasso di cambio valutario
Fabrikam East ha una fattura aperta per il fornitore 100, Fourth Coffee. Per la fattura è disponibile uno sconto di cassa e viene generata una transazione IVA. Fabrikam registra un pagamento per il fornitore 3004 di Fabrikam, Fourth Coffee. Il pagamento viene liquidato con la fattura aperta di Fabrikam East. Durante il processo di liquidazione viene generata una transazione di perdita sul tasso di cambio valutario. Lo sconto di cassa viene registrato nella persona giuridica della fattura (Fabrikam East) e la perdita sul tasso di cambio valutario viene registrata nella persona giuridica del pagamento (Fabrikam).

-   Tasso di cambio da EUR a USD alla data della fattura: 1,2062
-   Tasso di cambio da EUR a USD alla data del pagamento: 1,2277

### <a name="invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-vendor-100"></a>Fattura registrata e transazione fiscale generata in Fabrikam East per il fornitore 100

| Conto                          | Importo in Dare            | Importo in Avere           |
|----------------------------------|-------------------------|-------------------------|
| Spese (Fabrikam East)          | 564,07 EUR / 680,38 USD |                         |
| IVA (Fabrikam East)        | 35,93 EUR / 43,34 USD   |                         |
| Contabilità fornitori (Fabrikam East) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>Pagamento generato e registrato in Fabrikam per il fornitore 3004

| Conto                     | Importo in Dare            | Importo in Avere           |
|-----------------------------|-------------------------|-------------------------|
| Contabilità fornitori (Fabrikam) | 588,72 EUR / 722,77 USD |                         |
| Cassa (Fabrikam East)        |                         | 588,72 EUR / 722,77 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Pagamento Fabrikam liquidato con fattura Fabrikam East

**Registrazione Fabrikam**

| Conto                           | Importo in Dare            | Importo in Avere           |
|-----------------------------------|-------------------------|-------------------------|
| Dovuto da Fabrikam East (Fabrikam) | 588,72 EUR / 722,77 USD |                         |
| Contabilità fornitori (Fabrikam)       |                         | 588,72 EUR / 722,77 USD |
| Perdita realizzata (Fabrikam)          | 0,00 EUR / 12,66 USD    |                         |
| Dovuto da Fabrikam East (Fabrikam) |                         | 0,00 EUR / 12,66 USD    |

**Registrazione Fabrikam East**

| Conto                          | Importo in Dare            | Importo in Avere           |
|----------------------------------|-------------------------|-------------------------|
| Contabilità fornitori (Fabrikam East) | 588,72 EUR / 722,77 USD |                         |
| Dovuto a Fabrikam (Fabrikam East)  |                         | 588,72 EUR / 722,77 USD |
| Dovuto a Fabrikam (Fabrikam East)   | 0,00 EUR / 12,66 USD    |                         |
| Contabilità fornitori (Fabrikam East) |                         | 0,00 EUR / 12,66 USD    |
| Contabilità fornitori (Fabrikam East) | 11,28 EUR / 13,61 USD   |                         |
| Sconto di cassa (Fabrikam East)    |                         | 11,28 EUR / 13,61 USD   |

## <a name="example-5-vendor-credit-note-with-primary-payment"></a>Esempio 5: nota di accredito fornitore con pagamento primario
Fabrikam genera un pagamento di 75,00 per il fornitore 3004, Fourth Coffee. Il pagamento viene liquidato con una fattura aperta per il fornitore 3004 di Fabrikam West e una nota di accredito aperta per il fornitore 100 di Fabrikam East. Il pagamento viene selezionato come pagamento primario nella pagina **Liquida transazioni**.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>Fattura registrata in Fabrikam West per il fornitore 3004

| Conto                          | Importo in Dare | Importo in Avere |
|----------------------------------|--------------|---------------|
| Spese (Fabrikam West)          | 100,00       |               |
| Contabilità fornitori (Fabrikam West) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>Nota di accredito registrata in Fabrikam East per il fornitore 100

| Conto                          | Importo in Dare | Importo in Avere |
|----------------------------------|--------------|---------------|
| Contabilità fornitori (Fabrikam East) | 25,00        |               |
| Resi acquisti (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>Pagamento registrato in Fabrikam per il fornitore 3004

| Conto                     | Importo in Dare | Importo in Avere |
|-----------------------------|--------------|---------------|
| Contabilità fornitori (Fabrikam) | 75,00        |               |
| Cassa (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Pagamento Fabrikam liquidato con fattura Fabrikam West e nota di accredito Fabrikam East

**Registrazione Fabrikam**

| Conto                           | Importo in Dare | Importo in Avere |
|-----------------------------------|--------------|---------------|
| Contabilità fornitori (Fabrikam)       | 25,00        |               |
| Dovuto a Fabrikam East (Fabrikam)   |              | 25,00         |
| Dovuto da Fabrikam West (Fabrikam) | 100,00       |               |
| Contabilità fornitori (Fabrikam)       |              | 100,00        |

**Registrazione Fabrikam East**

| Conto                           | Importo in Dare | Importo in Avere |
|-----------------------------------|--------------|---------------|
| Dovuto da Fabrikam (Fabrikam East) | 25,00        |               |
| Contabilità fornitori (Fabrikam East)  |              | 25,00         |

**Registrazione Fabrikam West**

| Conto                          | Importo in Dare | Importo in Avere |
|----------------------------------|--------------|---------------|
| Contabilità fornitori (Fabrikam West) | 100,00       |               |
| Dovuto a Fabrikam (Fabrikam West)  |              | 100,00        |

## <a name="example-6-vendor-credit-note-without-primary-payment"></a>Esempio 6: nota di accredito fornitore senza pagamento primario
Fabrikam genera un pagamento di 75,00 per il fornitore 3004, Fourth Coffee. Il pagamento viene liquidato con una fattura aperta per il fornitore 3004 di Fabrikam West e una nota di accredito aperta per il fornitore 100 di Fabrikam East. Il pagamento non viene selezionato come pagamento primario nella pagina **Liquida transazioni**.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>Fattura registrata in Fabrikam West per il fornitore 3004

| Conto                          | Importo in Dare | Importo in Avere |
|----------------------------------|--------------|---------------|
| Spese (Fabrikam West)          | 100,00       |               |
| Contabilità fornitori (Fabrikam West) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>Nota di accredito registrata in Fabrikam East per il fornitore 100

| Conto                          | Importo in Dare | Importo in Avere |
|----------------------------------|--------------|---------------|
| Contabilità fornitori (Fabrikam East) | 25,00        |               |
| Resi acquisti (Fabrikam East) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>Pagamento registrato in Fabrikam per il fornitore 3004

| Conto                     | Importo in Dare | Importo in Avere |
|-----------------------------|--------------|---------------|
| Contabilità fornitori (Fabrikam) | 75,00        |               |
| Cassa (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Pagamento Fabrikam liquidato con fattura Fabrikam West e nota di accredito Fabrikam East

**Registrazione Fabrikam**

| Conto                           | Importo in Dare | Importo in Avere |
|-----------------------------------|--------------|---------------|
| Dovuto da Fabrikam West (Fabrikam) | 75,00        |               |
| Contabilità fornitori (Fabrikam)       |              | 75,00         |

**Registrazione Fabrikam East**

| Conto                                | Importo in Dare | Importo in Avere |
|----------------------------------------|--------------|---------------|
| Dovuto da Fabrikam West (Fabrikam East) | 25,00        |               |
| Contabilità fornitori (Fabrikam East)       |              | 25,00         |

**Registrazione Fabrikam West**

| Conto                              | Importo in Dare | Importo in Avere |
|--------------------------------------|--------------|---------------|
| Contabilità fornitori (Fabrikam West)     | 75,00        |               |
| Dovuto a Fabrikam (Fabrikam West)      |              | 75,00         |
| Contabilità fornitori (Fabrikam West)     | 25,00        |               |
| Dovuto a Fabrikam East (Fabrikam West) |              | 25,00         |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]