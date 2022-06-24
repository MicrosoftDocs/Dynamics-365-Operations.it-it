---
title: Proposta della risoluzione del leasing
description: Questo articolo spiega come proporre un leasing per la risoluzione.
author: moaamer
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseTerminateLeaseListPage
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a5939f165943ff76ba453fb49d8c0c376c8ce4b1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879655"
---
# <a name="propose-a-lease-for-termination"></a>Proporre un leasing per la risoluzione

[!include [banner](../includes/banner.md)]

Se un leasing viene terminato anticipatamente, il leasing dei beni può registrare una risoluzione della scrittura contabile per annullare l'obbligazione sul leasing, asset Right of use (ROU) e l'ammortamento accumulato e prenotare un guadagno o una perdita. Il processo di risoluzione anticipata termina un leasing e i relativi libri di leasing associati. Non risolve i libri di leasing individuali. Questo articolo descrive la funzionalità che consente di proporre un leasing per la risoluzione e l'elaborazione della scrittura contabile del termine del leasing.

Se un leasing non è classificato come leasing per trattamento di passività sui contratti e non è associato a un cespite, il leasing di cespiti produce la seguente scrittura contabile del fine rapporto.

| Transazione                           | Dare (dr.) | Avere (cr.) |
|---------------------------------------|-------------|--------------|
| Obbligazione sul leasing dr.                   | X           |              |
| Ammortamento accumulato dr.          | X           |              |
| Profitti/Perdite per la modifica del leasing dr. | X           |              |
| Cespite di leasing cr.                       |             | X            |
| Profitti/Perdite per la modifica del leasing cr. |             | X            |

Se il libro del leasing è classificato come libro di passività sui contratti, la voce cancella il saldo della passività sui contratti prima della cessazione a conto profitti o perdite, come illustrato di seguito.

| Transazione                           | Dare (dr.) | Avere (cr.) | 
|---------------------------------------|-------------|--------------|
| Passività sui contratti dr.                     | X           |              |
| Profitti/Perdite per la modifica del leasing cr. |             | X            |
| Passività sui contratti cr.                     |             | X            |
| Profitti/Perdite per la modifica del leasing dr. | X           |              |

Se il libro di leasing è collegato a un cespite, il cespite ROU viene contabilizzato in Cespiti. Questa contabilità include la contabilizzazione delle cessazioni anticipate. Il leasing di cespiti produce la seguente scrittura contabile per cancellare l'obbligazione sul leasing.

| Transazione                           | Dare (dr.) | Avere (cr.) |
|---------------------------------------|-------------|--------------|
| Obbligazione sul leasing dr.                   | X           |              |
| Profitti/Perdite per la modifica del leasing cr. |             | X            |

Per informazioni sul modo corretto di smaltire un cespite ROU, vedi [Smaltire un cespite come scarto](../fixed-assets/dispose-of-a-fixed-asset-as-scrap.md).

## <a name="propose-a-lease-for-termination"></a>Proporre un leasing per la risoluzione

1. Passare al leasing che deve essere terminato e quindi, nel riquadro azioni, seleziona **Proposta di risoluzione**.

    > [!NOTE]
    > Il pulsante **Proposta di risoluzione** non è disponibile se sono presenti voci del giornale di registrazione non registrate per qualsiasi libro. Prima di poter terminare il leasing, è necessario registrare o eliminare tutte le voci del giornale di registrazione che sono state create per il leasing.

2. Nella finestra di dialogo che viene visualizzata, imposta i campi **Data effettiva** e **Data pubblicazione** per la scrittura contabile del termine del leasing.
3. Seleziona **Proposta di risoluzione** per proporre il termine del leasing.
4. Seleziona **Pubblica risoluzione leasing** per registrare automaticamente la scrittura contabile del termine del leasing.
5. Nella pagina **Risoluzioni leasing**, seleziona l'ID del leasing proposto per la risoluzione per visualizzare le righe di risoluzione. Le righe di risoluzione mostrano i valori contabili cespite ROU, obbligazione sul leasing, ammortamento accumulato, passività sui contratti (se applicabile) e profitti o perdite che devono essere rilevati alla cessazione del leasing.

Il contratto di leasing è ora pronto per la risoluzione. Il valore del campo **Stato risoluzione** del libro di leasing viene modificato in **Pronto per la risoluzione**. A questo punto, non è più possibile registrare voci di giornale a fronte del leasing, modificarlo o comprometterlo. 

## <a name="process-leases-that-are-ready-for-termination"></a>Elaborare i leasing pronti per la risoluzione

Per elaborare i leasing pronti per la risoluzione e registrare la scrittura contabile della risoluzione, seguire questi passaggi.

1. Nella pagina **Risoluzioni leasing**, seleziona il leasing da elaborare, quindi seleziona **Termina**.
2. Nella finestra di dialogo visualizzata, selezionare **OK**.

Il sistema registra la scrittura contabile della risoluzione. Il campo **Stato di leasing** per il libro di leasing è impostato su **Terminato** e il campo **Stato della proposta di risoluzione** è impostato su **Completato**.

## <a name="reverse-a-lease-termination"></a>Annullare una risoluzione del leasing

Per annullare una scrittura contabile della risoluzione del leasing e aprire un leasing terminato, segui questo passaggio.

- Nella pagina **Risoluzioni leasing**, seleziona il leasing terminato da annullare, quindi seleziona **Annulla risoluzione**.

Il sistema annulla la scrittura contabile della risoluzione. Il campo **Stato di leasing** per il libro di leasing è impostato su **Aperto**. Il contratto di leasing non compare più nella pagina **Risoluzioni leasing** e può essere riproposto per la risoluzione.

## <a name="example-of-a-lease-termination"></a>Esempio di risoluzione del contratto di leasing

Per questo esempio, il leasing è un associato a un cespite non specializzato e non trasferisce la proprietà del cespite né concede al locatario l'opzione di acquisto del cespite.

### <a name="setup"></a>Attrezzaggio

Le tabelle seguenti mostrano i valori impostati nelle schede **Generale** e **Righe scadenzario pagamenti** per il leasing utilizzato in questo esempio.

**Scheda Generale**

| Campo                      | Valore            |
|----------------------------|------------------|
| Valore equo del cespite    | 600,000          |
| Valuta                   | USD              |
| Costi diretti iniziali       | 1.000            |
| Tasso incrementale di prestito | 7%               |
| Intervallo interessi composti       | Annualmente         |
| Vita utile cespite (mesi) | 600              |
| Tipo di rendita finanziaria               | Rendita finanziaria posticipata |
| Data di inizio          | 1/1/2019         |

**Scheda Righe scadenzario pagamenti**

| Campo             | Valore      |
|-------------------|------------|
| Data di inizio        | 1/1/2019   |
| Intervallo periodico   | Ogni mese    |
| Periodi           | 120        |
| Data di fine          | 31/12/2028 |
| Frequenza pagamenti | Annualmente   |
| Importo pagamento    | 10,000     |

### <a name="steps-for-terminating-the-lease"></a>Passaggi per la risoluzione del leasing

1. Dopo aver creato il leasing come descritto in precedenza in questo articolo, vai al libro dei leasing e conferma lo scadenziario dei pagamenti. Quindi registra la scrittura contabile del riconoscimento iniziale. Il cespite ROU iniziale è $ 71.235,81 e l'obbligazione sul leasing dovrebbe essere pari a $ 70.235,81. In questo esempio, il leasing è stato classificato come leasing operativo ai sensi dell'Accounting Standards Codification Topic 842 (ASC 842).
2. Esegui il processo di registrazione batch tre volte per simulare il passaggio di tre anni per i canoni di leasing, gli interessi passivi e le spese di ammortamento.
3. Dopo aver terminato l'esecuzione di tutti e tre i processi batch, torna al libro dei leasing e aprire le tabelle delle transazioni delle passività e dei cespiti per visualizzare il valore contabile corrente dell'asset ROU e dell'obbligazione sul leasing. Dopo tre anni, il valore della passività dovrebbe essere di circa $ -53.893,00 e il valore del cespite dovrebbe essere di circa $54.593,00.

    Trascorsi i tre anni, l'azienda e il locatore si accordano reciprocamente per risolvere il contratto di leasing. Pertanto, è ora necessario terminare il contratto di leasing.

4. Passare al leasing che deve essere terminato e quindi, nel riquadro azioni, seleziona **Proposta di risoluzione**. 
5. Nella finestra di dialogo che viene visualizzata, nei campi **Data effettiva** e **Data pubblicazione**, inserisci **1/1/2021**.
6. Seleziona **Proposta di risoluzione** per proporre il termine del leasing.

    Viene visualizzata la pagina **Risoluzioni leasing** e mostra il leasing che verrà terminato.

7. Per visualizzare le righe di risoluzione, seleziona l'ID del leasing proposto per la risoluzione. Le righe di risoluzione mostrano i valori contabili del leasing. La tabella seguente mostra quali dovrebbero essere questi valori per questo esempio. 

    | Campo                                                 | Valore      |
    |-------------------------------------------------------|------------|
    | Saldo contabile delle passività nella valuta della transazione | $ 53.892,89 |
    | Asset Right of use in valuta della transazione            | $ 71.235,81 |
    | Ammortamento accumulato in valuta della transazione      | $ 16.642,92 |
    | Profitti (perdite) in valuta di transazione                   | $ 700,00   |

8. Per registrare la scrittura contabile della risoluzione, seleziona il leasing nella pagina **Risoluzioni leasing**, quindi seleziona **Termina**.
9. Nella finestra di dialogo visualizzata, selezionare **OK**.
10. Per visualizzare la scrittura contabile della risoluzione che è stata creata e registrata, accedi al giornale del leasing del cespite nel libro di leasing. La tabella seguente mostra come questa voce dovrebbe essere per questo esempio.

    | Transazione                           | Dare (dr.) | Avere (cr.) |
    |---------------------------------------|-------------|--------------|
    | Obbligazione sul leasing dr.                   | 53,892.89   |              |
    | Ammortamento accumulato dr.          | 16,642.92   |              |
    | Profitti/Perdite per la modifica del leasing dr. | 700.00      |              |
    | Cespite di leasing cr.                       |             | 71,235.81    |

11. Per visualizzare l'effetto netto della risoluzione, dove il cespite ROU e l'obbligazione sul leasing sarà 0 (zero), apri le tabelle Passività e Transazioni attività.

Lo stato del leasing dovrebbe ora essere **Terminato**. Non verranno registrate voci aggiuntive per questo leasing a meno che la risoluzione non venga annullata.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
