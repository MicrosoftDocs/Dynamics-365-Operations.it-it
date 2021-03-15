---
title: Ridurre asset Right of use
description: Questo argomento descrive la funzionalità che registra una riduzione di valore e regola il piano di ammortamento dei cespiti di un leasing Accounting Standards Codification Topic 842 (ASC 842) operativo.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9822a11dbb277726b60ff82843bd26314e968345
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003258"
---
# <a name="impair-right-of-use-assets"></a>Ridurre asset Right of use

[!include [banner](../includes/banner.md)]

Se il valore contabile di un asset Right of use non è recuperabile, potrebbe essere necessario verificare se i cespite ha subito una riduzione di valore. Se si determina che il cespite ha subito una riduzione di valore, Leasing cespite può registrare la riduzione di valore e rettificare il piano di ammortamento di conseguenza. Questo argomento descrive la funzionalità che registra una riduzione di valore e regola il piano di ammortamento di un leasing Accounting Standards Codification Topic 842 (ASC 842) operativo. Lo stesso metodo si applica anche ai leasing dell'International Financial Reporting Standard 16 (IFRS 16).

Il saldo residuo dell'asset ROU sarà ammortizzato a quote costanti per il numero di periodi rimanenti, indipendentemente dal fatto che il leasing sia stato classificato come leasing finanziario secondo l'IFRS 16 o come leasing operativo secondo ASC 842.

## <a name="impair-an-rou-asset"></a>Ridurre un asset ROU

1. Vai al leasing con valore ridotto e seleziona **Libri**.
2. Nel riquadro azioni, seleziona **Riduzione del valore**.
3. Nella finestra di dialogo che appare, nel campi **Importo di riduzione**, immetti l'importo della riduzione di valore del cespite. Per diminuire l'asset ROU, è necessario immettere un valore positivo.
4. Nel campo **Data della transazione** immetti la data in cui deve essere registrato il movimento di riduzione del valore.
5. Nel campo **Periodi rimanenti**, immetti il numero di mesi rimanenti da ammortizzare.
6. Attiva il parametro **Registra** se desideri che il sistema registri automaticamente la scrittura contabile della spese di riduzione del valore. Se lasci questo parametro disattivato, il sistema crea il movimento ma non lo registra. Puoi quindi registrare la voce dalla pagina **Giornali di registrazione leasing di cespiti**.
7. Imposta l'opzione **Visualizza anteprima prima della registrazione** su **Sì** per visualizzare la voce proposta prima che venga creata o registrata.
8. Imposta l'opzione **Chiudi libro** su **Sì** per chiudere il libro di leasing. Non è possibile annullare questa azione. Le voci non possono essere registrate a fronte di contratti di leasing chiusi e i leasing chiusi non possono essere rettificati.
9. Seleziona **OK** per creare o registrare la voce di riduzione del valore.
10. Per visualizzare il piano di ammortamento dei cespiti con riduzione del valore, apri il piano di ammortamento dei cespiti per tale libro di leasing. Il cespite verrà ora ammortizzato a quote costanti per il numero di mesi immesso nel campo **Periodi rimanenti**.
11. Per visualizzare la scrittura contabile di spesa per riduzione di valore, seleziona **Giornale di registrazione leasing cespite** nel riquadro azioni del libro di leasing con riduzione del valore. Il sistema crea una scrittura contabile che addebita il conto di registrazione delle spese di riduzione del valore e accredita il conto di registrazione del cespite del leasing.
12. Per visualizzare il nuovo valore contabile dell'asset ROU, seleziona **Transazioni cespiti** nel riquadro azioni del libro di leasing.

## <a name="example-of-rou-asset-impairment"></a>Esempio di riduzione del valore dell'asset ROU

Per questo esempio, il leasing è un cespite non specializzato che non trasferisce la proprietà né concede al locatario l'opzione di acquisto.

### <a name="setup"></a>Attrezzaggio

Le tabelle seguenti mostrano i valori impostati nelle schede **Generale** e **Righe scadenzario pagamenti** per il leasing utilizzato in questo esempio.

**Scheda Generale**

| Campo                      | Valore            |
|----------------------------|------------------|
| Valore equo del cespite    | 600,000          |
| Tasso incrementale di prestito | 7%               |
| Intervallo interessi composti       | Annualmente         |
| Vita utile cespite (mesi) | 600              |
| Tipo di rendita finanziaria               | Rendita finanziaria posticipata |
| Data di inizio          | 01/01/2019       |

**Scheda Righe scadenzario pagamenti**

| Campo             | Valore      |
|-------------------|------------|
| Data di inizio        | 1/1/2019   |
| Intervallo periodico   | Ogni mese    |
| Periodi           | 120        |
| Data di fine          | 31/12/2028 |
| Frequenza pagamenti | Annualmente   |
| Importo pagamento    | 10,000     |

### <a name="steps"></a>Gradi

1. Dopo aver creato il leasing come descritto in precedenza in questo argomento, vai al libro dei leasing e conferma lo scadenziario dei pagamenti. Quindi registra la scrittura contabile del riconoscimento iniziale. L'asset ROU iniziale e l'obbligazione sul leasing dovrebbero essere pari a $70.235,81. In questo esempio, il leasing è stato classificato come leasing operativo ai sensi di ASC 842.
2. Esegui il processo di registrazione batch tre volte per simulare il passaggio di tre anni per i canoni di leasing, gli interessi passivi e le spese di ammortamento.
3. Dopo aver terminato l'esecuzione di tutti e tre i processi batch, torna al libro dei leasing e aprire le tabelle delle transazioni delle passività e dei cespiti per visualizzare il valore contabile corrente dell'asset ROU e dell'obbligazione sul leasing. Dopo tre anni, il valore della passività dovrebbe essere di circa $ -53.893,00 e il valore del cespite dovrebbe essere di circa $53.893,00. 

    Dopo tre anni, l'azienda esegue test di riduzione del valore e determina che l'asset ROU ha una riduzione del valore di $35.000. Ora devi registrare questa riduzione del valore.
    
4. Vai al libro di leasing e quindi, nel riquadro azioni, seleziona **Riduzione del valore**.
5. Nella pagina **Parametro di riduzione del valore**, immetti i seguenti dettagli.

    | Campo                  | Valore    |
    |------------------------|----------|
    | Importo di svalutazione      | 35,000   |
    | Data transazione       | 1/1/2022 |
    | Periodi rimanenti      | 84       |
    | Registra                   | Sì      |
    | Visualizza anteprima prima della registrazione | Nessuno       |
    | Chiudi libro             | Nessuno       |

6. Una scrittura contabile di spesa per riduzione del valore è stata creata e registrata. Per visualizzarla, accedi al giornale di registrazione dei leasing del cespite nel libro di leasing. Tieni presente che l'importo della riduzione di valore è stato addebitato sul conto di registrazione delle spese di riduzione di valore ed è stato accreditato sul conto di registrazione dell'asset ROU.
7. Per visualizzare l'effetto netto della riduzione del valore, consulta le tabelle delle transazioni di passività e attività. Tien presente che la spesa per riduzione di valore ha diminuito l'asset ROU, ma il valore contabile dell'obbligazione sul leasing non è cambiato.

La riduzione del valore ha un altro effetto che dovresti considerare. Poiché l'importo dell'asset ROU è ora molto inferiore all'obbligazione sul leasing, l'importo deve essere ammortizzato in modo diverso rispetto a prima. In particolare, il cespite viene ora ammortizzato in modo lineare durante i restanti 84 mesi di leasing, a partire dalla data di transazione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]