---
title: Visualizzare la cronologia delle versioni per ripristinare pagine e frammenti
description: In questo articolo viene descritto come visualizzare la cronologia delle versioni per una pagina o un frammento e ripristinarne una versione precedente nel generatore di siti di Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 06/21/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: fa2ecdd9d9bc7e60b279d850573b5caa6df2c659
ms.sourcegitcommit: 9cfccb5c260ce56a3457f9ea12e80f54ea55a3b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183676"
---
# <a name="view-version-history-to-revert-pages-and-fragments"></a>Visualizzare la cronologia delle versioni per ripristinare pagine e frammenti

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

In questo articolo viene descritto come visualizzare la cronologia delle versioni per una pagina o un frammento e ripristinarne una versione precedente nel generatore di siti di Microsoft Dynamics 365 Commerce.

Il generatore di siti di Commerce permette di visualizzare la cronologia delle versioni di una pagina o di un frammento e ripristinare una versione precedente di un documento specifico se necessario. Mentre un documento è aperto, è possibile selezionare **Mostra cronologia** nella barra dei comandi per aprire una finestra di dialogo **Cronologia versioni**, dove nella scheda **Versione** viene elencata la cronologia di tutte le versioni e delle attività di salvataggio per la pagina o per il frammento. È possibile quindi selezionare una versione precedente del documento nell'elenco, visualizzarla in anteprima e ripristinarla come versione corrente. Nella scheda **Attività** della finestra di dialogo viene elencata la cronologia completa delle attività del documento, inclusi tutti gli eventi di salvataggio, pubblicazione e annullamento della pubblicazione.

> [!NOTE]
> Viene creata una nuova versione di un documento ogni volta che un autore del sito apporta modifiche al documento e seleziona quindi **Modifica completata**. 

Per visualizzare la cronologia delle versioni per una pagina o un frammento e ripristinare una versione precedente, attenersi alla seguente procedura.

1. Nel generatore di siti, aprire la pagina o il frammento per il quale si desidera visualizzare la cronologia delle versioni.
1. Nella barra dei comandi, selezionare **Mostra cronologia**.

    ![Pulsante Mostra cronologia.](./media/version-history-1.png)

1. Nella scheda **Versione** della finestra di dialogo **Cronologia versioni**, selezionare una versione precedente del documento. Nel riquadro delle proprietà a destra viene visualizzata un'anteprima della versione selezionata assieme alle informazioni sull'autore e sulla data della modifica.

    ![Visualizzazione elenco Cronologia versioni.](./media/version-history-2.png)

1. Per visualizzare un'anteprima completa della versione selezionata del documento, selezionare **Anteprima**. Per chiudere l'anteprima e tornare alla finestra di dialogo **Cronologia versioni**, selezionare **Chiudi anteprima**.
1. Per ripristinare una versione precedente del documento, selezionarla nell'elenco nella scheda **Versione**, quindi selezionare **Ripristina**. Viene visualizzata una casella di messaggio **Ripristina versione \<version number\>** in cui viene richiesto di confermare l'azione di ripristino. 

    ![Pulsante Ripristina e casella di messaggio di conferma.](./media/version-history-3.png)

1. Per procedere con l'azione di ripristino, selezionare **Ripristina**. Il generatore di siti viene aggiornato e mostra la versione ripristinata della pagina o del frammento.
1. Per pubblicare la versione ripristinata, selezionare **Termina modifica**, quindi selezionare **Pubblica**.
