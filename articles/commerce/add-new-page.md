---
title: Aggiungere una nuova pagina di sito
description: In questo argomento viene descritto come aggiungere una nuova pagina di sito in Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 68461f1f0be46f979a67e1806e03c02200cf61db
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001348"
---
# <a name="add-a-new-site-page"></a>Aggiungere una nuova pagina di sito


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere una nuova pagina di sito in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Dopo aver creato modelli e frammenti per il sito, è necessario iniziare a creare le pagine che li utilizzano. Per iniziare, selezionare un modello o un layout, un nome di pagina e un URL di pagina.

## <a name="template-or-layout"></a>Modello o layout

È possibile utilizzare un modello o un layout per la nuova pagina. Per ulteriori informazioni, vedere [Panoramica modelli e layout](templates-layouts-overview.md).

## <a name="page-name"></a>Nome pagina

Scegliere un nome di pagina univoco. Deve inoltre essere descrittivo, di modo che sia facile trovare la pagina e identificarne lo scopo. Scegliere il nome di pagina attentamente, in quanto non può essere modificato in un secondo momento.

## <a name="page-url"></a>URL pagina

È possibile immettere un URL per la nuova pagina. Quando si crea una pagina, è possibile immettere una stringa che sarà utilizzata per formare un URL completo. Tale stringa è nota come URL relativo o slug URL. Un URL completo viene quindi generato in base allo slug URL e la nuova pagina viene assegnata a tale URL. Lo slug URL può essere modificato in seguito, dopo la pubblicazione della pagina. Per ulteriori informazioni, vedere [Creare un URL di pagina](create-page-URL.md).

> [!NOTE]
> Dynamics 365 Commerce scollega gli URL e il contenuto. Ovvero, è possibile creare una pagina che non è associata a un URL e un URL che non è associato a una pagina. Di conseguenza, è possibile eseguire lo swapping di contenuto per un URL senza periodo di inattività e gli reindirizzamenti sono più facili da gestire.

## <a name="add-a-new-page"></a>Aggiungere una nuova pagina

Per aggiungere un nuova pagina, effettuare le seguenti operazioni.

1. In **Siti**, selezionare **Fabrikam** (o il nome del proprio sito).
1. Selezionare **Nuova pagina**.
1. Nella finestra di dialogo **Nuova pagina** selezionare un modello e quindi **OK**.
1. Nel campo **Nome pagina**, immettere un nome di pagina, ad esempio **Nuova pagina**.
1. Nel campo **URL**, immettere una stringa (slug URL) per completare l'URL (ad esempio **nuovapagina**).
1. Selezionare **OK**. Viene visualizzato l'editor delle pagine. Si noti che un'intestazione e un piè di pagina vengono automaticamente aggiunti alla pagina, in base al modello selezionato.
1. Nella struttura delle pagine, selezionare lo slot **Principale**, il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Selezionare **Contenitore** e quindi **OK**.
1. Selezionare **Contenitore fluido**, il pulsante con i puntini di sospensione e quindi **Aggiungi modulo**.
1. Selezionare **Blocco ricco di contenuti** e quindi **OK**.
1. Selezionare **Blocco ricco di contenuti**, il pulsante con i puntini di sospensione e quindi **Aggiungi modulo**.
1. Selezionare **Elemento blocco ricco di contenuti** e quindi **OK**.
1. Nel riquadro delle proprietà a destra, selezionare **Paragrafo**, quindi nel campo immettere **Testo di prova**.
1. Selezionare **Salva** e quindi selezionare **Archivia**.
1. Nel campo **Commenti**, immettere **Aggiunta nuova pagina** e selezionare **OK**.
1. Selezionare **Anteprima** per visualizzare l'anteprima della pagina. Al termine, chiudere la scheda Anteprima per tornare allo strumento di creazione.
1. Selezionare **Pubblica**
1. Nel percorso di navigazione (barra di navigazione), selezionare **Fabrikam** (o il nome del sito).
1. Nel pannello di navigazione a sinistra, selezionare **URL**.
1. Trovare e selezionare l'URL (**nuovapagina**) nell'elenco.
1. Selezionare **Pubblica**

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare una pagina di sito esistente](modify-existing-page.md)

[Selezionare layout di pagina](select-page-layouts.md)

[Gestire i metadati SEO](manage-seo-metadata.md)

[Salvare, visualizzare in anteprima e pubblicare una pagina](save-preview-publish-page.md)

[Migliorare una pagina prodotto](enrich-product-page.md)

[Migliorare una pagina di destinazione di categoria](enrich-category-page.md)

[Verificare l'accessibilità del contenuto della pagina](verify-accessibility.md)
