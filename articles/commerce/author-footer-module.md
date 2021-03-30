---
title: Modulo Piè di pagina
description: In questo argomento vengono descritti i moduli Piè di pagina e la procedura per crearli in Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 16c9ca145aff97f0af242da4cf662367f1f4ca3d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211450"
---
# <a name="footer-module"></a>Modulo Piè di pagina  

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Piè di pagina e la procedura per crearli in Microsoft Dynamics 365 Commerce.

Il modulo Piè di pagina è un contenitore speciale utilizzato per l'hosting dei moduli visualizzati nel piè di pagina. Ad esempio, può includere collegamenti a varie pagine del sito, ad esempio le pagine **Politiche del punto vendita** e **Contattaci**.

L'immagine seguente mostra un esempio di modulo Piè di pagina in una pagina di sito.

![Esempio di modulo Piè di pagina](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a>Proprietà del modulo Piè di pagina 

Come la maggior parte dei contenitori, un modulo Piè di pagina supporta le proprietà per l'intestazione e la larghezza. Supporta inoltre l'aggiunta di molteplici moduli categoria Piè di pagina. Per ogni modulo Categoria piè di pagina aggiunto viene eseguito il rendering come colonna nel modulo Piè di pagina.

## <a name="modules-available-in-a-footer-module"></a>Moduli disponibili in un modulo Piè di pagina

**Elementi piè di pagina** - Un modulo Elementi piè di pagina può contenere un'intestazione, un'immagine e un collegamento. L'intestazione può essere utilizzata da sola o in combinazione con un'immagine e un collegamento. Ogni collegamento nel piè di pagina può essere configurato di modo che abbia solo testo (ad esempio i collegamenti "Contattaci" e "Privacy") oppure del testo e un'immagine (ad esempio collegamenti ai social media).

**Torna all'inizio** - Un modulo Torna all'inizio fornisce un collegamento per spostarsi rapidamente all'inizio della pagina. È necessaria una destinazione. Il valore di destinazione predefinito è \#, che porta l'utente all'inizio della pagina.

## <a name="create-a-footer-module"></a>Creare modulo piè di pagina

1. Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.
1. Nella finestra di dialogo **Nuovo frammento**, selezionare il modulo **Contenitore**, immettere un nome per il frammento e selezionare **OK**.
1. Nello slot **Contenitore predefinito** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Categoria piè di pagina** e quindi **OK**.
1. Nello slot **Categoria piè di pagina** selezionare i puntini di sospensione (**...**) quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Elemento piè di pagina** e quindi **OK**.
1. Selezionare lo slot **Elemento piè di pagina** e nel riquadro delle proprietà a destra, configurare l'intestazione, il collegamento, il testo del collegamento e l'immagine come necessario.
1. Per aggiungere ulteriori elementi piè di pagina, ripetere i passaggi da 5 a 7 per ognuno.
1. Per aggiungere un collegamento "torna all'inizio" al piè di pagina, selezionare i puntini di sospensione (**...**) nello slot **Categoria piè di pagina** e quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Torna all'inizio** e quindi **OK**.
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