---
title: Modulo Galleria multimediale
description: In questo argomento vengono descritti i moduli Galleria multimediale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 647387bafe8866cb1bee8c57675629af796f33e6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413552"
---
# <a name="media-gallery-module"></a>Modulo Galleria multimediale

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Galleria multimediale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

I moduli Galleria multimediale mostrano una o più immagini in una vista galleria. I moduli Galleria multimediale supportano le immagini di anteprima, che possono essere disposte orizzontalmente (come riga sotto l'immagine) o verticalmente (come colonna accanto all'immagine). I moduli Galleria multimediale offrono anche funzionalità che consentono di ingrandire le immagini o visualizzarle in modalità a schermo intero. Per eseguire il rendering in un modulo Galleria multimediale, un'immagine deve essere disponibile nella libreria multimediale Creazione di siti Web Commerce. Attualmente, i moduli Galleria multimediale supportano solo immagini.

Nella modalità predefinita, un modulo Galleria multimediale utilizza l'ID prodotto disponibile nel contesto della pagina di una pagina dei dettagli del prodotto (PDP) per eseguire il rendering delle immagini del prodotto corrispondenti. In Commerce Headquarters, è necessario definire un percorso di file multimediale per tutti i prodotti. Le immagini devono quindi essere caricate nella libreria multimediale Creazione di siti Web in base al percorso di file definito per i prodotti in Commerce Headquarters. Queste immagini includono immagini di prodotti ed eventuali varianti di prodotto. Per ulteriori informazioni su come caricare immagini nella libreria multimediale Creazione di siti Web, vedere [Caricare immagini](dam-upload-images.md).

In alternativa, un modulo Galleria multimediale può ospitare un set di immagini completamente curato su una pagina della galleria di immagini, dove non vi sono dipendenze dall'ID prodotto o dal contesto della pagina. In questo caso, le immagini devono essere caricate nella libreria multimediale Creazione di siti Web e specificate in Creazione di siti Web.

Ecco alcuni esempi di utilizzo per i moduli Galleria multimediale:

- Rendering delle immagini dei prodotti in una PDP
- Rendering delle immagini dei prodotti in una pagina di marketing del prodotto
- Visualizzazione di un set curato di immagini su una pagina di marketing, come una pagina della galleria

Nell'esempio nella figura seguente, una casella acquisti in una PDP ospita le immagini dei prodotti utilizzando un modulo Galleria multimediale.

![Esempio di una casella acquisti in una pagina dei dettagli del prodotto che ospita le immagini del prodotto utilizzando un modulo Galleria multimediale](./media/ecommerce-pdp-buybox.PNG)

## <a name="media-gallery-properties"></a>Proprietà della galleria multimediale

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Origine immagine | **Contesto pagina** o **ID prodotto** | Il valore predefinito è **Contesto pagina**. Se **Contesto pagina** è selezionato, il modulo prevede che la pagina fornisca le informazioni sull'ID prodotto. Se **ID prodotto** è selezionato, l'ID prodotto per un'immagine deve essere fornito come valore della proprietà **ID prodotto**. Questa funzionalità è disponibile in Commerce versione 10.0.12. |
| ID prodotto | Un ID prodotto | Questa proprietà è applicabile solo se il valore della proprietà **Origine immagine** è **ID prodotto**. |
| Zoom immagine | **In linea** o **Contenitore** | Questa proprietà consente all'utente di ingrandire le immagini nel modulo Galleria multimediale. Un'immagine può essere ingrandita in linea o in un contenitore separato accanto all'immagine. Questa funzionalità è disponibile in 10.0.12 |
| Scala zoom | Un numero decimale | Questa proprietà specifica il fattore di scala per lo zoom delle immagini. Ad esempio, se il valore è impostato su **2,5**, le immagini vengono ingrandite 2,5 volte.|
| Schermo intero | **True** o **False** | Questa proprietà specifica se le immagini possono essere visualizzate in modalità a schermo intero. In modalità a schermo intero, le immagini possono essere ulteriormente ingrandite se la funzione di zoom è attivata. Questa funzionalità è disponibile in Commerce versione 10.0.13. |
| Immagini | Immagini selezionate dalla libreria multimediale Creazione di siti Web | Oltre al rendering eseguito da un prodotto, le immagini possono essere curate per un modulo Galleria multimediale. Queste immagini verranno aggiunte a tutte le immagini dei prodotti disponibili. Questa funzionalità è disponibile in Commerce versione 10.0.12. |
| Orientamento dell'anteprima | **Verticale** o **Orizzontale** | Questa proprietà specifica se le immagini di anteprima devono essere visualizzate in una striscia verticale o in una striscia orizzontale. |

La seguente illustrazione mostra un esempio di un modulo Galleria multimediale in cui sono disponibili le opzioni di schermo intero e zoom.

![Esempio di un modulo Galleria multimediale in cui sono disponibili le opzioni di schermo intero e zoom](./media/ecommerce-media-zoom.png)

La seguente illustrazione mostra un esempio di un modulo Galleria multimediale con immagini curate (ovvero, le immagini specificate non dipendono dall'ID prodotto o dal contesto della pagina).

![Esempio di un modulo Galleria multimediale con immagini curate](./media/ecommerce-media-curated.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interazione con Commerce Scale Unit

Quando l'origine dell'immagine viene derivata dal contesto della pagina, l'ID prodotto della PDP viene utilizzato per recuperare le immagini. Il modulo Galleria multimediale recupera il percorso di file delle immagini per i prodotti utilizzando le API di Commerce Scale Unit. Le immagini vengono quindi estratte dalla libreria multimediale in modo che possa essere eseguito il rendering nel modulo.

## <a name="add-a-media-gallery-module-to-a-page"></a>Aggiungere un modulo Galleria multimediale a una pagina

Per aggiungere un modulo Galleria multimediale in una pagina di marketing, effettuare le seguenti operazioni.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello di marketing**, quindi selezionare **OK**.
1. Nello slot **Corpo** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Pagina predefinita** e quindi selezionare **OK**.
1. Nello slot **Principale** della pagina predefinita, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Scegli un modello**, selezionare il modello **Modello di marketing**. Sotto **Nome pagina**, immettere **Pagina Galleria multimediale** e selezionare **OK**.
1. Nello slot **Principale** della nuova pagina, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Galleria multimediale** e quindi selezionare **OK**.
1. Nel riquadro delle proprietà per il modulo Galleria multimediale, in **Origine immagine** selezionare **Productid**. Quindi, nel campo **ID prodotto** immettere un ID prodotto.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina. Dovrebbe essere possibile vedere le immagini per il prodotto in una vista galleria.
1. Per utilizzare solo immagini curate, nel riquadro delle proprietà, in **Origine immagine** selezionare **Productid**. Quindi, in **Immagini** selezionare **Aggiungi un'immagine** tutte le volte che è necessario per aggiungere immagini dalla libreria multimediale.
1. Impostare eventuali proprietà aggiuntive, ad esempio **Zoom immagine**, **Fattore di zoom** e **Orientamento anteprime**.
1. Al termine, selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo casella acquisti](add-buy-box.md)

[Modulo contenitore](add-container-module.md)

[Caricare immagini](dam-upload-images.md)
