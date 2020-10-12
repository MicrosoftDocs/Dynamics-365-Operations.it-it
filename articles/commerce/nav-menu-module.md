---
title: Modulo menu di spostamento
description: In questo argomento vengono descritti i moduli menu di spostamento per i cookie e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 91239bd1db3f5819b7ad8d45ccfd8ab0d88b1b41
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817876"
---
# <a name="navigation-menu-module"></a>Modulo menu di spostamento

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

In questo argomento vengono descritti i moduli menu di spostamento per i cookie e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Lo scopo principale dei moduli del menu di spostamento è quello di consentire agli utenti del sito di sfogliare i prodotti e le pagine del sito secondo la gerarchia di navigazione del canale definita in Dynamics 365 Commerce headquarters. Gli elementi configurati in un modulo del menu di spostamento vengono visualizzati come spostamento dell'intestazione del sito. I moduli del menu di spostamento supportano anche voci di menu statiche che collegano ad altre pagine su un sito di e-commerce.

Il modulo del menu di spostamento può essere aggiunto al modulo dell'intestazione di una pagina. Nel tema Fabrikam, il menu di spostamento mostra due livelli per impostazione predefinita. Nel tema Starter, il menu di spostamento mostra tre livelli per impostazione predefinita. Per passare al numero di livelli, è necessaria un'estensione di visualizzazione per il tema.

La figura seguente mostra un esempio di un menu di spostamento per il sito Fabrikam con due livelli di gerarchia di categorie e alcune voci di menu statiche.
![Esempio di modulo del menu di spostamento](./media/ecommerce-header.png)

## <a name="navigation-menu-module-properties"></a>Proprietà del modulo menu di spostamento

| Nome proprietà             | Valore                 | descrizione |
|---------------------------|-----------------------|-------------|
| Origine                  | **Vendita al dettaglio**, **Creazione manuale**, **Vendita al dettaglio e creazione manuale** | Il valore **Vendita al dettaglio** consente di visualizzare la gerarchia di spostamento del canale da Commerce headquarters nel menu di spostamento. Il valore **Creazione manuale** consente di curare le voci di menu statiche. Il valore **Vendita al dettaglio e creazione manuale** consente una combinazione di entrambi. |
| Mostrare le immagini di categoria | **True** o **False**    | Se abilitata, questa proprietà visualizza le immagini delle categorie nel menu di spostamento come definito in Commerce headquarters per ciascuna categoria. Aggiunto nella versione Commerce 10.0.14. |
| Voce di menu statico| Matrice di valori| Voci di menu statico che associano il nome di una voce di menu a un collegamento di una pagina del sito statico. È possibile creare voci di menu sotto altre voci di menu. Per impostazione predefinita, i menu statici vengono visualizzati al livello radice e verranno aggiunti alla gerarchia di spostamento del canale, se esistente. |

La figura seguente mostra un esempio di un'immagine di categoria visualizzata nel menu di spostamento per il sito Fabrikam.
![Esempio di un modulo menu di spostamento con immagini di categorie](./media/ecommerce-categoryimages.PNG)

## <a name="add-a-navigation-menu-module-to-a-header-module"></a>Aggiungere un modulo del menu di spostamento a un modulo di intestazione

Per dettagli su come aggiungere un modulo del menu di spostamento a un modulo di intestazione, vedere [Modulo di intestazione](author-header-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo casella acquisti](add-buy-box.md)

[Conformità dei cookie](cookie-compliance.md)

[Modulo intestazione](author-header-module.md)
