---
title: Archiviazione dati di aging cliente
description: Questo articolo descrive il processo di utilizzo dell'archiviazione esterna per i dati di aging dei clienti. È possibile eseguire il processo di archiviazione dei dati di aging del cliente per rendere disponibile l'output per l'esportazione in un sistema esterno.
author: JodiChristiansen
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d7a66485cc9a538f5c3999009b6dbe295d7a5b9f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894144"
---
# <a name="customer-aging-data-storage"></a>Archiviazione dati di aging cliente

[!include [banner](../includes/banner.md)]

Questo articolo descrive il processo di utilizzo dell'archiviazione esterna per i dati di aging dei clienti. In Microsoft Dynamics 365 Finance è possibile eseguire il processo **Archiviazione dati di aging cliente** per rendere disponibile l'output per l'esportazione in un sistema esterno. Quando si esegue il processo, le stesse opzioni di report di aging disponibili nel sistema sono disponibili per i sistemi esterni. I dettagli sono sempre inclusi nei dati esportati.

Può essere utile rendere disponibili i dati di aging dei clienti a un sistema esterno per l'archiviazione nei casi in cui l'output contenga molti clienti e/o molte transazioni. Se l'esistente report **Aging del cliente** esegue un timeout perché ha troppi dati da stampare, questa funzione fornisce un modo alternativo per ottenere gli stessi dati.

## <a name="enable-the-customer-aging-data-storage-feature"></a>Abilitare la funzionalità di archiviazione dei dati di aging del cliente

Prima di utilizzare questa funzionalità, è necessario abilitarla nel sistema. Gli amministratori possono utilizzare le impostazioni della gestione delle funzionalità per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** Crediti e riscossioni
- **Nome funzionalità:** Archiviazione dei dati di aging del cliente

## <a name="run-the-customer-aging-data-storage-process"></a>Eseguire il processo di archiviazione dei dati di aging del cliente

1. Vai a **Crediti e riscossioni \> Richieste di informazioni e report \> Cliente \> Archiviazione dei dati di aging del cliente**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome** immetti un nome per il processo.
4. Imposta i parametri rimanenti come desideri.

    > [!NOTE]
    > I dettagli della transazione sono sempre inclusi e l'elaborazione viene sempre eseguita in un processo batch.

5. Seleziona **OK**.
6. Aggiorna la pagina **Archiviazione dei dati di aging del cliente** per vedere i valori **Nome batch** e **Tempo di esecuzione batch** che vengono mostrati insieme al valore **Stato di elaborazione**. Quando il processo batch è completato, il campo **Stato di elaborazione** è impostato su **Completato** e il campo **Numero di righe di aging** è impostato. Se il lavoro batch è ricorrente, il campo **Stato di elaborazione** è impostato su **In attesa**.
7. Seleziona il pulsante **Filtro** accanto al campo **Numero di righe di aging** per rivedere i filtri che sono stati aggiunti per il processo batch.

La pagina **Archiviazione dei dati di aging del cliente** non include i risultati. In ogni caso, l'entità dati **Archiviazione dei dati di aging del cliente** consente di esportare l'output in qualsiasi formato supportato da Gestione dati.

> [!NOTE]
> Prima di eseguire un'esportazione, aggiungi un filtro per limitare i risultati esportati ai dati di aging più recenti. Ad esempio, aggiungi i seguenti criteri per restituire l'esecuzione batch più recente:
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchName())
>
> In alternativa, aggiungi i seguenti criteri per restituire l'esecuzione batch più recente per l'utente corrente:
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchNameForCurrentUser())
