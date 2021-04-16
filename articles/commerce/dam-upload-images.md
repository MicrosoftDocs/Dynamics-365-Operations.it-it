---
title: Caricare immagini
description: In questo argomento viene descritto come caricare immagini in Creazione di siti Web Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2a0a2fdb275cbeb65c06c01128e90ba660f98c9b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799231"
---
# <a name="upload-images"></a>Caricare immagini

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come caricare immagini in Creazione di siti Web Microsoft Dynamics 365 Commerce.

La libreria multimediale Creazione di siti Web Commerce consente di caricare le immagini, singolarmente o in blocco, utilizzando le cartelle. È sempre necessario caricare la versione dell'immagine con la risoluzione e la qualità più alte, perché il componente di dimensionamento immagine ottimizza automaticamente l'immagine per essere adatta a diversi riquadri di visualizzazione e ai punti di interruzione.

### <a name="image-information-specified-during-upload"></a>Informazioni sull'immagine specificate durante il caricamento

Quando si carica un'immagine, è possibile specificare le seguenti informazioni.

- **Titolo, testo alternativo, Descrizione, parole chiave**: i metadati dell'immagine o delle immagini. Titolo e testo alternativo sono valori obbligatori.
- **Seleziona categoria**:
    - **Nessuna**: utilizzato per un'immagine o immagini di storytelling e-commerce.
    - **Prodotto, categoria, cliente, dipendente, catalogo**: usati per un'immagine o immagini omnicanale Dynamics 365 Commerce.
- **Pubblica risorse dopo il caricamento**: quando questa casella di controllo è selezionata, l'immagine o le immagini vengono pubblicate immediatamente dopo il caricamento.

> [!NOTE]
> Le risorse immagine con una categoria assegnata vengono inoltre automaticamente contrassegnate con la categoria come parola chiave per facilitare la ricerca di risorse di una categoria specifica.

### <a name="naming-conventions-for-omni-channel-images"></a>Convenzioni di denominazione per immagini omnicanale 

Se la libreria multimediale è stata configurata come backend dell'immagine omnicanale, è possibile utilizzare le categorie di immagini per indicare a quale categoria appartiene l'immagine caricata. Esiste anche una convenzione di denominazione che deve essere seguita per garantire che le immagini vengano recuperate correttamente da altri canali, come il punto vendita (POS).

La convenzione di denominazione predefinita varia in base alla categoria:
- Le immagini del catalogo devono essere denominate "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"
- Le immagini di categoria devono essere denominate "**/Categories/\{CategoryName\}.png**"
- Le immagini dei clienti devono essere denominate "**/Customers/\{CustomerNumber\}.jpg**"
- Le immagini dei dipendenti devono essere denominate "**/Workers/\{WorkerNumber\}.jpg**"
- Le immagini dei prodotti devono essere denominate "**/Products/\{ProductNumber\}_000_001.png**"
    - 001 è la sequenza dell'immagine e può essere 001, 002, 003, 004 o 005
- Le immagini varianti dei prodotti devono essere denominate "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"
    - Ad esempio: 93039 \^ \^ 2 \^ Black \^_000_001.png

## <a name="upload-an-image"></a>Caricare un'immagine

Per caricare un'immagine in Creazione di siti Web, attenersi alla seguente procedura.

1. Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.
1. Sulla barra dei comandi, selezionare **Carica \> Carica elementi multimediali**.
1. Nella finestra Esplora file, individuare e selezionare uno o più file immagine da caricare, quindi selezionare **Apri**.
1. Nella finestra di dialogo **Carica elemento multimediale**, immettere il titolo e il testo alternativo richiesti.
1. Immettere una descrizione e le parole chiave facoltative e selezionare una categoria, se lo si desidera. 
1. Se si desidera pubblicare le immagini immediatamente dopo averle caricate, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**.
1. Selezionare **OK**.

## <a name="upload-a-folder-of-images"></a>Caricare una cartella di immagini

Per caricare in blocco una cartella di immagini in Creazione di siti Web, attenersi alla seguente procedura.

1. Nel riquadro di spostamento sinistro, selezionare **Libreria multimediale**.
1. Sulla barra dei comandi, selezionare **Carica \> Carica cartella**.
1. Nella finestra Esplora file, individuare e selezionare una cartella da caricare, quindi selezionare **Apri**.
1. Nella finestra di dialogo **Carica elementi multimediali**, inserire le parole chiave opzionali e selezionare una categoria, se lo si desidera. 
1. Se si desidera pubblicare le immagini nella cartella immediatamente dopo averla caricata, selezionare la casella di controllo **Pubblica elementi multimediali dopo il caricamento**.
1. Selezionare **OK**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della gestione risorse digitali](dam-overview.md)

[Caricare video](dam-upload-video.md)

[Caricare file](dam-upload-files.md)

[Tagliare immagini](dam-crop-images.md)

[Personalizzare punti focali immagine](dam-custom-focal-point.md)

[Caricare e fornire file statici](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
