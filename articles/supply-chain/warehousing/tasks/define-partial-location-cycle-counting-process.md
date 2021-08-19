---
title: 'Definire il processo di conteggio ciclo parziale di ubicazione '
description: Quando si utilizzano i piani di conteggio ciclo per creare il lavoro di conteggio, è possibile definire le operazioni di conteggio effettive richiedendo che vengano conteggiati solo i prodotti specifici e le varianti prodotto anziché tutti le scorte disponibili nell'ubicazione.
author: ShylaThompson
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d3362aed9627d30f8c117e303e1124fa1dd2069e8629e55325c6ff21fe51c01
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722105"
---
# <a name="define-partial-location-cycle-counting-process"></a>Definire il processo di conteggio ciclo parziale di ubicazione  

[!include [banner](../../includes/banner.md)]

Quando si utilizzano i piani di conteggio ciclo per creare il lavoro di conteggio, è possibile definire le operazioni di conteggio effettive richiedendo che vengano conteggiati solo i prodotti specifici e le varianti prodotto anziché tutti le scorte disponibili nell'ubicazione. Applicando un filtro per prodotti specifici, il responsabile del magazzino può ridurre i costi generali di revisione, evitare errori di consolidamento e risparmiare tempo. In genere, un responsabile del magazzino esegue le attività di impostazione. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure con dati propri.


## <a name="create-a-cycle-counting-work-template"></a>Creare un modello di lavoro di conteggio ciclo
1. Andare a Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro.
2. Nel campo Tipo ordine di lavoro selezionare "Conteggio ciclo".
3. Fare clic su Nuovo.
4. Immettere un numero nel campo Numero progressivo.
    * L'ordinamento è crescente. Il valore deve essere maggiore di 0 (zero).  
5. Nell'elenco contrassegnare la riga selezionata.
6. Digitare un valore nel campo Modello di lavoro.
7. Nel campo Descrizione modello di lavoro, immettere un valore.
8. Nel campo ID pool lavoro immettere o selezionare un valore.
9. Nel campo Priorità lavoro immettere un numero.
10. Fare clic su Salva.
11. Fare clic su Nuovo.
12. Nell'elenco contrassegnare la riga selezionata.
13. Nel campo Tipo di lavoro selezionare "Conteggio".
14. Nel campo ID classe lavoro immettere o selezionare un valore.
15. Fare clic su Salva.
16. Fare clic su Interruzioni riga lavoro.
17. Fare clic su Nuovo.
18. Immettere un numero nel campo Numero progressivo.
    * L'ordinamento è crescente. Il valore deve essere maggiore di 0 (zero).  
19. Fare clic su Salva.
20. Chiudere la pagina.
21. Chiudere la pagina.

## <a name="create-a-cycle-counting-plan"></a>Crea un piano di conteggio ciclo
1. Andare a Gestione magazzino > Impostazioni > Conteggio ciclo > Piani di conteggio ciclo.
2. Fare clic su Nuovo.
3. Nel campo ID piano di conteggio ciclo immettere un valore.
4. Digitare un valore nel campo Descrizione.
5. Nel campo Numero massimo di conteggi ciclo immettere un numero.
6. Nel campo Modello di lavoro immettere o selezionare un valore.
7. Fare clic su Nuovo.
8. Immettere un numero nel campo Numero progressivo.
    * L'ordinamento è crescente. Il valore deve essere maggiore di 0 (zero).  
9. Nel campo Descrizione digitare un valore.
10. Fare clic su Salva.
11. Fare clic su Definisci query prodotto.
12. Nell'elenco contrassegnare la riga selezionata.
13. Nel campo Criteri immettere o selezionare un valore.
14. Fare clic su OK.
15. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]