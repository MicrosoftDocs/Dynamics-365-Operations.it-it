---
title: Impostare l'analisi Recency, di frequenza e monetaria (RFM)
description: In questo argomento viene illustrato come impostare un'analisi Recency, Frequency and Monetary (RFM) dei clienti.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRRFMDefinition
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c7cb79fa82b579bee01e51cb635597cc5f711a98
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413531"
---
# <a name="set-up-recency-frequency-and-monetary-rfm-analysis"></a>Impostare l'analisi Recency, di frequenza e monetaria (RFM)

[!include [banner](includes/banner.md)]

In questo argomento viene illustrato come impostare un'analisi Recency, Frequency and Monetary (RFM) dei clienti.

L'analisi di recency, di frequenza e monetaria (RFM) è uno strumento di marketing che l'organizzazione può utilizzare per valutare i dati generati dagli acquisti dei clienti. Dopo aver impostato l'analisi RFM, ai clienti viene assegnato un punteggio calcolato RFM mentre eseguono gli acquisti. Il punteggio RFM può essere una valutazione a tre cifre o un numero di aggregazione a seconda del modo in cui l'organizzazione ha configurato l'analisi RFM. Di seguito viene illustrata la determinazione prezzo se l'organizzazione utilizza una valutazione di tre cifre per il punteggio:

- La prima cifra corrisponde alla valutazione di recency del cliente, ovvero quando il cliente ha effettuato l'ultimo acquisto dall'organizzazione.
- La seconda cifra è la valutazione della frequenza del cliente: con quale frequenza il cliente effettua gli acquisti dall'organizzazione.
- La terza cifra indica la valutazione monetaria del cliente: quanto spende il cliente quando effettua acquisti dall'organizzazione.

Si supponga, ad esempio, che l'organizzazione abbia impostato le valutazioni su una scala da 1 a 5, dove 5 è la valutazione più alta. In questo caso, la valutazione di 535 di un cliente fornisce le seguenti informazioni sul cliente:

- **Valutazione di recency di 5**: il cliente ha effettuato un acquisto recentemente.
- **Valutazione di frequenza di 3**: il cliente acquista prodotti dall'organizzazione abbastanza spesso.
- **Valutazione monetaria di 5**: quando il cliente effettua un acquisto, spende una cifra significativa.

Se l'organizzazione utilizza un numero di aggregazione per il punteggio, le singole valutazioni vengono sommate insieme. Se consideriamo lo stesso esempio, il cliente ha una valutazione pari a 13 (5 + 3 + 5).

## <a name="set-up-rfm-analysis-for-the-customers-in-your-organization"></a>Impostare analisi RFM per i clienti nell'organizzazione

1. Passare a **Servizio clienti** \> **Periodico** \> **Analisi RFM**.
2. Nella pagina **Analisi RFM** selezionare **Nuovo**. Nel campo **Definizione RFM** immettere un nome descrittivo per la definizione RFM. Ad esempio, è possibile chiamare la definizione RFM-A.
3. Immettere una data di inizio e di fine per questa definizione RFM.
4. Nella scheda dettaglio **Generale** eseguire le operazioni seguenti:

    - Se ogni sezione del punteggio RFM deve contenere un conteggio uguale di clienti, selezionare la casella di controllo **Distribuzione uniforme**.
    - Selezionare la casella di controllo **Aggiungi punteggi** per aggregare i tre punteggi. Ad esempio, questo fornirebbe a un cliente un punteggio RFM di 13 anziché di 535.
    - Selezionare la casella di controllo **Salva storico** per richiedere al sistema di salvare i dati statistici per i clienti in modo da poter utilizzare i dati per calcolare il punteggio RFM.

5. Nella scheda dettaglio **Recency** eseguire le operazioni seguenti:

    - Nel campo **Divisioni** immettere il numero di divisioni o gruppi, che verranno utilizzati per calcolare il punteggio di recency per i clienti. Ad esempio, se si dispone di 100 clienti, una divisione di 5 indica che ci sono 20 clienti per ogni punteggio. I 20 clienti che hanno effettuato acquisti più di recente hanno un punteggio di recency di 5. I successivi 20 clienti hanno un punteggio di recency di 4, e così via. Se ci sono 50 clienti, 10 hanno un punteggio di recency di 5, 10 hanno punteggio di recency di 4 e così via.
    - Nel campo **Priorità** selezionare il peso da assegnare al parametro di recency rispetto agli altri parametri quando viene calcolato il punteggio RFM per un cliente. Ad esempio, è possibile dare più valore al punteggio di recency rispetto al punteggio monetario.
    - Nel campo **Moltiplicatore** immettere il valore per cui moltiplicare il punteggio di recency. Se non si immette alcun valore, il punteggio non viene moltiplicato.
    - Nel campo **Periodo** selezionare il periodo di tempo per cui viene calcolato il punteggio di recency. Ad esempio, per settimana o per mese.

6. Nella scheda dettaglio **Frequenza** eseguire le operazioni seguenti:

    - Nel campo **Divisioni** immettere il numero di divisioni o gruppi, che verranno utilizzati per calcolare il punteggio di frequenza per i clienti.
    - Nel campo **Priorità** selezionare il peso da assegnare al parametro di frequenza rispetto agli altri quando viene calcolato il punteggio RFM per un cliente.
    - Nel campo **Moltiplicatore** immettere il valore per cui moltiplicare il punteggio di frequenza. Se non si immette alcun valore, il punteggio non viene moltiplicato.

7. Nella scheda dettaglio **Monetario** eseguire le operazioni seguenti:

    - Nel campo **Divisioni** immettere il numero di divisioni o gruppi, che verranno utilizzati per calcolare il punteggio di monetario per i clienti.
    - Nel campo **Priorità** selezionare il peso da assegnare al parametro monetario rispetto agli altri quando viene calcolato il punteggio RFM per un cliente.
    - Nel campo **Moltiplicatore** immettere il valore per cui moltiplicare il punteggio monetario. Se non si immette alcun valore, il punteggio non viene moltiplicato.
    - Nel campo **Lordo/netto** selezionare se il punteggio monetario del cliente deve essere calcolato utilizzando l'importo fattura lordo o netto.
    - Se gli importi dei resi di un cliente devono essere sottratti dal calcolo totale della fattura cliente, selezionare la casella di controllo **Sottrai resti**.

## <a name="view-a-customers-rfm-score"></a>Visualizzare il punteggio RFM di un cliente

Utilizzare questa procedura per visualizzare il punteggio RFM di un cliente.

1. Passare a **Servizio clienti** \> **Giornali di registrazione** \> **Servizio clienti**.
2. Nela pagina **Servizio clienti**, nel riquadro **Servizio clienti**, nei campi di ricerca selezionare il tipo di parola chiave per eseguire la ricerca e immettere il testo di ricerca.
3. Selezionare **Cerca**.
4. Nella pagina **Ricerca cliente** selezionare il record cliente che si desidera e fare clic su **Seleziona cliente**.

Il punteggio RFM viene visualizzato nel gruppo **Storico ordini** sul lato destro del modulo **Servizio clienti**.

## <a name="view-or-clear-the-history-of-an-rfm-analysis-record"></a>Visualizzare o cancellare lo storico di un record di analisi RFM

Utilizzare questa procedura per visualizzare o cancellare lo storico di un record di analisi RFM.

1. Passare a **Servizio clienti** \> **Periodico** \> **Analisi RFM**.
2. Nella pagina **Analisi RFM** selezionare il record da visualizzare.
3. Per visualizzare lo storico del record, selezionare la scheda dettaglio **Storico**.
4. Per cancellare lo storico del record, selezionare la scheda dettaglio **Cancella storico**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]