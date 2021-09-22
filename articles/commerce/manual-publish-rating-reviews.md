---
title: Abilitare la pubblicazione manuale di valutazioni e recensioni da parte di un moderatore
description: Questo argomento descrive come abilitare la pubblicazione manuale di valutazioni e recensioni da parte di un moderatore in Microsoft Dynamics 365 Commerce e come pubblicare manualmente valutazioni e recensioni.
author: gvrmohanreddy
manager: annbe
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: ebf104502783cf4046dc7b265a7ecda30cf2e8cf
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472634"
---
# <a name="enable-manual-publishing-of-ratings-and-reviews-by-a-moderator"></a>Abilitare la pubblicazione manuale di valutazioni e recensioni da parte di un moderatore

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Questo argomento descrive come abilitare la pubblicazione manuale di valutazioni e recensioni da parte di un moderatore in Microsoft Dynamics 365 Commerce e come pubblicare manualmente valutazioni e recensioni.

La soluzione per valutazioni e recensioni di Dynamics 365 Commerce usa Azure Cognitive Services per oscurare automaticamente le volgarità nei titoli e nei contenuti delle recensioni e per pubblicare valutazioni e recensioni. Pertanto, non è necessario l'intervento manuale per rivedere e pubblicare valutazioni e recensioni sul sito di e-commerce.

Tuttavia, alcune aziende potrebbero preferire che i moderatori esaminino e approvino manualmente le recensioni prima che vengano pubblicate. Per abilitare la pubblicazione manuale di valutazioni e recensioni da parte di un moderatore, è necessario abilitare la funzionalità **Richiedi un moderatore per valutazioni e recensioni** nel generatore di siti di Commerce.

## <a name="enable-the-require-moderator-for-ratings-and-reviews-feature-in-commerce-site-builder"></a>Abilitare la funzionalità Richiedi moderatore per valutazioni e recensioni nel generatore di siti di Commerce

Per abilitare la funzionalità **Richiedi moderatore per valutazioni e recensioni** nel generatore di siti di Commerce, eseguire queste operazioni.

1. Andare a **Home \> Recensioni \> Impostazioni**.
1. Impostare l'opzione **Richiedi moderatore per valutazioni e recensioni** su **Attivata**.

> [!NOTE]
> Se si abilita la funzionalità **Richiedi moderatore per valutazioni e recensioni**, si interrompe la pubblicazione automatica di valutazioni e recensioni, in modo che sia necessaria la pubblicazione manuale. Azure Cognitive Services continuerà tuttavia a oscurare volgarità nei titoli e nei contenuti delle recensioni.

<!--![Require moderator for ratings and reviews setting in Commerce site builder.](media/Ratings-reviews-settings-human-moderation.png)-->

## <a name="publish-ratings-and-reviews"></a>Pubblicare valutazioni e recensioni

Quando si abilita la funzionalità **Richiedi moderatore per valutazioni e recensioni**, un moderatore deve rivedere e pubblicare manualmente valutazioni e recensioni per farle apparire sul sito di e-commerce.

Per esaminare e pubblicare valutazioni e recensioni nel generatore di siti di Commerce, eseguire queste operazioni.

1. Andare a **Recensioni \> Moderazione**.
1. Nella griglia, se il campo **Stato** per una riga è impostato su **Non pubblicato**, la valutazione e la recensione di tale riga non sono ancora state pubblicate. Per visualizzare solo valutazioni e recensioni non pubblicate, selezionare **Stato: necessita di revisione** nel filtro di stato sopra la griglia.
1. Selezionare una o più valutazioni e recensioni con stato **Non pubblicato**, quindi selezionare **Pubblica** sulla barra dei comandi. Le valutazioni e le recensioni selezionate vengono aggiunte alla coda di pubblicazione e verranno visualizzate sul sito di e-commerce dopo la pubblicazione.

> [!NOTE]
> - Dopo che una valutazione e una recensione sono state pubblicate, il valore dello stato cambia da **Non pubblicato** a un valore Null (campo vuoto).
> - Se si selezionano più valutazioni e recensioni con stati misti e quindi si seleziona **Pubblica**, le valutazioni e le recensioni non ancora pubblicate verranno pubblicate. Tuttavia, le valutazioni e le recensioni già pubblicate non verranno pubblicate di nuovo.

L'illustrazione seguente mostra un esempio in cui tre valutazioni e recensioni non pubblicate sono selezionate sulla pagina **Moderazione** nel generatore di siti di Commerce.

![Tre valutazioni e recensioni non pubblicate nella pagina Moderazione nel generatore di siti di Commerce.](media/Ratings-reviews-publishing-reviews.png)

<!--![Dynamics 365 Commerce - Ratings and Review configuration 2](media/Ratings-reviews-published-reviews.png)-->
<!--![Status filter](media/Ratings-reviews-published-reviews-status-filter.png)-->

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica valutazioni e revisioni](ratings-reviews-overview.md)
