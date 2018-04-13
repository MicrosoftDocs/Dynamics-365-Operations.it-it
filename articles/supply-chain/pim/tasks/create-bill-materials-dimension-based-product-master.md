--- 
title: Creare una distinta base per una rappresentazione generale prodotto basata su dimensioni
description: "Per questa procedura è necessario completare le 4 guide precedenti di questa sequenza di otto registrazioni."
author: YuyuScheller
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8b5432addd1dd79a64dcbb751a59cf3084a63ab1
ms.openlocfilehash: 05837c2b21957133729074f614a6d3d7b7c08dad
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Creare una distinta base per una rappresentazione generale prodotto basata su dimensioni

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Per questa procedura è necessario completare le 4 guide precedenti di questa sequenza di otto registrazioni. Nelle prime 4 registrazioni vengono impostati i dati necessari per completare questa procedura. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa attività viene in genere gestita nella finestra di progettazione del prodotto.


## <a name="select-the-product"></a>Selezionare il prodotto
1. Fare clic su Gestione prodotti rilasciati.
2. Fare clic su Prodotti rilasciati.
3. Nell'elenco contrassegnare la riga selezionata.
    * Individuare la rappresentazione generale prodotto rilasciata con la tecnologia di configurazione basata su dimensioni creata nella prima attività della guida di questa sequenza.  
4. Nel riquadro azioni fare clic su Progettazione.
5. Fare clic su Versioni DBA.

## <a name="create-new-bom-and-bom-version"></a>Creare una nuova DBA e una nuova versione DBA
1. Fare clic su Nuovo.
2. Fare clic su DBA e versione DBA.
3. Digitare un valore nel campo Nome.
    * Impostazione di un sito  
    * In questa procedura non impostiamo un sito specifico per la DBA.  
4. Fare clic su OK.
5. Fare clic su Nuovo.
    * In questa procedura aggiungeremo quattro righe alla DBA. Due righe rappresentano le opzioni di cavo e due righe rappresentano le opzioni di gabinetto.  
6. Nell'elenco contrassegnare la riga selezionata.
7. Nel campo Numero di articoli immettere o selezionare un valore.
    * Selezionare il numero di articolo A0001, cavi HDMI 6.  
8. Nel campo Gruppo di configurazioni immettere o selezionare un valore.
    * Selezionare il gruppo di configurazione dei cavi creato nella guida 4 di questa sequenza.  
9. Fare clic su Nuovo.
    * Selezionare il numero di articolo A0002, cavi HDMI 12.  
10. Nell'elenco contrassegnare la riga selezionata.
11. Nel campo Numero di articoli immettere o selezionare un valore.
12. Nel campo Gruppo di configurazioni immettere o selezionare un valore.
    * Selezionare di nuovo il gruppo di configurazioni dei cavi.  
13. Fare clic su Nuovo.
14. Nell'elenco contrassegnare la riga selezionata.
15. Nel campo Numero di articoli immettere o selezionare un valore.
    * Selezionare il numero di articolo D0002, cabinet.  
16. Nel campo Gruppo di configurazioni immettere o selezionare un valore.
    * Selezionare il gruppo di configurazioni del cabinet per questa riga DBA.  
17. Fare clic su Nuovo.
18. Nell'elenco contrassegnare la riga selezionata.
19. Nel campo Numero di articoli immettere o selezionare un valore.
    * Selezionare il numero di articolo M0007 StandardCabinet come ultima riga DBA.  
20. Nel campo Gruppo di configurazioni immettere o selezionare un valore.
    * Selezionare il gruppo di configurazioni del cabinet per l'ultima riga DBA.  

## <a name="approve-and-activate"></a>Approva e attiva
1. Chiudere la pagina.
2. Fare clic su Approva.
3. Nel campo Approvato da immettere o selezionare un valore.
4. Selezionare Sì nel campo Approvare anche la distinta base? .
5. Fare clic su OK.
6. Fare clic su Attiva.


