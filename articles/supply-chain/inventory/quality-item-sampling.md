---
title: Campionamento degli articoli per la gestione della qualità
description: In questo argomento viene descritto come impostare il campionamento degli articoli.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae8bfd329ca0d7c30adcd93a759ee6bea7b76278
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022230"
---
# <a name="quality-management-item-sampling"></a>Campionamento degli articoli per la gestione della qualità

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
