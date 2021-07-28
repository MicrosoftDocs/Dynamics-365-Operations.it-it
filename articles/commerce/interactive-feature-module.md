---
title: Modulo funzionalità interattiva
description: Questo argomento descrive i moduli funzionalità e la procedura per aggiungerli alle pagine di siti Web in Microsoft Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
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
ms.openlocfilehash: a01fb446a1b7dd07e0429b96ff949b88a591f800
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479486"
---
# <a name="interactive-feature-module"></a>Modulo funzionalità interattiva

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Questo argomento descrive i moduli funzionalità e la procedura per aggiungerli alle pagine di siti Web in Microsoft Microsoft Dynamics 365 Commerce.

I moduli funzionalità interattiva sono moduli a mosaico che possono essere utilizzati per commercializzare più categorie di prodotti o marchi di prodotti utilizzando una combinazione di immagini e testo. Ad esempio, un rivenditore può aggiungere un modulo funzionalità interattiva alla home page di un sito di e-commerce per promuovere le categorie più vendute. Il modulo funzionalità interattiva è simile al modulo elenco riquadri, ma ha un layout diverso e una diversa funzionalità di interazione.

Ogni modulo funzionalità interattiva è una raccolta di moduli di elementi di funzionalità interattive. Ogni modulo funzionalità è basato sui dati del sistema di gestione dei contenuti (CMS). Non dipende da altri moduli o dati della sede commerciale. Un modulo funzionalità interattiva può essere aggiunto a qualsiasi pagina di unsito in cui un rivenditore desidera commercializzare o promuovere qualcosa, ad esempio prodotti, categorie o marchi.

> [!IMPORTANT]
> - Il modulo funzionalità interattiva è disponibile a partire da Dynamics 365 Commerce versione 10.0.20.
> - Il modulo funzionalità interattiva è mostrato nel tema Adventure Works.

L'illustrazione seguente mostra un esempio di un modulo funzionalità interattiva nella home page di Adventure Works.

![Esempio di un modulo funzionalità interattiva nella home page di Adventure Works](./media/Feature.PNG)

## <a name="interactive-feature-module-and-themes"></a>Modulo funzionalità interattiva e temi

Il modulo funzionalità interattiva può supportare vari layout e stili in base a un tema. Ad esempio, nel tema Adventure Works, il modulo funzionalità interattiva ha un layout a due colonne che mostra gli effetti animazione quando un utente del sito passa con il mouse su ogni elemento. Il modulo funzionalità interattiva è ottimizzato per un numero pari di immagini disposte in un layout a due colonne.

## <a name="interactive-feature-module-properties"></a>Proprietà del modulo funzionalità interattiva

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Intestazione       | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un'intestazione di testo per il modulo funzionalità interattiva. |

## <a name="interactive-feature-item-module-properties"></a>Proprietà del modulo elemento funzionalità interattiva

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Immagine         | File di immagine | Un'immagine che rappresenta un prodotto o una categoria. L'immagine può essere caricata nella libreria multimediale in Creazione di siti di Commerce oppure è possibile utilizzare un'immagine esistente. |
| Intestazione       | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Per impostazione predefinita, viene utilizzato il tag di intestazione **H2**, ma è possibile utilizzare un altro tag per soddisfare i requisiti di accessibilità. |
| Paragrafo     | Testo paragrafo | Il modulo supporta testo di paragrafo in formato RTF. Alcune funzionalità RTF di base sono supportate, ad esempio collegamenti ipertestuali e testo in grassetto, sottolineato e in corsivo. Alcune funzionalità possono essere sostituite dal tema di pagina applicato al modulo. |
| Collega          | Testo del collegamento, URL del collegamento, etichetta ARIA e selettore **Apri collegamento in una nuova scheda** | Il modulo supporta uno o più collegamenti "invito all'azione". Se un collegamento viene aggiunto, il testo del collegamento, un URL e un'etichetta ARIA sono necessari. Le etichette ARIA devono essere descrittive per soddisfare i requisiti di accessibilità. I collegamenti possono essere configurati di modo che siano aperti in una nuova scheda. |

## <a name="add-an-interactive-feature-module-to-a-new-page"></a>Aggiungere un modulo funzionalità interattiva a una nuova pagina

Per aggiungere un modulo funzionalità interattiva a una nuova pagina e impostare le proprietà necessarie nel generatore del sito Commercio, effettuare le seguenti operazioni.

1. Andare a **Modelli** e aprire il modello di marketing per la home page del sito (o creare un nuovo modello di marketing).
1. Nello slot **Principale** della pagina predefinita, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Funzionalità interattiva**, quindi scegli **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare in **Pagine** e aprire la home page del sito (o creare una nuova home page utilizzando il modello di marketing).
1. Nello slot **Principale** della pagina predefinita, selezionare il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, in **Seleziona moduli**, seleziona il modulo **Funzionalità interattiva**, quindi seleziona **OK**.
1. Nel riquadro delle proprietà del modulo funzionalità interattiva, aggiungere un'intestazione.
1. Nello slot **Funzionalità interattiva** selezionare il pulsante con i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Elemento funzionalità interattiva**, quindi scegli **OK**.
1. Nel riquadro delle proprietà del modulo elemento funzionalità interattiva, aggiungere un'immagine, un testo di intestazione, un testo in paragrafi e un URL.
1. Aggiungere e configurare moduli elemento funzionalità interattiva in base alle esigenze.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Tema Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
