---
title: Contenitori di spedizione
description: In questo articolo viene descritto come configurare contenitori di spedizione per il modulo Costo di spedizione.
author: Weijiesa
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 345f815a4f85db30db18aba3f8a4d41835c2e3f2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860844"
---
# <a name="shipping-container-setup"></a>Configurazione dei contenitori di spedizione

[!include [banner](../../includes/banner.md)]

In questo articolo viene descritto come configurare contenitori di spedizione per il modulo **Costo di spedizione**.

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a>Configurare tipi di contenitore di spedizione

I tipi di contenitore di spedizione definiscono i tipi di contenitore di spedizione disponibili per l'uso durante la spedizione e i viaggi.

Selezionare **Costo sbarcato \> Configurazione contenitori \> Tipi di contenitore di spedizione** per visualizzare, aggiungere e rimuovere i record dei tipi di contenitore. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Tipo di contenitore di spedizione | Immettere un nome/numero di identificazione univoco per il tipo di contenitore di spedizione. |
| Descrizione | Immettere una descrizione del tipo di contenitore di spedizione. |
| Volume | Immettere il volume massimo consentito nei contenitori di spedizione di questo tipo. |
| Peso | Immettere il paso massimo consentito nei contenitori di spedizione di questo tipo. |
| A rendere | Specificare se i contenitori di spedizione di questo tipo possono essere restituiti al fornitore dopo essere stati utilizzati in un viaggio. Se questa opzione è impostata su *Sì*, è possibile che vengano applicati costi aggiuntivi per la restituzione dei contenitori di questo tipo al porto di origine. |

## <a name="set-up-shipping-containers"></a>Configurare contenitori di spedizione

I record di contenitore di spedizione consentono di identificare ogni contenitore utilizzato durante i viaggi. Quando si crea un viaggio, è possibile selezionare uno specifico contenitore nell'elenco di tutti i record di contenitore di spedizione definiti qui. Questa funzione è particolarmente utile se l'azienda possiede dei contenitori di spedizione.

Non è necessario immettere i numeri dei contenitori di spedizione che verranno utilizzati una sola volta. È invece possibile aggiungere i numeri dei contenitori di spedizione quando si crea un viaggio.

I record di contenitore di spedizione sono utilizzati solo in Costo sbarcato. Non sono disponibili nel modulo **Gestione trasporti** standard.

Selezionare **Costo sbarcato \> Configurazione contenitori \> Contenitori di spedizione** per visualizzare, aggiungere e rimuovere i record dei contenitori di spedizione. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Contenitore di spedizione | Immettere un nome/numero di identificazione univoco per il contenitore di spedizione. |
| Tipo di contenitore di spedizione | Selezionare il tipo di contenitore di spedizione. Per ulteriori informazioni, vedi la sezione [Configurare tipi di contenitori di spedizione](#shipping-container-types) descritta precedentemente in questo articolo. |

> [!NOTE]
> - La configurazione dei contenitori di spedizione è facoltativa. In genere, la si utilizza solo se l'azienda possiede dei contenitori di spedizione o se riutilizza spesso gli stessi contenitori di spedizione.
> - Non vengono calcolate cifre di controllo per i numeri dei contenitori di spedizione.

## <a name="set-up-unit-types"></a><a name="unit-types"></a>Configurare tipi di unità

I tipi di unità stabiliscono raggruppamenti e metodi di identificazione aggiuntivi per i contenitori di spedizione. Il tipo di unità viene generalmente utilizzato per identificare il tipo di contenitore in cui vengono imballate le merci, come pallet o fusti. È possibile selezionare un tipo di unità quando si configura un contenitore nella pagina **Tutti i contenitori di spedizione**.

I tipi di unità sono utilizzati solo in Costo sbarcato. Non sono disponibili nel modulo Gestione trasporti.

Selezionare **Costo sbarcato \> Configurazione contenitori \> Tipi di unità** per visualizzare, aggiungere e rimuovere i record dei tipi di unità. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Tipo di unità | Immettere un nome/numero di identificazione univoco per il tipo di unità. |
| Descrizione | Immettere una descrizione del tipo di unità. |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a>Configurare tipi di refrigerazione

I tipi di refrigerazione stabiliscono raggruppamenti e metodi di identificazione aggiuntivi per i contenitori di spedizione (solitamente contenitori refrigerati). È possibile selezionare un tipo di refrigerazione quando si configura un contenitore nella pagina **Tutti i contenitori di spedizione**.

Selezionare **Costo sbarcato \> Configurazione contenitori \> Tipi di refrigerazione** per visualizzare, aggiungere e rimuovere i record dei tipi di refrigerazione. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Tipo di refrigerazione | Immettere un nome/numero di identificazione univoco per il tipo di refrigerazione. |
| Descrizione | Immettere una descrizione del tipo di refrigerazioneE. |
