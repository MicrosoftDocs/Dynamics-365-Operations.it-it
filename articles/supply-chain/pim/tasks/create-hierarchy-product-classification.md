---
title: Creare una gerarchia di classificazione del prodotto
description: Questa procedura mostra come creare una nuova gerarchia di categorie e assegnare un tipo di gerarchia di codici di voce doganale.
author: ShylaThompson
manager: tfehr
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole, EcoResProductCategory, EcoResCategorySearchList, EcoResCategoryHierarchyFactbox, EcoResCategoryFriendlyName, EcoResCategoryAddProduct
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 439df63a4f8f0cc1c030554d18f80e9934c88b00
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431150"
---
# <a name="create-a-hierarchy-of-product-classification"></a>Creare una gerarchia di classificazione del prodotto

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come creare una nuova gerarchia di categorie e assegnare un tipo di gerarchia di codici di voce doganale. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata al responsabile della categoria.


## <a name="create-the-new-category-hierarchy"></a>Creare la nuova gerarchia di categorie
1. Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Impostazioni > Categorie e attributi > Gerarchie di categorie.**
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Nome**.
4. Digitare un valore nel campo **Descrizione**
5. Fare clic su **Crea**.

## <a name="build-the-hierarchy"></a>Sviluppare la gerarchia
1. Fare clic su nodo **Nuova categoria**.
2. Digitare un valore nel campo **Nome**.
3. Digitare un valore nel campo **Codice**.
4. Digitare un valore nel campo **Nome descrittivo**.
5. Fare clic su nodo **Nuova categoria**.
6. Digitare un valore nel campo **Nome**.
7. Digitare un valore nel campo **Codice**.
8. Digitare un valore nel campo **Nome descrittivo**.
9. Fare clic su nodo **Nuova categoria**.
10. Digitare un valore nel campo **Nome**.
11. Digitare un valore nel campo **Codice**.
12. Digitare un valore nel campo **Nome descrittivo**.
13. Fare clic su nodo **Nuova categoria**.
14. Digitare un valore nel campo **Nome**.
15. Digitare un valore nel campo **Codice**.
16. Digitare un valore nel campo **Nome descrittivo**.
17. Chiudere la pagina.

## <a name="classify-the-hierarchy"></a>Classificare la gerarchia
1. Nell'elenco trovare e selezionare il record desiderato.
2. Nel **riquadro Azioni** fare clic su **Gerarchia di categorie**.
3. Fare clic su **Associa tipo gerarchia**.
4. Fare clic su **Nuovo**.
5. Selezionare un'opzione nel campo **Tipo di gerarchia di categorie**. Selezionare il **tipo Gerarchia di codici di voce doganale per la classificazione di prodotto**.  
6. Nel campo **Gerarchia di categorie** fare clic sul pulsante a discesa per aprire la ricerca.
7. Trovare e selezionare il record desiderato nell'elenco.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]