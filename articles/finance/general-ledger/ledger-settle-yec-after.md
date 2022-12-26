---
title: Funzionalità Riconoscimento tra liquidazione saldi contabili dopo la chiusura di fine anno
description: Questo articolo spiega come utilizzare la funzionalità Riconoscimento tra liquidazione saldi contabili dopo la chiusura di fine anno della contabilità generale.
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
ms.openlocfilehash: 7efa9d652d74bd836f51b5b1c5f6bfaf8934ea40
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832176"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close"></a>Funzionalità Riconoscimento tra liquidazione saldi contabili dopo la chiusura di fine anno

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-after-year-end-close"></a>Preparazione per la funzionalità Riconoscimento tra liquidazione saldi contabili dopo la chiusura di fine anno

Una modifica importante della funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno** (la funzionalità **Riconoscimento**) è che la liquidazione saldi contabili non può essere effettuata tra anni fiscali. Questa limitazione interannuale è rilevante solo per la liquidazione saldi contabili, non per la liquidazione della contabilità clienti o della contabilità fornitori.

Prima che la funzione **Riconoscimento** sia abilitata, l'anno fiscale che subirà la chiusura di fine anno non deve avere transazioni contabili liquidate tra gli anni fiscali. In particolare, tutte le transazioni registrate nell'anno fiscale per il quale si sta eseguendo la chiusura di fine anno devono essere non liquidate dalle transazioni registrate in un anno fiscale diverso. Le transazioni possono essere liquidate nuovamente rispetto alle transazioni nello stesso anno fiscale.

In questo articolo vengono descritti i passaggi necessari per identificare, annullare la liquidazione e reimpostare le transazioni contabili liquidate negli anni fiscali. Nell'esempio fornito, l'anno fiscale 2022 è stato chiuso. L'obiettivo è preparare le transazioni di liquidazione dei saldi contabili ben prima che venga eseguita la chiusura di fine anno 2023.

## <a name="example-setup"></a>Esempio di impostazione

La figura seguente mostra le transazioni registrate per il conto principale 110190. Le transazioni contabili in verde vengono liquidate nello stesso anno fiscale e non devono essere modificate. Le transazioni in rosso sono state sottoposte alla compensazione dei saldi contabili, ma hanno date di transazione in anni fiscali diversi. Tali transazioni devono essere identificate e potrebbe essere necessario stornare la liquidazione contabile.

![Transazioni contabili.](./media/afterYEC1.png)

## <a name="example"></a>Esempio

Segui questi passaggi se la tua organizzazione desidera utilizzare la funzione **Riconoscimento** dopo l'esecuzione della chiusura di fine anno per l'anno fiscale 2022.

> [!NOTE]
> La chiusura di fine anno per gli anni fiscali 2022 e precedenti deve essere rieseguita solo se le nuove transazioni vengono registrate nell'anno fiscale 2022 o precedenti. Una volta completata la seguente procedura, nel 2022 non devono essere registrate nuove transazioni. Pertanto, la chiusura di fine anno non deve essere ripetuta.
>
> Le transazioni contabili liquidate negli anni fiscali possono rimanere liquidate contabilmente se non vengono liquidate a fronte di una transazione registrata nel 2023 o in una data successiva. Ad esempio, se hai liquidato le transazioni tra il 2019 e il 2020, possono rimanere liquidate.

1. Completa la chiusura di fine anno per il 2022 senza la funzione **Riconoscimento** abilitata.
2. Facoltativo: una volta completata la chiusura di fine anno per il 2022, abilita la funzione **Riconoscimento**. Una chiusura di fine anno viene considerata completata quando tutte le rettifiche vengono registrate e il processo di chiusura di fine anno non viene eseguito nuovamente.

    > [!IMPORTANT]
    > La funzione **Riconoscimento** non deve essere abilitata se la chiusura di fine anno per il 2022 viene ripetuta. Il vantaggio di abilitare la funzione ora è che si impedisce agli utenti di liquidare le transazioni contabili che sono state registrate in diversi anni fiscali.

    Se la chiusura di fine anno non è stata completata, puoi comunque completare i passaggi successivi senza abilitare la funzione **Riconoscimento**. Abiliterai la funzione in un passaggio successivo, come indicato.

3. Nella pagina **Liquidazione contabilità generale**, identifica il totale di tutte le transazioni liquidate negli anni fiscali 2022 e 2023. Tieni presente che le transazioni del 2021 liquidate rispetto alle transazioni del 2022 non sono rilevanti perché il 2022 è già stato chiuso. Queste transazioni possono essere liquidate.

    1. Specifica un intervallo di date per tutto l'anno fiscale 2022. Ad esempio, specifica dal 1° gennaio 2022 al 31 dicembre 2022, se utilizzi un anno solare come anno fiscale.
    2. Nel campo **Stato** seleziona **Liquidato**.
    3. Filtra su un conto contabile alla volta.

        - Dovrai ripetere questi passaggi per ogni conto contabile per il quale si verifica la liquidazione contabile.
        - Se altri conti contabili non sono più impostati per la liquidazione contabile, potrebbe essere necessario aggiungerli temporaneamente all'impostazione della liquidazione contabile. Quindi completa questi passaggi se i conti contabili hanno transazioni nel 2023 che vengono liquidate rispetto a transazioni del 2022 o precedenti.

    4. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) nella colonna **Stato**, quindi seleziona per raggruppare in base a questa colonna.
    5. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) nella colonna **Importo in valuta di transazione**, quindi seleziona per eseguire il totale di questa colonna.

        - Se hai liquidato le transazioni solo nel 2022, il totale sarà 0 (zero).
        - Se hai transazioni che sono state liquidate in più anni fiscali, il totale non sarà 0 (zero).

    6. Identifica quali transazioni sono state liquidate tra il 2022 e il 2023 filtrando il valore **Data di liquidazione**. Se filtri una data di liquidazione dal 1° gennaio 2023 al 31 dicembre 2023, ottieni un totale di $700, ovvero il totale delle transazioni che sono state liquidate in contabilità generale tra il 2022 e il 2023.

    ![Transazioni contabili totali del 2022.](./media/afterYEC2.png)

4. Ripeti il passaggio 3 per l'anno fiscale 2023. Il totale deve corrispondere al valore $700 del 2022 perché nessuna transazione del 2023 è stata liquidata rispetto alle transazioni del 2024.

    ![Transazioni contabili totali del 2023.](./media/afterYEC3.png)

5. Se hai abilitato la funzione **Riconoscimento** nel passaggio 2, disabilitala prima di passare al passaggio 6. Nei passaggi successivi, annullerai la liquidazione contabile nei vari anni fiscali. Se la funzione **Riconoscimento** è abilitata, la liquidazione contabile non può essere stornata per l'anno fiscale 2022. Pertanto, è necessario disabilitare la funzione prima di continuare.
6. Dopo aver disattivato la funzione **Riconoscimento**, utilizza gli stessi filtri nella pagina **Liquidazione contabile** per annullare la liquidazione contabile delle transazioni dettagliate.

    1. Torna alla pagina **Liquidazione contabile** e filtra in base alle date delle transazioni per il 2023. Quindi trova le transazioni dettagliate che compongono il totale $700. Filtrare queste informazioni potrebbe non essere facile. Potrebbe essere necessario inviare i dati a Microsoft Excel per valutarli.
    2. Dopo aver ottenuto l'elenco delle transazioni, seleziona le transazioni contabili nella pagina **Liquidazione contabile** e seleziona **Contrassegna selezionati**. Non è necessario visualizzare entrambi i lati delle transazioni contabili liquidate. Se contrassegni il debito o il credito, tutto ciò che ha lo stesso valore **ID liquidazione** verrà stornato, anche se il valore **Importo contrassegnato** non è **0** (zero).
    3. Seleziona **Storna transazioni contrassegnate** per annullare la liquidazione delle transazioni.

    ![Storna le transazioni.](./media/afterYEC4.png)

7. Crea un giornale di registrazione generale di rettifica per suddividere il saldo iniziale per il 2023 in due importi: la parte liquidata rispetto alla transazione dell'anno fiscale 2022 e la parte non ancora liquidata nel 2023.

    - **Parte del saldo iniziale liquidata rispetto all'anno precedente:** Il primo importo è $700, in base ai totali trovati che sono stati liquidati tra il 2022 e il 2023.
    - **Parte del saldo iniziale non liquidata rispetto all'anno precedente:** Il secondo importo è la differenza tra il saldo iniziale e il primo importo di $525. L'importo rimanente è $1700 – $700 = $1000.

    In questo modo, puoi liquidare le transazioni del 2023 rispetto all'importo $700 originariamente liquidata rispetto alla transazione del 2022. Questo passaggio è necessario perché la liquidazione contabile non consente la liquidazione parziale.

    1. Vai al giornale di registrazione generale e registra la rettifica. La tua organizzazione dovrà decidere quale data di transazione utilizzare, in base ai periodi aperti nel 2023.
    2. Potrebbe essere necessario disattivare temporaneamente il parametro **Non consentire l'immissione manuale** nella pagina **Conto principale**. Questa rettifica non verrà registrata se il conto principale non consente l'immissione manuale.

    ![Rettifica non registrata.](./media/afterYEC5.png)

8. È ora possibile liquidare nuovamente le transazioni non liquidate. Torna alla pagina **Compensazione dei saldi contabili** e limita l'intervallo di date dal 1° gennaio 2022 al 31 dicembre 2022. L'illustrazione seguente mostra le transazioni non liquidate attualmente esistenti.

    ![Transazioni non liquidate.](./media/afterYEC6.png)

    - Il saldo iniziale di $1.700 può essere liquidato rispetto alla rettifica per -$1.700.
    - Le transazioni dettagliate non liquidate per -$700 possono essere liquidate a fronte della rettifica per $700,00.

9. Riabilita la funzione **Riconoscimento**.
10. Dopo aver abilitato la funzione **Riconoscimento**, la liquidazione contabile non può essere eseguita tra gli anni fiscali. Potrebbe essere necessario dividere ulteriormente il saldo rimanente di $1.000 in importi minori prima di poter liquidare rispetto a nuove transazioni nel 2023. Alcuni clienti scelgono di registrare quel dettaglio durante il passaggio 8, dove $1.000 è ulteriormente suddiviso per rappresentare le transazioni non liquidate nel 2022. Questo approccio imita essenzialmente ciò che fa la funzione **Riconoscimento** solo per l'anno in corso. L'anno prossimo, verrà eseguito automaticamente utilizzando l'impostazione **Mantieni dettagli** nella configurazione della liquidazione contabile.
