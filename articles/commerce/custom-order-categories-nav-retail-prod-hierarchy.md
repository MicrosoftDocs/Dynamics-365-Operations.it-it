---
title: Modificare l'ordine di visualizzazione per entità di merchandising
description: In questo argomento vengono descritti i concetti correlati al controllo dell'ordine di visualizzazione per varie entità di merchandising in Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 694f95e274dc068cba02a2a519c1ce3ed186eaf0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976765"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Modificare l'ordine di visualizzazione per entità di merchandising


[!include [banner](includes/banner.md)]

Per i rivenditori, l'individuazione dei prodotti è uno strumento principale per l'interazione dei clienti in tutti i canali. Varie funzionalità possono consentire ai clienti di scoprire facilmente i prodotti. Ad esempio, possono esaminare le categorie, cercare e filtrare.

In questo argomento vengono descritti i concetti correlati al controllo dell'ordine di visualizzazione per varie entità di merchandising. Viene inoltre illustrato come modificare l'ordine di visualizzazione.

## <a name="overview"></a>Panoramica

Il supporto per ordinare varie entità di merchandising è stato migliorato. Questo supporto è ora meglio allineato agli scenari per clienti esistenti che in precedenza richiedevano estensioni da partner di implementazione.

Nelle versioni di Retail precedenti alla versione 10.0.5, l'ordine delle categorie nella gerarchia di navigazione è alfabetico. La nuova funzionalità di ordinamento personalizzata consente ai responsabili del merchandising di configurare l'ordine per varie entità di merchandising in tutti i client dell'utente finale. Questi client includono le sedi e i servizi clienti.

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a>Configurare l'ordine di visualizzazione delle categorie nella gerarchia di prodotti

Per poter completare questa procedura, i dati dimostrativi devono essere installati nell'ambiente.

1. Selezionare **Retail e Commerce \> Prodotti e categorie \> Gerarchia di prodotti di Commerce**.
2. Fare clic su **Modifica gerarchia di categorie**.
3. Fare clic su **Modifica**.
4. Nella struttura espandere **TUTTO \> Sport d'azione**.
5. Nella struttura espandere **TUTTO \> Sport di squadra**.
6. Immettere un numero nel campo **Ordine di visualizzazione** (questo numero può essere negativo).
7. Ripetere i passaggi da 4 a 6 per tutte le categorie aggiuntive di cui si desidera modificare l'ordine.

L'ordine di visualizzazione della gerarchia di navigazione nei canali verrà riflessa nella sede per la gerarchia di prodotti di Commerce e i prodotti rilasciati per categoria.

![Gerarchia di prodotti ordinata con valori negativi](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Prodotti rilasciati per categoria ordinati in base alla gerarchia di prodotti](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>Configurare l'ordine di visualizzazione delle categorie nella gerarchia di navigazione nei canali

Per poter completare questa procedura, i dati dimostrativi devono essere installati nell'ambiente.

1. Andare a **Retail e Commerce \> Prodotti e categorie \> Categorie di navigazione nei canali**.
2. Nell'elenco, selezionare **Gerarchia di navigazione articoli di moda**.
3. Fare clic su **Modifica gerarchia di categorie**.
4. Fare clic su **Modifica**.
5. Nella struttura, selezionare **Abbigliamento \> Donna \> Scarpe**.
6. Immettere un numero nel campo **Ordine di visualizzazione**
7. Nella struttura, selezionare **Abbigliamento \> Donna \> Top**.

    Analogamente, è possibile definire l'ordine delle sottocategorie.

8. Nella struttura, selezionare **Abbigliamento \> Uomo \> Camicie casual**.
9. Immettere un numero nel campo **Ordine di visualizzazione**
10. Nella struttura, selezionare **Abbigliamento \> Uomo \> Giacche e cappotti**.
11. Immettere un numero nel campo **Ordine di visualizzazione**
12. Ripetere per tutte le altre categorie di cui si desidera modificare l'ordine.

L'ordine di visualizzazione della gerarchia di navigazione nei canali è rispecchiato nella sede centrale, nel catalogo e nei canali.

![Ordinamento personalizzato nella gerarchia di navigazione nei canali](./media/ChannelNavCustomSorted.png)

![Gerarchia di navigazione nei canali ordinata in base alla gerarchia di navigazione nei canali](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![POS con categorie ordinate](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Per impostazione predefinita, la personalizzazione della funzionalità di ordinamento è disattivata. Per informazioni su come attivare questa e altre funzionalità, vedere [Gestione funzionalità](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).
