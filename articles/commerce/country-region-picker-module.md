---
title: Modulo di selezione paese/area geografica
description: In questo articolo viene descritto il modulo di selezione paese/area geografica e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: d20b3be008a37b1c86e6fefe0ccc90c581e18340
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861994"
---
# <a name="countryregion-picker-module"></a>Modulo di selezione paese/area geografica

[!include [banner](includes/banner.md)]

In questo articolo viene descritto il modulo di selezione paese/area geografica e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.

Il modulo di selezione paese/area geografica utilizza la funzionalità di [rilevamento geografico e reindirizzamento](geo-detection-redirection.md) in Dynamics 365 Commerce per mostrare i siti consigliati ai clienti che richiedono l'URL di un sito di e-commerce non associato al loro paese o area geografica.

Ad esempio, un cliente in Canada richiede l'URL di un sito associato a un paese diverso dal Canada. In questo caso, il modulo di selezione paese/area geografica mostra una finestra di dialogo che consiglia gli URL dei siti associati al Canada. 

## <a name="how-it-works"></a>Funzionamento

Quando il rilevamento geografico e il reindirizzamento sono abilitati per un sito e un cliente richiede un URL del sito, il paese rilevato per il cliente e l'URL richiesto vengono utilizzati per determinare se tale URL è mappato al paese in cui si trova il cliente. La mappatura tra URL e paesi è definita nella pagina **Canali** sotto **Impostazioni del sito** in Creazione di siti di Commerce. 

Se l'URL della richiesta non corrisponde a nessun URL mappato al paese del cliente, nella risposta viene restituito l'elenco di uno o più URL mappati a quel paese. Il selettore paese/area geografica confronta ogni URL in quell'elenco con gli URL che sono stati configurati nel modulo paese/area geografica. Per ogni corrispondenza esatta trovata, il selettore paese/area geografica visualizza l'intestazione, il sottotitolo e l'immagine visualizzati per quell'URL e collega questi elementi utilizzando l'URL.

Quando un cliente seleziona un'opzione nel selettore paese/area geografica, viene indirizzato all'URL con collegamento ipertestuale. Quell'URL è scritto nel cookie **\_msdyn365\_\_\_site\_** in modo che possa essere utilizzato come preferenza del sito del cliente. Quindi, la prossima volta che il cliente richiede l'URL che non è associato al proprio paese o regione, viene automaticamente reindirizzato al proprio paese preferito. Pertanto, ti consigliamo di utilizzare anche il [modulo di selezione del sito](site-selector.md) sul tuo sito di e-commerce, in modo che i clienti abbiano un modo per ignorare o aggiornare le preferenze del sito. 

Se un cliente chiude la finestra di dialogo di selezione del paese/area geografica, non viene scritto alcun cookie e il cliente rimane sul sito corrente. 

Nella figura seguente è illustrato un esempio della finestra dialogo di selezione paese/area geografica.

![Esempio di una finestra di dialogo di selezione paese/area geografica in una home page.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Proprietà del modulo di selezione paese/area geografica

| Nome proprietà              | Valore       | descrizione                                                  |
| -------------------------- | ----------- | ------------------------------------------------------------ |
| Intestazione                    | Testo        | L'intestazione che appare nella parte superiore della finestra di dialogo.       |
| Intestazione secondaria                 | Testo        | Il sottotitolo che appare sotto l'intestazione.               |
| Paese: stringa di visualizzazione    | Testo        | Il nome visualizzato per un'opzione URL (ad esempio, "Canada").   |
| Paese: sottostringa di visualizzazione | Testo        | Una sottostringa di visualizzazione facoltativa per un'opzione URL (ad esempio, "inglese" o "francese"). |
| Paese: immagine del paese     | Risorsa multimediale | Un'immagine facoltativa associata a un'opzione URL (ad esempio, un'immagine della bandiera canadese). |
| Paese: URL del paese       | Testo        | L'URL del sito per il paese/area geografica in fase di configurazione. Questo URL deve corrispondere esattamente all'URL che hai specificato per questo paese/area geografica nella pagina **Canali** sotto **Impostazioni del sito** nel generatore di siti di Commerce. Inoltre, il dominio dell'URL deve essere il dominio personalizzato specificato in **Corrispondenza dominio** nella pagina **Canali**, non l'indirizzo di lavoro del sito che Commerce fornisce quando crei il tuo ambiente di e-commerce (ad esempio, l'URL `https://<yourcompany>.commerce.dynamics.com/`). |
| Collegamento azione                | Collegamento azione | Un collegamento facoltativo visualizzato nella parte inferiore della finestra di dialogo. Ad esempio, questo collegamento può puntare a una pagina interna che fornisce un elenco di tutti i paesi e le aree geografiche supportati dal sito. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Aggiungi un modulo di selezione paese/area geografica a una pagina

Il modulo di selezione paese/area geografica può essere aggiunto al modulo di intestazione direttamente o tramite un frammento condiviso. Per ulteriori informazioni sui moduli di intestazione, vedere [Modulo intestazione](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Configurare il modulo di selezione paese/area geografica in Creazione di siti di Commerce

> [!NOTE]
> Gli URL che si consigliano ai clienti devono essere configurati come oggetti paese/area geografica nel modulo di selezione paese/area geografica.

Per ogni URL del sito che vuoi mostrare e consigliare ai clienti, segui questi passaggi in Creazione di siti di Commerce.

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

[Modulo di selezione sito](site-selector.md)

[Modulo percorso di navigazione](add-breadcrumb.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
