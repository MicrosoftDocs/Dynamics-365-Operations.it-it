---
title: Modulo Sequenza
description: In questo argomento vengono descritti i moduli Sequenza e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f09f3f98d174f965a75e27ee6a5c2ed8599042fc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413383"
---
# <a name="carousel-module"></a>Modulo Sequenza

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Sequenza e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo Sequenza viene utilizzato per inserire molteplici articoli promozionali (incluse immagini) in un banner sequenza rotante al quale i clienti possono accedere. Ad esempio, un rivenditore può utilizzare un modulo Sequenza in una home page per presentare molteplici nuovi prodotti o promozioni.

È possibile aggiungere moduli Blocco di contenuto a un modulo Sequenza. Le proprietà del modulo Sequenza definiscono quindi il modo in cui viene eseguito il rendering di tali moduli.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Esempi di moduli Sequenza in e-Commerce

- Una sequenza che include più moduli promozionali può essere utilizzata in una home page.
- Una sequenza con più moduli promozionali può essere utilizzata in una pagina dettagli prodotto.
- Una sequenza può essere utilizzata in qualsiasi pagina marketing per promuovere molteplici promozioni o prodotti.

L'immagine seguente mostra un esempio di modulo Sequenza utilizzato in una home page. Questo modulo Sequenza contiene molteplici elementi del blocco di contenuto.

![Esempio di modulo Sequenza](./media/Hero.PNG)

## <a name="carousel-module-properties"></a>Proprietà del modulo Sequenza

| Nome proprietà             | Valore                 | descrizione |
|---------------------------|-----------------------|-------------|
| Riproduzione automatica                  | **True** o **False** | Se il valore è impostato su **True**, la transizione tra gli articoli nella sequenza viene eseguita automaticamente. Se il valore è impostato su **False**, non viene eseguita alcuna transizione a meno che il cliente non utilizzi la tastiera o il mouse per passare da un articolo all'articolo successivo. |
| Intervallo di transizione diapositiva | Un valore in secondi    | L'intervallo delle transizioni tra gli articoli. |
| Tipo di transizione           | **Diapositiva** o **Dissolvenza** | L'effetto di transizione tra gli articoli. |
| Nascondi flipper sequenza     | **True** o **False** | Se il valore è **True**, il flipper sequenza e l'indicatore di sequenza sono nascosti. |
| Consenti chiusura sequenza    | **True** o **False** | Se il valore è **True**, gli utenti possono chiudere la sequenza. |

## <a name="add-a-carousel-module-to-a-page"></a>Aggiungere un modulo Sequenza a una pagina

Per aggiungere un modulo Sequenza a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello sequenza**, quindi selezionare **OK**.
1. Nello slot **Corpo**, aggiungi un modulo **Pagina predefinita**.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.  
1. Utilizzare il modello sequenza appena creato per creare una pagina denominata **Pagina sequenza**.
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo Contenitore. 
1. Nel riquadro a destra, impostare il **Larghezza** su **Riempi schermo**.
1. Sotto **Struttura pagina**, aggiungere un modulo Sequenza al modulo Contenitore.
1. Aggiungere un modulo Blocco di contenuto al modulo Sequenza. Impostare le proprietà del modulo Blocco di contenuto fornendo **Intestazione**, **Collegamento**, **Layout** e altre proprietà.
1. Aggiungere e configurare un altro modulo Blocco di contenuto.
1. Impostare proprietà aggiuntive per il modulo Sequenza come necessario.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina. La pagina dovrebbe visualizzare una sequenza con due moduli (un modulo Hero e un modulo Funzionalità). È possibile modificare ulteriori proprietà dei moduli Sequenza, Hero e Funzionalità per ottenere l'effetto desiderato.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo banner promozionale](add-alert.md)

[Modulo blocco testo](add-content-rich-block.md)

[Modulo blocco contenuto](add-hero-module.md)

[Modulo Lettore video](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]