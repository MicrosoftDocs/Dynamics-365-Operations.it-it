---
title: Modulo elenco immagini
description: Questo argomento descrive i moduli elenco immagini e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 67da83410d819d01396d0b7d421076ee3b0f17ec
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780845"
---
# <a name="image-list-module"></a>Modulo elenco immagini

[!include [banner](includes/banner.md)]

Questo argomento descrive i moduli elenco immagini e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

Il modulo elenco immagini può essere utilizzato per aggiungere facilmente una raccolta (array) di immagini alle pagine di siti. Ogni immagine nell'array può essere configurata con testo in paragrafi e URL di collegamenti. Il modulo elenco immagini è più adatto per visualizzare i loghi di marchi o un elenco che include loghi.

> [!IMPORTANT]
> - Il modulo elenco immagini è disponibile nella libreria del modulo Commercio a partire da Dynamics 365 Commerce versione 10.0.20.
> - Il modulo elenco immagini viene mostrato nel tema Adventure Works.

L'illustrazione seguente mostra un esempio in cui un modulo elenco immagini visualizza un elenco di testo che include loghi in una pagina del sito B2C (business-to-consumer) di Adventure Works.

![Esempio di un modulo elenco immagini che visualizza un elenco di testo che include loghi](./media/Image_list.PNG)

L'illustrazione seguente mostra un esempio in cui un modulo elenco immagini visualizza loghi di marchi in una pagina del sito B2B (business-to-business) di Adventure Works.

![Esempio di un modulo elenco immagini che visualizza loghi di marchi](./media/Image_list_B2B.PNG)

## <a name="image-list-module-properties"></a>Proprietà del modulo elenco immagini

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Intestazione       | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un'intestazione di testo per il modulo elenco immagini. |
| Elenco immagini    | Immagini, testo e URL | Ogni elemento nell'array è un'immagine accompagnata da testo in paragrafi e da un URL. |

## <a name="add-an-image-list-module-to-a-new-page"></a>Aggiungere un modulo elenco immagini a una nuova pagina

Per aggiungere un modulo elenco immagini a una nuova pagina e impostare le proprietà necessarie nel generatore del sito Commercio, effettuare le seguenti operazioni.

1. Andare a **Modelli** e aprire il modello di marketing per la home page del sito (o creare un nuovo modello di marketing).
1. Nello slot **Principale** della pagina predefinita, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Elenco immagini**, quindi scegli **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare in **Pagine** e aprire la home page del sito (o creare una nuova home page utilizzando il modello di marketing).
1. Nello slot **Principale** della pagina predefinita, seleziona il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona **Elenco immagini** e quindi **OK**.
1. Nel riquadro delle proprietà per il modulo elenco immagini, aggiungere un'intestazione, ad esempio **I nostri marchi**.
1. Aggiungere un elemento elenco immagini e specificare un'immagine, del testo in paragrafi e un URL di reindirizzamento.
1. Aggiungere e configurare ulteriori moduli elenco immagini in base alle esigenze.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Tema Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
