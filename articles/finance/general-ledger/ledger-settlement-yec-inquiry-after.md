---
title: Funzionalità Riconoscimento tra liquidazione saldi contabili dopo la chiusura di fine anno usando la pagina di richiesta
description: Questo articolo spiega come utilizzare la funzionalità Riconoscimento tra liquidazione saldi contabili usando la nuova pagina di richiesta dopo la chiusura di fine anno della contabilità generale.
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
ms.openlocfilehash: 921d2a17409ae10cd9c22eeca11557ba1248b9bc
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853129"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close-using-the-inquiry-page"></a>Funzionalità Riconoscimento tra liquidazione saldi contabili dopo la chiusura di fine anno usando la pagina di richiesta

Una modifica principale della funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno** (la funzionalità **Riconoscimento**) è che la liquidazione saldi contabili non può essere effettuata tra anni fiscali. Questa limitazione interannuale è rilevante solo per la liquidazione saldi contabili, non per la liquidazione della contabilità clienti o della contabilità fornitori.

Prima di abilitare la funzione **Riconoscimento**, l'anno fiscale che subirà la chiusura di fine anno non deve avere transazioni contabili liquidate tra gli anni fiscali. In particolare, tutte le transazioni registrate nell'anno fiscale per il quale si sta eseguendo la chiusura di fine anno devono essere non liquidate dalle transazioni registrate in un anno fiscale diverso. Le transazioni possono essere liquidate nuovamente rispetto alle transazioni nello stesso anno fiscale.

In questo articolo vengono descritti i passaggi necessari per identificare, annullare la liquidazione e reimpostare le transazioni contabili liquidate negli anni. Nell'esempio fornito, l'anno fiscale 2022 è stato chiuso. L'obiettivo è preparare le transazioni di liquidazione dei saldi contabili prima che venga eseguita la chiusura di fine anno 2023.

A partire da Microsoft Dynamics 365 Finance versione 10.0.29, puoi identificare, annullare e riliquidare le transazioni contabili utilizzando una nuova pagina di richiesta disponibile. Se al momento non usi Microsoft Dynamics 365 Finance versione 10.0.29 o successiva, puoi trovare i passaggi per identificare, annullare la liquidazione e reimpostare le transazioni contabili nei seguenti articoli:

- [Funzionalità Riconoscimento tra liquidazione saldi contabili prima della chiusura di fine anno](ledger-settle-yec.md)
- [Funzionalità Riconoscimento tra liquidazione saldi contabili dopo la chiusura di fine anno](ledger-settle-yec-after.md)

Per ulteriori informazioni sulla nuova finestra di richiesta, vedi [Richiesta compensazione dei saldi contabili](ledger-settlement-inquiry.md). 

## <a name="example-setup"></a>Esempio di impostazione

La figura seguente mostra le transazioni registrate per il conto principale 110200. Le transazioni in verde sono state liquidate nello stesso anno fiscale e non devono essere modificate. Le transazioni in rosso sono state sottoposte alla compensazione dei saldi contabili, ma hanno date di transazione in anni fiscali diversi. Tali transazioni devono essere identificate e potrebbe essere necessario stornare la liquidazione contabile.

![Transazioni contabili registrate.](./media/excel.png)

## <a name="example"></a>Esempio

Segui questi passaggi se la tua organizzazione desidera utilizzare la funzione **Riconoscimento** dopo l'esecuzione della chiusura di fine anno per l'anno fiscale 2022.

> [!NOTE]
> La chiusura di fine anno per gli anni fiscali 2022 e precedenti deve essere rieseguita solo se le nuove transazioni vengono registrate nell'anno fiscale 2022 o precedenti. Una volta completata la seguente procedura, nel 2022 non sono registrate nuove transazioni. Pertanto, la chiusura di fine anno non deve essere ripetuta.
>
> Le transazioni contabili liquidate negli anni fiscali possono rimanere liquidate contabilmente se non vengono liquidate a fronte di una transazione registrata nel 2022 o in una data successiva. Ad esempio, se hai liquidato le transazioni nel 2019 e nel 2020, possono rimanere liquidate.

1. Completa la chiusura di fine anno per il 2022 senza la funzione **Riconoscimento** abilitata.
2. Identifica tutte le transazioni registrate in altri anni fiscali ma liquidate rispetto a transazioni registrate nel 2023 (l'anno fiscale che verrà chiuso).

    > [!NOTE]
    > Le transazioni del 2021 liquidate rispetto alle transazioni del 2022 non sono rilevanti perché l'anno 2022 è già stato chiuso. Queste transazioni possono essere liquidate.

    1. Nella pagina **Compensazioni dei saldi contabili** seleziona **Verifica liquidazioni incrociate**.
    2. Seleziona l'anno fiscale 2023, il successivo anno fiscale di cui vuoi eseguire la chiusura di fine anno.
    3. Seleziona un valore nel campo **Set di dimensioni finanziarie** per visualizzare le dimensioni finanziarie che vuoi visualizzare per il conto contabile. Il conto principale viene sempre visualizzato, anche se il set di dimensioni selezionato non contiene un conto principale.
    4. Seleziona **Mostra transazioni**.

    La pagina di richiesta mostrerà tutte le transazioni di altri anni fiscali liquidate rispetto alle transazioni registrate nel 2023.

    ![Liquidazioni tra anni del 2023.](./media/2023-cross-settlement.png)

3. Seleziona e tieni premuta (o fai clic con il pulsante destro del mouse) la griglia, quindi seleziona **Esporta tutte le righe**. Queste righe sono tutte le transazioni che devono essere annullate dalle transazioni nel 2022 prima che possa essere eseguita la chiusura di fine anno per il successivo anno (2023). Vuoi un record di queste transazioni.

    Dopo che tutte le transazioni dettagliate del 2022 sono state esportate in Excel, sei pronto per annullare le transazioni utilizzando la pagina di richiesta.

4. Seleziona tutti i record nella griglia, quindi seleziona **Record contrassegnati non liquidati**. Tutte le transazioni selezionate nella griglia saranno annullate.

    Vengono visualizzati due messaggi di avviso per garantire che i dettagli della transazione vengano esportati in Excel prima che le transazioni vengano annullate. Se si annullano accidentalmente le transazioni contabili prima di inviare i dettagli a Excel, non c'è modo di annullare la liquidazione.

    ![Annullamento della liquidazione tra anni.](./media/revert-settlement.png)

5. Utilizza i dati di Excel per trovare l'importo totale delle transazioni nel 2022 liquidate rispetto alle transazioni nel 2023. In questo esempio, le transazioni del 2023 fanno un totale di $700.
6. Crea un giornale di registrazione generale di rettifica per suddividere il saldo iniziale per il 2022 in due importi: la parte liquidata alla transazione dell'anno fiscale 2022 e la parte non ancora liquidata al 2023.

    - **Parte del saldo iniziale liquidata nell'anno precedente:** Il primo importo è $700, in base ai totali trovati che sono stati liquidati tra il 2021 e il 2022.
    - **Parte del saldo iniziale non liquidata nell'anno precedente:** Il secondo importo è la differenza tra il saldo iniziale e l'importo liquidato di $700. L'importo rimanente è $1700 – $700 = $1000.

    In questo modo, puoi liquidare le transazioni del 2023 rispetto all'importo $700 originariamente liquidata rispetto alla transazione del 2022. Questo passaggio è necessario perché la liquidazione contabile non consente la liquidazione parziale.

    1. Vai al giornale di registrazione generale e registra la rettifica. La tua organizzazione dovrà decidere quale data di transazione utilizzare, in base ai periodi aperti nel 2023.
    2. Potrebbe essere necessario disattivare temporaneamente il parametro **Non consentire l'immissione manuale** nella pagina **Conto principale**. Questa rettifica non verrà registrata se il conto principale non consente l'immissione manuale.

    ![Registrazione di un giornale di registrazione generale di rettifica.](./media/no-manual4.png)

7. È ora possibile liquidare nuovamente le transazioni non liquidate. Torna alla pagina **Compensazione dei saldi contabili** e limita l'intervallo di date dal 1° gennaio al 31 dicembre 2023. Quindi utilizza le transazioni dettagliate che hai esportato in Excel per trovare le transazioni specifiche che devono essere riliquidate. L'illustrazione seguente mostra le transazioni non liquidate attualmente esistenti.

    ![Transazioni non liquidate 2023.](./media/2023-unsettled5.png)

    - Il saldo iniziale di $1.700 può essere liquidato rispetto alla rettifica per -$1.700.
    - Le transazioni dettagliate non liquidate per -$700 possono essere liquidate a fronte della rettifica per $700,00.

8. Abilita la funzione **Riconoscimento**. Ora sei pronto per eseguire la chiusura di fine anno.

    - Prima di eseguire la chiusura di fine anno per il 2023, valuta la possibilità di selezionare l'opzione **Mantieni dettagli** nella configurazione della liquidazione contabile per tutti i conti dello stato patrimoniale. Per altre informazioni vedi [Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno](awareness-between-ledger-settlement-year-end-close.md).
    - Quando inizi la chiusura di fine anno per il 2023, se vengono ancora rilevate transazioni che sono state liquidate negli anni fiscali, il processo di chiusura di fine anno ti avviserà immediatamente. Questa situazione potrebbe verificarsi se gli utenti liquidano le transazioni negli anni fiscali prima di abilitare la funzione **Riconoscimento**.
    - Se le transazioni 2022 e 2023 sono ancora liquidate, dovrai disattivare nuovamente la funzione **Riconoscimento** e ripetere i passaggi precedenti per annullare la liquidazione delle transazioni. Questo approccio è necessario perché il 2022 è chiuso e le transazioni non possono essere annullate in un anno fiscale chiuso.

Dopo che la chiusura di fine anno per il 2022 è stata eseguita correttamente, puoi lasciare abilitata la funzione **Riconoscimento** d'ora in poi.
