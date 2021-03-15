---
title: Formule e versioni di formula
description: Questo argomento fornisce informazioni sulle formule e sulle versioni di formula. Una formula definisce i materiali, gli ingredienti e i risultati di uno specifico processo nella produzione di processo. Le formule vengono utilizzate per progettare e creare prodotti nella produzione di processo.
author: cvocph
manager: tfehr
ms.date: 09/12/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PlanActivity, ReqSupplyDemandSchedule, EcoResProductProdTypeFormulaNoActiveFormulaFormPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e5ff5916366f968cbf8dc9a5614466ef89faa92
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007163"
---
# <a name="formulas-and-formula-versions"></a>Formule e versioni di formula

[!include [banner](../includes/banner.md)]

Una formula definisce i materiali, gli ingredienti e i risultati di uno specifico processo nella produzione di processo. Insieme al ciclo di lavorazione corrispondente, la formula definisce l'intero processo nella produzione di processo. Le formule vengono utilizzate per progettare e creare prodotti nella produzione di processo.

Una formula è costituita dagli ingredienti e dalla quantità necessari per produrre una determinata quantità di un articolo formula. A seconda dell'attività da eseguire, è possibile accedere a funzionalità per formule da Gestione articoli e magazzino o Gestione informazioni sul prodotto.

## <a name="formulas-and-formula-lines"></a>Formule e righe di formula
Una formula è costituita da una o più righe che identificano gli ingredienti o gli articoli che la costituiscono. Una riga di formula può contenere articoli della distinta base (DBA), articoli formula, articoli a peso variabile, articoli acquistati, co-prodotti o sottoprodotti. Poiché molti articoli vengono utilizzati in più prodotti, è possibile utilizzare un articolo in più di una formula.

Un esempio di formula è la formula per dei biscotti al cioccolato. Gli ingredienti della formula utilizzano più righe, ad esempio farina, zucchero, uova, burro e cioccolato. La formula dei biscotti al cioccolato contiene ingredienti che sono probabilmente utilizzati in altre formule. In seguito alla preparazione dei biscotti, è possibile che siano rimaste delle briciole oppure che alcuni biscotti siano troppo o poco cotti. Questi articoli possono essere definiti come co-prodotti o sottoprodotti, in base alle operazioni di produzione.

Quando si crea una riga di formula, si utilizza il tipo di riga per indicare come il sistema deve gestire la riga quando si esegue la pianificazione generale e si producono ordini batch. Il risultato è diverso per ogni tipo di riga. Nella tabella indicata di seguito vengono descritti i tipi di riga che è possibile selezionare. 

| Tipo di riga     | descrizione  |
|---------------|--------------|
| Articolo          | Selezionare **Articolo** se l'articolo è una materia prima o un articolo semi-lavorato prelevato dal magazzino o se è un servizio. |
| Fittizio       | Selezionare **Fittizio** quando si desidera esplodere qualsiasi articolo formula di livello inferiore contenuto nelle righe della formula. Se quando si stima l'ordine batch gli articoli della formula sono esplosi, gli articoli componente sono elencati come righe della formula nell'ordine batch. Inoltre, i cicli di lavorazione corrispondenti vengono aggiunti al ciclo di lavorazione produzione. Gli articoli formula vengono esplosi utilizzando la configurazione corrente. Quando si utilizza il tipo di riga **Fittizio**, è possibile gestire le configurazioni di produzione e di misurazione che si verificano a differenti livelli della formula. Se si seleziona **Fittizio** per un prodotto nella scheda dettaglio **Progettazione** della pagina **Dettagli prodotto rilasciato** e si utilizza questo prodotto in una formula, il tipo della riga della formula diventa **Fittizio**. Non è possibile selezionare **Fittizio** per un articolo a peso variabile o per articoli in cui tipo di produzione è **Co-prodotto**, **Sottoprodotto** o **Articolo pianificazione**. |
| Fornitura sottoposta a pegging | Selezionare **Fornitura sottoposta a pegging** per creare un ordine batch, ordine di produzione, kanban, ordine di trasferimento o ordine fornitore per l'ingrediente contenuto nella riga della formula. L'ordine correlato viene determinato in base alle impostazioni di ordine predefinite e al tipo di produzione dell'ingrediente e viene creato al momento della stima dell'ordine batch. Le quantità di ingredienti richieste vengono prenotate per l'ordine batch. |
| Fornitore        | Selezionare **Fornitore** se per il processo di produzione viene utilizzato un terzista e si desidera creare una produzione secondaria o un ordine fornitore per il terzista. Il servizio o il lavoro eseguito dal terzista deve essere creato utilizzando un articolo formula o un articolo di tipo Assistenza. È possibile collegare l'articolo all'articolo padre come riga della formula. Nel ciclo di lavorazione deve essere presente un'operazione assegnata alla risorsa operativa del terzista. Tale operazione viene associata alla riga della formula utilizzando il campo **Oper. n.**. . |

## <a name="formula-versions"></a>Versioni formula
Quando si crea una nuova formula, è necessario dapprima creare una versione della formula prima di aggiungere gli articoli delle righe della formula e le relative caratteristiche specifiche. A ogni formula deve essere associata almeno una versione. Il pulsante **Approvato** in una versione della formula diventa disponibile solo dopo aver salvato un record di versione. Ogni record di versione della formula è associato a uno o più co-prodotti e sottoprodotti che possono essere creati con il prodotto finito. Molti prodotti possono essere creati a partire dagli stessi ingredienti in dimensioni di batch differenti, in multipli oppure utilizzando rese differenti. È possibile creare un numero illimitato di versioni di una formula.

Per gestire più versioni di formula attive, utilizzare intervalli di date di validità oppure i campi Da quantità. Molteplici versioni di formula attive possono essere presenti solo se l'intervallo di date e il valore del campo Da quantità non si sovrappongono.

A differenza di una DBA, che è spesso associata a molte versioni di DBA, in genere per una formula si ha una sola versione di formula. Tenere presente che per le dimensioni e la quantità di copertura di uno specifico prodotto, è possibile attivare una sola versione di formula. Tuttavia, molte versioni di formula possono esistere per altre ragioni ed è possibile selezionarle manualmente quando si crea un ordine batch.

## <a name="approve-and-activate-formulas-and-formula-versions"></a>Approvare e attivare formule e versioni di formula
Formule e versioni di formula devono essere approvate prima di essere utilizzate per la pianificazione e la produzione. Le formule vengono in genere attivate prima di essere utilizzate. Tuttavia, durante la produzione, è possibile selezionare una versione di formula approvata ma non attivata.

Per proteggere una formula o una versione di formula, è possibile impostare i parametri **Blocca la modifica** e **Blocca rimozione approvazione** nella pagina **Parametri di controllo di produzione**.

Se si seleziona **Blocca la modifica** e la formula viene approvata, nessun campo nelle righe della formula può essere eliminato o modificato. Tuttavia, se si rimuove l'approvazione della formula, è possibile eliminare e modificare le righe della formula. È anche possibile creare nuove formule e nuove versioni di formula.

Se si seleziona **Blocca rimozione approvazione**, non è possibile rimuovere l'approvazione di una formula o di una versione di formula approvata. È tuttavia possibile creare nuove formule e nuove versioni di formula e rimuovere l'attivazione della versione di formula.

È possibile aggiungere più livelli di controllo utilizzando la funzionalità di firma elettronica. Se la configurazione richiede per un utente l'uso di una firma elettronica al momento dell'approvazione della formula, una pagina **Firma** viene visualizzata quando la formula è attivata. L'utente deve essere autorizzato a utilizzare la firma elettronica e il certificato deve essere convalidato perché la modifica venga applicata. Se la firma non può essere autenticata, l'approvazione o la rimozione dell'approvazione verrà negata e verrà ripristinato lo stato originale della modifica all'origine dell'approvazione o della rimozione dell'approvazione.

## <a name="use-the-scalable-feature"></a>Utilizzare la funzionalità Dimensionabile
La funzionalità Dimensionabile è disponibile solo se tutti i componenti dell'articolo nella formula sono impostati su **Consumo variabile**. La funzionalità non è disponibile se i componenti dell'articolo sono impostati su **Consumo fisso** o **Consumo fase**. Se si modifica un ingrediente in una formula quando si utilizza la funzionalità Dimensionabile, la quantità degli altri ingredienti viene modificata di conseguenza. Anche la dimensione della formula verrà rettificata. Analogamente, se si modificano le dimensioni della formula, la quantità di tutti gli ingredienti dimensionabili viene modificata. Questa funzionalità viene utilizzata specificatamente per la creazione e la gestione delle formule. Non indica se la quantità di un ingrediente verrà ridimensionata verso l'alto o verso il basso in un ordine batch.

## <a name="use-step-consumption"></a>Utilizzare Consumo fase
L'opzione Consumo fase elimina la necessità di immettere una quantità nella scheda **Riga formula** per un ingrediente. Questa opzione è invece configurata per avere un valore **Da serie** e un valore **Quantità**. Le informazioni del record Consumo fase per serie che soddisfano la quantità nell'ordine batch vengono selezionate. L'opzione Consumo fase è utile quando il tasso di consumo non è lineare rispetto alle dimensioni dell'ordine batch e aumenta la richiesta solo quando viene raggiunta una specifica soglia di quantità. Per attivare questa funzionalità per una nuova formula, nel gruppo **Calcolo consumo**, cambiare l'impostazione della formula per l'ingrediente applicabile da **Standard** a **Fase**. Si specifica questo metodo di consumo nella scheda **Impostazione** della pagina **Riga formula**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]