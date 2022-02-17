---
title: Compensazioni dei saldi contabili
description: In questo argomento viene illustrato come utilizzare la pagina delle compensazioni dei saldi contabili per liquidare le transazioni contabili e stornare le liquidazioni.
author: kweekley
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: e98b012210338e7f18cb874eefbc8a023aa4428b
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075326"
---
# <a name="ledger-settlements"></a>Compensazioni dei saldi contabili

[!include [banner](../includes/banner.md)]

La compensazione dei saldi contabili è il processo di abbinamento tra le transazioni in Dare e in Avere nella contabilità generale. La liquidazione degli importi a debito e a credito viene utilizzata per riconciliare il saldo del conto contabile con le transazioni dettagliate che compongono tale saldo.

Le transazioni liquidate possono essere escluse da richieste e report. In questo modo, è più facile analizzare le transazioni contabili aperte che costituiscono il saldo del conto contabile.

> [!IMPORTANT] 
> Anche i moduli Contabilità fornitori e Contabilità clienti includono liquidazioni di fatture e pagamenti. Quando la liquidazione avviene nei giornali di registrazione secondari della contabilità clienti e della contabilità fornitori, i movimenti contabili corrispondenti non vengono liquidati automaticamente.

## <a name="ledger-settlement-features"></a>Funzionalità di compensazione dei saldi contabili
In Microsoft Dynamics 365 Finance versione 10.0.21, l'opzione **Abilitare le compensazioni avanzate dei saldi contabili** è stata rimossa dalla pagina **Parametri di contabilità generale**. La liquidazione dei saldi contabili avanzata ora è sempre abilitata.
Nella versione Finance 10.0.25, è stata introdotta la funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno**. Questa funzionalità modifica la funzionalità fondamentale sia nella liquidazione dei saldi contabili che nella chiusura di fine anno della contabilità generale. Prima di abilitare questa funzionalità nell'area di lavoro **Gestione funzionalità**, vedi [Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno](awareness-between-ledger-settlement-year-end-close.md).

## <a name="set-up-ledger-settlement"></a>Impostare la liquidazione dei saldi contabili
È necessario selezionare i conti principali per i quali si desidera effettuare la liquidazione dei saldi contabili. Esistono due modi per selezionare questi conti principali.

1. Selezionare **Contabilità generale** > **Impostazione contabilità generale** > **Parametri di contabilità generale**.
2. Nella scheda **Compensazioni dei saldi contabili**, selezionare i piani dei conti da cui si desidera selezionare i conti principali.
3. Selezionare i conti principali per cui eseguire la liquidazione dei saldi contabili. Poiché i piani dei conti sono globali, tutte le società a cui sono assegnati i piani dei conti selezionati avranno gli stessi conti principali selezionati per la liquidazione dei saldi contabili.

  oppure

1. Passa a **Contabilità generale** > **Attività periodiche** > **Compensazioni dei saldi contabili**.
2. Seleziona **Conti compensazione saldi contabili**.
3. Nella finestra di dialogo, seleziona i piani dei conti e i conti principali per i quali effettuare la liquidazione dei saldi contabili. Questa finestra di dialogo è un collegamento. Tutti i conti principali che aggiungi qui si rifletteranno anche nella pagina **Parametri di contabilità generale**.

È possibile utilizzare le stesse procedure di base per rimuovere i conti principali dalla liquidazione dei saldi contabili in qualsiasi momento. La rimozione di un conto principale non ha effetto sulle precedenti liquidazioni dei saldi contabili. Tuttavia, il conto principale e le transazioni non appariranno più nella pagina **Compensazione dei saldi contabili**.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Liquida transazioni
Per liquidare transazioni contabili, seguire questi passaggi.

1. Passa a **Contabilità generale** > **Attività periodiche** > **Compensazioni dei saldi contabili**.
2. Impostare i filtri nella parte superiore della pagina:

    - Seleziona un intervallo di date. In alternativa, seleziona un intervallo di date, oppure seleziona un codice intervallo date per compilare automaticamente l'intervallo di date. Non è consigliabile eseguire la liquidazione dei saldi contabili per le transazioni che attraversano gli anni fiscali.
    - Modificare il livello di registrazione in base alle esigenze. Non puoi liquidare transazioni che si trovano in livelli di registrazione diversi.
    - Per visualizzare separatamente il conto principale e le dimensioni, selezionare un set di dimensioni finanziarie.

3. Selezionare **Visualizza le transazioni** per visualizzare tutte le transazioni che corrispondono ai filtri impostati e l'elenco dei conti specificato quando si è impostato l'elenco del piano dei conti nella sezione precedente.

    - Se si modifica uno dei filtri o dei set di dimensioni, è necessario selezionare nuovamente **Visualizza transazioni**.
    - Per filtrare le transazioni su un singolo conto principale, utilizzare il filtro nel campo **Conto CoGe**. Non è consigliabile eseguire la liquidazione dei saldi contabili per le transazioni registrate in conti principali diversi.

4. Seleziona le righe per la liquidazione. Il valore del campo **Importo selezionato** nella parte superiore della pagina aumenta o diminuisce per riflettere l'importo totale delle righe selezionate.
5. Quando hai terminato di selezionare le transazioni, seleziona **Contrassegna selezionati**. Per ogni transazione selezionata, viene visualizzato un segno nella colonna **Contrassegnato**. Inoltre, il valore del campo **Importo contrassegnato** nella parte superiore della griglia aumenta o diminuisce per riflettere l'importo totale delle righe contrassegnate.
6. Quando il valore nel campo **Importo contrassegnato** è **0** (zero), selezionare **Liquida transazioni contrassegnate**. Lo stato delle transazioni contrassegnate viene aggiornato a **Liquidato**.

    > [!IMPORTANT]
    > Tutte le transazioni che hai contrassegnato per la liquidazione per la persona giuridica attiva verranno liquidate, anche se non sono attualmente visualizzate nella pagina Compensazione dei saldi contabili perché hai applicato un filtro.

## <a name="make-transactions-easier-to-find"></a>Facilitare l'individuazione delle transazioni
Nella pagina **Compensazioni dei saldi contabili** sono disponibili le funzionalità che rendono più semplice visualizzare le transazioni di cui hai richiesto la liquidazione.

- Utilizza il filtro **Contrassegnato** per filtrare le transazioni a seconda che la casella di controllo **Contrassegnato** sia selezionata.
- Utilizza il filtro **Stato** per filtrare le transazioni in base al loro stato.
- Seleziona **Ordina per importo assoluto** per ordinare gli importi in base al valore assoluto. In questo modo puoi raggruppare addebiti e crediti di pari importo.

## <a name="reverse-a-settlement"></a>Stornare una liquidazione
È possibile stornare una liquidazione effettuata per errore.

1. Segui i passaggi da 1 a 3 nella sezione [Liquidare le transazioni](#settle-transactions) per mostrare le transazioni che ti interessano.
2. Nel filtro **Stato**, selezionare **Liquidato**.
3. Seleziona le righe per lo storno.
4. Seleziona **Storna transazioni contrassegnate**. Lo stato di tutte le transazioni che hanno lo stesso ID liquidazione viene aggiornato in **Non liquidato**.

    > [!IMPORTANT]
    > Tutte le transazioni che hanno lo stesso ID liquidazione verranno stornate, anche se non contrassegnate. Ad esempio, quattro righe sono state contrassegnate e liquidate. Tutte e quattro le righe hanno lo stesso ID liquidazione. Se contrassegni una di queste quattro righe e poi selezioni **Storna transazioni contrassegnate**, tutte e quattro le righe verranno stornate.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
