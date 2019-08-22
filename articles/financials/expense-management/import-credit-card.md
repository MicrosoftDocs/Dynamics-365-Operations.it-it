---
title: Importare e gestire transazioni con carta di credito
description: Questo argomento descrive come importare e gestire le transazioni con carta di credito correlate alle spese. Queste transazioni possono essere impostate per essere incluse automaticamente in una programmazione ricorrente o importate manualmente quando necessarie.
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPbsMainDataLines
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 4484ea6fa446c73b8854e7822237bb3c6b9f9023
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840939"
---
# <a name="import-and-maintain-credit-card-transactions"></a>Importare e gestire transazioni con carta di credito

[!include [banner](../includes/banner.md)]

Le transazioni con carte di credito correlate alle spese possono essere impostate per essere incluse automaticamente in una programmazione ricorrente. In alternativa, le transazioni possono essere importate manualmente secondo le esigenze. Le transazioni con carta di credito vengono importate mediante l'entità di dati Transazioni con carta di credito.

Per ulteriori informazioni sulle entità di dati, vedere [Entità di dati](../../dev-itpro/data-entities/data-entities.md).

## <a name="import-credit-card-transactions"></a>Importa le transazioni con carta di credito

1. Nella pagina **Transazioni con carta di credito**, selezionare **Importa transazioni**. Se si apre per la prima volta la gestione dei dati, il sistema deve aggiornare l'elenco delle entità di dati prima di continuare.
2. Nel campo **Nome** immettere una descrizione univoca del processo di importazione.
3. Nel campo **Formato dati di origine**, selezionare il formato del file contenente le transazioni con carta di credito da importare.
4. Selezionare **Carica** e quindi individuare e selezionare il file da importare.
5. Dopo che il file è stato caricato, convalidare il mapping del file delle transazioni con carta di credito e le colonne dell'entità di dati Transazioni con carta di credito selezionando il collegamento **Visualizza mapping** nel riquadro. Se vi sono errori di mapping, o se è necessario modificare il mapping, apportare le modifiche al mapping nella scheda **Visualizzazione mapping** o **Dettagli mapping**.
6. Per automatizzare le transazioni con carta di credito, selezionare **Crea processo dati ricorrente**. È quindi possibile impostare la ricorrenza che definisce la frequenza di importazione delle transazioni con carta di credito. Al termine, selezionare **OK**.
7. Per importare il file selezionato, selezionare **Importa**.
8. Se si verificano degli errori durante l'importazione, è possibile visualizzare i dati di gestione temporanea o del registro di esecuzione per visualizzare gli errori che è necessario correggere per garantire una corretta importazione.

> [!NOTE]
> Se è necessario importare più formati di file, è necessario creare processi di importazione distinti per ogni tipo di formato.

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a>Riassegnare le transazioni con carta di credito per dipendenti con rapporto chiuso.

Dopo che un record dipendente viene terminato, l'account di Servizi di dominio Active Directory del dipendente viene disattivato. È tuttavia possibile che vi siano transazioni con carta di credito attive che devono ancora essere spese e rimborsate. Nella pagina **Transazioni con carta di credito**, è possibile riassegnare a un altro dipendente qualsiasi transazione con carta di credito del dipendente associato che ha concluso il rapporto di lavoro.

Selezionare una o più transazioni con carta di credito e selezionare **Riassegna transazioni**. È quindi possibile selezionare un altro dipendente a cui assegnare le transazioni con carta di credito. Dopo aver riassegnato le transazioni con carta di credito, possono essere selezionate per una nota spese e pagate tramite il normale processo di rimborso della nota spese.
