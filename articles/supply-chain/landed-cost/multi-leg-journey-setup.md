---
title: Configurare percorsi con più scali
description: In questo argomento viene descritto come configurare percorsi con più scali per il modulo Costo sbarcato.
author: sherry-zheng
manager: tfehr
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMLegTable, ITMJourneyTable, ITMActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 88e1d94f7c3a9b624447c5fc000afc3faab395f1
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500432"
---
# <a name="multi-leg-journey-setup"></a>Configurare percorsi con più scali

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo argomento viene descritto come configurare percorsi con più scali per il modulo **Costo sbarcato**.

## <a name="legs"></a>Scali

Gli scali sono utilizzati per identificare parti distinte di un viaggio. Ogni scalo viene creato selezionando i porti di spedizione di origine e di destinazione e il metodo di trasporto utilizzato per quello scalo. I lead time possono essere associati a ciascun scalo. I lead time possono consentire la tracciabilità di una spedizione e anche essere utilizzati per calcolare la data di consegna stimata delle merci di un viaggio. Inoltre, quando uno scalo di un percorso viene completato, lo stato del viaggio, del contenitore di spedizione e delle righe di ordine fornitore associate può essere aggiornato tramite la configurazione del controllo di tracciabilità. Gli scali possono essere utilizzati da un singolo modello di percorso oppure possono essere riutilizzati da più modelli di percorso. Il carico dei contenitori, la dogana e il trasporto locale sono generalmente impostati come scali e per questi viene utilizzato un porto di spedizione non specifico.

Selezionare **Costo sbarcato \> Configurazione percorso con più scali \> Scali** per visualizzare, aprire, creare ed eliminare record per gli scali. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Scalo | Immettere un nome/numero di identificazione univoco per lo scalo del percorso. |
| Descrizione | Immettere una descrizione dello scalo del percorso. In genere, questa descrizione identifica i porti di destinazione e di origine o la fase del percorso. |
| Porto di origine | Immettere il punto di origine delle merci nello scalo. |
| Porto di destinazione | Immettere il punto di destinazione delle merci nello scalo. |
| Metodo di consegna | Immettere il metodo di trasporto dello scalo. |

## <a name="journey-templates"></a>Modelli di percorso

Un modello di percorso definisce il percorso con più scali delle merci tra due porti durante un viaggio. Gli scali del percorso vengono combinati per identificare il tempo necessario affinché le merci viaggino dal punto di origine del fornitore al magazzino di destinazione finale. Quando gli scali vengono inseriti nel modello di percorso in un ordine specifico, i lead time identificheranno la data di ciascun scalo e lo stato del viaggio, del contenitore e delle righe di acquisto per il viaggio. Per impostare i lead time associati a ciascuno scalo che compone il modello di viaggio, si utilizza il [Centro di controllo tracciabilità](delivery-information-setup.md). Il modello di percorso viene utilizzato anche quando vengono impostati i costi automatici di un viaggio. Quando viene definito un percorso, il costo associato al trasporto delle merci può essere definito nella pagina dei costi automatici.

Selezionare **Costo sbarcato \> Configurazione percorso con più scali \> Modelli di percorso** per visualizzare, aprire, creare ed eliminare modelli di percorso.

Per ogni modello di percorso, impostare i seguenti campi nell'intestazione.

| Campo | Descrizione |
|---|---|
| Modello di percorso | Immettere un nome/numero di identificazione univoco per il modello di percorso. Il modello di percorso in genere descrive il punto di origine e il punto di destinazione del percorso. |
| Descrizione | Immettere una descrizione del modello di percorso. La descrizione in genere indica i porti di destinazione e di origine e il tipo di viaggio. |

Nella sezione **Righe**, aggiungere una riga per ogni scalo del percorso e ordinare le righe. Usare le frecce **Su** e **Giù** nella barra degli strumenti per modificare l'ordine delle righe. Nella seguente tabella vengono descritti i campi disponibili per ogni riga.

| Campo | Descrizione |
|---|---|
| Scalo | Selezionare uno scalo da aggiungere al percorso. |
| Descrizione | La descrizione dello scalo. |
| Porto di origine | Il porto che il punto di origine delle merci nello scalo. Questo porto è il porto di destinazione utilizzato per determinare i costi automatici per un viaggio. |
| Porto di destinazione | Il porto di destinazione finale delle merci nello scalo. |
| Modalità di consegna | La modalità di consegna utilizzata per lo scalo. |
| Porto di origine percorso | Se il porto specificato per lo scalo viene utilizzato per determinare i costi automatici, selezionare questa casella di controllo per identificarlo come porto di origine del percorso. Questo porto verrà visualizzato nell'intestazione del viaggio. |
| Porto di destinazione percorso | Se il porto specificato per lo scalo viene utilizzato per determinare i costi automatici, selezionare questa casella di controllo per identificarlo come porto di destinazione del percorso. Questo porto verrà visualizzato nell'intestazione del viaggio. |
| Società di spedizione | Selezionare la società di spedizione utilizzata per lo scalo. |

## <a name="activities"></a>Attività

Le impostazioni nella pagina **Attività** stabilisce i tipi di attività che possono verificarsi nel porto di destinazione di uno scalo. Nella pagina **Tutti i contenitori di spedizione** gli utenti possono selezionare questi valori quando eseguono la stima della durata di ciascuna attività e registrano la durata effettiva per scopi di confronto.

Per impostare le attività, selezionare **Costo sbarcato \> Configurazione viaggi con più scali \> Attività**. In Attività, è possibile aggiungere, rimuovere e modificare attività utilizzando i pulsanti nel riquadro Azioni.

Nella seguente tabella vengono descritti i campi disponibili per ogni attività della griglia.

| Campo | Descrizione |
|---|---|
| Attività | Il nome dell'attività. |
| Descrizione | Una descrizione dell'attività. |
| Società di spedizione | Il conto fornitore della società di spedizione associata all'attività. |
