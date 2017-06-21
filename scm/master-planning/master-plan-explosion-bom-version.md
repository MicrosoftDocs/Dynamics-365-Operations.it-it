---
title: Esplosione di una versione DBA
description: Questo articolo descrive uno scenario di pianificazione generale che include l'esplosione di una versione di distinta base (DBA).
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: efb184269c66483304af0589e4305a55ae08ce08
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="explosion-of-a-bom-version"></a>Esplosione di una versione DBA

[!include[banner](../includes/banner.md)]


Questo articolo descrive uno scenario di pianificazione generale che include l'esplosione di una versione di distinta base (DBA).

Un'esplosione della domanda di una versione DBA (distinta base) crea una domanda per ciascun articolo della riga DBA in un sito specifico e, probabilmente, in un magazzino specifico. In una DBA specifica del sito può essere definito un magazzino specifico per ogni riga DBA. Inoltre, per ogni riga DBA, le impostazioni delle dimensioni dell'articolo determinano la necessità o meno del magazzino. La domanda risultante per ciascun elemento della riga DBA diventa, quindi, il punto di inizio per un'ulteriore esplosione della domanda. In questo scenario di pianificazione generale sono previste le seguenti condizioni:

-   La dimensione sito è obbligatoria e deve essere immessa nella transazione relativa alla domanda.
-   La dimensione sito è coerente. Di conseguenza, il sito relativo alla domanda di livello inferiore corrisponde a quello riportato nella transazione della domanda iniziale.

Nella figura riportata di seguito è illustrato il processo di esplosione della domanda nella pianificazione generale. ![Esplosione della domanda mediante una versione DBA](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="see-also"></a>Vedere anche
--------

[Pianificazione generale - Come determinare la versione DBA](master-plan-bom-version-determined.md)

[Pianificazione generale e funzionalità multisito](master-plan-multisite-functionality.md)




