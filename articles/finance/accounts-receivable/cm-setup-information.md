---
title: Impostazione di Gestione crediti
description: Questo argomento descrive l'impostazione di Gestione crediti.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: d1d33dbbd37daaa75f4b64359194a2328728b27f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444655"
---
# <a name="credit-management-setup"></a>Impostazione di Gestione crediti 

[!include [banner](../includes/banner.md)]

## <a name="credit-management-workflows"></a>Flussi di lavoro di gestione crediti

Andare **Credito e riscossioni \> Impostazione \> Flussi di lavoro di gestione crediti** per definire i flussi di lavoro utilizzati per gestire le correzioni del limite di credito.

- È possibile creare un flusso di lavoro che consente di approvare un batch di correzioni del limite di credito mediante un'unica approvazione.
- È possibile aggiungere un flusso di lavoro a livello di riga, di modo che le correzioni del limite di credito possano essere approvate individualmente.
- È possibile creare un flusso di lavoro di rilascio che instrada automaticamente le sospensioni a un processo del flusso di lavoro.

## <a name="blocking-rules"></a>Regole di bloccaggio

### <a name="ranking-payment-terms"></a>Classificazione dei termini di pagamento

È possibile mettere in attesa un ordine cliente se i termini di pagamento nell'ordine non corrispondono ai termini di pagamento predefiniti per il cliente. A volte, tuttavia, i termini di pagamento differiscono ma sono abbastanza simili, a tal punto che non si intende mettere in attesa l'ordine. È possibile classificare i termini di pagamento di modo che alcuni abbiano la stessa classificazione, mentre per altri la classificazione sia superiore o inferiore.

Se le classificazioni per i termini di pagamento sono attive e se i termini di pagamento nell'ordine hanno una classificazione superiore rispetto ai termini di pagamento predefiniti per il cliente, l'ordine cliente viene messo in attesa.

Per impostare la classificazione dei termini di pagamento andare a **Credito e riscossioni \> Impostazione \> Impostazione gestione crediti \>Classifica termini di pagamento**  

### <a name="ranking-settlement-discounts"></a>Classificazione degli sconti di liquidazione

È possibile mettere in attesa un ordine cliente se lo sconto di cassa nell'ordine non corrisponde a quello per il cliente. A volte, tuttavia, gli sconti di cassa differiscono ma sono abbastanza simili, a tal punto che non si intende mettere in attesa l'ordine. È possibile classificare gli sconti di cassa di modo che alcuni abbiano la stessa classificazione, mentre per altri la classificazione sia superiore o inferiore.

Se le classificazioni per gli sconti di liquidazione sono attive e se lo sconto di cassa nell'ordine ha una classificazione superiore rispetto allo sconto di cassa predefinito per il cliente, l'ordine cliente verrà messo in attesa.

Per impostare la classificazione dei termini di pagamento andare a **Credito e riscossioni \> Impostazione \> Impostazione gestione crediti \>Classifica sconti liquidazione**  

## <a name="reasons"></a>Motivi

Diversi tipi di motivi sono utilizzati in Gestione crediti:

- I motivi di sospensione indicano perché un ordine cliente è stato messo in attesa.
- I motivi di rilascio vengono assegnati a un ordine quando viene rilasciato dalla sospensione.
- I motivi di stato indicano perché uno stato dell'account è stato assegnato a un cliente.

È possibile impostare i motivi nella pagina **Motivi gestione crediti** (**Credito e riscossioni \> Impostazione \> Impostazione gestione crediti \> Motivi gestione crediti**).

1. Nel campo **Tipo di motivo**, selezionare il tipo di motivo: **Sospensione**, **Rilascio** o **Stato**.
2. Nel campo **Motivo** immettere un nome per il motivo.
3. Nel campo **Descrizione** immettere una descrizione del codice motivo.

## <a name="credit-management-groups"></a>Gruppi di gestione crediti

I gruppi di gestione crediti sono utilizzati per identificare clienti o gruppi di clienti che hanno le stesse proprietà di gestione crediti. Ad esempio, i gruppi di gestione crediti possono essere utilizzati per determinare le regole di blocco ed esclusione di gestione crediti per i clienti.

È possibile creare gruppi di gestione crediti nella pagina **Gruppi di gestione crediti** (**Credito e riscossioni \> Impostazione > Impostazione gestione crediti \> Gruppi di gestione crediti**).

1. Selezionare **Nuovo** per creare una riga.
2. Immettere l'ID per il gruppo. L'ID può avere fino a 10 caratteri.
3. Nel campo **Descrizione** immettere un nome per il gruppo. Il nome può avere fino a 60 caratteri.

Il gruppo di gestione crediti viene assegnato a un cliente nella scheda dettaglio **Credito e riscossioni** della pagina **Tutti i clienti** (**Contabilità clienti \> Clienti \> Tutti i clienti**).

## <a name="account-statuses"></a>Stati conto

È possibile creare stati di conto per identificare la solvibilità di un conto cliente. È possibile definire uno stato e il relativo effetto sui processi di fatturazione e consegna sospesa. Gli stati di conto possono anche essere utilizzati per determinare le regole di blocco per un cliente.

È possibile creare stati di conto nella pagina **Stati conto** (**Credito e riscossioni \> Impostazione > Impostazione gestione crediti \> Stati conto**).

1. Aggiungere uno stato di conto e inserire una descrizione che rappresenti la solvibilità di un cliente. Ad esempio, utilizzare **Normale** per indicare che la solvibilità di un cliente è buona e che gli ordini aperti sono soggetti a un'elaborazione standard della gestione dei crediti.
2. Nei campi **Fatturazione** e **Consegna sospesa**, selezionare il tipo di sospensione che dovrebbe verificarsi per i clienti con questo stato di conto. È possibile sospendere tutta l'elaborazione, solo l'elaborazione delle fatture o nessuna elaborazione quando vengono applicate le regole del limite di credito.

## <a name="scoring-groups"></a>Gruppi di punteggio

È possibile impostare gruppi di punteggio per definire i fattori di rischio e i criteri utilizzati per misurarli. Quando le informazioni su un cliente vengono applicate a un gruppo di punteggio, viene calcolato un punteggio per ciascun fattore di rischio e utilizzato per inserire il cliente in un gruppo di rischio. Il gruppo di rischio può essere utilizzato per identificare l'affidabilità creditizia e calcolare limiti di credito automatici.

È possibile creare gruppi di punteggio nella pagina **Gruppi di punteggio** (**Credito e riscossioni \> Impostazione \> Impostazione gestione crediti \> Rischio \> Gruppi di punteggio**).

1. Creare un gruppo di punteggio e assegnargli un nome.
2. Immettere una descrizione per descrivere ulteriormente il gruppo di punteggio.
3. Selezionare un tipo di gruppo. Esistono otto tipi predefiniti. È anche possibile selezionare **Definito dall'utente** per definire un tipo di gruppo più adatto alla propria organizzazione.
4. Selezionare un tipo di punteggio per definire il modo in cui il gruppo di punteggio calcola il punteggio di rischio. Di seguito vengono illustrate le opzioni disponibili.

    - **Intervallo** - Utilizzare questa opzione per definire un intervallo di valori che devono essere utilizzati per calcolare un punteggio.
    - **Definiti dall'utente** - Utilizzare questa opzione per definire manualmente un elenco di valori che devono essere utilizzati per il punteggio.

5. Se si seleziona **Intervallo** come tipo di punteggio, aggiungere righe per definire l'intervallo di valori e i punteggi corrispondenti.

    1. Nel campo **Dal valore**, specificare il valore più basso nell'intervallo.
    2. Nel campo **Al valore**, specificare il valore più alto nell'intervallo.
    3. Nel campo **Punteggio**, immettere il punteggio che deve essere assegnato quando il valore fornito è compreso nell'intervallo "da"/"a".

    Se si seleziona **Definiti dall'utente** come tipo di punteggio, aggiungere righe per definire i valori definiti dall'utente e i punteggi corrispondenti.

    1. Nel campo **Valore**, immettere il valore definito dall'utente che deve essere fornito dalle informazioni sul cliente.
    2. Nel campo **Punteggio**, immettere il punteggio che deve essere assegnato quando il valore fornito è compreso nell'intervallo "da"/"a".

## <a name="risk-classification"></a>Classificazione rischio

È possibile definire le valutazioni del rischio che possono essere assegnate ai clienti, in base al relativo punteggio di rischio. Un punteggio di rischio viene calcolato confrontando le informazioni sui clienti a ciascun gruppo di punteggio. I punteggi vengono sommati e il punteggio totale viene confrontato ai valori nell'impostazione dei gruppi di rischio per identificare il gruppo di rischio a cui appartiene il cliente. Il punteggio del gruppo di rischio viene quindi utilizzato per definire le regole di blocco ed esclusione della gestione dei crediti per il cliente.

È possibile impostare gruppi di rischio nella pagina **Valutazioni del rischio** (**Credito e riscossioni \> Impostazione \> Impostazione gestione crediti \> Rischio \> Classificazione rischio**).

1. Immettere un ID gruppo di rischio.
2. Immettere una descrizione per descrivere ulteriormente il gruppo di rischio.
3. Immettere un intervallo di punteggi utilizzato per determinare quali clienti appartengono al gruppo a rischio.
4. Selezionare un indicatore di gruppo di rischio per specificare il simbolo che rappresenta il gruppo di rischio.

## <a name="guaranteeinsurance-types"></a>Tipi di garanzie/assicurazioni

È possibile impostare i tipi di garanzie/assicurazioni nella pagina **Tipi di garanzie/assicurazioni** (**Credito e riscossioni \> Impostazione \> Impostazione gestione crediti \> Assicurazione e garanzie \> Tipi di garanzie e assicurazioni**).

1. Immettere un tipo di garanzia o assicurazione che identifichi il nome del garante o del broker assicurativo.
2. Immettere una descrizione per descrivere il garante/broker assicurativo.

## <a name="coverage-types"></a>Tipi di copertura

I tipi di copertura possono essere utilizzati per classificare ulteriormente le polizze assicurative. Non possono essere utilizzati con le garanzie.

È possibile aggiungere tipi di copertura nella pagina **Tipi di copertura** (**Credito e riscossioni \> Impostazione \> Impostazione gestione crediti \> Assicurazione e garanzie \> Tipi di copertura**).

1. Immettere un tipo di copertura per identificare il tipo di copertura da aggiungere come assicurazione o garanzia.
2. Immettere una descrizione del tipo di copertura.

## <a name="automatic-credit-limits"></a>Limiti di credito automatici

È possibile creare criteri per limiti di credito automatici nella pagina **Limiti di credito automatici** (**Credito e riscossioni \> Impostazione \> Impostazione gestione crediti \> Rischio \> Limiti di credito automatici**).

1. Selezionare un gruppo di rischio a cui assegnare il limite di credito automatico.
2. Seleziona la valuta per il limite di credito automatico. È possibile creare più limiti di credito automatici in valute diverse per lo stesso gruppo di rischio.
3. Immettere l'importo dei ricavi che rappresenta i ricavi aziendali massimi utilizzabili per questo limite di credito automatico. Quando si creano i limiti di credito, l'importo dei ricavi viene confrontato a il valore dei ricavi indicato nella pagina **Dati finanziari** (**Contabilità clienti \> Tutti i clienti \> Seleziona un cliente \> Generale \> Statistiche \> Dati finanziari**). Il sistema utilizza l'ultimo valore nella sezione **Panoramica**.

Attenersi alla seguente procedura per aggiungere righe che rappresentano il limite di credito che verrà generato in base ai criteri selezionati.

1. Seleziona il gruppo di punteggio che definisce le informazioni sul cliente che devono essere utilizzate per calcolare il limite di credito.
2. Selezionare l'operatore di confronto che definisce come valutare le informazioni del gruppo di punteggio.
3. Immettere il valore che deve essere confrontato al valore specificato per il gruppo di punteggio.
4. Immettere il limite di credito che deve essere assegnato se le informazioni sul cliente corrispondono al valore specificato per il gruppo di punteggio. Ad esempio, si crea un limite di credito automatico per il gruppo di punteggio **Basso**. Se gli anni di attività sono uno dei gruppi di punteggio, è possibile definire una riga che assegna un limite di credito di 100.000 se il cliente è in attività da cinque anni e un'altra riga che assegna un limite di credito di 200.000 se il cliente è in attività da 10 anni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]