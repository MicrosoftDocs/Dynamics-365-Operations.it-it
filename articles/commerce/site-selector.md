---
title: Modulo di selezione sito
description: In questo argomento viene descritto il modulo di selezione sito e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ad4d4d5f950d0631059d8f509e9e808a9106eb98
ms.sourcegitcommit: 4861ec2d3ae24cc9dd4ad3ac748fd05be3d80c70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2022
ms.locfileid: "8551696"
---
# <a name="site-picker-module"></a>Modulo di selezione sito

[!include [banner](includes/banner.md)]

In questo argomento viene descritto il modulo di selezione sito e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.

Quando un'azienda ha siti diversi in mercati, regioni e impostazioni locali, gli utenti del sito hanno bisogno di un modo semplice per passare da un sito all'altro e selezionare il loro sito di acquisto preferito. Per soddisfare questo scenario, il modulo di selezione sito consente agli utenti di spostarsi su più siti. Ti consigliamo anche un selettore di siti quando [rilevamento e reindirizzamento geografico](geo-detection-redirection.md) sono stati implementati per il tuo sito di e-commerce, in modo che i clienti abbiano un modo per ignorare la preferenza del sito che indicano utilizzando il modulo [selettore paese/area geografica](country-region-picker-module.md). 

Il modulo di selezione sito deve essere configurato con l'elenco dei siti (mercati, regioni o impostazioni locali) che gli utenti del sito possono esplorare. La figura seguente mostra un esempio di un modulo di selezione sito presente nell'intestazione di una pagina del sito.

![Esempio di un modulo di selezione sito nell'intestazione di una pagina del sito.](./media/ecommerce-sitepicker.PNG)

## <a name="site-picker-module-properties"></a>Proprietà del modulo di selezione sito

| Nome proprietà | Valore                 | Description |
|---------------|-----------------------|-------------|
| Intestazione       | Testo                  | L'intestazione del modulo. |
| Opzioni sito  | Nome, immagine, URL      | Questa proprietà specifica un nome, un collegamento alla home page del sito e un'immagine facoltativa da mostrare per ogni sito incluso nel modulo. L'immagine può essere un flag o una rappresentazione di un mercato, una regione o un'impostazione locale. |

## <a name="add-a-site-picker-module-to-a-page"></a>Aggiungere un modulo di selezione sito a una pagina

Il modulo di selezione sito può essere aggiunto allo slot **Selezione sito** del [modulo di intestazione](author-header-module.md). Dopo aver aggiunto un modulo di selezione sito, è possibile definire l'intestazione del modulo e le opzioni del sito. In genere, un modulo di intestazione è contenuto in un frammento di intestazione che può essere condiviso tra le pagine di e-commerce di un sito. Nell'esempio seguente, il modulo di selezione sito è stato aggiunto allo slot **Selezione sito** di un modulo di intestazione contenuto in un frammento di intestazione denominato **HeaderContainer**.

![Esempio di un modulo di selezione sito in un frammento di intestazione.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo intestazione](author-header-module.md)

[Modulo percorso di navigazione](add-breadcrumb.md)

[Modulo menu di spostamento](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
