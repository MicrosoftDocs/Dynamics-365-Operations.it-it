---
title: Modulo di iscrizione
description: Questo articolo descrive i moduli di iscrizione e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 23b74f5853ffb7f191ea7ee3da0d3238db339d34
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852695"
---
# <a name="subscribe-module"></a>Modulo di iscrizione

[!include [banner](includes/banner.md)]

Questo articolo descrive i moduli di iscrizione e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

I moduli di iscrizione possono essere utilizzati nelle pagine del sito per acquisire informazioni sui clienti per newsletter o promozioni.

L'illustrazione seguente mostra un esempio di un modulo di iscrizione nel piè di pagina di una pagina del sito di Adventure Works.

![Esempio di un modulo di iscrizione nel piè di pagina di una pagina del sito di Adventure Works](./media/Subscribe.PNG)

> [!IMPORTANT]
> - Il modulo di iscrizione è disponibile nella libreria del modulo Commercio a partire da Dynamics 365 Commerce versione 10.0.20.
> - Il modulo di iscrizione viene mostrato nel tema Adventure Works.
> - Il modulo di iscrizione richiede un'estensione azione dati per funzionare con alcuni provider di posta elettronica di marketing, in modo che sia possibile inviare newsletter o e-mail promozionali dopo l'acquisizione delle informazioni sui clienti.

## <a name="subscribe-module-properties"></a>Proprietà del modulo di iscrizione

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Intestazione       | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un'intestazione di testo per il modulo di iscrizione, ad esempio **Iscriviti alla newsletter** o **Iscriviti per il 10% di sconto**. |
| Paragrafo     | Testo paragrafo | Il modulo di iscrizione supporta il testo in paragrafi in formato RTF, per fornire dettagli aggiuntivi per l'invito all'azione nell'intestazione. |

## <a name="add-a-subscribe-module-to-a-new-page"></a>Aggiungere un modulo di iscrizione a una nuova pagina

Per aggiungere un modulo di iscrizione a una nuova pagina e impostare le proprietà necessarie nel generatore del sito Commercio, effettuare le seguenti operazioni.

1. Andare a **Modelli** e aprire il modello di marketing per la home page del sito (o creare un nuovo modello di marketing).
1. Nello slot **Principale** della pagina predefinita, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Sottoscrizione** e quindi **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare in **Pagine** e aprire la home page del sito (o creare una nuova home page utilizzando il modello di marketing).
1. Nello slot **Principale** della pagina predefinita, seleziona il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Sottoscrizione** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo di iscrizione, aggiungere un'intestazione, ad esempio **Iscriviti**.
1. Aggiungere il testo del paragrafo, ad esempio **Ultime tendenze, mode e promozioni. Sei nell'elenco? Iscriviti e ricevi le ultime offerte speciali!**
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Tema Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
