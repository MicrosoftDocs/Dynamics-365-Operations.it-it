---
title: Selezionare un tema per il sito
description: In questo articolo viene descritto come impostare o modificare il tema del sito in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 3b7b3e8d6fd75a31bf9830c50b5c641ab3e62ab3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286785"
---
# <a name="select-a-site-theme"></a>Selezionare un tema per il sito

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come impostare o modificare il tema del sito in Microsoft Dynamics 365 Commerce.

Il layout e lo stile di un sito (ad esempio caratteri, dimensioni e colori) vengono definiti mediante il tema selezionato e applicato al sito. Un tema viene creato e distribuito da uno sviluppatore nella società. Per una panoramica dei temi, vedere [Panoramica dello sviluppo di temi](e-commerce-extensibility/theming.md). Per ulteriori informazioni su come creare e distribuire temi, vedere [Creare un nuovo tema](e-commerce-extensibility/create-theme.md).

Per impostazione predefinita, quando si crea un sito per la prima volta, questo utilizza un tema denominato **Fabrikam**. Questo tema predefinito viene fornito con la libreria di moduli di Commerce. Dopo aver sviluppato temi aggiuntivi per il sito, è possibile configurare il sito di modo che utilizzi uno di questi temi.

## <a name="select-the-site-theme"></a>Selezionare il tema del sito

Per selezionare il tema che viene applicato al sito, procedere come segue.

1. Nell'ambiente di creazione di siti, accedere al proprio sito.
1. Scegliere **Gestione sito** \> **Estendibilità**.
1. In **Tema**, selezionare un tema nel menu a discesa.
1. Per applicare il tema selezionato al sito, selezionare **Salva e pubblica**.

> [!NOTE]
> Il tema selezionato viene pubblicato nel sito non appena si seleziona **Salva e pubblica** nella pagina **Estendibilità**. Per visualizzare un'anteprima di un tema nel sito prima di applicarlo, è possibile utilizzare il proprio ambiente di sviluppo o sandbox.

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere un logo](add-logo.md)

[Utilizzare i file di sostituzione CSS](css-override-files.md)

[Aggiungere una favicon](add-favicon.md)

[Aggiungere informazioni sul copyright](add-copyright-notice.md)

[Aggiungere lingue al sito](add-languages-to-site.md)

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)

[Panoramica dello sviluppo di temi](e-commerce-extensibility/theming.md)

[Creare un nuovo tema](e-commerce-extensibility/create-theme.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
