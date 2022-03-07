---
title: Aggiungere informazioni sul copyright
description: In questo argomento viene descritto come aggiungere informazioni sul copyright nel sito di e-Commerce.
author: psimolin
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4a9a7fed4393f9c35b0bdc765fe7d0723c193f89
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "7964758"
---
# <a name="add-a-copyright-notice"></a>Aggiungere informazioni sul copyright

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere informazioni sul copyright nel sito di e-Commerce.

## <a name="prerequisites"></a>Prerequisiti

Prima di aggiungere informazioni sul copyright al sito, è necessario disporre di quanto segue:

- Un modello che include un frammento piè di pagina condiviso.
- Una pagina che utilizza quel modello.

## <a name="add-a-copyright-notice"></a>Aggiungere informazioni sul copyright

Per aggiungere informazioni sul copyright nella parte inferiore di ogni pagina che utilizza un modello specifico, effettuare le seguenti operazioni.

1. Andare a **Frammenti** quindi selezionare **Nuovo**.
1. Nella finestra di dialogo **Nuovo frammento**, selezionare il modulo **Piè di pagina** e denominare il frammento. Ad esempio, immettere **Piè di pagina-Copyright**.
1. Selezionare **OK**.
1. Nel pannello di navigazione, selezionare il pulsante con i puntini di sospensione (**...**) accanto a **Piè di pagina** e selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo, selezionare **Categoria piè di pagina** e quindi **OK**.
1. Nel pannello di navigazione, selezionare il pulsante con i puntini di sospensione accanto a **Piè di pagina** e selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo, selezionare **Blocco di testo** e quindi **OK**.
1. Nel pannello di navigazione, selezionare **Blocco di testo**.
1. Nel riquadro delle proprietà a destra, nel campo **Paragrafo**, aggiungere le informazioni sul copyright. Ad esempio, immettere **(C) Fabrikam 2019**.
1. Selezionare **Salva**, **Fine modifica** e quindi **Pubblica**.
1. Andare a **Modelli**, selezionare il modello e quindi **Modifica**.
1. Sotto **Struttura pagina** espandere **Corpo** e quindi **Pagina predefinita**.
1. Selezionare il pulsante con i puntini di sospensione accanto a **Slot piè di pagina** e quindi selezionare **Aggiungi frammento**.
1. Selezionare il frammento creato in precedenza e quindi **Seleziona**.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.

Il piè di pagina contenente le informazioni sul copyright viene automaticamente visualizzato nella parte inferiore di tutte le pagine che utilizzano il modello selezionato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiungere un logo](add-logo.md)

[Selezionare un tema per il sito](select-site-theme.md)

[Utilizzare i file di sostituzione CSS](css-override-files.md)

[Aggiungere una favicon](add-favicon.md)

[Aggiungere lingue al sito](add-languages-to-site.md)

[Aggiungere codice script nelle pagine del sito per supportare la telemetria](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
