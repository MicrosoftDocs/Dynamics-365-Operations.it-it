---
title: Funzionalità e capacità di accessibilità
description: In questo argomento vengono fornite informazioni sulle funzionalità e capacità di accessibilità in Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 427e82ab75ba16076a3f99ef7df28e9b419d2e7b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980583"
---
# <a name="accessibility-features-and-capabilities"></a>Funzionalità e capacità di accessibilità


[!include [banner](includes/banner.md)]

In questo argomento vengono fornite informazioni sulle funzionalità e capacità di accessibilità in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Le caratteristiche e le capacità di accessibilità forniscono i mezzi funzionali a tutti gli utenti per accedere ed eseguire azioni in modo da poter raggiungere i propri obiettivi. Questa vasta gamma di utenti potrebbe richiedere strumenti di assistenza per l'udito, la visione, la mobilità o la neurodiversità.

Varie funzioni in Dynamics 365 Commerce ti consentono di costruire il sito in modo che includa funzionalità di assistenza. Quando progetti il tuo sito, dovresti considerare le aree di funzionalità di accessibilità menzionate nel [Centro di accessibilità Microsoft](https://www.microsoft.com/accessibility). 

Questo argomento descrive alcune aree aggiuntive di funzionalità di accessibilità che è necessario considerare quando si utilizza Dynamics 365 Commerce.

## <a name="image-alt-text"></a>Testo alternativo all'immagine

Dynamics 365 Commerce ha un sistema integrato di gestione delle risorse digitali per tenere traccia delle risorse di immagini e video utilizzate nel tuo sito. I sottotitoli, le descrizioni e il testo alternativo delle immagini possono essere aggiunti nel riquadro delle proprietà per un'immagine quando viene selezionata o caricata.

## <a name="video-accessibility"></a>Accessibilità video

Il sistema di gestione delle risorse digitali Dynamics 365 Commerce supporta diverse funzionalità di accessibilità per i contenuti video. Alcuni esempi sono elencati nella seguente tabella.

| Funzionalità video               | Descrizione |
|-----------------------------|-------------|
| Sottotitoli (CC)      | Testo che può essere mostrato per gli elementi audio descrittivi e l'audio di un video, per aiutare gli utenti sordi o con problemi di udito |
| Sottotitoli                   | File di sottotitoli che mostrano il testo di indizi dal contesto o della finestra di dialogo sullo schermo |
| Trascrizioni audio           | Una trascrizione testuale di parole pronunciate che viene generata dall'audio di una risorsa video |
| Audio descrittivo           | Un canale audio non primario che descrive il contenuto o il contesto che appare sullo schermo |
| Verifica dell'età minima            | Un attributo che può memorizzare l'età minima che deve avere uno spettatore per visualizzare un video (solo metadati) |

### <a name="configure-video-accessibility-elements"></a>Configurare elementi di accessibilità video

In Commerce, nella sezione **Libreria multimediale**, puoi caricare risorse video che hanno file separati per sottotitoli, audio normale e audio descrittivo. I sottotitoli possono anche essere generati automaticamente quando viene caricata una risorsa video.

#### <a name="generate-or-upload-closed-caption-files-during-video-asset-upload"></a>Generare o caricare file di sottotitoli codificati durante il caricamento delle risorse video

Per generare automaticamente un file di sottotitoli quando carichi un video, segui questo passaggio.

- Nella finestra di dialogo **Carica risorsa**, selezionare **Genera automaticamente sottotitoli**. Se stai generando un file di sottotitoli, il selettore di file per i file di sottotitoli non sarà disponibile nella finestra di dialogo.

Per caricare manualmente un file di sottotitoli quando carichi un video, segui questo passaggio.

- Nella finestra di dialogo **Carica risorsa**, deselezionare **Genera automaticamente sottotitoli**.

Per caricare normali file audio o file audio descrittivi per il video, utilizzare il selettore file nella finestra di dialogo **Carica risorsa**.

> [!NOTE]
> È inoltre possibile aggiungere sottotitoli, audio normale e risorse audio descrittive dopo aver caricato una risorsa video. Andare a **Libreria multimediale**, selezionare la risorsa video e selezionare **Modifica** per verificarla. Quindi, nel riquadro delle proprietà per la risorsa video, caricare le risorse aggiuntive.

#### <a name="edit-cc-and-audio-transcript-files"></a>Modificare i file di trascrizione audio e CC

I file di trascrizione audio e CC possono essere modificati direttamente nello strumento di creazione. La riproduzione video è disponibile durante la modifica.

Per modificare i file di trascrizione audio e CC, attenersi alla seguente procedura.

1. Andare a **Libreria multimediale** e selezionare il nome del file della risorsa video. Viene visualizzato l'editor dei contenuti dei sottotitoli codificati e delle trascrizioni.
1. Selezionare **Modifica**.
1. Modificare il testo dei sottotitoli o della trascrizione.
1. Al termine, selezionare **Salva**, quindi selezionare **Fine modifica**.
1. Quando sei pronto per la pubblicazione, seleziona **Pubblica**.

#### <a name="set-the-minimum-age-attribute"></a>Imposta l'attributo Età minima

Un attributo dei metadati **Età minima** può essere associato alle risorse video.

Per impostare l'attributo **Età minima** per una risorsa video, attenersi alla seguente procedura.

1. Andare a **Libreria multimediale** e selezionare la risorsa video.
1. Selezionare **Modifica**.
1. Nel riquadro delle proprietà della risorsa video, impostare l'attributo **Età minima**.

> [!NOTE]
> Il riquadro delle proprietà viene utilizzato solo per impostare e archiviare il valore dell'attributo dei metadati. I moduli personalizzati devono essere creati per utilizzare questo attributo per il controllo dell'accesso per la riproduzione.

## <a name="additional-resources"></a>Risorse aggiuntive

[Accessibilità per moduli, prodotti e controlli](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/user-interface/enable-accessibility)

[Centro di accessibilità Microsoft](https://www.microsoft.com/accessibility)

[Centro di accessibilità Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/accessibility/index)

[Panoramica sulla conformità](compliance-overview.md)

[Conformità dei cookie](cookie-compliance.md)

[Aggiungere una pagina dell'Informativa sulla privacy](add-privacy-page.md)

[Sostituire gli ID utente associati alle modifiche al contenuto monitorato](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]