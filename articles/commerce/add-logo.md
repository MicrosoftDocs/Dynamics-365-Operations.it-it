---
title: Aggiungere un logo
description: In questo argomento viene descritto come aggiungere un logo al sito in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d9e1cba6bd07e0c3d9ed7d741d87e10837d8021c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797601"
---
# <a name="add-a-logo"></a>Aggiungere un logo

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere un logo al sito in Microsoft Dynamics 365 Commerce.

Quando crei il sito, una delle prime cose che probabilmente farai è aggiungere il logo della tua azienda o del tuo marchio all'intestazione del sito. La libreria dei moduli online di Dynamics 365 Commerce fornisce un modulo che semplifica questa attività.

È possibile aggiungere un logo direttamente a un modello, layout o pagina. In questo modo, puoi facilmente modificare il logo che appare su pagine specifiche o gruppi specifici di pagine. Tuttavia, questo argomento tratta lo scenario più frequente, in cui aggiungi il logo a un frammento di intestazione che può essere riutilizzato in tutte le pagine del tuo sito.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter aggiungere un logo a tutte le pagine del tuo sito, è necessario completare queste attività.

1. Caricare il logo nella libreria multimediale.
1. Creare un frammento di intestazione Per ulteriori informazioni su come creare e utilizzare i frammenti, vedere [Utilizzare i frammenti ](work-with-fragments.md).
1. Includi il frammento di intestazione nel modello utilizzato dalle pagine del tuo sito per le opzioni di layout e di modulo. Per ulteriori informazioni sui modelli, vedere [Utilizzare i modelli](work-with-templates.md).

## <a name="add-a-logo-to-a-header-fragment"></a>Aggiungere un logo a un frammento di intestazione

Per aggiungere un logo al frammento di intestazione del tuo sito, effettuare le seguenti operazioni.

1. Selezionare **Frammenti** nel pannello di navigazione a sinistra.
1. Selezionare il frammento intestazione creato e selezionare **Modifica**.
1. Espandere il modulo di intestazione.
1. Nel riquadro delle proprietà per il modulo di intestazione, fornire un'immagine e un collegamento per il logo. 
1. Salvare il frammento intestazione, finalizzare la modifica e pubblicarlo.

Dopo aver pubblicato il frammento di intestazione aggiornato, tutte le pagine del sito che utilizzano il modello che contiene il frammento di intestazione mostreranno il logo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Selezionare un tema per il sito](select-site-theme.md)

[Utilizzare i file di sostituzione CSS](css-override-files.md)

[Aggiungere una favicon](add-favicon.md)

[Aggiungere un messaggio di benvenuto](add-welcome-message.md)

[Aggiungere informazioni sul copyright](add-copyright-notice.md)

[Aggiungere lingue al sito](add-languages-to-site.md)

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
