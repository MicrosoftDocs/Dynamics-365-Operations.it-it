---
title: Modulo iFrame
description: In questo argomento viene descritto il modulo iFrame e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 11/04/2021
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
ms.openlocfilehash: bce6a50e8c145f8961bd0c839fe16c1f4d69e811
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2021
ms.locfileid: "7754016"
---
# <a name="iframe-module"></a>Modulo Iframe

[!include [banner](includes/banner.md)]

In questo argomento viene descritto il modulo iFrame e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.

Un modulo iFrame fornisce un iFrame (frame in linea) che ospita contenuti esterni su un sito. Ad esempio, può essere utilizzato per ospitare un video YouTube o un visualizzatore di file PDF in qualsiasi pagina del sito. 

Un modulo iFrame richiede un URL di destinazione. Ospita quindi il contenuto della pagina di destinazione all'interno di un elemento **iFrame** HTML. Gli URL esterni devono essere presenti nell'elenco dei consentiti in base alle direttive sui criteri di sicurezza dei contenuti (CSP) del sito. Per i contenuti iFrame, gli URL dovrebbero essere consentiti utilizzando la direttiva **frame-ancestor**. Per altre informazioni, vedere [Gestire i criteri di sicurezza del contenuto (CSP)](manage-csp.md).

> [!NOTE]
> Il modulo iFrame è disponibile in Dynamics 365 Commerce versione 10.0.13.

L'immagine seguente mostra esempi di moduli iFrame che presentano video esterni sulle pagine del sito.

![Esempio di moduli iFrame che presentano video esterni.](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a>Proprietà del modulo iFrame

| Nome proprietà             | Valore                 | descrizione |
|---------------------------|-----------------------|-------------|
| Intestazione | Testo | L'intestazione del modulo. |
| URL destinazione | URL | L'URL ospitato nel modulo. |
| Altezza | Numero o percentuale | L'altezza del modulo, in pixel o in percentuale. Ad esempio, il valore **100** sarà trattato come un numero di pixel e il valore **100%** sarà trattato come una percentuale. |
| Aria-label | Testo | Un'etichetta ARIA (Accessible Rich Internet Applications) può essere definita per scopi di accessibilità.. |

## <a name="add-an-iframe-module-to-a-page"></a>Aggiungere un modulo iFrame a una pagina

Per aggiungere un modulo iFrame a una pagina per mostrare un video esterno, attenersi alla seguente procedura.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello di marketing**, quindi selezionare **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Scegli un modello**, selezionare il modello **Modello di marketing**. Sotto **Nome pagina**, immettere **Pagina di marketing** e selezionare **OK**.
1. Nello slot **Principale** della nuova pagina, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **iFrame** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo, impostare il valore **URL di destinazione** su un URL esterno per un video.
1. Impostare altre proprietà, ad esempio **Intestazione** e **Altezza**, in base alle esigenze.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.
1. Andare alla pagina di marketing sul sito. Il rendering del video nel modulo iFrame dovrebbe essere visibile.

> [!NOTE]
> Poiché il modulo iframe ospita contenuto esterno, gli autori del sito devono garantire che il contenuto ospitato all'interno di un modulo iframe non violi i criteri di restrizione dei contenuti nel rispettivo mercato. Se si verifica una violazione del contenuto su una pagina che utilizza il modulo iframe, l'autore del sito può rimuovere il modulo iframe aprendo la pagina nel generatore di siti, selezionando **Rimuovi modulo** nello slot del modulo iframe, quindi salvare e ripubblicare la pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Gestire i criteri di sicurezza del contenuto (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
