---
title: Campionamento di elementi per la gestione della qualità
description: In questo articolo viene descritto come impostare il campionamento degli articoli.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 644eae4fbd9f82027c1cb69efba00dc893f8fc66
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865152"
---
# <a name="quality-management-item-sampling"></a>Campionamento di elementi per la gestione della qualità

[!include [banner](../includes/banner.md)]

Il campionamento degli articoli viene utilizzato come parte di un'associazione di controllo qualità. Definisce la quantità di scorte fisiche correnti da ispezionare. Il campionamento può essere basato su quantità fisse, una percentuale o una targa completa.

## <a name="set-up-item-sampling"></a>Imposta il campionamento articoli

Per impostare il campionamento degli articoli, effettuare le seguenti operazioni:

1. Fare clic su **Gestione scorte \> Impostazioni \> Controllo qualità \> Campionamento articoli**.
1. Selezionare **Nuovo**.
1. Nel campo **Campionamento articoli**, digitare un valore.
1. Nel campo **Descrizione** immettere un valore.
1. Nel campo **Valore** immettere un numero. Questo valore è correlato al valore della specifica della quantità selezionato nel campo adiacente.
1. Nella sezione **Elaborazione** selezionare la casella di controllo **Blocco completo** se l'intero lotto o la quantità della riga ordine deve essere bloccata se un test non è riuscito. Se questa casella di controllo è deselezionata, solo gli articoli nell'ordine di controllo qualità verranno bloccati se un test non viene superato.
1. Selezionare **Salva**.
1. Chiudere la pagina.

> [!NOTE]
> La funzionalità *Gestione della qualità per i processi di magazzino* fornisce ulteriori funzionalità di campionamento degli articoli. Aggiunge il concetto di *ambito di campionamento articoli* e consente di definire una targa completa come specifica della quantità. Se è stata abilitata questa funzionalità, vedere [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
