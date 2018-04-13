--- 
title: Creare un numero di prodotto per le varianti prodotto predefinite
description: "In questa guida viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato."
author: BibiSp
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3a1bfd4bd5f396c05277159ac112eaa8197d5818
ms.openlocfilehash: c423aab341ddad9383c4c95b9dbb63c9875c99ef
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---
# <a name="create-a-product-number-for-predefined-product-variants"></a>Creare un numero di prodotto per le varianti prodotto predefinite

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

In questa guida viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. La nuova nomenclatura di numero prodotto è assegnata al gruppo di dimensioni prodotto Colore e Dimensioni. Questa attività viene in genere effettuata da un responsabile del design del prodotto.


## <a name="create-a-product-number-nomenclature"></a>Creare una nomenclatura di numero prodotto
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Nomenclatura di prodotto.
3. Fare clic su Nuovo.
4. Nel campo Nome immettere un nome di nomenclatura che consenta di identificare il gruppo di dimensioni prodotto di destinazione, ad esempio ColorSize.
5. Nel campo Descrizione digitare un valore.
6. Scegliere Aggiungi.
7. Fare clic su Numero rappresentazione generale prodotto.
8. Scegliere Aggiungi.
9. Fare clic su Costante testo.
10. Digitare un valore nel campo Testo.
11. Scegliere Aggiungi.
12. Fare clic su Colore.
13. Scegliere Aggiungi.
14. Fare clic su Costante testo.
15. Digitare un valore nel campo Testo.
16. Scegliere Aggiungi.
17. Fare clic su Dimensione.
18. Chiudere la pagina.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Assegnare la nomenclatura a una rappresentazione generale prodotto
1. Fare clic su Gruppi di dimensioni prodotto.
2. Selezionare il gruppo di dimensioni prodotto SizeCol.
3. Fare clic su Modifica.
4. Selezionare Sì nel campo Utilizza nomenclatura.
5. Nel campo Nomenclatura di numero di variante prodotto immettere o selezionare un valore.
6. Chiudere la pagina.


