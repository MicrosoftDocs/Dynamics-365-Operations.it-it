---
title: Giustificativo singolo con più record cliente o fornitore
description: In questo argomento viene fornita una panoramica di cosa succede se si registra un singolo giustificativo con più record cliente o fornitore. Questa funzionalità verrà dismessa nelle versioni future di Microsoft Dynamics 365 for Finance and Operations e pertanto non è consigliabile utilizzare questo metodo di registrazione a causa dell'impatto della contabilità sull'elaborazione della liquidazione.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 222534
ms.assetid: d4df11ce-4d36-4c66-8230-f5fc58e021bc
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acd0ca65685bc32f4601ad1e38d072f5ab79858d
ms.sourcegitcommit: dd1e1636d351a15f9c1b6808bea359417a9bd690
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "897019"
---
# <a name="single-voucher-with-multiple-customer-or-vendor-records"></a>Giustificativo singolo con più record cliente o fornitore

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica di cosa succede se si registra un singolo giustificativo con più record cliente o fornitore. Questa funzionalità verrà dismessa nelle versioni future di Microsoft Dynamics 365 for Finance and Operations e pertanto non è consigliabile utilizzare questo metodo di registrazione a causa dell'impatto della contabilità sull'elaborazione della liquidazione. 

Alcuni esempi comuni in cui un giustificativo viene utilizzato per più clienti o fornitori includono i trasferimenti del saldo tra clienti e la compensazione dei saldi tra clienti e fornitori nella stessa organizzazione. 

È possibile immettere un giustificativo contenente più di un cliente o fornitore utilizzando uno dei metodi seguenti:

-   Tramite un giornale di registrazione con l'opzione **Un solo numero di giustificativo** selezionata in modo che ogni riga aggiunta al giornale di registrazione venga inclusa nello stesso giustificativo.
-   Tramite un giustificativo con più righe senza conto CoGe di contropartita con più di un cliente o fornitore.
-   Immettendo un giustificativo con il conto e il conto di contropartita da fornitore/fornitore, cliente/cliente, fornitore/cliente o cliente/fornitore.

In questo argomento viene illustrato come viene elaborata la liquidazione quando viene registrato un giustificativo con più record cliente o fornitore. Inoltre, in questo argomento vengono fornite le soluzioni alternative per capire come si evita l'uso di un giustificativo con più clienti o fornitori. In particolare, sono esempi in cui vengono illustrati due scenari comuni di liquidazione interessati dall'utilizzo di un giustificativo con più clienti o fornitori:

-   Contabilità sconto di cassa
-   Contabilità rivalutazione

## <a name="how-does-settlement-impact-single-voucher-usage"></a>In che modo alla liquidazione interessa l'utilizzo del singolo giustificativo
Quando viene registrato un giustificativo contenente più record cliente o fornitore, viene creato un singolo giustificativo contabile che contiene più saldi di contabilità fornitori o contabilità clienti. Durante il processo di liquidazione, le voci contabili originali vengono utilizzate per creare le voci contabili per lo sconto di cassa, i profitti e le perdite non realizzati, i profitti e le perdite realizzati e la detrazione del conto riepilogativo del documento originale. Ad esempio, se lo sconto di cassa viene prelevato quando si sta liquidando un pagamento fornitore di una fattura, la contabilità dello sconto di cassa deve eseguire la registrazione nel conto CoGe di contabilità fornitori della fattura originale. Se la fattura originale è stata registrata in un giustificativo contenente più record fornitori, la contabilità originale viene riepilogata. In questo caso, poiché non è possibile accedere alla voce contabile dettagliata per ciascuna transazione fornitore nel singolo giustificativo, non c'è modo di determinare la modalità di contabilizzazione progettata per lo sconto di cassa.

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-cash-discount-accounting"></a>Un giustificativo con più fornitori e l'impatto sulla contabilità dello sconto di cassa

Nel seguente esempio, più fatture fornitore vengono registrate nella contabilità generale in un singolo giustificativo nella pagina **Giornale di registrazione generale**. Queste fatture vengono distribuite in più dimensioni conto.

|             |                  |              |                 |           |            |
|-------------|------------------|--------------|-----------------|-----------|------------|
| **Giustificativo** | **Tipo di conto** | **Conto**  | **Descrizione** | **Dare** | **Avere** |
| GNJL001     | Fornitore           | 1001         | INV1            |           | 100,00     |
| GNJL001     | Fornitore           | 1001         | INV2            |           | 200,00     |
| GNJL001     | Fornitore           | 1001         | INV3            |           | 300,00     |
| GNJL001     | Contabilità generale           | 606300-001-- | INV1            |   50,00   |            |
| GNJL001     | Contabilità generale           | 606300-002-- | INV1            |   50,00   |            |
| GNJL001     | Contabilità generale           | 606300-003-- | INV2            | 200,00    |            |
| GNJL001     | Contabilità generale           | 606300-004-- | INV3            | 300,00    |            |

Dopo la registrazione viene creato un giustificativo.

|             |              |                  |                                    |
|-------------|--------------|------------------|------------------------------------|
| **Giustificativo** | **Conto**  | **Tipo di registrazione** | **Importo in valuta di transazione** |
| GNJL001     | 606300-001-- | Giornale di registrazione contabile   | 50,00                              |
| GNJL001     | 606300-002-- | Giornale di registrazione contabile   | 50,00                              |
| GNJL001     | 606300-003-- | Giornale di registrazione contabile   | 200,00                             |
| GNJL001     | 606300-004-- | Giornale di registrazione contabile   | 300,00                             |
| GNJL001     | 200110-001-  | Saldo fornitore   | -100,00                            |
| GNJL001     | 200110-001-  | Saldo fornitore   | -200,00                            |
| GNJL001     | 200110-001-  | Saldo fornitore   | -300,00                            |

Si noti che il giustificativo contiene tre voci per il tipo di registrazione del saldo fornitore nel singolo giustificativo. Non è possibile indicare che il debito 50,00 per 606300-001 e il debito 50,00 per 606300-002 sono intesi a compensare la voce saldo fornitore 200110-001. Questo perché l'utente ha fornito più record fornitore in un singolo giustificativo.

Utilizzando questo esempio, si può analizzare l'impatto di un giustificativo sulla contabilità della liquidazione downstream. Si supponga di pagare 197,00 della fattura 200,00, con uno sconto di cassa di 3,00. Si noti che il valore del conto dello sconto di cassa verrà assegnato per tutte dimensioni dai conti spese del giustificativo della fattura. Questo perché è stato utilizzato un giustificativo per registrare la fattura precendente, senza indicazione di come l'utente intende correlare le distribuzioni spese al saldo fornitore nel singolo giustificativo.

|             |              |                      |           |            |
|-------------|--------------|----------------------|-----------|------------|
| **Giustificativo** | **Conto**  | **Tipo di registrazione**     | **Dare** | **Avere** |
| APPAYM001   | 200110-001-  | Saldo fornitore       | 197,00    |            |
| APPAYM001   | 110110-001-  | Gestione banche                 |           | 197,00     |
| 14000056    | 520200-001-- | Sconto di cassa fornitore |           | 0.25       |
| 14000056    | 520200-002-- | Sconto di cassa fornitore |           | 0.25       |
| 14000056    | 520200-003-- | Sconto di cassa fornitore |           | 1,00       |
| 14000056    | 520200-004-- | Sconto di cassa fornitore |           | 1.50       |
| 14000056    | 200110-001-  | Saldo fornitore       | 3,00      |            |

Se l'utente non è soddisfatto dell'allocazione dello sconto di cassa per tutte distribuzioni di spesa della fattura originale, anziché un giustificativo, più giustificativi dovranno essere usati per registrare le fatture. Di seguito è riportato un esempio di come più giustificativi possono essere immessi nella contabilità generale, anziché utilizzare un giustificativo, come illustrato all'inizio di questo esempio.

|             |                  |              |                 |           |            |                 |                    |
|-------------|------------------|--------------|-----------------|-----------|------------|-----------------|--------------------|
| **Giustificativo** | **Tipo di conto** | **Conto**  | **Descrizione** | **Dare** | **Avere** | **Tipo contropartita** | **Conto di contropartita** |
| GNJL001     | Fornitore           | 1001         | INV1            |           | 100,00     | Contabilità generale          | &lt;vuoto&gt;:      |
| GNJL001     | Contabilità generale           | 606300-001-- | INV1            |   50,00   |            | Contabilità generale          | &lt;vuoto&gt;:      |
| GNJL001     | Contabilità generale           | 606300-002-- | INV1            |   50,00   |            | Contabilità generale          | &lt;vuoto&gt;:      |
| GNJL002     | Fornitore           | 1001         | INV2            |           | 200,00     | Contabilità generale          | 606300-003--       |
| GNJL003     | Fornitore           | 1001         | INV3            |           | 300,00     | Contabilità generale          | 606300-004--       |

Ora, quando INV2 viene pagata, la seguente voce verrà creata. Si noti che le dimensioni finanziarie dello sconto di cassa seguono le dimensioni finanziarie della spesa associata.

|             |              |                      |           |            |
|-------------|--------------|----------------------|-----------|------------|
| **Giustificativo** | **Conto**  | **Tipo di registrazione**     | **Dare** | **Avere** |
| APPAYM001   | 200110-001-  | Saldo fornitore       | 197,00    |            |
| APPAYM001   | 110110-001-  | Gestione banche                 |           | 197,00     |
| 14000056    | 520200-003-- | Sconto di cassa fornitore |           | 3,00       |
| 14000056    | 200110-001-  | Saldo fornitore       | 3,00      |            |

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-realized-gainloss-accounting"></a>Un giustificativo con più fornitori e l'impatto sulla contabilità di profitti/perdite realizzati

|             |                  |             |                 |           |            |                  |              |
|-------------|------------------|-------------|-----------------|-----------|------------|------------------|--------------|
| **Giustificativo** | **Tipo di conto** | **Conto** | **Descrizione** | **Dare** | **Avere** | **Tipo di conto** | **Conto**  |
| GNJL001     | Fornitore           | 1001        | INV1            |           | 100,00     | Contabilità generale           | 606300-001-- |
| GNJL001     | Fornitore           | 1001        | INV2            |           | 200,00     | Contabilità generale           | 606300-002-- |

Nel seguente esempio, più fatture fornitore vengono registrate nella contabilità generale in un singolo giustificativo nella pagina **Giornale di registrazione generale**. Queste fatture vengono distribuite in più dimensioni conto. Dopo la registrazione viene creato un giustificativo.

|             |              |                  |                                          |                                         |
|-------------|--------------|------------------|------------------------------------------|-----------------------------------------|
| **Giustificativo** | **Conto**  | **Tipo di registrazione** | **Importo nella valuta di transazione (EUR)** | **Importo nella valuta di contabilizzazione (USD)** |
| GNJL001     | 606300-001-- | Giornale di registrazione contabile   | 100,00                                   | 114,00                                  |
| GNJL001     | 606300-002-- | Giornale di registrazione contabile   | 200,00                                   | 228,00                                  |
| GNJL001     | 200110-001-  | Saldo fornitore   | -100,00                                  | -114,00                                 |
| GNJL001     | 200110-001-  | Saldo fornitore   | -200,00                                  | -228,00                                 |

Si noti che il giustificativo contiene due voci per il tipo di registrazione del saldo fornitore nel singolo giustificativo. Non è possibile indicare che il debito per 606300-001 deve compensare la voce saldo fornitore 100,00 per 200110-001. Questo perché l'utente ha fornito più record fornitore in un singolo giustificativo. 

Utilizzando questo esempio, si può analizzare l'impatto di un giustificativo sulla contabilità della liquidazione downstream. Si supponga che la valuta di contabilizzazione sia USD e che le transazioni precendenti siano state registrate nella valuta di transazione EUR. Si supponga che la fattura di EUR 200,00 sia stata interamente pagata ma che sia stata rilevata una perdita realizzata a causa di una differenza del tasso di cambio tra il momento della registrazione della fattura e il pagamento. Si noti che il valore del conto della perdita realizzata verrà assegnato per tutte dimensioni dai conti spese del giustificativo della fattura. In questo caso, le dimensioni 001 e 002 sono state assegnate anche se la percezione dell'utente può essere che solo 002 che appartiene al conto spese dalla fattura da liquidare. Questo perché è stato utilizzato un giustificativo per registrare la fattura precendente, senza fornire alcuna indicazione di come l'utente intende correlare le distribuzioni spese al saldo fornitore nel singolo giustificativo.

|             |             |                    |                                          |                                         |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| **Giustificativo** | **Conto** | **Tipo di registrazione**   | **Importo nella valuta di transazione (EUR)** | **Importo nella valuta di contabilizzazione (USD)** |
| APPAYM001   | 200110-001- | Saldo fornitore     | 200,00                                   | 230,00                                  |
| APPAYM001   | 110110-001- | Gestione banche               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-001- | Perdita sul tasso di cambio | 0,00                                     | 0.67                                    |
| 14000056    | 801300-002- | Perdita sul tasso di cambio | 0,00                                     | 1.33                                    |
| 14000056    | 200110-001- | Saldo fornitore     |                                          | -2,00                                   |

Se l'utente non è soddisfatto dell'allocazione della perdita sul tasso di cambio per tutte distribuzioni di spesa della fattura originale, anziché un giustificativo, più giustificativi dovranno essere utilizzati per registrare le fatture. Di seguito è riportato un esempio di come più giustificativi possono essere immessi nella contabilità generale, anziché utilizzare un giustificativo, come illustrato all'inizio di questo esempio.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Giustificativo** | **Tipo di conto** | **Conto** | **Descrizione** | **Dare** | **Avere** | **Tipo contropartita** | **Conto di contropartita** |
| GNJL002     | Fornitore           | 1001        | INV1            |           | 100,00     | Contabilità generale          | 606300-001--       |
| GNJL003     | Fornitore           | 1001        | INV2            |           | 200,00     | Contabilità generale          | 606300-002--       |

Ora, quando INV2 viene pagata, la seguente voce verrà creata. Si noti che le dimensioni finanziarie della perdita sul tasso di cambio seguono le dimensioni finanziarie della spesa associata.

|             |             |                    |                                          |                                         |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| **Giustificativo** | **Conto** | **Tipo di registrazione**   | **Importo nella valuta di transazione (EUR)** | **Importo nella valuta di contabilizzazione (USD)** |
| APPAYM001   | 200110-001- | Saldo fornitore     | 200,00                                   | 230,00                                  |
| APPAYM001   | 110110-001- | Gestione banche               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-002- | Perdita sul tasso di cambio | 0,00                                     | 2,00                                    |
| 14000056    | 200110-001- | Saldo fornitore     |                                          | -2,00                                   |

## <a name="one-voucher-for-balance-transfers-and-netting-scenarios"></a>Un giustificativo per i trasferimenti di saldo e gli scenari di compensazione
Due scenari comuni che utilizzano un giustificativo contenente più clienti o fornitori includono i trasferimenti di saldo da un cliente/fornitore a un altro cliente/fornitore e la compensazione di un cliente e un fornitore che appartengono alla stessa organizzazione. Nei due esempi seguenti è illustrato il metodo preferito per gestire questi scenari in Finance and Operations in alternativa all'uso di un giustificativo. 

Un *trasferimento di saldo* è un giustificativo con più clienti, immessi allo scopo di trasferire il saldo da un cliente a un altro cliente (stessa cosa per i fornitori). Questo scenario può verificarsi quando la responsabilità del pagamento della fattura passa a un'altra parte, ad esempio una società figlio che passa la responsabilità a una società padre. 

Questo esempio presuppone una vendita in cui il cliente ha diritto a uno sconto di cassa se il pagamento viene effettuato entro 10 giorni. Il cliente in questo esempio utilizza una società di assicurazioni responsabile del pagamento della fattura. La società di assicurazioni è impostata come secondo cliente nel sistema. Il saldo del cliente originale viene trasferito alla società di assicurazioni che paga la fattura con conto uno sconto di cassa del 2% per il pagamento entro il periodo di sconto. 

Per un esempio, si supponga che la seguente vendita venga effettuata al cliente ACME. Le seguenti voci contabili rappresentano la vendita.

|                    |                  |           |            |
|--------------------|------------------|-----------|------------|
| **Conto CoGe** | **Tipo di registrazione** | **Dare** | **Avere** |
| 401100-002-023-    | Ricavi          |           | 100        |
| 130100-002-        | Saldo cliente | 100       |            |

A questo punto, l'utente trasferisce il saldo esigibile da ACME alla società di assicurazioni, in un giustificativo nel giornale di registrazione pagamenti della contabilità clienti. In Finance and Operations la società di assicurazioni è impostata come assicurazione del cliente.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Giustificativo** | **Tipo di conto** | **Conto** | **Descrizione** | **Dare** | **Avere** | **Tipo contropartita** | **Conto di contropartita** |
| ARPAYM001   | Cliente         | ACME        | Trasferimenti        |           | 100,00     | Cliente        | Assicurazione          |

Si noti che la voce precendente è inclusa in un giustificativo. Nel giustificativo sono presenti due record cliente. Il giustificativo successivo viene creato quando la voce di contabilità generale precedente viene registrata.

|             |             |                  |                                    |
|-------------|-------------|------------------|------------------------------------|
| **Giustificativo** | **Conto** | **Tipo di registrazione** | **Importo in valuta di transazione** |
| ARPAYM001   | 130100-002- | Saldo cliente | 100,00                             |
| ARPAYM001   | 130100-002- | Saldo cliente | -100,00                            |

Successivamente, si supponga di ricevere un pagamento dal cliente Assicurazione per 98,00 e che si sceglie di liquidare il pagamento con la fattura creata dal trasferimento del saldo. Ciò determina la registrazione del giustificativo successivo. L'aspettativa potrebbe essere che la liquidazione utilizzi le dimensioni finanziarie della fattura originale, ma non è possibile perché non è presente un documento fattura per il cliente Assicurazione. Si noti che per impostazione predefinita, le dimensioni di distribuzione dello sconto di cassa provengono dalla transazione cliente creata dal trasferimento e non del conto ricavi della fattura originale. Il valore predefinito risulta nell'uso di un giustificativo per trasferire i saldi.

|             |             |                  |           |            |
|-------------|-------------|------------------|-----------|------------|
| **Giustificativo** | **Conto** | **Tipo di registrazione** | **Dare** | **Avere** |
| ARPAYM002   | 110110-002- | Gestione banche             | 98,00     |            |
| ARPAYM002   | 130100-002- | Saldo cliente |           | 98,00      |

Nel giustificativo correlato per lo sconto di cassa, il valore predefinito della dimensione finanziaria deriva dalla transazione cliente creata dal trasferimento perché il trasferimento ha più di un cliente.

|             |             |                        |           |            |
|-------------|-------------|------------------------|-----------|------------|
| **Giustificativo** | **Conto** | **Tipo di registrazione**       | **Dare** | **Avere** |
| ARP-00001   | 403300-002- | Sconto di cassa cliente | 2,00      |            |
| ARP-00001   | 130100-002- | Saldo cliente       |           | 2,00       |

Se l'utente non è soddisfatto dell'impostazione predefinita delle dimensioni finanziarie per lo sconto di cassa, anziché un giustificativo, più giustificativi dovranno essere utilizzati per registrare il trasferimento del saldo. Questo scenario deve essere completato creando una nota di credito per il cliente DA cui il saldo viene spostato e una nota di debito o una fattura creata per il cliente A cui il saldo viene spostato. Nel seguente esempio viene illustrato come più giustificativi possono più essere immessi nel giornale pagamenti contabilità clienti per trasferire il saldo, anziché utilizzare un giustificativo, come illustrato in precedenza in questo esempio.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Giustificativo** | **Tipo di conto** | **Conto** | **Descrizione** | **Dare** | **Avere** | **Tipo contropartita** | **Conto di contropartita** |
| ARPAYM001   | Cliente         | ACME        |                 |           | 100,00     | Contabilità generale          | 401100-002-023-    |
| ARPAYM002   | Cliente         | Assicurazione   |                 | 100,00    |            | Contabilità generale          | 401100-002-023-    |

Ciò significa che dopo che il cliente Assicurazione paga 98,00 con il giustificativo ARPAYM02, verranno utilizzate le dimensioni finanziarie corrette della voce di conto CoGe del giustificativo ARPAYM002.

|             |             |                  |           |            |
|-------------|-------------|------------------|-----------|------------|
| **Giustificativo** | **Conto** | **Tipo di registrazione** | **Dare** | **Avere** |
| ARPAYM003   | 110110-002- | Gestione banche             | 98,00     |            |
| ARPAYM003   | 130100-002  | Saldo cliente |           | 98,00      |

Nel giustificativo correlato per lo sconto di cassa, le dimensioni finanziarie verranno utilizzate dal conto ricavi contropartita indicato nel giustificativo di ARPAYM002.

|             |                 |                        |           |            |
|-------------|-----------------|------------------------|-----------|------------|
| **Giustificativo** | **Conto**     | **Tipo di registrazione**       | **Dare** | **Avere** |
| ARP-00001   | 403300-002-023- | Sconto di cassa cliente | 2,00      |            |
| ARP-00001   | 130100-002-     | Saldo cliente       |           | 2,00       |

### 

## <a name="one-voucher-with-a-netting-for-multiple-customers-and-vendors"></a>Un giustificativo con una compensazione per più clienti e fornitori
La compensazione può essere utile per le vendite e gli acquisti di un'organizzazione alla stessa società. Anziché pagare le fatture del fornitore e attendere di ricevere il pagamento per le fatture cliente, le fatture cliente e fornitore vengono compensate. La transazione di compensazione viene liquidata a fronte dei saldi residui. 

Per illustrare, si supponga che il fornitore 1001 e il cliente US-008 siano la stessa entità, in modo che l'organizzazione desideri compensare i saldi contabilità fornitori e contabilità clienti prima di pagare/ricevere il saldo residuo. Si supponga che il record cliente deve 75,00 EUR e al record fornitore spettano 100,00 EUR e che si preferisce compensare i saldi e pagare al fornitore solo 25,00 EUR. Si supponga inoltre che la valuta di contabilizzazione sia EUR. In questo caso, una transazione di compensazione viene immessa in un giustificativo nel giornale di registrazione pagamenti contabilità fornitori.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Giustificativo** | **Tipo di conto** | **Conto** | **Descrizione** | **Dare** | **Avere** | **Tipo contropartita** | **Conto di contropartita** |
| APPAYM001   | Fornitore           | 1001        | Compensazione         |  75,00    |            | Cliente        | US-008             |

Per evitare problemi indesiderati con le liquidazioni future per la transazione, anziché utilizzare un giustificativo, è possibile inserire nel giornale di registrazione più giustificativi per registrare la transazione di compensazione. Si noti che i saldi cliente e fornitore vengono compensati con un singolo conto di compensazione per evitare l'utilizzo di un giustificativo contenente più saldi cliente e fornitore.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Giustificativo** | **Tipo di conto** | **Conto** | **Descrizione** | **Dare** | **Avere** | **Tipo contropartita** | **Conto di contropartita** |
| 001         | Cliente         | US-008      |                 |           |  75,00     | Contabilità generale          | 999999---          |
| 002         | Fornitore           | 1001        |                 |  75,00    |            | Contabilità generale          | 999999---          |





