---
title: Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno
description: Questo articolo fornisce informazioni sui miglioramenti che influiscono sulle liquidazioni di saldi contabili e sulla chiusura di fine anno della contabilità generale.
author: kweekley
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: b0c454745bc02a101514d44a20bd47dad0c548d5
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815685"
---
# <a name="awareness-between-ledger-settlement-and-year-end-close"></a>Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno

[!include [banner](../includes/banner.md)]


In Microsoft Dynamics 365 Finance versione 10.0.25, la funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno** è disponibile nell'area di lavoro **Gestione funzionalità**. Questa funzionalità aggiunge due miglioramenti principali che influiscono sulla liquidazione dei saldi contabili e sulla chiusura di fine anno della contabilità generale.

Durante la chiusura di fine anno della contabilità generale, le transazioni contabili che sono state liquidate non saranno più incluse nel saldo iniziale dell'anno fiscale successivo. Questo miglioramento garantisce che solo le transazioni contabili non liquidate siano incluse nel saldo iniziale. È importante quando viene eseguita la rivalutazione della valuta estera della contabilità generale. La rivalutazione della valuta estera viene eseguita solo per le transazioni contabili con stato di **Non liquidato**. Tuttavia, prima che fosse rilasciata la funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno**, il saldo iniziale riepilogava entrambe le transazioni con uno stato di **Liquidato** e quelle con lo stato di **Non liquidato** e lo stato dell'importo riepilogato era impostato su **Non liquidato**.

Il secondo miglioramento consente di registrare transazioni di saldo iniziale dettagliate durante la chiusura di fine anno della contabilità generale. Se l'opzione **Mantieni dettagli durante la chiusura di fine anno** è impostata su **Sì**, verrà creato un saldo iniziale separato per ogni transazione contabile non liquidata. Questa impostazione viene definita per ogni conto principale nell'impostazione della liquidazione dei saldi contabili. Mantenendo le transazioni dettagliate per il saldo iniziale, si migliora notevolmente la capacità di liquidare le transazioni contabili non liquidate nell'anno fiscale successivo.

Per supportare i nuovi miglioramenti, sono state apportate modifiche alla liquidazione dei saldi contabili e alla chiusura di fine anno.

### <a name="changes-to-ledger-settlement"></a>Modifiche alla liquidazione dei saldi contabili

- La liquidazione dei saldi contabili deve essere effettuata entro un anno fiscale.
- La liquidazione dei saldi contabili deve essere eseguita per le transazioni in un unico conto principale. Il conto principale è ora un filtro obbligatorio nella pagina **Compensazione dei saldi contabili**.
- La liquidazione dei saldi contabili e lo storno della liquidazione dei saldi contabili non possono essere effettuati per le transazioni registrate entro un anno fiscale chiuso (in altre parole, la chiusura di fine anno è stata eseguita).

### <a name="changes-to-year-end-close"></a>Modifiche alla chiusura di fine anno

- Una chiusura di fine anno non può essere stornata se le transazioni del saldo iniziale sono state liquidate nell'anno fiscale successivo. Questa modifica si applica quando una chiusura di fine anno viene stornata o quando una chiusura di fine anno viene rieseguita e l'opzione **Elimina le voci di fine anno esistenti quando si richiude l'anno** è impostata su **Sì** nei parametri di contabilità generale.
- Se l'opzione **Mantieni dettagli durante la chiusura di fine anno** è impostata su **Sì** per qualsiasi conto dello stato patrimoniale nella liquidazione dei saldi contabili, verranno create transazioni di saldo iniziale più dettagliate per quel conto principale.

## <a name="before-you-enable-the-feature"></a>Prima di abilitare la funzionalità

A causa delle modifiche alla funzionalità e al modello di dati, è importante considerare i seguenti punti prima di abilitare la funzionalità:

- Poiché solo le transazioni liquidate vengono anticipate nel saldo di apertura, è necessario annullare le transazioni dell'anno fiscale corrente che vengono liquidate con le transazioni dell'anno fiscale precedente. Le transazioni devono essere liquidate nuovamente rispetto alle transazioni entro l'anno fiscale in corso. Questo può essere fatto attraverso una voce di rettifica nell'anno fiscale in corso. La rettifica storna i saldi di apertura riepilogati e compensa con la transazione dettagliata necessaria per regolare le scritture contabili nell'anno in corso. 

  > [!IMPORTANT]
  > In caso contrario, riceverai un errore di **sbilanciamento** quando esegui la chiusura di fine anno per l'anno fiscale corrente. Se non è possibile annullare e reimpostare le transazioni contabili con lo stesso anno fiscale, non abilitare questa funzione fino al completamento della chiusura di fine anno. Abilita la funzione subito dopo il completamento della chiusura di fine anno e prima che le nuove transazioni contabili vengano liquidate nell'anno fiscale successivo. 
  
- Tutte le transazioni che sono state contrassegnate per la liquidazione ma non sono state liquidate verranno automaticamente deselezionate quando la funzionalità è abilitata. Per evitare qualsiasi perdita di lavoro, liquida tutte le transazioni contrassegnate prima di abilitare la funzionalità.
- Alcune organizzazioni eseguono la chiusura di fine anno più volte per lo stesso anno fiscale. Non abilitare la funzionalità se la chiusura di fine anno è già stata eseguita una volta e verrà eseguita nuovamente per lo stesso anno fiscale. La funzionalità deve essere abilitata prima di elaborare la prima chiusura di fine anno o dopo aver elaborato l'ultima chiusura di fine anno per l'anno fiscale.

  Se vuoi abilitare la funzionalità, ma la chiusura di fine anno è già stata eseguita una volta, è necessario stornare la chiusura di fine anno prima di poter abilitare la funzionalità.

- Poiché la liquidazione tra conti principali non è più consentita, modifica il piano dei conti o i processi come richiesto per garantire che la liquidazione dei saldi contabili possa essere eseguita nello stesso conto principale.
- La funzionalità può essere abilitata se viene utilizzato il processo di chiusura di fine anno del settore pubblico.

## <a name="set-up-ledger-settlement"></a>Impostare la liquidazione dei saldi contabili

Dopo aver abilitato la funzionalità e prima di eseguire la chiusura di fine anno successiva, ogni organizzazione deve determinare se manterrà i dettagli della transazione durante la chiusura di fine anno. La scelta non ha alcun impatto sulle registrazioni di saldi iniziali dei precedenti processi di chiusura di fine anno.

L'opzione **Mantieni dettagli durante la chiusura di fine anno** viene impostata per ogni conto principale nella pagina **Impostazione liquidazione saldi contabili**.

1.  Selezionare **Contabilità generale** > **Impostazione contabilità generale** > **Parametri di contabilità generale**.
2.  Nella scheda **Liquidazioni saldi contabili**, seleziona **Conti compensazione saldi contabili**.

oppure

1.  Passa a **Contabilità generale** > **Attività periodiche** > **Compensazioni dei saldi contabili**.
2.  Seleziona **Conti compensazione saldi contabili**.

Sono state aggiunte due colonne alla pagina **Compensazioni dei saldi contabili**:
    
- **Tipo di conto principale**: questa colonna è solo a scopo informativo. Mostra il tipo assegnato al conto principale.
- **Mantieni dettagli durante la chiusura di fine anno**: per impostazione predefinita, l'opzione è impostata su **No**. Può essere impostata su **Sì** solo se il valore nella colonna **Tipo di conto principale** è **Stato patrimoniale**, **Attività** o **Passività**. Quando l'opzione è impostata su **No**, i saldi iniziali saranno registrai nel riepilogo, come di consueto durante la chiusura di fine anno. Se è impostata su **Sì**, i saldi iniziali verranno creati in dettaglio per ogni transazione contabile non liquidata per il conto principale.

## <a name="year-end-close"></a>Chiusura di fine anno

Quando esegui la chiusura di fine anno passando a **Contabilità generale** > **Periodo chiuso** > **Chiusura di fine anno**, il processo crea i saldi iniziali per i conti principali definiti per la liquidazione dei saldi contabili. I saldi iniziali vengono creati in modo riepilogativo o dettagliato, a seconda dell'impostazione della liquidazione dei saldi contabili. Il processo esclude le transazioni contabili che vengono liquidate, indipendentemente dal fatto che si registri il saldo iniziale per ciascun conto principale in modo riepilogativo o dettagliato.

Ad esempio, più transazioni vengono registrate nel conto principale 130100 nell'anno fiscale 2021.

| Numero giornale di registrazione | Giustificativo  | Data       | Tipo      | Conto CoGe | Nome conto        | Description       | Valuta | Importo nella valuta della transazione | Importo  | Importo nella valuta di dichiarazione |
|----------------|----------|------------|-----------|----------------|---------------------|-------------------|----------|--------------------------------|---------|------------------------------|
| 20853          | FTV-3000 | 3/12/2021  | In funzione | 130100-001-    | Contabilità clienti | Tariffa per il servizio       | USD      | 100                            | 100     | 100                          |
| 20855          | FTV-3004 | 5/12/2021  | In funzione | 130100-002-    | Contabilità clienti | Utilità         | USD      | 175                            | 175     | 175                          |
| 20854          | CMV-4000 | 16/12/2021 | In funzione | 130100-001-    | Contabilità clienti | Rimborso            | USD      | -100                           | -100    | -100                         |
| 20851          | ARP-8000 | 20/12/2021 | In funzione | 130100-002-    | Contabilità clienti |                   | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 20/12/2021 | In funzione | 130100-002-    | Contabilità clienti |                   | EUR      | -127,11                        | -174,12 | -174,12                      |
| 20856          | CMV-4010 | 21/12/2021 | In funzione | 130100-002-    | Contabilità clienti | Conto in Avere | USD      | -175                           | -175    | -175                         |
| 20857          | FTV-3011 | 28/12/2021 | In funzione | 130100-001-    | Contabilità clienti | Utilità         | USD      | 400                            | 400     | 400                          |
| 20910          | FTV-3020 | 29/12/2021 | In funzione | 130100-002-    | Contabilità clienti | Assistenza           | USD      | 300                            | 300     | 300                          |

Di queste transazioni, tre vengono liquidate durante la liquidazione dei saldi contabili.

C'è una fattura per 175 dollari USA (175 USD). Questa fattura è stata pagata con un pagamento in euro (EUR) ed è stato applicato uno sconto in contanti.

| Numero giornale di registrazione | Giustificativo  | Data       | Tipo      | Conto CoGe | Nome conto        | Description | Valuta | Importo nella valuta della transazione | Importo  | Importo nella valuta di dichiarazione |
|----------------|----------|------------|-----------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20855          | FTV-3004 | 5/12/2021  | In funzione | 130100-002-    | Contabilità clienti | Utilità   | USD      | 175                            | 175     | 175                          |
| 20851          | ARP-8000 | 20/12/2021 | In funzione | 130100-002-    | Contabilità clienti |             | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 20/12/2021 | In funzione | 130100-002-    | Contabilità clienti |             | EUR      | -127,11                        | -174,12 | -174,12                      |

I risultati per il conto principale 130100 dipendono dal fatto che la funzionalità sia stata abilitata prima dell'esecuzione della chiusura di fine anno. Se la funzionalità è abilitata, il risultato dipende anche dall'impostazione dell'opzione Mantieni dettagli durante la chiusura di fine anno.

### <a name="the-feature-isnt-enabled"></a>La funzionalità non è abilitata
La chiusura di fine anno crea tre transazioni di saldo iniziale per il conto principale 130100 nel 2022. La somma delle transazioni nella valuta di contabilizzazione è USD 525.

| Numero giornale di registrazione | Giustificativo  | Data     | Tipo    | Conto CoGe | Nome conto        | Description | Valuta | Importo nella valuta della transazione | Importo  | Importo nella valuta di dichiarazione |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-002-    | Contabilità clienti |             | USD      | 299.12                         | 299.12  | 299.12                       |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-001-    | Contabilità clienti |             | USD      | 400                            | 400     | 400                          |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-002-    | Contabilità clienti |             | EUR      | -127,11                        | -174,12 | -174,12                      |

Anche se la transazione di pagamento per EUR -127,11 è stata liquidata nei saldi contabili, la transazione viene comunque presentata come saldo iniziale.

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--no"></a>La funzionalità è abilitata e Mantieni dettagli durante la chiusura di fine anno = No

La chiusura di fine anno crea due transazioni di saldo iniziale per il conto principale 130100 nel 2022. La somma delle transazioni nella valuta contabile è ancora USD 525, ma le transazioni liquidate per i saldi contabili sono escluse dal saldo iniziale. L'importo totale per il conto 130100-002- è USD 125 invece di USD 299,12 e la transazione per EUR 127,11/USD 174,12 è totalmente esclusa.

| Numero giornale di registrazione | Giustificativo  | Data     | Tipo    | Conto CoGe | Nome conto        | Description | Valuta | Importo nella valuta della transazione | Importo | Importo nella valuta di dichiarazione |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-002-    | Contabilità clienti |             | USD      | 125                            | 125    | 125                          |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-001-    | Contabilità clienti |             | USD      | 400                            | 400    | 400                          |

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--yes"></a>La funzionalità è abilitata e Mantieni dettagli durante la chiusura di fine anno = Sì

La chiusura di fine anno crea cinque transazioni di saldo iniziale per il conto principale 130100 nel 2022. Viene creata una transazione di saldo iniziale separata per ciascuna delle cinque transazioni che non sono state liquidate. La somma delle transazioni nella valuta di contabilizzazione è ancora USD 525.

| Numero giornale di registrazione | Giustificativo  | Data     | Tipo    | Conto CoGe | Nome conto        | Description       | Valuta | Importo nella valuta della transazione | Importo | Importo nella valuta di dichiarazione |
|----------------|----------|----------|---------|----------------|---------------------|-------------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-001-    | Contabilità clienti | Tariffa per il servizio       | USD      | 100                            | 100    | 100                          |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-001-    | Contabilità clienti | Rimborso            | USD      | -100                           | -100   | -100                         |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-002-    | Contabilità clienti | Conto in Avere | USD      | -175                           | -175   | -175                         |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-001-    | Contabilità clienti | Utilità         | USD      | 400                            | 400    | 400                          |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-002-    | Contabilità clienti | Assistenza           | USD      | 300                            | 300    | 300                          |

Quando i dettagli della transazione vengono mantenuti, le transazioni con dettaglio originali non sono interessate. Rimangono registrate e non liquidate nell'anno fiscale che si sta chiudendo. Viene creata una copia di tali transazioni per il saldo iniziale. I seguenti valori per le transazioni originali vengono copiati nelle transazioni del saldo iniziale.

- Conto CoGe (il conto principale e tutte le dimensioni finanziarie)
- Importi nelle valute di transazione, contabile e di dichiarazione
- Description
- Livello di registrazione
- Tipo di registrazione

   > [!NOTE]
   > A nessun'altra transazione del saldo iniziale viene assegnato un tipo di registrazione. Pertanto, il tipo di registrazione può essere utilizzato per differenziare le transazioni di apertura anticipate in dettaglio.

Alcuni campi delle transazioni originali devono cambiare nelle transazioni dettagliate del saldo iniziale. La data delle transazioni del saldo iniziale è sempre il primo giorno dell'anno fiscale successivo. Il numero del giornale di registrazione deve cambiare e il numero del giustificativo cambia nel valore immesso nella finestra di dialogo di chiusura di fine anno.

Le informazioni sulle transazioni originali sono disponibili nella pagina **Compensazione dei saldi contabili**. Ogni transazione dettagliata del saldo iniziale mostra la colonna **Data transazione originale** nella griglia. Questa colonna può aiutarti ad abbinare le transazioni nel nuovo anno fiscale. Puoi selezionare **Visualizza giustificativo originale** per eseguire il drill back fino al giustificativo originale completo.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Liquida transazioni
Per liquidare transazioni contabili, seguire questi passaggi.

1. Passa a **Contabilità generale** > **Attività periodiche** > **Compensazioni dei saldi contabili**.
2.  Imposta i filtri nella parte superiore della pagina.

    1. Seleziona un intervallo di date. In alternativa, seleziona un intervallo di date, oppure seleziona un codice intervallo date per compilare automaticamente l'intervallo di date.

       - L'intervallo di date non può attraversare gli anni fiscali. Se l'intervallo di date supera gli anni fiscali, nessuna transazione verrà visualizzata quando selezioni **Visualizza transazioni**.
       - Se l'intervallo di date è in un anno fiscale aperto, le transazioni possono essere liquidate e la liquidazione può essere stornata. Se l'intervallo di date è in un anno fiscale chiuso o se la chiusura di fine anno è stata completata, le transazioni vengono visualizzate, ma non possono essere liquidate o annullate. Puoi deselezionare le transazioni solo in un anno fiscale chiuso. Se l'intervallo di date è in un anno fiscale chiuso, i pulsanti **Contrassegna selezionati**, **Liquida transazioni contrassegnate** e **Storna transazioni contrassegnate** non sono disponibili.

    2. Seleziona il conto principale per cui mostrare le transazioni. Questo campo è obbligatorio. La ricerca mostra solo i conti principali selezionati nella pagina **Compensazione dei saldi contabili** per il piano dei conti della società.
    3. Seleziona il livello di registrazione. Non puoi liquidare transazioni che si trovano in livelli di registrazione diversi.
    4. Per visualizzare in colonne separate il conto principale e le dimensioni, seleziona un set di dimensioni finanziarie.

3.  Seleziona **Visualizza transazioni** per mostrare tutte le transazioni che corrispondono ai filtri impostati. Se si modifica uno dei filtri o dei set di dimensioni, è necessario selezionare nuovamente **Visualizza transazioni**.
4.  Seleziona le righe per la liquidazione. Il valore del campo **Importo selezionato** nella parte superiore della pagina aumenta o diminuisce per riflettere l'importo totale delle righe selezionate.
5.  Quando hai terminato di selezionare le transazioni, seleziona **Contrassegna selezionati**. Per ogni transazione selezionata, viene visualizzato un segno nella colonna **Contrassegnato**. Inoltre, il valore del campo **Importo contrassegnato** nella parte superiore della griglia aumenta o diminuisce per riflettere l'importo totale delle righe contrassegnate.
6.  Quando il valore nel campo **Importo contrassegnato** è **0** (zero), selezionare **Liquida transazioni contrassegnate**.

    - Non è consentita la liquidazione parziale. Ad esempio, non puoi saldare un addebito di $100 a fronte di un accredito di $90. L'accredito rimanente di $10 deve essere contrassegnato per essere incluso nella liquidazione.
    - Immetti una data di liquidazione. La data deve coincidere o essere successiva alla data più recente delle transazioni contrassegnate per la liquidazione.

Lo stato delle transazioni contrassegnate viene aggiornato a **Liquidato**.

> [!IMPORTANT]
> Tutte le transazioni contrassegnate per la liquidazione per la persona giuridica attiva e per il conto principale selezionato verranno liquidate. Le transazioni non devono apparire nella pagina. Verrano liquidate anche se sono nascoste a causa di un filtro.

Alcuni processi, come lo storno di una transazione, regolano automaticamente le transazioni contabili. Ad esempio, un pagamento e una fattura vengono liquidati in Contabilità clienti e la liquidazione genera un guadagno/perdita realizzato. La liquidazione del pagamento e della fattura non liquida le transazioni contabili, ad esempio le transazioni per il conto CoGe Contabilità clienti. Tuttavia, se il pagamento e la fattura non sono liquidati in Contabilità clienti, la registrazione contabile di storno che è stata registrata durante lo storno della liquidazione di Contabilità clienti farà sì che le registrazioni contabili originali e di storno vengano liquidate in Contabilità generale. Quando la funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno** è abilitata, la liquidazione contabile di uno storno non si verifica automaticamente se la data di storno è in un anno fiscale diverso.

## <a name="use-excel-for-ledger-settlement"></a>Utilizzare Excel per la liquidazione dei saldi contabili

Le transazioni che sono mostrate nella pagina **Compensazione dei saldi contabili** può essere esportata in Excel. In Excel puoi filtrare ulteriormente le transazioni per determinare quali transazioni contrassegnare per la liquidazione.
Entrambe le entità di liquidazione dei saldi contabili esportano le transazioni contabili solo per il conto principale selezionato nella pagina **Compensazione dei saldi contabili**. Sebbene le transazioni per gli anni fiscali chiusi possano ancora essere contrassegnate o deselezionate utilizzando Excel, non possono essere liquidate. Inoltre, le transazioni liquidate non possono essere stornate per quell'anno fiscale.

## <a name="make-transactions-easier-to-find"></a>Facilitare l'individuazione delle transazioni

Nella pagina **Compensazioni dei saldi contabili** sono disponibili le funzionalità che rendono più semplice visualizzare le transazioni di cui hai richiesto la liquidazione.

•   Utilizza il filtro **Contrassegnato** per filtrare le transazioni a seconda che la casella di controllo **Contrassegnato** sia selezionata o deselezionata.
•   Utilizza il filtro **Stato** per filtrare le transazioni in base al loro stato.
•   Seleziona **Ordina per importo assoluto** per ordinare gli importi in base al valore assoluto. In questo modo puoi raggruppare addebiti e crediti di pari importo.

## <a name="reverse-a-settlement"></a>Stornare una liquidazione

È possibile stornare una liquidazione effettuata per errore.

1.  Segui i passaggi da 1 a 3 nella sezione [Liquidare le transazioni](#settle-transactions) per mostrare le transazioni che ti interessano.
2.  Nel filtro **Stato**, selezionare **Liquidato**.
3.  Seleziona le righe per lo storno.
4.  Seleziona **Storna transazioni contrassegnate**. Lo stato di tutte le transazioni che hanno lo stesso ID liquidazione viene aggiornato in **Non liquidato**.

> [!IMPORTANT]
> Tutte le transazioni che hanno lo stesso ID liquidazione verranno stornate, anche se non contrassegnate. Ad esempio, quattro righe sono state contrassegnate e liquidate. Tutte e quattro le righe hanno lo stesso ID liquidazione. Se contrassegni una di queste quattro righe e poi selezioni **Storna transazioni contrassegnate**, tutte e quattro le righe verranno stornate.






