---
title: Aggiungere un logo
description: In questo argomento viene descritto come aggiungere un logo al sito in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23bac9aae6beb59912bbc9e1f2c6958c007550b0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914624"
---
# <a name="add-a-logo"></a>Aggiungere un logo

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere un logo al sito in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Quando crei il sito, una delle prime cose che probabilmente farai è aggiungere il logo della tua azienda o del tuo marchio all'intestazione del sito. Lo starter kit online di Dynamics 365 Commerce fornisce un modulo che semplifica questa attività.

È possibile aggiungere un logo direttamente a un modello, layout o pagina. In questo modo, puoi facilmente modificare il logo che appare su pagine specifiche o gruppi specifici di pagine. Tuttavia, questo argomento tratta lo scenario più frequente, in cui aggiungi il logo a un frammento di intestazione che può essere riutilizzato in tutte le pagine del tuo sito.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter aggiungere un logo a tutte le pagine del tuo sito, è necessario completare queste attività.

1. Carica il logo in Gestione risorse digitali, a cui puoi accedere dalla pagina **Risorse**.
1. Creare un frammento di intestazione Per ulteriori informazioni su come creare e utilizzare i frammenti, vedere [Utilizzare i frammenti ](work-with-fragments.md).
1. Includi il frammento di intestazione nel modello utilizzato dalle pagine del tuo sito per le opzioni di layout e di modulo. Per ulteriori informazioni sui modelli, vedere [Utilizzare i modelli](work-with-templates.md).

## <a name="add-a-logo-to-a-header-fragment"></a>Aggiungere un logo a un frammento di intestazione

Per aggiungere un logo al frammento di intestazione del tuo sito, effettuare le seguenti operazioni.

1. Nel riquadro di navigazione a sinistra, selezionare **Frammenti**, quindi selezionare il frammento di intestazione creato.
2. Selezionare **Estrai**.
3. Espandere lo slot **Intestazione** e lo slot **Logo**.
4. Selezionare il pulsante con i puntini di sospensione (**...**) per lo slot **Logo** e quindi selezionare **Aggiungi modulo**.
5. Selezionare il modulo del logo.
6. Nel riquadro delle proprietà a destra, configurare il modulo del logo in modo che mostri il logo.
7. Salvare il frammento intestazione, verificarlo e pubblicarlo.

Dopo aver pubblicato il frammento di intestazione aggiornato, tutte le pagine del sito che utilizzano il modello che contiene il frammento di intestazione mostreranno il logo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Selezionare un tema per il sito](select-site-theme.md)

[Utilizzare i file di sostituzione CSS](css-override-files.md)

[Aggiungere una favicon](add-favicon.md)

[Aggiungere un messaggio di benvenuto](add-welcome-message.md)

[Aggiungere informazioni sul copyright](add-copyright-notice.md)

[Aggiungere lingue al sito](add-languages-to-site.md)

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)

