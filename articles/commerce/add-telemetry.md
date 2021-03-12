---
title: Aggiungere codice script nelle pagine del sito per supportare la telemetria
description: In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.
author: bicyclingfool
manager: annbe
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: dfebc6616186a3a8859b00e90c178129feaa324b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980159"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Aggiungere codice script nelle pagine del sito per supportare la telemetria

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere il codice script sul lato client alle pagine del sito per supportare la raccolta di telemetria sul lato client.

## <a name="overview"></a>Panoramica

L'analisi dei dati Web è uno strumento essenziale se si desidera comprendere come i clienti interagiscono con il sito e prendono decisioni che consentono di ottimizzare l'esperienza per la massima conversione. Molti pacchetti di analisi dei dati Web sono disponibili per consentire il raggiungimento di questi obiettivi, ad esempio Google Analytics, Clicky, Moz Analytics e KISSMetrics. La maggior parte dei pacchetti di analisi dei dati Web richiede l'aggiunta di codice script sul lato client nell'elemento **\<head\>** del codice HTML per tutte le pagine del sito.

> [!NOTE]
> Le istruzioni fornite in questo argomento si applicano anche all'altra funzionalità personalizzata sul lato client che Microsoft Dynamics 365 Commerce non offre in modalità nativa.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Creare un frammento riutilizzabile per il codice script

Un frammento consente di riutilizzare il codice script incorporato o esterno in tutte le pagine del sito, indipendentemente dal modello che utilizzano.

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a>Creare un frammento riutilizzabile per il codice script inline

Per creare un frammento riutilizzabile per il codice di script inline in Creazione di siti Web, attenersi alla seguente procedura.

1. Andare a **Frammenti** quindi selezionare **Nuovo**.
1. Nella finestra di dialogo **Nuovo frammento** selezionare **Script inline**.
1. Sotto **Nome frammento**, inserire un nome per il frammento, quindi selezionare **OK**.
1. Sotto il frammento creato, selezionare il modulo **Script inline predefinito**.
1. Nel riquadro delle proprietà sulla destra, sotto **Script inline**, inserire lo script lato client. Quindi configurare altre opzioni come richiesto.
1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Selezionare **Pubblica**

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a>Creare un frammento riutilizzabile per il codice script esterno

Per creare un frammento riutilizzabile per il codice di script esterno in Creazione di siti Web, attenersi alla seguente procedura.

1. Andare a **Frammenti** quindi selezionare **Nuovo**.
1. Nella finestra di dialogo **Nuovo frammento** selezionare **Script esterno**.
1. Sotto **Nome frammento**, inserire un nome per il frammento, quindi selezionare **OK**.
1. Sotto il frammento creato, selezionare il modulo **Script esterno predefinito**.
1. Nel riquadro delle proprietà sulla destra, sotto **Origine script**, aggiungere un URL esterno o relativo per l'origine dello script esterno. Quindi configurare altre opzioni come richiesto.
1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Selezionare **Pubblica**

> [!NOTE]
> Se i criteri di sicurezza dei contenuti (CSP) sono abilitati per il tuo sito, assicurati che tutti gli URL esterni vengano aggiunti alla direttiva CSP **script-src** in Creazione di siti Web di Commerce. Per altre informazioni, vedere [Gestire i criteri di sicurezza del contenuto (CSP)](manage-csp.md).

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a>Aggiungere un frammento che includa il codice dello script in un modello

Per aggiungere un frammento che includa codice di script in un modello in Creazione di siti Web, attenersi alla seguente procedura.

1. Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.
1. Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.
1. Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**) quindi selezionare **Aggiungi frammento**.
1. Selezionare il frammento creato per il codice script.
1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Selezionare **Pubblica**

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a>Aggiungere uno script esterno o uno script inline direttamente a un modello

Se si desidera inserire uno script inline o esterno direttamente in un set di pagine controllate da un singolo modello, non è necessario creare prima un frammento.

### <a name="add-an-inline-script-directly-to-a-template"></a>Aggiungere uno script inline direttamente a un modello

Per aggiungere uno script inline direttamente a un modello in Creazione di siti Web, attenersi alla seguente procedura.

1. Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.
1. Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.
1. Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare **Script inline**.
1. Nel riquadro delle proprietà sulla destra, sotto **Script inline**, inserire lo script lato client. Quindi configurare altre opzioni come richiesto.
1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Selezionare **Pubblica**

### <a name="add-an-external-script-directly-to-a-template"></a>Aggiungere uno script esterno direttamente a un modello

Per aggiungere uno script esterno direttamente a un modello in Creazione di siti Web, attenersi alla seguente procedura.

1. Passare a **Modelli** e aprire il modello per le pagine che si desidera aggiungere al codice script.
1. Nel riquadro sinistro, espandere la gerarchia dei modelli per visualizzare lo slot **Intestazione HTML**.
1. Nello slot **Intestazione HTML** selezionare il pulsante con i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare **Script esterno**.
1. Nel riquadro delle proprietà sulla destra, sotto **Origine script**, aggiungere un URL esterno o relativo per l'origine dello script esterno. Quindi configurare altre opzioni come richiesto.
1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Selezionare **Pubblica**

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere un logo](add-logo.md)

[Selezionare un tema per il sito](select-site-theme.md)

[Utilizzare i file di sostituzione CSS](css-override-files.md)

[Aggiungere una favicon](add-favicon.md)

[Aggiungere un messaggio di benvenuto](add-welcome-message.md)

[Aggiungere informazioni sul copyright](add-copyright-notice.md)

[Aggiungere lingue al sito](add-languages-to-site.md)
