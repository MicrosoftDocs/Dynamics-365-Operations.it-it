---
title: Modificare l'ordine di visualizzazione per entità di merchandising
description: In questo articolo vengono descritti i concetti correlati al controllo dell'ordine di visualizzazione per varie entità di merchandising in Dynamics 365 Commerce.
author: josaw1
ms.date: 08/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 80586597f4f60476b341e4cf1cfd90f3681e15c0
ms.sourcegitcommit: 52e31b1ef2b3ed8675de931d06090cd57e057fc2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9265838"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Modificare l'ordine di visualizzazione per entità di merchandising


[!Include [banner](includes/banner.md)]

Per i rivenditori, l'individuazione dei prodotti è uno strumento principale per l'interazione dei clienti in tutti i canali. Sono disponibili varie funzionalità per consentire ai clienti di scoprire facilmente i prodotti. Ad esempio, i clienti possono esaminare le categorie, effettuare ricerche e applicare filtri.

In questo articolo vengono descritti i concetti correlati al controllo dell'ordine di visualizzazione per varie entità di merchandising. Viene inoltre illustrato come modificare l'ordine di visualizzazione.

## <a name="overview"></a>Panoramica

In Commerce, l'ordinamento di varie entità relative al merchandising è allineato agli scenari dei clienti esistenti e non richiede più estensioni da parte dei partner di implementazione.

In Commerce versioni 10.0.5 e precedenti, l'ordine delle categorie nella gerarchia di navigazione è alfabetico. La funzionalità di ordinamento personalizzata corrente consente ai responsabili del merchandising di configurare l'ordine per varie entità di merchandising in tutti i client dell'utente finale. Questi client includono le sedi e i servizi clienti.

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

![Gerarchia di prodotti ordinata con valori negativi.](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Prodotti rilasciati per categoria ordinati in base alla gerarchia di prodotti.](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>Configurare l'ordine di visualizzazione delle categorie nella gerarchia di navigazione nei canali

Per poter completare questa procedura, i dati dimostrativi devono essere installati nell'ambiente.

1. Andare a **Retail e Commerce \> Prodotti e categorie \> Categorie di navigazione nei canali**.
2. Nell'elenco, selezionare **Gerarchia di navigazione articoli di moda**.
3. Fare clic su **Modifica gerarchia di categorie**.
4. Fare clic su **Modifica**.
5. Nella struttura, seleziona **Abbigliamento \> Donna \> Scarpe**.
6. Immettere un numero nel campo **Ordine di visualizzazione**
7. Nella struttura, selezionare **Abbigliamento \> Donna \> Top**.

Analogamente, puoi definire l'ordine delle sottocategorie.

8. Nella struttura, selezionare **Abbigliamento \> Uomo \> Camicie casual**.
9. Immettere un numero nel campo **Ordine di visualizzazione**
10. Nella struttura, selezionare **Abbigliamento \> Uomo \> Giacche e cappotti**.
11. Immettere un numero nel campo **Ordine di visualizzazione**
12. Ripetere per tutte le altre categorie di cui si desidera modificare l'ordine.

L'ordine di visualizzazione della gerarchia di navigazione nei canali è rispecchiato nella sede centrale, nel catalogo e nei canali.

![Ordinamento personalizzato nella gerarchia di navigazione nei canali.](./media/ChannelNavCustomSorted.png)

![Gerarchia di navigazione nei canali ordinata in base alla gerarchia di navigazione nei canali.](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![POS con categorie ordinate.](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Per impostazione predefinita, la funzionalità **Abilita ordine di visualizzazione per entità di merchandising** è disattivata. Usa [Gestione funzionalità](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivarla. Dopo l'attivazione della funzionalità, esegui il processo CDX **Configurazione globale - 1110** dalla pianificazione di distribuzione.
> Se l'ordine delle tue categorie nel POS non viene aggiornato, riattiva il dispositivo. Le informazioni sulla categoria vengono recuperate all'attivazione del dispositivo, quindi il dispositivo potrebbe dover recuperare di nuovo le informazioni sulla categoria con gli ordini di visualizzazione aggiornati. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
