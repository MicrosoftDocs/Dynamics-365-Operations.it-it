---
title: Creare varianti prodotto predefinite
description: Questa procedura guida nella creazione di varianti prodotto per una rappresentazione generale prodotto mediante le combinazioni di dimensioni prodotto.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c33bbc7fa0ef7c3ce9768dd3688f9d1d575a513e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259868"
---
# <a name="create-predefined-product-variants"></a>Creare varianti prodotto predefinite

[!include [banner](../../includes/banner.md)]

Questa procedura guida nella creazione di varianti prodotto per una rappresentazione generale prodotto mediante le combinazioni di dimensioni prodotto. La società dimostrativa utilizzata per creare questa procedura è USMF.


## <a name="create-a-product-master"></a>Creare una rappresentazione generale prodotto
1. Andare a Gestione informazioni sul prodotto > Prodotti > Rappresentazioni generali prodotto.
2. Fare clic su Nuovo.
3. Nel campo Numero prodotto, digitare un valore.
    * Immettere un numero prodotto manualmente è obbligatorio solo se nessuna sequenza numerica è stata impostata per il campo relativo al numero di prodotto. In altre parole, ignorare il passaggio se la sequenza numerica è stata impostata per il campo.  
4. Digitare un valore nel campo Nome prodotto.
5. Nel campo Gruppo di dimensioni prodotto immettere o selezionare un valore.
    * Selezionare il gruppo di dimensioni prodotto SizeCol (dimensione e colore).  
6. Fare clic su OK.

## <a name="add-product-dimensions"></a>Aggiungere dimensioni prodotto
1. Fare clic su Dimensioni prodotto.
    * In questo esempio viene illustrato come immettere manualmente le dimensioni prodotto. È inoltre possibile scegliere di selezionare un gruppo di dimensioni, colore o stile che include i valori della dimensione prodotto si desidera utilizzare.  
2. Fare clic su Nuovo.
3. Nell'elenco contrassegnare la riga selezionata.
4. Nel campo Sito immettere o selezionare un valore.
5. Digitare un valore nel campo Nome.
6. Fare clic su Nuovo.
7. Nell'elenco contrassegnare la riga selezionata.
8. Nel campo Sito immettere o selezionare un valore.
9. Digitare un valore nel campo Nome.
10. Fare clic sulla scheda Colori.
11. Fare clic su Nuovo.
12. Nell'elenco contrassegnare la riga selezionata.
13. Nel campo Colore immettere o selezionare un valore.
14. Digitare un valore nel campo Nome.
15. Fare clic su Nuovo.
16. Nell'elenco contrassegnare la riga selezionata.
17. Nel campo Colore immettere o selezionare un valore.
18. Digitare un valore nel campo Nome.
19. Fare clic su Salva.
20. Chiudere la pagina.

## <a name="generate-product-variants"></a>Generare varianti prodotto
1. Fare clic su Varianti prodotto.
2. Fare clic su Suggerimenti variante.
3. Fare clic su Seleziona tutto.
    * In questo esempio sono selezionate tutte le possibili varianti. Se solo un sottoinsieme delle possibili combinazioni di dimensione prodotto verrà utilizzato per creare le varianti, è possibile selezionare le singole voci.  
4. Fare clic su Crea.
    * È possibile generare le descrizioni per tutte le varianti in base alla combinazione di valori di dimensione prodotto. La descrizioni sono facoltativa.  
5. Fare clic su Salva.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]