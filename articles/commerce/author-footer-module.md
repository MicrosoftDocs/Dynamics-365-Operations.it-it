---
title: Modulo Piè di pagina
description: In questo articolo vengono descritti i moduli Piè di pagina e la procedura per crearli in Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4e7796d9700eabc923f2bb45187832d5993ae56e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876614"
---
# <a name="footer-module"></a>Modulo Piè di pagina  

[!include [banner](includes/banner.md)]

In questo articolo vengono descritti i moduli Piè di pagina e la procedura per crearli in Microsoft Dynamics 365 Commerce.

Il modulo Piè di pagina è un contenitore speciale utilizzato per l'hosting dei moduli visualizzati nel piè di pagina. Ad esempio, può includere collegamenti a varie pagine del sito, ad esempio le pagine **Politiche del punto vendita** e **Contattaci**.

L'immagine seguente mostra un esempio di modulo Piè di pagina in una pagina di sito.

![Esempio di modulo Piè di pagina.](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a>Proprietà del modulo Piè di pagina 

Come la maggior parte dei contenitori, un modulo Piè di pagina supporta le proprietà per l'intestazione e la larghezza. Supporta inoltre l'aggiunta di molteplici moduli categoria Piè di pagina. Per ogni modulo Categoria piè di pagina aggiunto viene eseguito il rendering come colonna nel modulo Piè di pagina.

## <a name="modules-available-in-a-footer-module"></a>Moduli disponibili in un modulo Piè di pagina

**Elemento piè di pagina** - Un modulo di elemento piè di pagina può contenere un'intestazione o un collegamento. L'intestazione è generalmente utilizzata come titolo della sezione del piè di pagina.  Ogni collegamento nel piè di pagina può essere configurato di modo che abbia solo testo (ad esempio i collegamenti "Contattaci" e "Privacy") oppure del testo e un'immagine (ad esempio collegamenti ai social media). Se vengono forniti sia un'intestazione che un collegamento, la proprietà dell'intestazione avrà la precedenza sul collegamento. 

**Torna all'inizio** - Un modulo Torna all'inizio fornisce un collegamento per spostarsi rapidamente all'inizio della pagina. È necessaria una destinazione. Il valore di destinazione predefinito è \#, che porta l'utente all'inizio della pagina.

## <a name="create-a-footer-module"></a>Creare modulo piè di pagina

1. Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.
1. Nella finestra di dialogo **Seleziona un frammento**, seleziona il modulo **Contenitore**, immetti un nome per il frammento e seleziona **OK**.
1. Nello slot **Contenitore predefinito** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli**, seleziona il modulo **Categoria piè di pagina** e quindi **OK**.
1. Nello slot **Categoria piè di pagina** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Elemento piè di pagina** e quindi **OK**.
1. Selezionare lo slot **Elemento piè di pagina** e nel riquadro delle proprietà a destra, configurare l'intestazione, il collegamento, il testo del collegamento e l'immagine come necessario.
1. Per aggiungere ulteriori elementi piè di pagina, ripetere i passaggi da 5 a 7 per ognuno.
1. Per aggiungere un collegamento "torna all'inizio" al piè di pagina, seleziona i puntini di sospensione (**...**) nello slot **Categoria piè di pagina** e quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Torna all'inizio** e quindi **OK**.
1. Selezionare lo slot **Torna all'inizio** e nel riquadro delle proprietà a destra, configurare il testo e altre proprietà del modulo come necessario.
1. Selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.

Per garantire che un'intestazione sia visualizzata in ogni pagina, effettuare le seguenti operazioni in ogni modello di pagina creato per il sito.

1. Nello slot **Piè di pagina** del modulo **Pagina predefinita**, aggiungere il frammento piè di pagina creato.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.

Aggiungendo il frammento ai modelli di pagina, si assicura il rendering del piè di pagina in ogni pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo casella acquisti](add-buy-box.md)

[Modulo carrello](add-cart-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
