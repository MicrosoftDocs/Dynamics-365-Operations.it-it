---
title: Modulo Iframe
description: In questo articolo viene descritto il modulo iframe e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 248da5132d1a2c6dcf8f246628f969c8a200b26c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269897"
---
# <a name="iframe-module"></a>Modulo Iframe

[!include [banner](includes/banner.md)]

In questo articolo viene descritto il modulo iframe e la procedura per aggiungerlo alle pagine del sito in Microsoft Dynamics 365 Commerce.

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
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immetti **Modello di marketing**, quindi seleziona **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Accedi a **Pagine** e quindi seleziona **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Crea una nuova pagina**, sotto **Nome pagina**, immetti **Pagina marketing**, quindi seleziona **Avanti**.
1. Sotto **Scegli un modello**, seleziona il **modello di marketing** creato e seleziona **Avanti**.
1. Sotto **Scegli un layout**, seleziona un layout di pagina (ad esempio, **Layout flessibile**), quindi seleziona **Avanti**.
1. Sotto **Verifica e termina**, rivedi la configurazione della pagina. Se è necessario modificare le informazioni sulla pagina, seleziona **Indietro**. Se le informazioni sulla pagina sono corrette, seleziona **Crea pagina**. 
1. Nello slot **Principale** della nuova pagina, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Nello slot **Contenitore** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **iframe** e quindi **OK**.
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
