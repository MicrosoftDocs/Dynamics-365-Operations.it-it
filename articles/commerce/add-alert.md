---
title: Modulo Banner promozionale
description: In questo argomento vengono descritti i moduli Banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f781ed22852cb2108850e7dc6762aa6a9ba0db97574cb0dcc7959f8926e47a08
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718782"
---
# <a name="promo-banner-module"></a>Modulo banner promozionale

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Banner promozionale e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

I moduli Banner promozionale sono utilizzati per visualizzare messaggi informativi incorporati in una pagina. Possono essere utilizzati per visualizzare promozioni in tutto le pagine di un sito di e-Commerce. 

I moduli Banner promozionale supportano un messaggio di testo e un collegamento. Se vengono aggiunti più messaggi a un modulo banner promozionale, questo diventa un banner sequenza rotante che consente ai clienti di scorrere tutti i messaggi. 

I moduli Banner promozionale sono basati sui dati del sistema di gestione dei contenuti e possono essere utilizzati in qualsiasi pagina.

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a>Esempi di utilizzo di banner promozionali in e-commerce

I banner promozionali possono essere utilizzati nell'intestazione del sito per mostrare promozioni o messaggi in tutto il sito, come negli esempi seguenti.

"La vendita annuale termina tra 10 giorni"

"Grandi risparmi con la vendita di articoli scolastici. Acquista ora".

"SALDI del Giorno del ringraziamento" 

L'immagine seguente mostra un esempio di banner promozionale.

![Esempio di modulo del banner promozionale.](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a>Proprietà dei moduli Banner promozionale

| Nome proprietà             | Valore                              | descrizione |
|---------------------------|------------------------------------|-------------|
| Messaggi banner           | Testo e collegamenti                     | Una matrice di testo e collegamenti. |
| Riproduzione automatica                  | **True** o **False**              | Un valore che indica se i messaggi vengono automaticamente passati in rassegna, se sono configurati più messaggi. |
| Intervallo di transizione diapositiva | Un numero di millisecondi (ms)      | L'intervallo utilizzato per scorrere i messaggi. |
| Consenti chiusura             | **True** o **False**              | Se il valore è impostato su **True**, i clienti possono chiudere l'avviso. |
| Mostra flipper sequenza     | **True** o **False**              | Un valore che indica se i flipper della sequenza devono essere visualizzati, di modo che i clienti possano scorrere manualmente più elementi del banner. |
| Allineamento testo            | **A destra**, **A sinistra** o **Al centro** | L'allineamento del testo nel modulo banner promozionale. |
| Collega                      | URL A                              | L'URL di un collegamento facoltativo. |
|Allineamento testo             | **A destra**, **A sinistra** o **Al centro** | Questa proprietà è disponibile come estensione del tema nel tema Adventure Works. Consente a un utente di impostare l'allineamento del testo nel banner promozionale. |

> [!IMPORTANT]
> Il tema Adventure Works è disponibile a partire dalla versione Dynamics 365 Commerce 10.0.20.

## <a name="add-a-promo-banner-module-to-a-page"></a>Aggiungere un modulo banner promozionale a una pagina 

Per aggiungere un modulo banner promozionale a una pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Modelli** e selezionare **Nuovo** per creare un nuovo modello.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere **Modello banner promozionale**, quindi selezionare **OK**.
1. Sotto **Struttura pagina** , aggiungere un modulo **Pagina predefinita** allo slot **Corpo**. 
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo. 
1. Utilizzare il modello appena creato per creare una pagina denominata **Pagina banner promozionale**. 
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo contenitore. 
1. Nel riquadro a destra, impostare il valore **Larghezza** su **Riempi contenitore**.
1. Sotto **Struttura pagina**, aggiungere un modulo banner promozionale al modulo contenitore.
1. Nelle impostazioni per il modulo banner, aggiungere uno o più messaggi banner. Ogni messaggio può avere del testo e un collegamento. È possibile modificare le altre proprietà per personalizzare ulteriormente il modulo.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina. Nella parte superiore della pagina, dovrebbe essere visualizzato un avviso che mostra il testo aggiunto.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

> [!NOTE]
> Un banner promozionale viene in genere utilizzato nello slot dell'intestazione di pagina o in uno slot del sottotitolo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo sequenza](add-carousel.md)

[Modulo blocco testo](add-content-rich-block.md)

[Modulo blocco contenuto](add-hero-module.md)

[Modulo Lettore video](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
