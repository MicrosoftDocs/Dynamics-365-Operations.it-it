---
title: Gestire unità di misura
description: Questo argomento descrive come definire un'unità di misura, come fornire conversioni per l'unità e la relativa descrizione e come definire le regole di conversione per le unità correlate.
author: sorenva
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d36839cd8e3398225d3421bf0f268068599ca49f
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921343"
---
# <a name="manage-units-of-measure"></a>Gestire unità di misura

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come definire un'unità di misura, come fornire conversioni per l'unità e la relativa descrizione e come definire le regole di conversione per le unità correlate.

## <a name="open-the-units-page"></a>Aprire la pagina Unità

Per creare e lavorare con le unità di misura disponibili nel tuo sistema, vai a **Amministrazione organizzazione \> Impostazioni \> Unità \> Unità**.

Le sezioni rimanenti di questo argomento descrivono cosa è possibile fare nella pagina **Unità**.

## <a name="create-standard-units-and-conversions"></a>Creare unità e conversioni standard

Se il tuo sistema non include già le unità di misura più comunemente utilizzate per il sistema metrico e / o US Customary System (USCS), la procedura guidata di configurazione delle unità può aiutarti a iniziare rapidamente con le definizioni e le conversioni di unità di base. Per completare la procedura guidata, seleziona **Creazione guidata unità** nel riquadro azioni, quindi seguire le istruzioni sullo schermo.

## <a name="create-or-edit-a-unit-of-measure"></a>Creare o modificare un'unità di misura

Per creare o modificare un'unità di misura, segui questi passaggi.

1. Eseguire uno dei passaggi riportati di seguito.

    - Per modificare un'unità esistente, selezionala nel riquadro elenco.
    - Nel riquadro azioni seleziona **Nuovo** per creare una nuova unità.

1. Nell'intestazione del record, impostare i seguenti campi:

    - **Unità** - Immettere l'ID o il simbolo da utilizzare per fare riferimento all'unità nella lingua del sistema. Questo ID o simbolo è solitamente un'abbreviazione comune per l'unità, ad esempio *pz* per pezzo o *cm* per centimetro.
    - **Descrizione** – Immettere un nome descrittivo dell'unità nella lingua del sistema. Questo nome è solitamente il nome completo dell'unità, ad esempio *Pezzo* o *Centimetro*.

1. Nella scheda dettaglio **Generale**, impostare i seguenti campi:<!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - **Classe di unità di misura** - Selezionare la proprietà misurata dall'unità (come lunghezza, area, massa o quantità).
    - **Sistema di misurazione** - Selezionare il sistema di misurazione a cui appartiene l'unità (*Unità sistema metrico decimale* o *Unità sistema di misura USA*).
    - **Unità di base** - Imposta questa opzione su *Sì* per utilizzare l'unità corrente come unità di base per la sua classe di unità di misura. In questo caso, devi solo specificare il fattore di conversione tra l'unità di base e ogni unità aggiuntiva nella classe di unità di misura. Il sistema può quindi convertire tra tutte le unità in quella classe di unità di misura. Pertanto, è più facile impostare le conversioni.

        Ad esempio, se gallone è l'unità di base per la classe di unità di misura *Volume*, devi solo impostare i fattori di conversione da quarto a gallone e da pinta a gallone. Il sistema può quindi anche convertire da un quarto a una pinta.

        Puoi avere una sola unità di base per classe di unità di misura.

    - **Unità di sistema** - Imposta questa opzione su *Sì* per utilizzare l'unità corrente come unità presunta per tutte le misurazioni non specificate nella sua classe di unità di misura. Ad esempio, se un campo utilizzato per immettere una quantità non consente di specificare un'unità (o se l'utente non seleziona un'unità), il sistema utilizza l'unità impostata come unità di sistema per la classe di unità di misura *Quantità*. Puoi avere una sola unità di sistema per classe di unità di misura.
    - **Precisione decimale** - Specificare il numero di cifre decimali a cui arrotondare i valori specificati per l'unità corrente o convertiti in essa.

1. Nel riquadro azioni selezionare **Salva**.

## <a name="define-unit-translations"></a>Definire conversioni unità

Per definire le traduzioni per l'ID o il simbolo e la descrizione per un'unità di misura, attenersi alla seguente procedura.

1. Crea o seleziona l'unità per cui creare le traduzioni.
1. Nel riquadro azioni, seleziona **Testi unità**.

    Viene visualizzata la pagina **Testi unità**. Utilizzare questa pagina per definire le traduzioni per l'ID o il simbolo per l'unità selezionata. Tali traduzioni possono quindi essere utilizzate su documenti esterni in lingue specifiche del cliente o del fornitore.

1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Lingua** selezionare la lingua in cui tradurre l'ID o il simbolo dell'unità.
1. Nel campo **Testo** campo, inserire la traduzione dell'ID unità o del simbolo nella lingua selezionata.
1. Nel riquadro azioni selezionare **Salva**.
1. Chiudere la pagina.
1. Nel **riquadro azioni** fai clic su **Descrizioni unità convertite**.

    La pagina **Descrizioni unità convertite** viene visualizzata. Utilizzare questa pagina per definire le descrizioni specifiche della lingua per l'unità selezionata.

1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Lingua** selezionare la lingua in cui tradurre la descrizione dell'unità.
1. Nel campo **Descrizione** campo, inserire la traduzione della descrizione unità nella lingua selezionata.
1. Nel riquadro azioni selezionare **Salva**.
1. Chiudere la pagina.

## <a name="define-unit-conversion-rules"></a>Definire regole di conversione unità

Per definire le regole per le conversioni tra unità di misura, segui questi passaggi.

1. Crea o seleziona l'unità per cui definire le regole di conversione.
1. Nel riquadro azioni, seleziona **Conversioni unità**.

    Viene aperta la pagina **Conversioni unità**. Usa questa pagina per fefinire le regole per la conversione dell'unità selezionata verso e da altre unità di misura incluse nella classe di unità di misura.

1. Selezionare una delle schede seguenti a seconda del tipo di conversione da impostare:

    - **Conversioni standard** – Consente di impostare le regole di conversione standard per tutti i prodotti.
    - **Conversioni in classi** - Consente di impostare le regole di conversione specifiche di un prodotto per le unità appartenenti alla stessa classe di unità di misura.
    - **Conversioni tra classi** - Consente di impostare le regole di conversione specifiche di un prodotto per le unità di diverse classi di unità di misura.

1. Eseguire uno dei passaggi riportati di seguito.

    - Nella barra degli strumenti seleziona **Nuovo** per creare una nuova conversione.
    - Per modificare una conversione esistente, seleziona la conversione nella griglia, quindi seleziona **Modifica** sulla barra degli strumenti.

1. Nella finestra di dialogo a discesa visualizzata, impostare i seguenti campi:

    - **Prodotto** - Seleziona il prodotto specifico a cui si applica la conversione. Questo campo è disponibile solo per conversioni in classi e tra classi.
    - **Layout formula** - Lascia questo campo impostato su *Semplice* per specificare una semplice conversione che ha un singolo fattore. Impostalo su *Avanzato* per impostare un'equazione più complessa. Il formato per le equazioni avanzate varia a seconda della classe di unità di misura.
    - **Dall'unità** - Questo campo mostra l'unità selezionata. Di solito, non dovresti modificare il valore. (Se modifichi il valore, devi aprire la pagina **Conversioni unità** per l'unità selezionata per visualizzare la nuova conversione dopo averla salvata.)
    - **All'unità** - Seleziona l'unità in cui convertire.
    - **Arrotondamento** - Seleziona come arrotondare le frazioni, in base al valore **Precisione decimale** dell'unità selezionata (*All'unità più vicina*, *Per eccesso*, o *Per difetto*).
    - **Formula di conversione** - Utilizzare i campi rimanenti nella parte superiore della finestra di dialogo a discesa per specificare la formula per la conversione tra le due unità. I campi disponibili variano a seconda della classe di unità di misura e del layout della formula selezionati.

1. Selezionare **OK**.
1. Chiudere la pagina.

> [!TIP]
> Puoi anche impostare conversioni di unità per variante di prodotto. Per ulteriori informazioni, vedere [Conversione di unità di misura per varianti prodotto](../uom-conversion-per-product-variant.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
