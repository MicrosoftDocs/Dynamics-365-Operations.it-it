---
title: Rivalutazione valuta per la contabilità fornitori e la contabilità clienti
description: Questo articolo fornisce informazioni sul processo di rivalutazione valuta estera eseguito per aggiornare il valore delle transazioni aperte in contabilità fornitori e contabilità clienti.
author: angelad116
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustExchRateAdjustment, VendExchRateAdjustment
audience: Application User
ms.reviewer: kfend
ms.custom: 14211
ms.assetid: defb1ea5-1f3e-4859-87d8-3f9954d3f388
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4ffa4e1a02c84eda5f6710cb9049eab06955fac0
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151822"
---
# <a name="currency-revaluation-for-accounts-payable-and-accounts-receivable"></a>Rivalutazione valuta per la contabilità fornitori e la contabilità clienti

[!include [banner](../includes/banner.md)]

Le fluttuazioni nei tassi di cambio causano la variazione nel tempo del valore teorico (contabile) delle transazioni aperte in valuta estera. Questo articolo fornisce informazioni sul processo di rivalutazione valuta estera eseguito per aggiornare il valore delle transazioni aperte in contabilità fornitori e contabilità clienti. 

Il valore teorico o contabile delle transazioni aperte in valuta estera varia nel tempo a causa delle fluttuazioni dei tassi di cambio. Per aggiornare il valore delle transazioni aperte in contabilità fornitori e contabilità clienti, eseguire il processo di rivalutazione valuta estera. La rivalutazione della valuta estera può essere eseguita sia per la contabilità fornitori che per la contabilità clienti. Il processo utilizza un nuovo tasso di cambio per rivalutare gli importi aperti, o non liquidati, in una data specificata. Le differenze tra gli importi registrati originali e gli importi rivalutati determinerà un profitto non realizzato o una perdita non realizzata per ogni transazione aperta. I giornali di registrazione secondari Contabilità fornitori e Contabilità clienti vengono quindi aggiornati in modo da riflettere il profitto non realizzato o la perdita non realizzata e nella contabilità generale viene registrata una voce contabile.

## <a name="simulate-a-foreign-currency-revaluation"></a>Simulare una rivalutazione fattura estera
Prima di rivalutare gli importi in valuta estera nelle transazioni aperte, è possibile eseguire un report di simulazione della rivalutazione valuta estera per la stessa data e metodo. Per eseguire il report di simulazione, nella pagina **Rivalutazione valuta estera** fare clic sul pulsante **Simulazione**. Il report fornisce un'anteprima del profitto non realizzato o dell'importo in perdita, in base ai parametri definiti per la simulazione.

## <a name="process-a-foreign-currency-revaluation"></a>Elaborare una rivalutazione valuta estera
Utilizzare la pagina **Rivalutazione valuta estera** in **Attività periodiche** per rivalutare le transazioni aperte. È possibile eseguire il processo in tempo reale o programmarne l'esecuzione utilizzando un batch. Quando si definiscono le impostazioni per il processo di rivalutazione, assicurarsi di verificare se si desidera stampare un report dei risultati. Il report di rivalutazione non può essere ristampato dopo che il processo è stato completato. Se si genera il report di rivalutazione valuta estera, tale report indicherà i diversi saldi a livello fornitore/cliente e a livello della valuta:

-   I saldi dei clienti o fornitori con transazioni in valuta estera rivalutate. Vengono visualizzati i seguenti saldi:
    -   Il saldo totale originale nella valuta estera.
    -   L'importo totale in valuta estera nella valuta di contabilizzazione prima della rivalutazione precedente.
    -   L'importo totale in valuta estera nella valuta di contabilizzazione alla data della rivalutazione corrente.
    -   La differenza tra la rivalutazione precedente e quella corrente. La differenza è il profitto non realizzato aggiuntivo o la perdita.
-   Il profitto non realizzato o la perdita totale per ogni valuta.

Viene generato un record ogni volta che si esegue una rivalutazione valuta estera. Nel record nella pagina **Rivalutazione valuta estera** selezionare **Transazioni** per visualizzare l'elenco dettagliato delle transazioni create a causa di rivalutazione. Ogni transazione giustificativo rappresenta la transazione aperta che è stata rivalutata. Se una transazione aperta viene rivalutata più volte, vi saranno due record che utilizzano lo stesso giustificativo. Un record sarà per lo storno del profitto non realizzato o della perdita non realizzata precedente e l'altro record sarà per il nuovo profitto non realizzato o la nuova perdita non realizzata. Per eseguire il processo di rivalutazione, fare clic sul pulsante **Rivalutazione valuta estera**. Definire le impostazioni appropriate per i parametri seguenti:

-   **Metodo**: metodo utilizzato nel processo di rivalutazione valuta estera selezionato:
    -   **Standard**: i processi di rivalutazione valuta estera vengono registrate indipendentemente dal risultato (profitto o perdita).
    -   **Minimo**: i processi di rivalutazione valuta estera vengono registrate solo se il risultato è una perdita.
    -   **Data fattura**: per i processi di rivalutazione valuta estera viene utilizzato il tasso di cambio originale delle transazioni, che vengono rivalutate al valore originale nella valuta di contabilizzazione. L'effetto di eventuali rivalutazioni precedenti viene annullato.
-   **Data da considerare**: data in cui vengono individuate tutte le transazioni con importi aperti (non liquidati) in tale data. Gli importi in valuta estera vengono rivalutati utilizzando i tassi di cambio specificati nella pagina **Tassi di cambio valutario** per la data considerata. Quando gli importi in valuta estera vengono rivalutati in una data specifica, quest'ultima diventa la data di ultima rivalutazione per le transazioni rettificate. Se si decide di eseguire una rivalutazione valuta estera per una data specifica precedente alla data di ultima rivalutazione valuta estera nelle transazioni già rettificate, il processo periodico non rettifica le transazioni aperte nella data considerata precedente, ma rettifica quelle con data di ultima rivalutazione più recente.
-   **Data del tasso**: data che determina il tasso di cambio utilizzato per la transazione di rivalutazione valuta estera.
-   **Utilizza profilo registrazione da**: profilo di registrazione utilizzato per immettere il conto principale predefinito per la contabilità clienti o la contabilità fornitori per le voci contabili delle transazioni di rivalutazione valuta estera:
    -   **Registrazione**: viene utilizzato il profilo registrazione della transazione cliente.
    -   **Selezione**: immettere il profilo di registrazione specificato nel campo **Profilo registrazione**.
-   **Profilo registrazione**: se nel campo **Seleziona** è indicato **Utilizza profilo registrazione da**, il profilo registrazione delle transazioni di rivalutazione valuta estera è determinato dal profilo specificato in questo campo.
-   **Dimensioni finanziarie**: dimensioni finanziarie registrate nelle voci contabili della transazione di rivalutazione valuta estera. Le dimensioni finanziarie non vengono convalidate in base alle regole per la struttura dei conti. La struttura dei conti in vigore al momento della registrazione delle fatture potrebbe non essere la stessa delle regole in vigore al termine della rivalutazione. Non sono disponibili opzioni per selezionare specifiche dimensioni finanziarie nel processo di rivalutazione, quindi la convalida della struttura dei conti viene ignorata.  
    -   **Nessuna**: non viene registrata alcuna dimensione finanziaria. Se nella struttura dei conti è presente una dimensione finanziaria obbligatoria, il processo di rivalutazione viene comunque eseguito e crea le voci contabili prive di dimensioni finanziarie. Verrà visualizzato prima un messaggio di avviso, in modo da poter annullare la rivalutazione.
    -   **Tabella**: nelle transazioni di rivalutazione valuta estera vengono registrate le dimensioni finanziarie del conto cliente o fornitore.
    -   **Registrazioni**: nelle transazioni di rivalutazione valuta estera vengono registrate le dimensioni finanziarie della transazione da rivalutare. Per impostazione predefinita, le dimensioni finanziarie del conto CoGe di contabilità clienti/fornitori della transazione originale verranno utilizzate per il conto principale di contabilità clienti/fornitori della della transazione di rivalutazione e le dimensioni finanziarie del conto CoGe di spesa, ricavi o cespiti verranno utilizzate per il conto principale di profitto non realizzato o perdita della transazione di rivalutazione.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
