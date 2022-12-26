---
title: Funzionalità Riconoscimento tra liquidazione saldi contabili prima della chiusura di fine anno usando la pagina di richiesta
description: Questo articolo spiega come utilizzare la funzionalità Riconoscimento tra liquidazione saldi contabili usando la nuova pagina di richiesta prima della chiusura di fine anno della contabilità generale.
author: kweekley
ms.date: 12/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: b138d2d5e88ff7f2ca2240cf256a4938f55a5606
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853138"
---
# <a name="awareness-between-ledger-settlement-feature-before-year-end-close-using-the-inquiry-page"></a>Funzionalità Riconoscimento tra liquidazione saldi contabili prima della chiusura di fine anno usando la pagina di richiesta

Una modifica principale della funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno** (la funzionalità **Riconoscimento**) è che la liquidazione saldi contabili non può essere effettuata tra anni fiscali. Questa limitazione interannuale è rilevante solo per la liquidazione saldi contabili, non per la liquidazione della contabilità clienti o della contabilità fornitori.

Prima di abilitare la funzione **Riconoscimento**, l'anno fiscale che subirà la chiusura di fine anno non deve avere transazioni contabili liquidate tra gli anni fiscali. In particolare, tutte le transazioni registrate nell'anno fiscale per il quale si sta eseguendo la chiusura di fine anno devono essere non liquidate dalle transazioni registrate in un anno fiscale diverso. Le transazioni possono essere liquidate nuovamente rispetto alle transazioni nello stesso anno fiscale.

In questo articolo vengono descritti i passaggi necessari per identificare, annullare la liquidazione e reimpostare le transazioni contabili liquidate negli anni fiscali. Nell'esempio fornito, l'anno fiscale 2021 è stato chiuso e ti stai preparando a eseguire la chiusura di fine anno per l'anno fiscale 2022.

A partire da Microsoft Dynamics 365 Finance versione 10.0.29, puoi identificare, annullare e riliquidare le transazioni contabili utilizzando una nuova pagina di richiesta disponibile. Se al momento non usi Finance versione 10.0.29 o successiva, puoi trovare i passaggi per identificare, annullare la liquidazione e reimpostare le transazioni contabili nei seguenti articoli:

- [Funzionalità Riconoscimento tra liquidazione saldi contabili prima della chiusura di fine anno](ledger-settle-yec.md)
- [Funzionalità Riconoscimento tra liquidazione saldi contabili dopo la chiusura di fine anno](ledger-settle-yec-after.md)

Per ulteriori informazioni sulla nuova finestra di richiesta, vedi [Richiesta compensazione dei saldi contabili](ledger-settlement-inquiry.md). 

## <a name="example-setup"></a>Esempio di impostazione

La figura seguente mostra le transazioni registrate per il conto principale 110200. Le transazioni in verde sono state liquidate nello stesso anno fiscale e non devono essere modificate. Le transazioni in rosso sono state sottoposte alla compensazione dei saldi contabili, ma hanno date di transazione in anni fiscali diversi. Tali transazioni devono essere identificate e potrebbe essere necessario stornare la liquidazione contabile.

![Transazioni contabili registrate.](./media/ledgersettlement.png)

## <a name="example"></a>Esempio

Segui questi passaggi se la tua organizzazione desidera utilizzare la funzione **Riconoscimento** prima dell'esecuzione della chiusura di fine anno per l'anno fiscale 2022.

> [!NOTE]
> La chiusura di fine anno per gli anni fiscali 2021 e precedenti deve essere rieseguita solo se le nuove transazioni vengono registrate nell'anno fiscale 2021 o precedenti. Una volta completata la seguente procedura, nel 2021 non sono registrate nuove transazioni. Pertanto, la chiusura di fine anno non deve essere ripetuta.
>
> Le transazioni contabili liquidate negli anni fiscali possono rimanere liquidate contabilmente se non vengono liquidate a fronte di una transazione registrata nel 2022 (l'anno da chiudere) o in una data successiva. Ad esempio, se hai liquidato le transazioni nel 2019 e nel 2020, possono rimanere liquidate.

1. **Non** abilitare la funzione **Riconoscimento**.
2. Nella pagina **Compensazioni dei saldi contabili** seleziona **Verifica liquidazioni incrociate**.
3. Identifica tutte le transazioni registrate in altri anni fiscali ma liquidate rispetto a transazioni registrate nel 2022.

    1. Seleziona l'anno fiscale 2022 di cui vuoi eseguire la chiusura di fine anno.
    2. Seleziona un valore nel campo **Set di dimensioni finanziarie** per visualizzare le dimensioni finanziarie che vuoi visualizzare per il conto contabile. Il conto principale viene sempre visualizzato, anche se il set di dimensioni selezionato non contiene un conto principale.
    3. Seleziona **Mostra transazioni**.

    La pagina di richiesta mostrerà tutte le transazioni, per tutti i conti contabili (anche se non sono più nella configurazione della liquidazione contabile), di tutti gli altri anni fiscali liquidati rispetto alle transazioni registrate nel 2022. Vengono visualizzati tre diversi conti contabili.

    ![Liquidazioni tra anni del 2022.](./media/review-cross-year.png)

3. Seleziona e tieni premuta (o fai clic con il pulsante destro del mouse) la griglia, quindi seleziona **Esporta tutte le righe**. Queste righe sono tutte le transazioni che devono essere annullate dalle transazioni nel 2022 prima che possa essere eseguita la chiusura di fine anno. Vuoi visualizzare l'elenco dettagliato delle transazioni in modo da poter riliquidare correttamente le transazioni in un secondo momento.
4. Prendi nota degli anni fiscali per i quali sono state registrate le transazioni. In questo esempio, ci sono transazioni nel 2021 e nel 2023.
5. Nella pagina di richiesta modifica l'anno fiscale in 2021, il primo anno fiscale che contiene le transazioni che sono state liquidate rispetto alle transazioni del 2022.
6. Filtra sulla colonna **Data transazione** in modo da includere solo le transazioni che sono state registrate nel 2022. Queste transazioni sono le transazioni dettagliate del 2022 che sono state regolate rispetto alle transazioni del 2021.
7. Seleziona e tieni premuta (o fai clic con il pulsante destro del mouse) la griglia, quindi seleziona **Esporta tutte le righe**.

    > [!IMPORTANT]
    > Nei passaggi seguenti, queste transazioni verranno annullate e quindi riliquidate rispetto alle transazioni nel 2022. È essenziale mantenere questo dettaglio in Excel.

    ![Liquidazioni tra anni del 2021.](./media/review-cross-year.png)

8. Nella pagina di richiesta modifica l'anno fiscale in 2023, il successivo anno fiscale che contiene le transazioni che sono state liquidate rispetto alle transazioni del 2022. 
9. Filtra sulla colonna **Data transazione** in modo da includere solo le transazioni che sono state registrate nel 2022. Queste transazioni sono le transazioni dettagliate del 2023 che sono state regolate rispetto alle transazioni del 2022. 
10. Seleziona e tieni premuta (o fai clic con il pulsante destro del mouse) la griglia, quindi seleziona **Esporta tutte le righe**.

    > [!IMPORTANT]
    > Nei passaggi seguenti, queste transazioni verranno annullate e quindi riliquidate rispetto alle transazioni nel 2022. È essenziale mantenere questo dettaglio in Excel.

    ![Liquidazioni tra anni del 2023.](./media/filter-transactions.png)

11. Ripeti i passaggi precedenti per ogni anno fiscale con transazioni liquidate a fronte di transazioni nel 2022. Esporta sempre le transazioni dettagliate in Excel.

    Dopo che tutte le transazioni dettagliate del 2021 e del 2023 sono state esportate in Excel, sei pronto per annullare le transazioni utilizzando la nuova pagina di richiesta.

12. Modifica l'anno fiscale in 2022.
13. Seleziona tutti i record nella griglia, quindi seleziona **Record contrassegnati non liquidati**. Tutte le transazioni selezionate nella griglia saranno annullate.

    Vengono visualizzati due messaggi di avviso per garantire che i dettagli della transazione vengano esportati in Excel prima che le transazioni vengano annullate. Se si annullano accidentalmente le transazioni contabili prima di inviare i dettagli a Excel, non c'è modo di annullare la liquidazione.

    ![Operazioni di annullamento della liquidazione incrociata.](./media/revert-unsettle.png)

14. Utilizza i dati di Excel per trovare l'importo totale delle transazioni nel 2021 e nel 2023 liquidate rispetto alle transazioni nel 2022. In questo esempio, le transazioni per il 2021 hanno il totale $525 e le transazioni per il 2023 hanno il totale $700.
15. Crea un giornale di registrazione generale di rettifica per suddividere il saldo iniziale per il 2022 in due importi: la parte liquidata all'anno fiscale 2021 e la parte non ancora liquidata al 2022.

    - **Parte del saldo iniziale liquidata nell'anno precedente:** Il primo importo è $525, in base ai totali trovati che sono stati liquidati tra il 2021 e il 2022.
    - **Parte del saldo iniziale non liquidata nell'anno precedente:** Il secondo importo è la differenza tra il saldo iniziale e l'importo liquidato di $525. L'importo rimanente è $1.025 – $525 = $500.

    In questo modo, puoi liquidare le transazioni del 2022 rispetto all'importo $525 originariamente liquidata rispetto alla transazione del 2021. Questo passaggio è necessario perché la liquidazione contabile non consente la liquidazione parziale.

    1. Vai al giornale di registrazione generale e registra la rettifica. La tua organizzazione dovrà decidere quale data di transazione utilizzare, in base ai periodi aperti. Queste transazioni possono essere state liquidate utilizzando una data di liquidazione di gennaio o febbraio 2022, ma la rettifica potrebbe essere stata registrata a dicembre se questo è l'unico periodo aperto.
    2. Potrebbe essere necessario disattivare temporaneamente il parametro **Non consentire l'immissione manuale** per il conto 110200 nella pagina **Conto principale**. Questa rettifica non verrà registrata se il conto principale non consente l'immissione manuale.

    ![Registrazione di un giornale di registrazione generale di rettifica.](./media/not-post.png)

16. È ora possibile liquidare nuovamente le transazioni non liquidate. Torna alla pagina **Liquidazioni contabili** , specifica un intervallo di date compreso tra il 1° gennaio e il 31 dicembre 2022 e filtra in base al conto principale 110200. Quindi utilizza le transazioni dettagliate che hai esportato in Excel per trovare le transazioni specifiche che devono essere riliquidate. L'illustrazione seguente mostra le transazioni non liquidate attualmente esistenti.

    ![Transazioni non liquidate.](./media/updated-unsettled.png)

    - Il saldo iniziale di $1.025 può essere liquidato rispetto alla rettifica per -$1.025.
    - Le transazioni dettagliate non liquidate per -$400, -$50, e -$75 possono essere liquidate a fronte della rettifica per $25.

17. Abilita la funzione **Riconoscimento**. Ora sei pronto per eseguire la chiusura di fine anno.

    - Prima di eseguire la chiusura di fine anno, valuta la possibilità di selezionare l'opzione **Mantieni dettagli** nella configurazione della liquidazione contabile per tutti i conti dello stato patrimoniale. Per altre informazioni vedi [Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno](awareness-between-ledger-settlement-year-end-close.md).
    - Quando inizi la chiusura di fine anno per il 2022, se vengono ancora rilevate transazioni che sono state liquidate negli anni fiscali, il processo di chiusura di fine anno ti avviserà immediatamente. Questa situazione potrebbe verificarsi se gli utenti hanno liquidato le transazioni negli anni fiscali dopo aver completato i passaggi precedenti.
    - Se le transazioni 2021 e 2022 sono ancora liquidate, dovrai disattivare nuovamente la funzione **Riconoscimento** e ripetere i passaggi precedenti per annullare la liquidazione delle transazioni. Questo approccio è necessario perché il 2021 è chiuso e le transazioni non possono essere annullate in un anno fiscale chiuso.
    - Se le transazioni 2022 e 2023 sono ancora liquidate, non devi disabilitare la funzione **Riconoscimento**. Poiché né il 2022 né il 2023 sono chiusi, puoi utilizzare i passaggi precedenti per annullare la liquidazione delle transazioni.

18. Puoi liquidare la transazione $700 dal 2023 rispetto alle transazioni dettagliate che sono state trasferite come saldi iniziali nel 2023. Questa transazione non verrà liquidata rispetto alla transazione originale nel 2022.

Dopo che la chiusura di fine anno per il 2022 è stata eseguita correttamente, puoi lasciare abilitata la funzione **Riconoscimento** d'ora in poi.
