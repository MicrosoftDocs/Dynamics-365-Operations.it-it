---
title: Conferma batch e targa
description: In questo argomento viene descritto come impostare e applicare la conferma batch e targa da un dispositivo mobile.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0444caa0f1cc176153c322b8619db65bd377ddd0
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="batch-and-license-plate-confirmation"></a>Conferma batch e targa

[!include[banner](../includes/banner.md)]

La conferma batch consente di verificare che il batch corretto viene selezionato nel dispositivo mobile. Nel prelievo iniziale del lavoro solo per batch sopra gli articoli, dove batch sopra indica che il batch è sopra l'ubicazione nella gerarchia di ricerca, è necessario verificare che il batch selezionato corrisponda al batch della riga di lavoro. 

La conferma targa consente di verificare che la targa corretta viene selezionata nel dispositivo mobile. Quando si seleziona il lavoro da un'ubicazione della fase, è necessario verificare che la targa selezionata corrisponda alla targa associata al lavoro. Se il lavoro viene avviato tramite la scansione della targa, questo passaggio di conferma verrà ignorato.

## <a name="where-it-applies"></a>Dove si applica
La conferma viene applicata nei seguenti scenari:

- La conferma batch viene applicata ai prelievi iniziali del lavoro per batch sopra gli articoli.
- La conferma targa si applica ai prelievi dalle ubicazioni della fase.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Configurare la conferma batch e targa
È possibile configurare la conferma batch e targa tramite le voci di menu del dispositivo mobile.  
1.  Dalle voci di menu del dispositivo mobile, aprire la configurazione della conferma del lavoro.  
2.  Selezionare l'opzione per la conferma batch o targa. Entrambe le opzioni sono disponibili per i prelievi di tipo lavoro senza la conferma automatica attivata.  

