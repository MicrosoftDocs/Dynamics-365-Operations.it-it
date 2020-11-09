---
title: Elenco scorte disponibili
description: Questo argomento descrive come utilizzare la pagina Elenco scorte disponibili per esaminare i relativi dettagli. La pagina mostra come le varie opzioni di filtro e ordinamento interagiscono tra loro e in che modo tali opzioni possano talvolta produrre risultati imprevisti quando vengono combinate.
author: sherry-zheng
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem, InventOnHandItemListPage, WHSOnHand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 33e5ccc454191e27e33835a05094b823ec54e891
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017393"
---
# <a name="inventory-on-hand-list"></a>Elenco scorte disponibili

[!include [banner](../includes/banner.md)]

Questo argomento descrive come utilizzare la pagina **Elenco scorte disponibili** per esaminare i relativi dettagli. La pagina mostra come le varie opzioni di filtro e ordinamento interagiscono tra loro e in che modo tali opzioni possano talvolta produrre risultati imprevisti quando vengono combinate.

## <a name="query-your-on-hand-inventory"></a>Eseguire query sulle scorte disponibili

Per verificare la disponibilità delle scorte, andare a **Gestione articoli \> Richieste di informazioni e report \> Elenco scorte disponibili**.

La pagina **Elenco scorte disponibili** viene automaticamente aggiornata quando vengono effettuate transazioni nel magazzino. Tali transazioni potrebbero essere transazioni previste, fisiche o finanziarie.

Utilizzare i seguenti strumenti per trovare il set di prodotti che si sta cercando:

- Nel riquadro azioni selezionare [**Dimensioni**](#dimensions) per aprire una finestra di dialogo in cui è possibile aggiungere o rimuovere le colonne mostrate nella griglia **Disponibilità**.
- Nel [riquadro **Filtri**](#filters-pane), immettere i valori per i campi specifici per mostrare solo i record che corrispondono a tali valori. Tenere presente che i filtri qui definiti si applicano alle tabelle di origine che potrebbero essere aggregate in un secondo momento, in base alle dimensioni selezionate per la visualizzazione. Per informazioni su come questo comportamento può influire sui risultati, consultare gli [esempi](#examples) più avanti in questo argomento.
- Nel riquadro **Filtri** , selezionare **Applica** per generare l'elenco di scorte disponibili corrispondente nella griglia **Disponibilità**.
- Nella griglia **Disponibilità** , selezionare un'intestazione di colonna per ordinare o filtrare i valori in quella colonna. Un filtro rapido nella parte superiore della griglia offre opzioni di filtro aggiuntive. Questi filtri si applicano ai risultati, non alle tabelle di origine. Per informazioni su come questo comportamento può influire sui risultati, consultare gli [esempi](#examples) più avanti in questo argomento.

Per ogni elemento corrispondente, la griglia **Disponibilità** fornisce le seguenti colonne di informazioni sulle scorte.

| Colonna | descrizione |
|---|---|
| Inventario fisico | Quantità fisica disponibile in magazzino. |
| Fisico prenotato | Quantità totale fisicamente prenotata. |
| Fisico disponibile | Quantità disponibile (non prenotata) nell'inventario fisico.<p>**Fisico disponibile** è un campo calcolato. Il valore è uguale al valore **Inventario fisico** meno il valore **Fisico prenotato**.</p> |
| Fisico disponibile su dimensioni extra | La quantità fisica disponibile per tutte le dimensioni mostrate nella griglia. |
| Ordinata in totale | La quantità totale inclusa negli ordini in entrata o che presenta una quantità positiva in vari giornali di registrazione magazzino. |
| Merci ordinate in corso di consegna | La quantità totale inclusa negli ordini in uscita o che presenta una quantità negativa in vari giornali di registrazione magazzino. |
| Ordinato prenotato | Quantità totale prenotata sulle entrate ordinate. Il valore in questo campo rappresenta la quantità totale di articoli in transazioni in uscita con uno stato di _Ordinato prenotato_. Gli articoli prenotati come ordinati non sono fisicamente disponibili in magazzino. Pertanto, non possono essere prelevati e consegnati direttamente. |
| Disponibile per prenotazione | Quantità totale di scorte disponibili che può essere prenotata.<p>**Nota:** se la casella di controllo **Prenota articoli ordinati** è selezionata nella pagina **Parametri di gestione articoli e magazzino** , il valore in questo campo include le entrate previste. Se la casella di controllo è deselezionata, il valore esclude le entrate previste.</p> |
| Totale disponibile | Quantità totale disponibile.<p>**Totale disponibile** è un campo calcolato. Il valore è uguale al valore **Fisico disponibile** più il valore **Ordinata in totale** meno il valore **In ordinazione**.</p> |

## <a name="apply-filters-to-find-the-records-that-youre-looking-for"></a><a name="filters-pane"></a>Applicare i filtri per trovare i record che si stanno cercando

Utilizzare il riquadro **Filtri** per filtrare l'elenco di scorte disponibili in modo che includa solo i record in cui i valori dei campi corrispondono ai criteri di filtro. Per definire un filtro, seguire questi passaggi.

1. Nel riquadro **Filtri** , trovare il campo in base al quale filtrare.
2. Nel campo sotto il nome del campo di destinazione, selezionare un operatore logico (ad esempio, *inizia con* , *uguale a* o *maggiore di* ).
3. Immettere o selezionare il valore da cercare.

> [!IMPORTANT]
> La pagina **Elenco scorte disponibili** è assemblata da una tabella dettagliata di scorte disponibili che include tutte le dimensioni disponibili. Tuttavia, l'elenco in questa pagina è un riepilogo. Pertanto, potrebbe combinare le righe dalla tabella di origine aggregando i valori in base alle dimensioni visualizzate.
>
> I filtri definiti nel riquadro **Filtri** si applicano alla tabella di origine, non all'elenco aggregato. Questo comportamento a volte può produrre risultati imprevisti. Per informazioni su come questo comportamento può influire sui risultati, consultare gli [esempi](#examples) più avanti in questo argomento.
> 
> Comunque, i [filtri forniti nella griglia](#grid-filters) *si applicano* all'elenco aggregato. Questi filtri includono sia un filtro rapido nella parte superiore della griglia sia il filtro per ciascuna intestazione di colonna.

È possibile modificare il set di filtri disponibile nel riquadro **Filtri** seguendo questi passaggi.

- Per rimuovere un filtro dal riquadro, selezionare il relativo pulsante **Chiudi** ( **X** ).
- Per aggiungere un filtro, selezionare **Aggiungi** nella parte superiore del riquadro **Filtri**. La finestra di dialogo **Aggiungi campi filtro** che appare mostra un elenco dei campi disponibili. Mostra anche informazioni sul tipo di dati e la tabella per ciascun campo. Utilizzare le intestazioni di colonna per filtrare e ordinare l'elenco come richiesto, quindi selezionare la casella di controllo per ciascun campo che si desidera aggiungere al riquadro **Filtro**. Al termine, selezionare **Inserisci** per applicare le modifiche.

## <a name="select-which-dimensions-to-show"></a><a name="dimensions"></a>Selezionare le dimensioni da mostrare

Le dimensioni forniscono ulteriori informazioni su ciascun articolo nell'elenco di scorte disponibili e offrono altri modi per ordinare e filtrare l'elenco. Le dimensioni selezionate per la visualizzazione influiscono anche sul modo in cui le righe vengono aggregate nella pagina **Elenco scorte disponibili**. Questa aggregazione, a sua volta, può influire sul modo in cui le righe delle tabelle di origine vengono combinate nei risultati visualizzati. Per informazioni su come questo comportamento può influire sui risultati, consultare gli [esempi](#examples) più avanti in questo argomento.

Per personalizzare la selezione delle dimensioni inventariali visualizzata, attenersi alla seguente procedura.

1. Nel riquadro azioni selezionare **Dimensioni**.

    La finestra di dialogo **Visualizzazione dimensioni** che appare mostra ogni dimensione.

2. Selezionare le caselle di controllo corrispondenti alle dimensioni che si desidera includere nella griglia.
3. Se si desidera che la selezione venga utilizzata per impostazione predefinita alla successiva apertura della pagina **Elenco scorte disponibili** , impostare l'opzione **Salva impostazione** su **Sì**. Se si imposta questa opzione su **No** , la selezione verrà utilizzata solo durante la sessione corrente. Pertanto, alla successiva apertura della pagina, verrà utilizzata la selezione predefinita corrente.
4. Seleziona **OK** per chiudere la finestra di dialogo e applicare le modifiche.

## <a name="filter-on-the-output-of-the-inventory-on-hand-list"></a><a name="grid-filters"></a>Filtro sull'output dell'elenco scorte disponibili

È possibile selezionare qualsiasi intestazione di colonna nella griglia **Disponibilità** per ordinare o filtrare i valori in quella colonna. Un filtro rapido nella parte superiore della griglia offre opzioni di filtro aggiuntive. Questi filtri si applicano ai risultati, non alle tabelle di origine. Per informazioni su come questo comportamento può influire sui risultati, consultare gli [esempi](#examples) più avanti in questo argomento.

> [!NOTE]
> Non è possibile filtrare e ordinare in tutte le colonne. La maggior parte delle colonne di quantità non include i controlli di ordinamento e filtro, poiché sono campi calcolati. La colonna **In ordinazione** è un'eccezione.

## <a name="examples"></a><a name="examples"></a>Esempi

Il sistema include una tabella di scorte dettagliata (non aggregata) che mostra le seguenti scorte disponibili.

| Numero articolo | Sito | Magazzino | Inventario fisico | Fisico disponibile |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 2 | 2 | 2 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-1"></a>Scenario 1

La pagina **Elenco scorte disponibili** è impostata per mostrare le seguenti dimensioni finali:

- Numero articolo
- Sito
- Magazzino

Nel riquadro **Filtri** , sono impostati i seguenti criteri di filtro:

- **Numero articolo** \| **è esattamente** \| _IA0001_
- **Fisico disponibile** \| **inferiore o uguale a** \| _1_

Ecco l'output risultante.

| Numero articolo | Sito | Magazzino | Inventario fisico | Fisico disponibile |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-2"></a>Scenario 2

La pagina **Elenco scorte disponibili** è impostata per mostrare le seguenti dimensioni finali:

- Numero articolo
- Sito

Nel riquadro **Filtri** , sono impostati i seguenti criteri di filtro:

- **Numero articolo** \| **è esattamente** \| _IA0001_
- **Fisico disponibile** \| **inferiore o uguale a** \| _1_

Ecco l'output risultante.

| Numero articolo | Sito | Inventario fisico | Fisico disponibile |
|---|---|---|---|
| IA0001 | 1 | 2 | 2 |

Si noti che le impostazioni nel riquadro **Filtri** si applicano alla tabella di scorte dettagliata (non aggregata) mostrata all'inizio di questa sezione. Pertanto, il criterio **Fisico disponibile** \| **inferiore o uguale a** \| _1_ trova due righe di quella tabella (la prima e la terza riga, ognuna delle quali mostra un valore **Fisico disponibile** di _1_ ). Tuttavia, in questo scenario, la pagina **Elenco scorte disponibili** non è impostata per mostrare la dimensione **Magazzino**. Pertanto, aggrega le due righe originali in una singola riga risultante, poiché entrambe le righe hanno valori identici in tutte le dimensioni visualizzate. Questa riga sembra violare il criterio di filtro, perché il valore **Fisico disponibile** è mostrato come _2_. Tuttavia, il risultato è corretto, perché le impostazioni nel riquadro **Filtri** si applicano alla tabella di origine, non alla tabella aggregata mostrata nella pagina **Elenco scorte disponibili**.
