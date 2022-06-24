---
title: Modulo elenco riquadro
description: Questo articolo descrive i moduli elenco riquadri e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 44eb9b82ef9625734c7fe5ccba85207d9f210a00
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905400"
---
# <a name="tile-list-module"></a>Modulo elenco riquadro

[!include [banner](includes/banner.md)]

Questo articolo descrive i moduli elenco riquadri e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

Un modulo elenco riquadro è una raccolta di riquadri in una sequenza. Viene utilizzato per commercializzare categorie o marchi di prodotti tramite immagini e testo. Ad esempio, un rivenditore può aggiungere un modulo elenco riquadro alla home page di un sito di e-commerce per promuovere tutte le categorie più vendute.

Un modulo elenco riquadro è basato sui dati del sistema di gestione dei contenuti (CMS). Non dipende da altri moduli o dati della sede commerciale. Il modulo elenco riquadro può essere aggiunto a qualsiasi pagina di un sito in cui un rivenditore desidera commercializzare o promuovere qualcosa, ad esempio prodotti, categorie o marchi.

L'illustrazione seguente mostra un esempio di un modulo elenco riquadro e i moduli riquadro nella home page di Adventure Works.

![Esempio di un modulo elenco riquadro e i moduli riquadro nella home page di Adventure Works.](./media/Tile_list.PNG)

> [!IMPORTANT]
> Il modulo elenco riquadro è disponibile a partire dalla versione Dynamics 365 Commerce 10.0.20.
> Il modulo elenco riquadro viene mostrato nel tema Adventure Works.

## <a name="tile-list-modules-and-themes"></a>Moduli e temi dell'elenco riquadro

Il modulo elenco riquadro può supportare vari layout e stili in base a un tema. Ad esempio, nel tema Adventure Works, i riquadri mostrano un effetto di animazione quando gli utenti del sito passano sopra di essi. Ogni tema può contenere proprietà aggiuntive per l'elenco riquadro e i moduli dei riquadri. Gli sviluppatori del tema possono inoltre costruire layout aggiuntivi per l'elenco riquadro e i moduli dei riquadri.

## <a name="tile-list-module-properties"></a>Proprietà del modulo elenco riquadro

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Intestazione       | Testo e tag di intestazione | Un'intestazione di testo per il modulo elenco riquadro. |

## <a name="tile-module-properties"></a>Proprietà del modulo riquadro

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Immagine         | File di immagine | Un'immagine può essere utilizzata per presentare un prodotto o una categoria. L'immagine può essere caricata nella libreria multimediale in Creazione di siti di Commerce oppure è possibile utilizzare un'immagine esistente. |
| Intestazione       | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Per impostazione predefinita, viene utilizzato il tag di intestazione **H2**, ma è possibile utilizzare un altro tag per soddisfare i requisiti di accessibilità. |
| Paragrafo     | Testo paragrafo | Il modulo supporta testo di paragrafo in formato RTF. Alcune funzionalità RTF di base sono supportate, ad esempio collegamenti ipertestuali e testo in grassetto, sottolineato e in corsivo. Alcune funzionalità possono essere sostituite dal tema di pagina applicato al modulo. |
| Collega          | Testo del collegamento, URL del collegamento, etichetta ARIA e **Apri collegamento in una nuova scheda** | I moduli supportano uno o più collegamenti "invito all'azione". Se un collegamento viene aggiunto, il testo del collegamento, un URL e un'etichetta ARIA sono necessari. Le etichette ARIA devono essere descrittive per soddisfare i requisiti di accessibilità. I collegamenti possono essere configurati di modo che siano aperti in una nuova scheda. |
| Collegamento riquadro     | Testo del collegamento, URL del collegamento, etichetta ARIA e selettore **Apri collegamento in una nuova scheda** | Questa proprietà viene utilizzata per definire un collegamento "invito all'azione". Se un collegamento viene aggiunto, il testo del collegamento, un URL e un'etichetta ARIA sono necessari. Le etichette ARIA devono essere descrittive per soddisfare i requisiti di accessibilità. I collegamenti possono essere configurati di modo che siano aperti in una nuova scheda.|
| Icona          | Immagine | Oltre all'immagine di un prodotto o una categoria, è possibile aggiungere un simbolo di icona. L'immagine del simbolo di icona viene visualizzato sopra l'immagine del prodotto o della categoria. |

## <a name="add-a-tile-list-module-to-a-new-page"></a>Aggiungere un modulo elenco riquadro a una nuova pagina

Per aggiungere un modulo elenco riquadro a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Modelli** e aprire il modello di marketing per la home page del sito (o creare un nuovo modello di marketing).
1. Nello slot **Principale** della pagina predefinita, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Elenco riquadri**, quindi scegli **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare in **Pagine** e aprire la home page del sito (o creare una nuova home page utilizzando il modello di marketing).
1. Nello slot **Principale** della pagina predefinita, seleziona il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Elenco riquadri**, quindi scegli **OK**.
1. Nel riquadro delle proprietà del modulo elenco riquadro, aggiungere un'intestazione.
1. Nello slot **Elenco riquadro** seleziona il pulsante con i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Modulo riquadro**, quindi scegli **OK**.
1. Nel riquadro delle proprietà del modulo riquadro, aggiungere un'immagine, un'intestazione e un'immagine del simbolo di icona.
1. Aggiungere e configurare ulteriori moduli riquadro in base alle esigenze.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Tema Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
