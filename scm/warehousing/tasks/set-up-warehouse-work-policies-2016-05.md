--- 
title: 'Impostare i criteri di lavoro magazzino '
description: I processi del magazzino non includono sempre il lavoro in magazzino.
author: johanhoffmann
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 5db1c99833276a92467ed57b7be51b0ebaa74d83
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-warehouse-work-policies"></a>Impostare i criteri di lavoro magazzino  

[!include[task guide banner](../../includes/task-guide-banner.md)]

I processi del magazzino non includono sempre il lavoro in magazzino. Definendo i criteri di lavoro, è possibile impedire la creazione di lavoro per il prelievo delle materie prime e lo stoccaggio di prodotti finiti per un set di prodotti in ubicazioni specifiche. La società di dati dimostrativi USMF è stata utilizzata per creare questa registrazione. Questa guida attività richiede l'applicazione Dynamics AX 7.0.1 o versione successiva.

1. Andare a Gestione magazzino > Impostazioni > Lavoro > Criteri di lavoro.
2. Fare clic su Nuovo.
3. Nel campo Nome criteri di lavoro digitare “No lavoro di stoccaggio".
4. Fare clic su Salva.
5. Scegliere Aggiungi.
6. Nell'elenco contrassegnare la riga selezionata.
7. Nel campo Tipo ordine di lavoro selezionare "Stoccaggio prodotti finiti".
8. Scegliere Aggiungi.
9. Nell'elenco contrassegnare la riga selezionata.
10. Nel campo Tipo ordine di lavoro selezionare "Stoccaggio co-prodotti e sottoprodotti".
11. Espandere la sezione Ubicazioni di magazzino.
12. Scegliere Aggiungi.
13. Nell'elenco contrassegnare la riga selezionata.
14. Nell'elenco di magazzino immettere "51".
15. Nel campo Ubicazione immettere o selezionare "001".
16. Espandere la sezione Prodotti.
17. Nel campo Selezione prodotto selezionare "Selezionato".
18. Scegliere Aggiungi.
19. Nell'elenco contrassegnare la riga selezionata.
20. Nel campo Numero articolo immettere o selezionare "L0101".
21. Fare clic su Salva.


