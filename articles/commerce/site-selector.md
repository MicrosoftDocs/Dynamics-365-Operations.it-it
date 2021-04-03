---
title: Modulo di selezione sito
description: In questo argomento viene descritto il modulo di selezione sito e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e24590d4a8f172809704aab0d761f6db0fb0e11b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234343"
---
# <a name="site-selector-module"></a>Modulo di selezione sito

[!include [banner](includes/banner.md)]

In questo argomento viene descritto il modulo di selezione sito e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.

Quando un'azienda ha siti diversi in mercati, regioni e impostazioni locali, gli utenti del sito hanno bisogno di un modo semplice per passare da un sito all'altro e selezionare il loro sito di acquisto preferito. Per soddisfare questo scenario, il modulo di selezione sito consente agli utenti di spostarsi su più siti.

Il modulo di selezione sito deve essere configurato con l'elenco dei siti (mercati, regioni o impostazioni locali) che gli utenti del sito possono esplorare.

> [!NOTE]
> Il modulo di selezione sito è disponibile in Dynamics 365 Commerce versione 10.0.14.

La figura seguente mostra un esempio di un modulo di selezione sito presente nell'intestazione di una pagina del sito.

![Esempio di un modulo di selezione sito nell'intestazione di una pagina del sito](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a>Proprietà del modulo di selezione sito

| Nome proprietà | Valore                 | Descrizione |
|---------------|-----------------------|-------------|
| Intestazione       | Testo                  | L'intestazione del modulo. |
| Opzioni sito  | Nome, immagine, URL      | Questa proprietà specifica un nome, un collegamento alla home page del sito e un'immagine facoltativa da mostrare per ogni sito incluso nel modulo. L'immagine può essere un flag o una rappresentazione di un mercato, una regione o un'impostazione locale. |

## <a name="add-a-site-selector-module-to-a-page"></a>Aggiungere un modulo di selezione sito a una pagina

Il modulo di selezione sito può essere aggiunto al [Modulo di intestazione](author-header-module.md) sotto lo slot di selezione sito. Dopo averlo aggiunto, è possibile definire l'intestazione del modulo e le opzioni del sito.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo intestazione](author-header-module.md)

[Modulo percorso di navigazione](add-breadcrumb.md)

[Modulo menu di spostamento](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]