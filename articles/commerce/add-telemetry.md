---
title: Aggiungere codice script nelle pagine del sito per supportare la telemetria
description: In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 674d00faf1b30f87a0b0062129e1b9fbff955dd4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001279"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Aggiungere codice script nelle pagine del sito per supportare la telemetria


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.

## <a name="overview"></a>Panoramica

L'analisi dei dati Web è uno strumento essenziale se si desidera comprendere come i clienti interagiscono con il sito e prendono decisioni che consentono di ottimizzare l'esperienza per la massima conversione. Molti pacchetti di analisi dei dati Web sono disponibili per consentire il raggiungimento di questi obiettivi, ad esempio Google Analytics, Clicky, Moz Analytics e KISSMetrics. La maggior parte dei pacchetti di analisi dei dati Web richiede l'aggiunta di codice script sul lato client nell'elemento **\<intestazione\>** del codice HTML per tutte le pagine del sito.

> [!NOTE]
> Le istruzioni fornite in questo argomento si applicano anche all'altra funzionalità personalizzata sul lato client che Microsoft Dynamics 365 Commerce non offre in modalità nativa.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Creare un frammento riutilizzabile per il codice script

Dopo aver creato un frammento per il codice script, può essere riutilizzato in tutte le pagine del sito.

1. Andare a **Frammenti \> Nuovo frammento pagina**.
2. Selezionare **Script esterno**, immettere un nome per il frammento e selezionare **OK**.
3. Nella gerarchia di frammenti, selezionare l'elemento figlio del modulo **Injector script** del frammento appena creato.
4. Nel riquadro delle proprietà a destra, aggiungere lo script sul lato client e impostare altre opzioni di configurazione come necessario.

## <a name="add-the-fragment-to-templates"></a>Aggiungere il frammento ai modelli

1. Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.
2. Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.
3. Selezionare il pulsante con i puntini di sospensione (**...**) per lo slot **Intestazione HTML** e quindi selezionare **Aggiungi frammento**.
4. Selezionare il frammento creato per il codice script.
5. Salvare il modello e verificarlo.

> [!NOTE]
> Al termine, è necessario pubblicare il frammento e il modello generale. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere un logo](add-logo.md)

[Selezionare un tema per il sito](select-site-theme.md)

[Utilizzare i file di sostituzione CSS](css-override-files.md)

[Aggiungere una favicon](add-favicon.md)

[Aggiungere un messaggio di benvenuto](add-welcome-message.md)

[Aggiungere informazioni sul copyright](add-copyright-notice.md)

[Aggiungere lingue al sito](add-languages-to-site.md)

