---
title: Conferma batch e targa
description: In questo argomento viene descritto come impostare e applicare la conferma batch e targa da un dispositivo mobile.
author: Mirzaab
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c588e6ed11d275b75133e2824f3d385048050426
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837539"
---
# <a name="batch-and-license-plate-confirmation"></a>Conferma batch e targa

[!include [banner](../includes/banner.md)]

La conferma batch consente di verificare che il batch corretto viene selezionato nel dispositivo mobile. Nel prelievo iniziale del lavoro solo per gli articoli *Batch-above\[location\]*, dove batch-above indica che il batch è sopra l'ubicazione nella gerarchia di ricerca, è necessario verificare che il batch selezionato corrisponda al batch della riga di lavoro.

La conferma targa consente di verificare che la targa corretta viene selezionata nel dispositivo mobile. Quando si seleziona il lavoro da un'ubicazione della fase, è necessario verificare che la targa selezionata corrisponda alla targa associata al lavoro. Se il lavoro viene avviato tramite la scansione della targa, questo passaggio di conferma verrà ignorato.

## <a name="where-it-applies"></a>Dove si applica

La conferma viene applicata nei seguenti scenari:

- La conferma batch viene applicata ai prelievi iniziali del lavoro per batch sopra gli articoli.
- La conferma targa si applica ai prelievi dalle ubicazioni della fase.

> [!IMPORTANT]
> Il rifornimento non è supportato per la conferma della targa. Quando si esegue il lavoro di rifornimento, non viene creato alcun passaggio di conferma della targa.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Configurare la conferma batch e targa

È possibile configurare la conferma batch e targa tramite le voci di menu del dispositivo mobile.

1. Dalle voci di menu del dispositivo mobile, aprire la configurazione della conferma del lavoro.  
1. Selezionare l'opzione per la conferma batch o targa. Entrambe le opzioni sono disponibili per i prelievi di tipo lavoro senza la conferma automatica attivata.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
