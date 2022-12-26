---
title: Valuta di dichiarazione sbilanciata quando viene eseguita la chiusura di fine anno
description: Questo articolo spiega come la valuta di dichiarazione può essere sbilanciata quando viene eseguita la chiusura di fine anno.
author: kweekley
ms.date: 12/12/2022
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
ms.openlocfilehash: 31f79791330e076d4fbd7b604ba9f9c6cd9b9195
ms.sourcegitcommit: 44f0b4ef8d74c86b5c5040be37981e32eb43e1a8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2022
ms.locfileid: "9850261"
---
# <a name="reporting-currency-out-of-balance-when-the-year-end-close-is-run"></a>Valuta di dichiarazione sbilanciata quando viene eseguita la chiusura di fine anno

Dopo aver abilitato la funzione **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno** (la funzionalità **Riconoscimento** ), le transazioni contabili che sono state liquidate non saranno più incluse nel saldo di apertura dell'anno fiscale successivo quando viene eseguita la chiusura di fine anno della contabilità generale. L'esclusione delle transazioni contabili liquidate potrebbe rappresentare una sfida per i clienti alla chiusura di fine anno se per la contabilità generale è definita una valuta di dichiarazione.

La liquidazione contabile viene eseguita solo per la valuta di contabilizzazione. Quando le transazioni contabili vengono liquidate, la convalida conferma solo che i debiti nella valuta di contabilizzazione sono uguali ai crediti nella valuta di contabilizzazione. Gli importi nella valuta di dichiarazione per tali transazioni contabili non sono convalidati e gli addebiti potrebbero non corrispondere agli accrediti. Inoltre, la liquidazione contabile non calcola e non registra automaticamente un profitto/perdita nella valuta di dichiarazione.

A causa di queste limitazioni, una transazione profitto/perdita deve essere nella valuta di dichiarazione quando viene eseguita la liquidazione contabile. Se nessun profitto/perdita è incluso nella liquidazione contabile, verrà visualizzato un messaggio di sbilancio quando viene eseguita la chiusura di fine anno.

L'esempio seguente illustra i passaggi per risolvere questo problema prima che venga eseguita la chiusura di fine anno.

## <a name="example-setup"></a>Esempio di impostazione

Per impostare questo esempio, abilita la funzione **Riconoscimento** e imposta il conto principale 110180 per la liquidazione contabile. La figura seguente mostra le transazioni contabili che sono state registrate nella persona giuridica DEMF. La valuta contabile per DEMF è il dollaro USA (USD) e la valuta di dichiarazione è l'euro (EUR).

![Transazioni contabili registrate nella valuta di dichiarazione.](./media/reporting-currency-1.png)

La pagina **Compensazioni dei saldi contabili** mostra le transazioni contabili per il conto principale 110180. Seleziona e tieni premuta (o fai clic con il pulsante destro del mouse) la griglia, quindi seleziona **Inserisci colonne**. Aggiungi la colonna **Importo in valuta di dichiarazione** in modo che vengano visualizzati gli importi nella valuta della transazione, nella valuta di contabilizzazione e nella valuta di dichiarazione.

![Colonna Importo in valuta di dichiarazione aggiunta alla pagina Compensazioni dei saldi contabili.](./media/Ledger-settlement2.png)

Le prime due transazioni contabili per 100,00 EUR vengono liquidate come un unico gruppo, mentre le successive due transazioni contabili per 200,00 EUR vengono liquidate come un altro gruppo. Le due transazioni avranno ID liquidazione diversi. Questa configurazione mostra che le organizzazioni avranno più gruppi di transazioni contabili che vengono liquidate in momenti diversi e hanno date di liquidazione diverse. Una volta completata la liquidazione, la pagina **Compensazioni dei saldi contabili** mostra le seguenti informazioni quando viene filtrata per visualizzare le transazioni con stato **Liquidato**.

![Transazioni liquidate nella pagina Compensazioni dei saldi contabili.](./media/Settled-trans-filtered3.png)

Nella pagina **Ledger settlements** seleziona e tieni premuta (o fai clic con il pulsante destro del mouse) la colonna **Importo** e seleziona **Calcola totale di questa colonna**. Ripeti questo passaggio per le colonne **Importo in valuta di dichiarazione**. La valuta di contabilizzazione deve avere una differenza pari a 0 (zero) affinché avvenga la liquidazione. Tuttavia, non vi è alcuna convalida dell'importo di liquidazione per la valuta di dichiarazione. L'illustrazione seguente mostra una differenza di -27,79 USD per la valuta di dichiarazione.

![Differenza della valuta di dichiarazione.](./media/Difference4.png)

## <a name="year-end-close"></a>Chiusura di fine anno

Se la chiusura di fine anno viene ora eseguita per il 2022, il processo terminerà con un errore di sbilanciamento. Questo errore è causato direttamente dal fatto che la valuta di dichiarazione non dispone di un importo di liquidazione contabile pari a 0 (zero).

![Messaggio di errore che indica che l'importo della liquidazione contabile non è 0 (zero).](./media/YEC5.png)

## <a name="posting-reporting-currency-gainloss"></a>Registrazione di profitti/Perdite in valuta di dichiarazione

Affinché la chiusura di fine anno venga eseguita correttamente, la differenza nell'importo nella valuta di dichiarazione deve essere contabilizzata, in genere come profitto o perdita, e inclusa nella liquidazione contabile. Il profitto/perdita nella valuta di dichiarazione può essere registrato in diversi modi:

- Se il conto principale è la contabilità fornitori o la contabilità clienti, la liquidazione AR/AP di tali documenti genererà il profitto/perdita richiesto. Tale movimento contabile deve essere incluso nella liquidazione contabile quando vengono liquidate le transazioni contabili corrispondenti dalla fattura, dai pagamenti, dalle note di credito e così via.
- Se il conto principale è un conto diverso da conto fornitori o conto clienti, il profitto/perdita deve essere inserito manualmente. Al momento della registrazione del profitto/perdita, il livello di dettaglio della registrazione contabile è determinato dall'organizzazione.
- Per ogni conto principale, identifica l'importo del profitto/perdita nella valuta di dichiarazione che deve essere registrato.

Come descritto in precedenza, questa registrazione può essere effettuata nella pagina **Compensazioni dei saldi contabili**.

1. Filtra in base all'intervallo di date per il quale desideri registrare il profitto/la perdita. Se prevedi di pubblicare un profitto/perdita al mese, filtra per ogni mese. Se prevedi di registrare un profitto/perdita per anno fiscale, filtra per l'intero anno.
2. Filtro sul conto principale.
3. Filtra sullo stato, in modo che vengano mostrate solo le transazioni **liquidate**.
4. Aggiungi un totale nella colonna **Importo in valuta di dichiarazione**.
5. Se vuoi registrare il profitto/la perdita a un livello più granulare, è possibile filtrare ulteriormente l'ID liquidazione, le dimensioni finanziarie e così via. L'importo totale per la colonna **Importo in valuta di dichiarazione** rappresenta l'importo per il quale verrà registrato il profitto/la perdita.
6. Vai a **Contabilità generale \> Inserimenti nel giornale di registrazione \> Giornali di registrazione rettifiche valuta di dichiarazione**.
7. Immetti la transazione per il profitto/perdita. Questo giornale di registrazione registrerà una rettifica solo nella valuta di dichiarazione. Gli importi in valuta di transazione e in valuta di contabilizzazione che vengono registrati sono sempre 0 (zero). Se questo giornale di registrazione non è mai stato utilizzato in precedenza, potrebbe essere necessario creare un nome di giornale che abbia un tipo di giornale di **Rettifica valuta di dichiarazione** in **Contabilità generale \> Impostazione giornale di registrazione \> Nomi giornale di registrazione**.
8. Se il conto principale non consente l'inserimento manuale, questa rettifica non verrà registrata. Pertanto potrebbe essere necessario disattivare temporaneamente il parametro **Non consentire l'immissione manuale** nella pagina **Conto principale**.

![Inserimento manuale nella pagina Giustificativo giornale di registrazione.](./media/Manual-entry6.png)

Dopo aver contabilizzato il giornale di registrazione rettifiche, torna alla pagina **Compensazioni dei saldi contabili** e seleziona il conto principale per il quale hai registrato il profitto/la perdita. La rettifica profitto/perdita deve essere inclusa in una liquidazione contabile. Poiché l'importo nella valuta di dichiarazione non deve essere pari a 0 (zero), è possibile annullare eventuali transazioni precedenti e quindi liquidarle di nuovo, ma questa volta includendo il profitto/la perdita. La precisione che applichi per la registrazione del profitto/perdita e la liquidazione di tale profitto/perdita nelle liquidazioni contabili dipende dalla tua organizzazione.

L'illustrazione seguente mostra che le transazioni per 200 EUR sono state annullate e contrassegnate nuovamente per la liquidazione. Questa volta includeranno la rettifica profitto/perdita.

![Rettifica profitto/perdita nella pagina Liquidazioni contabili.](./media/gain-loss7.png)

Dopo che le transazioni sono state liquidate, modifica il filtro **Stato** in modo che la pagina mostri le transazioni **liquidate**. Il totale per la colonna **Importo in valuta di dichiarazione** è ora 0 (zero). La chiusura di fine anno può ora essere completata.

![Chiusura di fine anno completata.](./media/Zero-settled8.png)
