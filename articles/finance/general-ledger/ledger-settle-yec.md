---
title: Funzionalità Riconoscimento tra liquidazione saldi contabili prima della chiusura di fine anno
description: Questo articolo spiega come utilizzare la funzionalità Riconoscimento tra liquidazione saldi contabili prima della chiusura di fine anno della contabilità generale.
author: kweekley
ms.date: 12/02/2022
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
ms.openlocfilehash: c79b6f50296560e1534be0621bb2aa8eaa2c1dc8
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832165"
---
# <a name="awareness-between-ledger-settlement-feature-before-year-end-close"></a>Funzionalità Riconoscimento tra liquidazione saldi contabili prima della chiusura di fine anno

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-before-year-end-close"></a>Preparazione per la funzionalità Riconoscimento tra liquidazione saldi contabili prima della chiusura di fine anno

Una modifica importante della funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno** (la funzionalità **Riconoscimento**) è che la liquidazione saldi contabili non può essere effettuata tra anni fiscali. Questa limitazione interannuale è rilevante solo per la liquidazione saldi contabili, non per la liquidazione della contabilità clienti o della contabilità fornitori.

Prima che la funzione **Riconoscimento** sia abilitata, l'anno fiscale che subirà la chiusura di fine anno non deve avere transazioni contabili liquidate tra gli anni fiscali. In particolare, tutte le transazioni registrate nell'anno fiscale per il quale si sta eseguendo la chiusura di fine anno devono essere non liquidate dalle transazioni registrate in un anno fiscale diverso. Le transazioni possono essere liquidate nuovamente rispetto alle transazioni nello stesso anno fiscale.

In questo articolo vengono descritti i passaggi necessari per identificare, annullare la liquidazione e reimpostare le transazioni contabili liquidate negli anni fiscali. Nell'esempio fornito, l'anno fiscale 2021 è stato chiuso e ti stai preparando a eseguire la chiusura di fine anno per l'anno fiscale 2022.

## <a name="example-setup"></a>Esempio di impostazione

La figura seguente mostra le transazioni registrate per il conto principale 110190. Le transazioni contabili in verde vengono liquidate nello stesso anno fiscale e non devono essere modificate. Le transazioni in rosso sono state sottoposte alla compensazione dei saldi contabili, ma hanno date di transazione in anni fiscali diversi. Tali transazioni devono essere identificate e potrebbe essere necessario stornare la liquidazione contabile.

![Transazioni contabili.](./media/YEC1.png)

## <a name="example"></a>Esempio

Segui questi passaggi se la tua organizzazione desidera utilizzare la funzione **Riconoscimento** prima dell'esecuzione della chiusura di fine anno per l'anno fiscale 2022.

> [!NOTE]
> La chiusura di fine anno per gli anni fiscali 2021 e precedenti deve essere rieseguita solo se le nuove transazioni vengono registrate nell'anno fiscale 2021 o precedenti. Una volta completata la seguente procedura, nel 2021 non sono registrate nuove transazioni. Pertanto, la chiusura di fine anno non deve essere ripetuta.
>
> Le transazioni contabili liquidate negli anni fiscali possono rimanere liquidate contabilmente se non vengono liquidate a fronte di una transazione registrata nel 2022 o in una data successiva. Ad esempio, se hai liquidato le transazioni tra il 2019 e il 2020, possono rimanere liquidate.

1. Facoltativo: abilita temporaneamente la funzione **Riconoscimento**.

    - Se scegli di abilitare la funzione, dovrai disabilitarla nei passaggi successivi, come indicato. Il vantaggio di abilitare la funzione ora è che si impedisce temporaneamente agli utenti di liquidare le transazioni contabili che sono state registrate in diversi anni fiscali.
    - Se scegli di non abilitare la funzione, ti consigliamo di chiedere al team di non liquidare le transazioni tra gli anni fiscali. Se la liquidazione interannuale si verifica dopo il completamento dei seguenti passaggi, sarà necessario ripetere i passaggi per identificare e annullare la liquidazione delle transazioni contabili.

2. Nella pagina **Liquidazione contabilità generale**, identifica il totale di tutte le transazioni liquidate negli anni fiscali 2021 e 2022.

    1. Specifica un intervallo di date per tutto l'anno fiscale 2021. Ad esempio, immetti dal 1° gennaio 2021 al 31 dicembre 2021, se utilizzi un anno solare come anno fiscale.

        Se la funzione **Riconoscimento** è abilitata, si riceve un avviso che le transazioni non possono essere liquidate o annullate per un anno fiscale chiuso. L'avviso non è rilevante perché in questa fase non si verifica alcuna liquidazione o annullamento della liquidazione.

    2. Nel campo **Stato** seleziona **Liquidato**.
    3. Filtra su un conto contabile alla volta.

        - Dovrai ripetere questi passaggi per ogni conto contabile per il quale si verifica la liquidazione contabile.
        - Se altri conti contabili non sono più impostati per la liquidazione contabile, potrebbe essere necessario aggiungerli temporaneamente all'impostazione della liquidazione contabile. Quindi completa questi passaggi se i conti contabili hanno transazioni nel 2022 che vengono liquidate rispetto a transazioni in un altro anno fiscale.

    4. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) nella colonna **Stato**, quindi seleziona per raggruppare in base a questa colonna.
    5. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) nella colonna **Importo in valuta di transazione**, quindi seleziona per eseguire il totale di questa colonna.

        - Se hai liquidato le transazioni solo nel 2021, il totale sarà 0 (zero).
        - Se hai transazioni che sono state liquidate in più anni fiscali, il totale non sarà 0 (zero).

        Nell'illustrazione seguente, c'è un saldo di $525,00. Questo saldo è il totale delle transazioni che sono state liquidate a fronte di transazioni in un anno fiscale diverso. Il totale potrebbe includere transazioni liquidate tra il 2021 e il 2022 e transazioni liquidate tra il 2022 e il 2023.

        ![Transazioni contabili 2021–2022.](./media/YEC2.png)

    6. Identifica quali transazioni sono state liquidate tra il 2020 e il 2021 filtrando ulteriormente il valore **Data di liquidazione**. Specifica un filtro per l'intervallo di date dal 1° gennaio 2021 al 31 dicembre 2021. Nessuna transazione viene mostrata perché nessuna transazione del 2020 è stata liquidata rispetto a transazioni registrate nel 2021.
    7. Identifica quali transazioni sono state liquidate tra il 2021 e il 2022 cambiando il filtro data sul valore **Data di liquidazione**. Specifica un filtro per l'intervallo di date dal 1° gennaio 2022 al 31 dicembre 2022. Le transazioni vengono nuovamente visualizzate e il totale è $525,00 perché tutte le transazioni sono state liquidate tra il 2021 e il 2022.

3. Nella pagina **Liquidazione contabilità generale**, identifica il totale di tutte le transazioni liquidate negli anni fiscali 2021 e 2022.

    1. Specifica un intervallo di date per tutto l'anno fiscale 2022. Ad esempio, specifica dal 1° gennaio 2022 al 31 dicembre 2022, se utilizzi un anno solare come anno fiscale.
    2. Nel campo **Stato** seleziona **Liquidato**.
    3. Filtra su un conto contabile alla volta.
    4. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) nella colonna **Stato**, quindi seleziona per raggruppare in base a questa colonna.
    5. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) nella colonna **Importo in valuta di transazione**, quindi seleziona per eseguire il totale di questa colonna.

        ![Importo totale della transazione contabile.](./media/YEC3.png)

    6. Aggiungi un ulteriore filtro sul valore **Data di liquidazione**. Specifica un filtro per l'intervallo di date dal 1° gennaio 2022 al 31 dicembre 2022. Viene mostrato lo stesso totale di $525,00. Questo risultato convalida che l'importo totale delle transazioni liquidate tra il 2021 e il 2022 è $525,00.

        ![Transazioni contabili per date di liquidazione nel 2022 e nel 2023.](./media/YEC4.png)

    7. Modifica il filtro sul valore **Data di liquidazione**. Specifica un filtro per l'intervallo di date dal 1° gennaio 2023 al 31 dicembre 2023. Viene mostrato un nuovo totale di $700. Questo totale è l'importo totale delle transazioni liquidate tra il 2022 e il 2023.
 
4. Ripeti il passaggio 3 per l'anno fiscale 2023. Il totale deve corrispondere al valore $700 del 2022 perché nessuna transazione del 2023 è stata liquidata rispetto alle transazioni del 2024.
5. Se hai abilitato la funzione **Riconoscimento** nel passaggio 1, disabilitala prima di passare al passaggio 6. Nei passaggi successivi, annullerai la liquidazione contabile nei vari anni fiscali. Se la funzione **Riconoscimento** è abilitata, la liquidazione contabile non può essere stornata per l'anno fiscale 2021. Pertanto, è necessario disabilitare la funzione prima di continuare.
6. Dopo aver disattivato la funzione **Riconoscimento**, utilizza gli stessi filtri nella pagina **Liquidazione contabile** per annullare la liquidazione contabile delle transazioni dettagliate.

    1. Torna alla pagina **Liquidazione contabile** e filtra in base alle date delle transazioni per il 2021. Aggiungi un ulteriore filtro sul valore **Data di liquidazione**. Specifica un filtro per l'intervallo di date dal 1° gennaio 2022 al 31 dicembre 2022. Quindi trova le transazioni dettagliate che compongono il totale $525. Filtrare queste informazioni potrebbe non essere facile. Potrebbe essere necessario inviare i dati a Microsoft Excel per valutarli.
    2. Dopo aver ottenuto l'elenco delle transazioni, seleziona le transazioni contabili nella pagina **Liquidazione contabile** e seleziona **Contrassegna selezionati**. Non è necessario visualizzare entrambi i lati delle transazioni contabili liquidate. Se contrassegni il debito o il credito, tutto ciò che ha lo stesso valore **ID liquidazione** verrà stornato, anche se il valore **Importo contrassegnato** non è **0** (zero).
    3. Seleziona **Storna transazioni contrassegnate** per annullare la liquidazione delle transazioni.

    ![Storna transazioni contrassegnate.](./media/YEC5.png)

7. Ripeti il passaggio 6 per annullare la liquidazione per le transazioni liquidate tra il 2022 e il 2023.

    ![Storna le transazioni contabili.](./media/YEC6.png)

8. Crea un giornale di registrazione generale di rettifica per suddividere il saldo iniziale per il 2022 in due importi: la parte liquidata rispetto alla transazione dell'anno fiscale 2021 e la parte non ancora liquidata nel 2022.

    - **Parte del saldo iniziale liquidata rispetto all'anno precedente:** Il primo importo è $525, in base ai totali trovati che sono stati liquidati tra il 2021 e il 2022.
    - **Parte del saldo iniziale non liquidata rispetto all'anno precedente:** Il secondo importo è la differenza tra il saldo iniziale e l'importo liquidato di $525. L'importo rimanente è $1025 – $525 = $500.

    In questo modo, puoi liquidare le transazioni del 2022 rispetto all'importo $525 originariamente liquidata rispetto alla transazione del 2021. Questo passaggio è necessario perché la liquidazione contabile non consente la liquidazione parziale.

    1. Vai al giornale di registrazione generale e registra la rettifica. La tua organizzazione dovrà decidere quale data di transazione utilizzare, in base ai periodi aperti. Queste transazioni possono essere state liquidate utilizzando una data di liquidazione di gennaio o febbraio 2022, ma la rettifica potrebbe essere stata registrata a dicembre se questo è l'unico periodo aperto.
    2. Potrebbe essere necessario disattivare temporaneamente il parametro **Non consentire l'immissione manuale** nella pagina **Conto principale**. Questa rettifica non verrà registrata se il conto principale non consente l'immissione manuale.

    ![Rettifica non registrata.](./media/YEC7.png)

9. È ora possibile liquidare nuovamente le transazioni non liquidate. Torna alla pagina **Compensazione dei saldi contabili** e limita l'intervallo di date dal 1° gennaio 2022 al 31 dicembre 2022. L'illustrazione seguente mostra le transazioni non liquidate attualmente esistenti.

    ![Transazioni non liquidate.](./media/YEC8.png)

    - Il saldo iniziale di $1.025 può essere liquidato rispetto alla rettifica per -$1.025.
    - Le transazioni dettagliate non liquidate per -$400, -$50, e -$75 possono essere liquidate a fronte della rettifica per $525,00.

    ![Transazioni dettagliate.](./media/YEC9.png)

10. Abilita la funzione **Riconoscimento**. Ora sei pronto per eseguire la chiusura di fine anno.

    - Prima di eseguire la chiusura di fine anno, valuta la possibilità di selezionare l'opzione **Mantieni dettagli** nella configurazione della liquidazione contabile per tutti i conti dello stato patrimoniale. Per ulteriori informazioni sui vantaggi derivanti dal completamento di questo passaggio, vedi il documento Riconoscimento.
    - Quando inizi la chiusura di fine anno per il 2022, se vengono ancora rilevate transazioni che sono state liquidate negli anni fiscali, il processo di chiusura di fine anno ti avviserà immediatamente.
    - Se le transazioni 2021 e 2022 sono ancora liquidate, dovrai disattivare nuovamente la funzione **Riconoscimento** e ripetere i passaggi precedenti per annullare la liquidazione delle transazioni. Questo approccio è necessario perché il 2021 è chiuso e le transazioni non possono essere annullate in un anno fiscale chiuso.
    - Se le transazioni 2022 e 2023 sono ancora liquidate, **non** devi disabilitare la funzione **Riconoscimento**. Poiché né il 2022 né il 2023 sono chiusi, puoi utilizzare i passaggi precedenti per annullare la liquidazione delle transazioni.

Dopo che la chiusura di fine anno per il 2022 è stata eseguita correttamente, puoi lasciare abilitata la funzione **Riconoscimento** d'ora in poi.
