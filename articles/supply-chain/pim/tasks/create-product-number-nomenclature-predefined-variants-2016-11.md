---
title: Creare una nomenclatura del numero di prodotto per le varianti prodotto predefinite
description: In questa guida viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b49e96677b94d5f669ea41861f64e62e118938c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "364881"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Creare una nomenclatura del numero di prodotto per le varianti prodotto predefinite

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa guida viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. La nuova nomenclatura di numero prodotto è assegnata al gruppo di dimensioni prodotto Colore e Dimensioni. Questa attività viene in genere effettuata da un responsabile del design del prodotto.


## <a name="create-a-product-number-nomenclature"></a>Creare una nomenclatura di numero prodotto
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Nomenclatura di prodotto.
3. Fare clic su Nuovo.
4. Nel campo Nome, immettere un nome di nomenclatura che consente di identificare il gruppo di dimensioni prodotto di destinazione, ad esempio ColorSize.
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

