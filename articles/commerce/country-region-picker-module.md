---
title: Modulo di selezione paese/area geografica
description: In questo argomento viene descritto il modulo di selezione paese/area geografica e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 09/01/2021
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
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: 3134e10c096525ec2d82365a25eff16a3c5d5e11
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472633"
---
# <a name="countryregion-picker-module"></a>Modulo di selezione paese/area geografica

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

In questo argomento viene descritto il modulo di selezione paese/area geografica e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.

Il modulo di selezione paese/area geografica utilizza la funzionalità di [rilevamento geografico e reindirizzamento](geo-detection-redirection.md) in Dynamics 365 Commerce per mostrare gli URL consigliati ai clienti che richiedono l'URL di un sito di e-commerce non associato al loro paese o area geografica.

Ad esempio, un cliente in Canada richiede l'URL di un sito non associato al Canada. In questo caso, il modulo di selezione paese/area geografica mostra una finestra di dialogo che consiglia gli URL dei siti associati al Canada. Nella figura seguente è illustrato un esempio della finestra dialogo di selezione paese/area geografica.

![Esempio di una finestra di dialogo di selezione paese/area geografica in una home page.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties&quot;></a>Proprietà del modulo di selezione paese/area geografica

| Nome proprietà              | Valore       | descrizione |
| -------------------------- | ----------- | ----------- |
| Intestazione                    | Testo        | L'intestazione che appare nella parte superiore della finestra di dialogo. |
| Intestazione secondaria                 | Testo        | Il sottotitolo che appare sotto l'intestazione. |
| Paese: stringa di visualizzazione    | Testo        | Il nome visualizzato per un'opzione URL (ad esempio, &quot;Canada"). |
| Paese: sottostringa di visualizzazione | Testo        | Una sottostringa di visualizzazione facoltativa per un'opzione URL (ad esempio, "inglese" o "francese"). |
| Paese: immagine del paese     | Risorsa multimediale | Un'immagine facoltativa associata a un'opzione URL (ad esempio, un'immagine della bandiera canadese). |
| Paese: URL del paese       | Testo        | L'URL che corrisponde al canale e alle impostazioni internazionali configurate per il paese o l'area geografica sulla pagina **Canali** in Creazione di siti di Commerce (**Impostazioni sito \> Canali**). Questo URL deve corrispondere esattamente all'URL configurato sulla pagina **Canali**. |
| Collegamento azione                | Collegamento azione | Un collegamento facoltativo visualizzato nella parte inferiore della finestra di dialogo. Ad esempio, questo collegamento può puntare a una pagina interna che fornisce un elenco di tutti i paesi e le aree geografiche supportati dal sito. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Aggiungi un modulo di selezione paese/area geografica a una pagina

Il modulo di selezione paese/area geografica può essere aggiunto al modulo di intestazione direttamente o tramite un frammento condiviso. Per ulteriori informazioni sui moduli di intestazione, vedere [Modulo intestazione](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Configurare il modulo di selezione paese/area geografica in Creazione di siti di Commerce

> [!NOTE]
> Gli URL che si consigliano ai clienti devono essere configurati come oggetti paese/area geografica nel modulo di selezione paese/area geografica.

Per ogni URL che si desidera mostrare e consigliare ai clienti, seguire questi passaggi in Creazione di siti di Commerce.

1. Selezionare lo slot del modulo di selezione paese/area geografica.
1. Nel riquadro delle proprietà, in **Elenco paesi/aree geografiche**, selezionare **Aggiungi paese/area geografica**.
1. Selezionare la nuova casella **Paese/area geografica**.
1. Nel campo **Visualizza stringa**, immettere un nome visualizzato (ad esempio **Canada**).
1. Facoltativo: nel campo **Visualizza sottostringa**, immettere una sottostringa di visualizzazione (ad esempio **francese** o **fr-ca**).
1. Facoltativo: selezionare un'immagine dal catalogo multimediale.
1. Nel campo **URL paese/area geografica**, immettere l'URL. Questo URL deve corrispondere esattamente all'URL che appare sulla pagina **Canali** ed è mappato al canale, incluse le impostazioni internazionali associate al paese o all'area geografica.
1. Selezionare **OK**.
1. Ripetere questi passaggi per qualsiasi altro URL di paese/area geografica che si desidera venga visualizzato nel modulo di selezione paese/area geografica.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare il rilevamento geografico e il reindirizzamento](geo-detection-redirection.md)

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo intestazione](author-header-module.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
