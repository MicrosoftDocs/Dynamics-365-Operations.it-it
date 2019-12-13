---
title: Modulo contenitore
description: In questo argomento vengono descritti i moduli contenitore e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 22a09b61fbe3bd1cca96011d3fb81a12ef1bc844
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697062"
---
# <a name="container-module"></a>Modulo contenitore

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli contenitore e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un modulo contenitore è un modulo che include altri moduli. Si tratta del contenitore più generico utilizzato in Dynamics 365 Commerce. Lo scopo principale di un modulo contenitore è definire, mediante le proprietà impostate per lo stesso, il layout dei moduli che include. Ad esempio, tali moduli possono apparire affiancati in un layout a due, tre, quattro o sei colonne. Possono anche essere limitati alla larghezza del contenitore, oppure riempire tutto lo schermo. Un'intestazione può inoltre essere aggiunta a ogni modulo contenitore.

Sono disponibili tre tipi standard di moduli contenitore: contenitore, contenitore con 2 slot e contenitore con 3 slot. Questi contenitori possono includere moduli di qualsiasi tipo. Vi sono inoltre tipi speciali di moduli contenitore, ad esempio Sequenza, Blocco ricco di contenuti, Posizionamento contenuti, Carrello, Checkout, Casella acquisti, Intestazione e Piè di pagina. Questi contenitori hanno scopi specifici e possono includere solo specifici tipi di moduli supportati.

Si consiglia di includere moduli in un contenitore, di modo che possano essere limitati alla larghezza del contenitore.

## <a name="examples-of-container-modules-in-e-commerce"></a>Esempi di moduli contenitore in e-Commerce

- Un autore di siti desidera un layout a tre colonne, in cui tre moduli appaiono affiancati. Di conseguenza, l'autore utilizza un modulo contenitore del contenitore con un tipo a 3 slot.
- Un autore di siti desidera un layout a sei colonne, in cui sei moduli appaiono affiancati. Di conseguenza, l'autore utilizza un contenitore del tipo con sei colonne.
- Un autore di siti desidera includere un modulo in una pagina che non deve essere visualizzato a schermo intero. Di conseguenza, l'autore aggiunge il modulo a un modulo contenitore e imposta la proprietà **Larghezza** del contenitore su **Adatta a contenitore**.

## <a name="container-module-properties"></a>Proprietà del modulo contenitore

| Nome proprietà     | Valori | Descrizione |
|-------------------|--------|-------------|
| Intestazione           | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**), | Un'intestazione facoltativa può essere fornita per il contenitore. Per impostazione predefinita, il tag di intestazione **H2** è utilizzato per l'intestazione. Tuttavia, il tag può essere modificato per soddisfare i requisiti di accessibilità. |
| Larghezza             | **Adatta a contenitore** o **Riempi schermo** | Se il valore è **Adatta a contenitore** (il valore predefinito), i moduli nel contenitore sono limitati alla larghezza del contenitore. Se il valore impostato è **Riempi schermo**, i moduli non sono limitati alla larghezza del contenitore ma possono essere visualizzati in modalità a schermo intero. |
| Numero di colonne | **1**, **2**, **3**, **4**, **6** o **12** | Questa proprietà definisce il numero di colonne nel contenitore. Un contenitore può avere fino a 12 colonne. |

## <a name="container-with-2-slots"></a>Contenitore con 2 slot

Il contenitore con un tipo a 2 slot è ottimizzato per un layout a due colonne. Questo tipo di contenitore dispone di due slot per consentire una visualizzazione affiancata dei moduli che include.

Ulteriori proprietà possono essere utilizzate per ottimizzare il layout per differenti porte di visualizzazione (dispositivi mobili, tablet, computer e così via). Per ogni porta di visualizzazione, è possibile definire la larghezza di ogni colonna. Le seguenti impostazioni sono disponibili per la larghezza di colonna:

- **75%/25%** - Il primo modulo ha una larghezza di colonna del 75% e il secondo modulo ha una larghezza di colonna del 25%. È inoltre disponibile un'opzione **25%/75%**.
- **50%/50%** - Entrambi i moduli hanno una larghezza di colonna uguale.
- **67%/33%** - Il primo modulo ha una larghezza di colonna del 67% e il secondo modulo ha una larghezza di colonna del 33%. È inoltre disponibile un'opzione **33%/67%**.
- **100%** - Entrambi i moduli hanno una larghezza di colonna del 100%. Di conseguenza, i moduli sono impilati verticalmente in una singola colonna. Sebbene questo layout a singola colonna non rientra nell'ambito del contenitore con il tipo a 2 slot, potrebbe essere preferibile per alcune porte di visualizzazione (ad esempio porte di visualizzazione molto piccole come i dispositivi mobili).

### <a name="container-with-2-slots-properties"></a>Proprietà del contenitore con 2 slot

| Nome proprietà                   | Valori | Descrizione |
|---------------------------------|--------|-------------|
| Intestazione                         | Testo e tag di intestazione | Un'intestazione facoltativa può essere fornita per il contenitore. |
| Configurazione per porte di visualizzazione molto piccole | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%** | Questa proprietà definisce il layout per le porte di visualizzazione molto piccole. |
| Configurazione per porte di visualizzazione molto piccole   | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%** | Questa proprietà definisce il layout per le porte di visualizzazione molto piccole come i dispositivi mobili. |
| Configurazione per porte di visualizzazione medie  | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%** | Questa proprietà definisce il layout per le porte di visualizzazione medie come i tablet. |
| Configurazione per porte di visualizzazione grandi   | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%** | Questa proprietà definisce il layout per le porte di visualizzazione grandi come i computer. |

## <a name="container-with-3-slots"></a>Contenitore con 3 slot

Il contenitore con il tipo di moduli a 3 slot è ottimizzato per un layout a tre colonne.

Ulteriori proprietà possono essere utilizzate per ottimizzare il layout per differenti porte di visualizzazione. Per ogni porta di visualizzazione, è possibile definire la larghezza di ogni colonna. Le seguenti impostazioni sono disponibili per la larghezza di colonna:

- **33%/33%/33%** - Tutti e tre i moduli hanno una larghezza di colonna uguale.
- **50%/25%/25%** - Il primo modulo ha una larghezza di colonna del 50% e ognuno dei due moduli rimanenti ha una larghezza di colonna del 25%. Sono disponibili anche le opzioni **25%/50%/25%** e**25%/25%/50%**.
- **16%/16%/67%** - Ognuno dei due primi moduli ha una larghezza di colonna del 16% e il terzo modulo ha una larghezza di colonna del 67%. Sono disponibili anche le opzioni **16%/67%/16%** e**67%/16%/16%**.

### <a name="container-with-3-slots-properties"></a>Proprietà del contenitore con 3 slot

| Nome proprietà                   | Valori | Descrizione |
|---------------------------------|--------|-------------|
| Intestazione                         | Testo e tag di intestazione | Un'intestazione facoltativa può essere aggiunta al contenitore. |
| Configurazione per porte di visualizzazione molto piccole | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%** | Questa proprietà definisce il layout per le porte di visualizzazione molto piccole. |
| Configurazione per porte di visualizzazione molto piccole   | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%** | Questa proprietà definisce il layout per le porte di visualizzazione molto piccole come i dispositivi mobili. |
| Configurazione per porte di visualizzazione medie  | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%** | Questa proprietà definisce il layout per le porte di visualizzazione medie come i tablet. |
| Configurazione per porte di visualizzazione grandi   | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%** | Questa proprietà definisce il layout per le porte di visualizzazione grandi come i computer. |

## <a name="add-a-container-module-to-a-page"></a>Aggiungere un modulo contenitore a una pagina

Per aggiungere un modulo contenitore a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Creare un modello pagina denominato **Modello contenitore**.
1. Nello slot **Principale** della pagina predefinita, aggiungere un modulo contenitore.
1. Aggiungere un modulo Funzionalità al modulo contenitore.
1. Archiviare il modello e pubblicarlo.
1. Utilizzare il modello contenitore appena creato per creare una pagina denominata **Pagina contenitore**.
1. Nello slot **Principale** della nuova pagina, aggiungere un modulo contenitore.
1. Nel riquadro delle proprietà del modulo contenitore, impostare la proprietà **Numero di colonne** su **1** e la proprietà **Larghezza** su **Adatta a contenitore**.
1. Aggiungere un modulo Funzionalità al modulo contenitore.
1. Nel riquadro delle proprietà del modulo Funzionalità, configurare un'intestazione.
1. Salvare la pagina e visualizzarne l'anteprima. Dovrebbe essere visualizzato un modulo Funzionalità adattato alla larghezza del modulo contenitore.
1. Nel riquadro delle proprietà del modulo contenitore, impostare la proprietà **Numero di colonne** su **3**.
1. Aggiungere due o più moduli Funzionalità al modulo contenitore.
1. Salvare la pagina e visualizzarne l'anteprima. Ora dovrebbero essere visualizzati tre moduli Funzionalità affiancati.
1. Dopo aver ottenuto il layout desiderato, archiviare la pagina e pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Sequenza](add-carousel.md)

[Modulo Blocco ricco di contenuti](add-content-rich-block.md)

[Modulo Posizionamento contenuti](add-content-placement-modules.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Checkout](add-checkout-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
