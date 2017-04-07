---
title: Report le distinte base come finite
description: L&quot;articolo prevede informazioni sulla dichiarazione di finito delle DBA.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMReportFinish, BOMReportFinishMax
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53251
ms.assetid: 510d05a3-0073-438d-b0c4-b6a6df1882ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 318c88f88277a8300b1fcda5056a9a92c9a81eae
ms.lasthandoff: 03/31/2017


---

# <a name="report-boms-as-finished"></a>Report le distinte base come finite

L'articolo prevede informazioni sulla dichiarazione di finito delle DBA.

Le pagine **Dichiarazione di finito** e **Dichiarazione di finito max** vengono utilizzate per dichiarare finite le distinte base (DBA). Concettualmente, il processo per la dichiarazione di finito DBA corrisponde al processo per la dichiarazione di finito dell'ordine di produzione. Questo processo può essere utilizzato in, ad esempio, processi semplici di assemblaggio e kitting, in cui le funzionalità più avanzate degli ordini di produzione non sono obbligatorie. La pagina **Dichiarazione di finito** consente di dichiarare più DBA finite in un batch. ** Dichiarazione di finito ** la pagina consente di creare report solo finita una DBA alla volta. ** Dichiarazione di finito ** la pagina è disponibile da una gestione degli articoli in magazzino del menu e entrambe le pagine sono disponibili come voci di menu ** prodotti rilasciati ** nella pagina.

## <a name="report-as-finished-page"></a>Pagina Dichiarato finito
Se si apre la pagina **Dichiarazione di finito ** per un prodotto rilasciato, la pagina suggerisce di registrare la quantità standard di impostazione predefinita come finita. Per impostazione predefinita viene visualizzata la versione DBA attiva, ma è possibile modificare la versione DBA se sono presenti altre versioni approvate. La pagina consente anche di eliminare record e creare nuovi record per i prodotti rilasciati che devono essere dichiarati finiti. Per utilizzare una query per selezionare i prodotti, fare clic sulla voce di menu **Seleziona**. È possibile confermare manualmente la dichiarazione di finito per i prodotti selezionati facendo clic su **OK**. È inoltre possibile impostare il processo in modo tale che venga eseguito in batch. Quando il processo di dichiarazione di finito viene confermato, il sistema genera un giornale di registrazione DBA in cui viene elaborata la registrazione magazzino. Il giornale di registrazione è costituito da una voce del prodotto finito e una voce per ogni riga DBA. È possibile verificare se il giornale di registrazione è registrato automaticamente o se resta aperto per correzioni aggiuntive.

## <a name="max-report-as-finished-page"></a>Massimo. Dichiarazione di finito pagina
Nella pagina **Dichiarazione di finito max** ogni riga DBA indica il numero di pezzi di un prodotto che può essere dichiarato finito. Il calcolo è basato sulle scorte disponibili fisiche di ogni riga relativa al materiale. Nel seguente esempio, un pezzo del numero di articolo FG utilizza due pezzi di materie prime RM10 e un pezzo di materie prime RM20. Poiché sono disponibili solo 10 pezzi di RM10, la quantità massima di FG che può essere dichiarata finita è cinque pezzi. Questo valore viene visualizzato nel campo **Dichiarazione di finito max**.

| Livello | Numero articolo | Quantità | Disponibilità | Massimo. Dichiarazione di finito |
|-------|-------------|----------|---------|-------------------------|
| 0     | FG          |  1       | 0       | 5                       |
| 1     | RM10        | -2       | 10      | 5                       |
| 1     | RM20        | -1       |  8      | 8                       |

## <a name="boms-that-have-multiple-levels"></a>DBA con più livelli
Quando una DBA ha più livelli, è possibile verificare come i materiali sono rappresentati a tutti i livelli utilizzando il campo **Esplosione**. Questo campo è disponibile sia nella pagina **Dichiarazione di finito** che nella pagina **Dichiarazione di finito max**. Sono disponibili le seguenti opzioni:

-   **Mai**: le DBA sottostanti non vengono esplose in caso di carenza di materiali.
-   **Sempre**: tutte le DBA sottostanti vengono interamente esplose. Le scorte disponibili per gli articoli componente semilavorati non vengono quindi utilizzate.
-   **Carenza**: le DBA sottostanti vengono esplose soltanto se la quantità completa di materiale desiderato non è disponibile.

### <a name="example"></a>Esempio

In questo esempio, tre pezzi del prodotto finito (numero articolo FG) sono pronti per essere dichiarati finiti. Vi è una DBA a due livelli, come illustrato qui.

| Livello | Numero articolo | Quantità riga DBA | Disponibilità |
|-------|-------------|-------------------|---------|
| 0     | FG          |                   |         |
| 1     | COMP        | 1                 | 2       |
| 1     | RM          | 1                 |         |

Nelle seguenti tabelle viene illustrato come l'impostazione del campo **Esplosione** influisce sulla modalità in cui righe del giornale di registrazione DBA vengono generate. **Esplosione: Mai**

| Livello | Numero articolo | Quantità |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -3       |

Durante la tabella precedente, vengono visualizzati solo i COMP. al numero di articolo vengono considerati nel giornale di registrazione. Il RM del numero di articolo, che fa parte di COMP., non vengono esplose nella riga del giornale di registrazione e ai due disponibili pezzi di COMP. non viene considerato. **Esplosione: Sempre**

| Livello | Numero articolo | Quantità |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | RM          | -3       |

In questo caso, il numero di articolo COMP viene esploso nelle materie prime, numero di articolo RM. I due pezzi di COMP disponibili non vengono considerati nella quantità di RM da utilizzare. **Esplosione: Carenza**

| Livello | Numero articolo | Quantità |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -2       |
| 1     | RM          | -1       |

In questo caso, i due pezzi disponibili del numero di articolo COMP vengono considerati. Tuttavia, poiché tre pezzi del numero di articolo FG sono necessari, un pezzo del numero di articolo RM è inoltre necessario per effettuare il pezzo di COMP aggiuntivo.


