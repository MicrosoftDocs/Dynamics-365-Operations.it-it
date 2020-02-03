---
title: Aggiungere una pagina dell'Informativa sulla privacy
description: In questo argomento viene descritto come aggiungere al sito una pagina dell'Informativa sulla privacy in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/08/2020
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fd39ff5f8c5d97f2d524043b65627dc7e87fcf64
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946037"
---
# <a name="add-a-privacy-policy-page"></a>Aggiungere una pagina dell'Informativa sulla privacy

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere al sito una pagina dell'Informativa sulla privacy in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

La conformità alla privacy include misure organizzative che informano gli utenti del sito su come i loro dati vengono raccolti e gestiti. Gli utenti possono quindi decidere come desiderano vengano gestiti i propri dati personali e intraprendere le azioni appropriate.

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a>Rivedi l'Informativa sulla privacy di Microsoft in Dynamics 365 Commerce

Per rivedere l'Informativa sulla privacy di Microsoft mentre è stato eseguito l'accesso agli strumenti di creazione di Dynamics 365 Commerce, selezionare il pulsante della **Guida** ( **?**) nell'angolo in alto a destra, quindi selezionare **Privacy e cookie**. Si apre una nuova scheda con un collegamento all'[Informativa sulla privacy di Microsoft ](https://privacy.microsoft.com/privacystatement).

## <a name="build-a-privacy-policy-page-for-your-site"></a>Creare una pagina di informativa sulla privacy per il tuo sito

In Dynamics 365 Commerce, esistono diversi modi per fornire agli utenti del sito l'accesso all'informativa sulla privacy. Questa sezione mostra come creare una pagina dell'informativa sulla privacy e quindi fare riferimento alla pagina utilizzando un frammento di piè di pagina.

Le linee guida che seguono sono un esempio che mostra come creare una pagina di informativa sulla privacy generica per un sito commerciale. L'utente è responsabile della progettazione e dell'implementazione di una soluzione di pagina di informativa sulla privacy che soddisfa al meglio i requisiti legali dell'azienda.

Per iniziare, negli strumenti di creazione, vai al sito per cui desideri creare una pagina di informativa sulla privacy.

### <a name="create-a-template"></a>Creare un modello

> [!NOTE]
> Se è già stato creato un modello che può essere utilizzato per la pagina dell'informativa sulla privacy, passare alla sezione [Creare una pagina di informativa sulla privacy ](#build-a-privacy-policy-page).

Per creare un nuovo modello, effettuare le seguenti operazioni.

1. Andare a **Modelli \> Nuovo modello**.
1. Immettere il nome del modello e selezionare **OK**.
1. Nel modello, aggiungere eventuali moduli necessari per gli slot di pagina richiesti. Per le linee guida, passare con il mouse sopra i punti esclamativi rossi.

    Ad esempio, lo slot **Intestazione HTML** potrebbe richiedere un modulo **Script esterno predefinito**.

1. Nello slot **Corpo**, aggiungi un modulo **Pagina predefinita**.
1. Nel modulo **Pagina predefinita** nello slot **Principale**, aggiungere un modulo **Blocco ricco di contenuti**.
1. Nel modulo **Blocco ricco di contenuti**, aggiungi un modulo **Elemento blocco ricco di contenuti**.
1. Archiviare il modello e pubblicarlo.

### <a name="build-a-privacy-policy-page"></a>Creare una pagina dell'Informativa sulla privacy

Per creare una pagina di informativa sulla privacy, attenersi alla seguente procedura.

1. Andare a **Pagine \> Nuova pagina**.
1. Seleziona il modello per la pagina dell'informativa sulla privacy.
1. Immettere un nome di pagina e un URL e selezionare **OK**. 
1. Nello slot **Principale**della pagina, aggiungere un modulo **Blocco ricco di contenuti**.
1. Nel modulo **Blocco ricco di contenuti**, aggiungi un modulo **Elemento blocco ricco di contenuti**.
1. Nel riquadro delle proprietà del modulo **Blocco ricco di contenuti**, selezionare **Aggiungi origine dati**, quindi selezionare **Contenuto RTF**.
1. Nell'editor di testo RTF, immettere il contenuto per la pagina dell'informativa sulla privacy. Espandere l'editor di testo RTF nella modalità a schermo intero in base alle necessità.
1. Dopo aver inserito i contenuti, selezionare **Anteprima**per visualizzare l'anteprima della pagina nel browser Web.
1. Completa eventuali aggiunte restanti alla pagina e alle proprietà del modulo.
1. Controllare la pagina dell'informativa sulla privacy e pubblicarla.

Per pubblicare l'URL per la pagina dell'informativa sulla privacy, procedere come segue.

1. Vai a **URL**e seleziona l'URL per la pagina dell'informativa sulla privacy.
1. Pubblicare l'URL selezionato

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a>Creare un collegamento alla pagina dell'informativa sulla privacy in un piè di pagina

È possibile aggiungere un collegamento alla pagina dell'informativa sulla privacy a un frammento. In questo modo, è possibile condividere il collegamento e aggiornarlo su più pagine del sito facendo riferimento al frammento. Questo esempio mostra come aggiungere un collegamento alla pagina dell'informativa sulla privacy a un frammento di piè di pagina.

Per aggiungere un collegamento a un frammento di piè di pagina, effettuare le operazioni indicate di seguito.

1. Andare a **Frammenti pagina \> Nuovo frammento pagina**.
1. Selezionare il modulo **Piè di pagina**e quindi inserire un nome nel campo **Nome frammento pagina**.
1. Nello slot **Categoria piè di pagina**, aggiungere un modulo **Elemento piè di pagina**.
1. Nel riquadro delle proprietà a destra, selezionare **Testo collegamento**.
1. Nella finestra di dialogo **Testo collegamento**, immettere il testo del collegamento e la destinazione del collegamento della pagina dell'informativa sulla privacy, quindi fare clic su **OK**.

    Per ottenere l'URL della pagina dell'informativa sulla privacy, vai a **Pagine**, quindi alla pagina dell'informativa sulla privacy e copia l'URL dal riquadro delle proprietà.

1. Salvare il frammento, controllarlo e pubblicarlo.
1. Visualizzare l'anteprima del frammento e testare il link alla pagina dell'informativa sulla privacy.

Ora è possibile fare riferimento al frammento nel modello per altre pagine del sito. Quando si fa riferimento a questo frammento nel modulo **Piè di pagina** di un modello, il riferimento al collegamento apparirà su tutte le pagine create utilizzando quel modello.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sulla conformità](compliance-overview.md)

[Funzionalità e capacità di accessibilità](accessibility.md)

[Conformità cookie](cookie-compliance.md)