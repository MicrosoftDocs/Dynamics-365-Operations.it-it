---
title: Compensazioni dei saldi contabili
description: In questo argomento viene illustrato come utilizzare la pagina delle compensazioni dei saldi contabili per liquidare le transazioni contabili e stornare le liquidazioni.
author: mikefalkner
manager: aolson
ms.date: 09/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: c6502a6fb0ceaed75fd5bb6ec5b2f13db1879eea
ms.openlocfilehash: ec659a53c187b1bdfd81565d6e2f20a59e08834c
ms.contentlocale: it-it
ms.lasthandoff: 10/12/2018

---

# <a name="ledger-settlements"></a>Compensazioni dei saldi contabili

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Le compensazioni dei saldi contabili consentono di abbinare le transazioni in Dare e in Avere nella contabilità generale e di contrassegnarle come liquidati. In questo modo, è possibile garantire che le transazioni correlate siano state liquidate. È inoltre possibile stornare le liquidazioni se sono state effettuate per errore.

## <a name="enable-advanced-ledger-settlements"></a>Abilitare le compensazioni avanzate dei saldi contabili

La pagina delle compensazioni saldi contabili avanzate offre funzionalità aggiuntive per filtrare e selezionare le transazioni. Per attivare la pagina delle compensazioni saldi contabili avanzate, effettuare le seguenti operazioni.

1. Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**. 
2. Nella scheda **Compensazioni dei saldi contabili**, impostare **Compensazione saldi contabili avanzata** su **Sì** per attivare la funzionalità relativa. Verrà utilizzata la pagina **Compensazioni saldi contabili avanzata** quando si seleziona **Compensazioni dei saldi contabili** in **Attività periodiche**. 
3. È necessario specificare l'elenco dei conti da utilizzare per le compensazioni saldi contabili per ciascun piano dei conti. Questo elenco viene utilizzato per filtrare l'elenco di transazioni che viene visualizzato nella pagina **Compensazioni dei saldi contabili**. Nell'elenco **Piano dei conti**, selezionare un piano dei conti e quindi selezionare **Nuovo** per aggiungere nuovi conti all'elenco.

## <a name="settle-transactions-by-using-the-advanced-ledger-settlements-page"></a>Liquidare le transazioni utilizzando la pagina delle compensazioni dei saldi contabili avanzate

Per liquidare transazioni contabili, seguire questi passaggi.

1. Selezionare **Contabilità generale** \> **Attività periodiche** \> **Compensazione dei saldi contabili**.
2. Impostare i filtri nella parte superiore della pagina:

    - Selezionare un intervallo di date, oppure selezionare **Codice intervallo date** per compilare automaticamente l'intervallo di date.
    - Modificare il livello di registrazione in base alle esigenze.
    - Per visualizzare separatamente il conto CoGe e dimensioni, selezionare un set di dimensioni finanziarie.

3. Selezionare **Visualizza le transazioni** per visualizzare tutte le transazioni che corrispondono ai filtri impostati e l'elenco dei conti specificato quando si è impostato l'elenco del piano dei conti nella sezione precedente. Se si modifica uno dei filtri o dei set di dimensioni, è necessario selezionare nuovamente **Visualizza transazioni**.
4. Selezionare una o più righe per la liquidazione. Il valore del campo **Importo selezionato** nella parte superiore della pagina aumenta o diminuisce dell'importo totale delle righe selezionate.
5. Al termine di selezionare le transazioni, selezionare **Contrassegna selezionati**. Un segno di spunta appare nella colonna **Contrassegnato** per ogni transazione selezionata. Inoltre, il valore del campo **Importo contrassegnato** nella parte superiore della griglia aumenta o diminuisce dell'importo totale delle righe contrassegnate.
6. Quando il valore **Importo contrassegnato** è **0** (zero), selezionare **Liquida transazioni contrassegnate**. Lo stato delle transazioni contrassegnate viene aggiornato a **Liquidato**.

## <a name="make-transactions-easier-to-find"></a>Facilitare l'individuazione delle transazioni

Nella pagina **Compensazioni dei saldi contabili** sono disponibili le funzionalità che rendono più semplice visualizzare le transazioni per la liquidazione.

- Il pulsante **Rimuovi contrassegno da selezionati** consente di rimuovere il campo **Contrassegnato** per tutte le righe selezionate.
- Il filtro **Contrassegnato** consente di filtrare le transazioni in base a seconda che il campo **Contrassegnato** sia selezionato o deselezionato.
- Il filtro **Stato** consente di filtrare le transazioni in base a se lo stato è **Liquidato** o **Non liquidato**.
- Il pulsante **Ordina per importo assoluto** consente di ordinare gli importi per valore assoluto, in modo da poter raggruppare gli importi Dare e Avere con lo stesso importo.

## <a name="reverse-a-settlement"></a>Stornare una liquidazione

È possibile stornare una liquidazione effettuata per errore.

1. Eseguire i passaggi da 1 a 3 della sezione "Liquidare le transazioni utilizzando la pagina delle compensazioni dei saldi contabili avanzate" per mostrare le transazioni richieste.
2. Nel filtro **Stato**, selezionare **Liquidato**.
3. Selezionare una o più righe per lo storno. Il valore del campo **Importo selezionato** nella parte superiore della pagina aumenta o diminuisce dell'importo totale delle righe selezionate.
4. Al termine di selezionare le transazioni, selezionare **Contrassegna selezionati**. Un segno di spunta appare nella colonna **Contrassegnato** per ogni transazione selezionata. Inoltre, il valore del campo **Importo contrassegnato** nella parte superiore della pagina aumenta o diminuisce dell'importo totale delle righe contrassegnate.
5. Quando il valore **Importo contrassegnato** è **0** (zero), selezionare **Storna transazioni contrassegnate**. Lo stato delle transazioni contrassegnate viene aggiornato a **Non liquidato**.

## <a name="update-the-list-of-accounts-that-are-included-in-the-list-of-transactions"></a>Aggiornare l'elenco dei conti inclusi nell'elenco di transazioni

Selezionare **Conti compensazione saldi contabili** per aprire una finestra di dialogo in cui è possibile modificare i conti inclusi nell'elenco di transazioni. Selezionare **Nuovo** per aggiungere nuovi conti all'elenco. Questo elenco viene utilizzato per filtrare l'elenco di transazioni che viene visualizzato nella pagina **Compensazioni dei saldi contabili**.

