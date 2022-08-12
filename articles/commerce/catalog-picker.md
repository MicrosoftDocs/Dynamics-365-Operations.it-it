---
title: Modulo di selezione catalogo
description: Questo articolo tratta dei moduli di selezione catalogo e descrive come aggiungerli ai siti di e-commerce business-to-business (B2B) di Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-04-21
ms.openlocfilehash: 642319eea7e40415fd32898f6ec07bfc86f3b1b1
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136944"
---
# <a name="catalog-picker-module"></a>Modulo di selezione catalogo

[!include [banner](includes/banner.md)]

Questo articolo tratta dei moduli di selezione catalogo e descrive come aggiungerli ai siti di e-commerce business-to-business (B2B) di Microsoft Dynamics 365 Commerce.

Un modulo di selezione catalogo è un contenitore speciale usato per elencare tutti i cataloghi di prodotti disponibili agli utenti del sito B2B per gli acquisti. Sono attualmente supportati svariati cataloghi solo per i siti B2B.

Nella figura seguente viene riportato un esempio di un modulo di selezione catalogo.

![Esempio di un modulo di selezione catalogo con tre cataloghi di prodotto elencati.](./media/Catalog-picker-sample.png)

## <a name="add-a-catalog-picker-module-to-your-site"></a>Aggiungere un modulo di selezione catalogo al sito

Per aggiungere un modulo di selezione catalogo al sito nel generatore di siti di Commerce, effettuare le seguenti operazioni.

### <a name="create-a-catalog-picker-page"></a>Creare una pagina di selezione catalogo

Per prima cosa, creare una pagina di selezione catalogo.

1. Accedere a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Crea una nuova pagina**, in **Nome pagina**, immettere **Selezione catalogo**.
1. In **URL pagina**, immettere un URL per la pagina, quindi selezionare **Avanti**.

    ![Creare una finestra di dialogo per una nuova pagina.](./media/Create-catalog-picker-page.png)

1. In **Scegli un modello**, selezionare **Contenuto generale**, quindi selezionare **Avanti**.
1. In **Scegli un layout**, selezionare **Layout flessibile**, quindi selezionare **Avanti**.
1. In **Verifica e termina**, rivedere la configurazione della pagina. Se è necessario modificare le informazioni sulla pagina, selezionare **Indietro**. Se le informazioni sulla pagina sono corrette, selezionare **Crea pagina**.
1. In **Selezione catalogo**, selezionare **Slot principale**, selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.

    ![Aggiunta di un modulo allo Slot principale in Selezione catalogo.](./media/Author-web-page-catalog-picker-1.png)

1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Contenitore** e quindi **OK**.
1. Selezionare lo slot **Contenitore**, selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Selezione catalogo**, quindi selezionare **OK**.
1. Nel riquadro delle proprietà **Selezione catalogo**, in **Intestazione**, selezionare **Cataloghi**, quindi immettere un'intestazione per la pagina di selezione catalogo.
1. In **Livello intestazione**, selezionare un livello di intestazione, quindi selezionare **OK**.
1. In **RTF**, immettere il testo che verrà visualizzato nella parte superiore della pagina di selezione del catalogo.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

### <a name="add-a-link-on-your-account-page"></a>Aggiungere un collegamento alla pagina dell'account

Quindi, aggiungere un riferimento alla pagina di selezione del catalogo nella pagina **Account personale**.

1. Andare a **Pagine**, trovare e selezionare la pagina **Account personale** del sito, quindi selezionare **Modifica**.
1. Nello slot **Principale** della pagina, selezionare lo slot **Riquadro generico account**. 
1. Nel riquadro delle proprietà **Riquadro generico account**, in **Collegamenti**, selezionare **Aggiungi collegamento azione**, quindi selezionare **Collegamento azione**.
1. Nella finestra di dialogo **Collegamento azione**, in **Testo collegamento**, immettere il testo per il collegamento alla pagina di selezione del catalogo.
1. In **Destinazione collegamento**, selezionare **Aggiungi un collegamento**.
1. Nella finestra di dialogo **Aggiungi un collegamento**, selezionare **Pagina personalizzata**, quindi selezionare **Avanti**.
1. In **Nome**, selezionare la pagina di selezione del catalogo, selezionare **Applica**, quindi selezionare **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

La figura seguente mostra un esempio di una pagina degli account con un riferimento alla pagina del catalogo.

![Pagina Account personali con collegamento al catalogo.](./media/my-accounts.png)

### <a name="add-a-link-from-the-header"></a>Aggiungere un collegamento dall'intestazione

Infine, aggiungere un collegamento dall'intestazione del sito ai cataloghi.

1. Andare a **Frammenti**, trovare e selezionare il frammento di intestazione del sito, quindi selezionare **Modifica**.
1. Selezionare lo slot **Intestazione**. 
1. Nel riquadro **Intestazione**, in **Collegamenti account personale**, selezionare **Aggiungi collegamento azione**, quindi selezionare **Collegamento azione**.
1. Nella finestra di dialogo **Collegamento azione**, in **Testo collegamento**, immettere il testo per il collegamento alla pagina di selezione del catalogo.
1. In **Destinazione collegamento**, selezionare **Aggiungi un collegamento**.
1. Nella finestra di dialogo **Aggiungi un collegamento**, selezionare **Pagina personalizzata**, quindi selezionare **Avanti**.
1. In **Nome**, selezionare la pagina di selezione del catalogo, selezionare **Applica**, quindi selezionare **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento di intestazione, quindi selezionare **Pubblica** per pubblicarlo.

La figura seguente mostra un esempio di un'intestazione del sito Web di e-commerce con un collegamento al catalogo B2B.

![Intestazione del sito Web di e-commerce con collegamento a discesa al catalogo.](./media/catalog-in-header.png)


## <a name="additional-resources"></a>Risorse aggiuntive 

[Crea cataloghi di Commerce per siti B2B](catalogs-b2b-sites.md)

[Impatto sull'estendibilità dei cataloghi di Commerce per le personalizzazioni B2B](catalogs-b2b-sites-dev.md)

[Domande frequenti sui cataloghi di Commerce per B2B](catalogs-b2b-sites-FAQ.md)

[Moduli e pagine gestione conti](account-management.md)

[Modulo intestazione](author-header-module.md)
