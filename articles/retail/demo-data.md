---
title: Layout della schermata di dati dimostrativi in Retail Modern POS (MPOS) e Cloud POS
description: Di seguito vengono descritti i layout schermo inclusi con il set di dati dimostrativi per le esperienze POS in Microsoft Dynamics 365 for Retail.
author: zlinster
manager: AnnBe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: zlinster
ms.search.validFrom: 2017-10-05
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 41930e89a7cae5cdb84e728da47de3bc5de312ca
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="demo-data-screen-layouts-in-retail-modern-pos-mpos-and-cloud-pos"></a>Layout della schermata di dati dimostrativi in Retail Modern POS (MPOS) e Cloud POS

[!include [banner](includes/banner.md)]

Di seguito vengono descritti i layout schermo inclusi con il set di dati dimostrativi per le esperienze POS in Microsoft Dynamics 365 for Retail.

## <a name="overview"></a>Panoramica

I layout schermo di esempio inclusi con i dati dimostrativi di Retail forniscono contenuto ottimizzato per vari segmenti di vendita al dettaglio, ruoli lavoratore punto vendita e dispositivi. Un singolo layout può contenere varie dimensioni di layout e combinazioni di griglie di pulsanti per assicurare la copertura quando i lavoratori di punti vendita vengono spostati tra dispositivi e stazioni. In questo argomento vengono evidenziate le differenze tra questi layout nonché le operazioni che forniscono e le esperienze globali che offrono.

![Layout con dati dimostrativi per vari dispositivi](../retail/media/demo-screen-layouts-fig-1-1.png)

## <a name="anatomy-of-a-screen-layout-id"></a>Anatomia di un ID layout schermo

Per trovare i layout schermo in Retail, accedere a **Vendita al dettaglio** > **Impostazione canale** > **Impostazione POS** > **POS** > **Layout schermo**.

![Pagina Layout schermo in Retail](../retail/media/demo-screen-layouts-fig-2-1.png)

Gli ID layout schermo possono avere un massimo di 10 caratteri. L'ID è una stringa costituita da tre informazioni, in questo ordine:

1. Società
2. Versione layout
3. Persona

### <a name="company"></a>Società

| Lettera | Società         |
|--------|-----------------|
| A      | Adventure Works |
| F      | Fabrikam        |
| Z      | Contoso         |

### <a name="layout-version"></a>Versione layout

| Numero versione | descrizione                                                                                |
|----------------|--------------------------------------------------------------------------------------------|
| 3              | La versione di base che supporta molteplici dimensioni di schermo per vari dispositivi e proporzioni |
| 3.1            | La versione di base con un supporto aggiuntivo per il pannello **Prodotti consigliati**        |

### <a name="persona"></a>Persona

| Abbreviazione | Persona       | Contenuto |
|--------------|---------------|----------|
| CSH          | Cassiere       | I layout Cassiere includono tutte le operazioni relative alle transazioni, ad esempio ordini cliente, resi, sconti, annullamenti e gift card. Questi layout includono anche le attività giornaliere per la gestione degli articoli, come controlli dei prezzi, ricerche in magazzino e conteggi delle scorte. La gestione di turni di base viene fornita anche per gli importi iniziali, sospensioni dei turni e orologio. |
| MGR          | Responsabile punto vendita | I layout Responsabile punto vendita includono tutte le operazioni relative alle transazioni presenti nei layout Cassiere nonché le forzature IVA. Questi layout includono anche le attività giornaliere per la gestione degli articoli, come controlli dei prezzi, ricerche in magazzino e conteggi delle scorte. La gestione dei turni viene fornita per iniziare, sospendere e chiudere turni. I layout includono inoltre le operazioni di cassetto per voci, rimozioni, riepiloghi incassi e depositi in cassaforte e bancari. Questi layout includono infine l'accesso ai report sulle prestazioni e consentono la stampa di report X e Z. |
| STK          | Addetto alle scorte   | I layout Addetto alle scorte sono ottimizzati per la gestione degli articoli. Comprendono l'accesso alle attività giornaliere per controlli dei prezzi, ricerche in magazzino, prelievo e ricezione, conteggi delle scorte e disassemblaggio kit. Questi layout forniscono inoltre operazioni per turni di base per l'orologio e la sospensione dei turni. Sebbene questi layout siano destinati principalmente per le attività di back office, le operazioni degli addetti alle scorte sono le stesse dei cassieri per le schermate delle transazioni. |

### <a name="example-layout"></a>Layout di esempio

Di seguito viene riportato un esempio di ID layout per la società Fabrikam, layout versione 3 e la persona Responsabile punto vendita:

F3MGR

Nella figura seguente è illustrato un esempio della schermata di benvenuto per un responsabile punto vendita di Fabrikam.

![Schermata di benvenuto per il responsabile punto vendita di Fabrikam](../retail/media/demo-screen-layouts-fig-2-2.png)

## <a name="layout-sizes"></a>Dimensioni layout

### <a name="full-vs-compact-layouts"></a>Layout completi e layout compatti

Un layout schermo può avere configurazioni per dispositivi completi e dispositivi compatti. Di conseguenza, un utente può essere assegnato a un singolo layout schermo utilizzabile con diverse dimensioni e fattori modulo nel punto vendita.

- **POS moderno - Completo** - In genere, i layout completi sono più adatti per schermi di maggiori dimensioni, ad esempio monitor di PC o tablet. Gli utenti possono selezionare gli elementi dell'interfaccia utente che il layout include, specificare la dimensione e la posizione di quegli elementi e configurarne le proprietà dettagliate. Il layout completo supporta entrambe le configurazioni orizzontale e verticale.
- **POS moderno - Compatto** - Il layout compatto in genere è migliore per telefoni o tablet di piccole dimensioni. Le opzioni di progettazione sono limitate per i dispositivi compatti. Gli utenti possono configurare le colonne e i campi dei riquadri ricevuta e totali.

### <a name="screen-resolutions-that-are-provided"></a>Risoluzioni schermo fornite

Nella tabella seguente vengono illustrate le dimensioni di layout fornite per risoluzioni schermo tipiche.

| Tipo di layout | Risoluzione | Proporzioni | Display di destinazione          |
|-------------|------------|--------------|-------------------------|
| Compatta\*   | 480 × 853  | 16:9         | Telefoni                  |
| Completo        | 1024 × 768 | 4:3          | Tablet                 |
| Completo\*      | 1280 × 720 | 16:9         | Tablet                 |
| Completo        | 1366 × 768 | 16:9         | Tablet, schermi più grandi |
| Completo        | 1440 × 960 | 3:2          | Tablet, schermi più grandi |

\* Queste dimensioni di layout aggiuntive sono disponibili solo nei layout di Fabrikam e Adventure Works.


>[!TIP]
> Il POS seleziona automaticamente le dimensioni di layout in base alla dimensione più vicina disponibile per la risoluzione schermo della finestra dell'app corrente. Per trovare l'ID layout schermo e la risoluzione di layout attualmente utilizzata, in Retail Modern POS (MPOS) o Retail Cloud POS (CPOS), aprire la pagina **Impostazioni** ed esaminare la sezione **Informazioni sessione**. È inoltre possibile visualizzare la risoluzione effettiva della finestra per il frame del browser o dell'applicazione corrente. Dopo aver acquisito queste informazioni, è possibile trovare l'origine del contenuto del layout in Retail accedendo a **Impostazione canale** > **Impostazione POS** > **POS** > **Layout schermo**.


![I layout schermo e le risoluzioni/dimensioni di layout in Retail e nel POS](../retail/media/demo-screen-layouts-fig-3-1.png)

## <a name="companies-and-brands"></a>Società e marchi

Ogni società fittizia è relativa ad un segmento di vendita al dettaglio differente ed include cataloghi di prodotti adattati per il mercato della società. Ogni società ha un marchio visivo univoco che ne accompagna i prodotti. Gli elementi del marchio includono il colore principale, un tema chiaro o scuro e le fotografie associate che forniscono esperienze realistiche.

### <a name="company-segment-and-visual-characteristics"></a>Caratteristiche grafiche e segmento della società

| Società         | Percorso | Segmento        | Principale | Tema |
|-----------------|----------|----------------|--------|-------|
| Adventure Works | Seattle  | Articoli sportivi | Blu   | Scuro  |
| Fabrikam        | Houston  | Abbigliamento        | Verde  | Leggero |
| Contoso         | Boston   | Elettronica    | Rosso    | Scuro  |


>[!NOTE]
> Adventure Works e Fabrikam sono i due marchi principali. Contoso è disponibile, ma non tutti i layout sono stati specificati.


Nelle figure seguenti vengono illustrati esempi della pagina di benvenuto e della pagina delle transazioni per le tre società fittizie.

### <a name="adventure-works"></a>Adventure Works

![Pagina iniziale con dati dimostrativi per Adventure Works](../retail/media/demo-screen-layouts-fig-4-1a.png)

![Pagina delle transazioni con dati dimostrativi per Adventure Works](../retail/media/demo-screen-layouts-fig-4-1b.png)

### <a name="fabrikam"></a>Fabrikam

![Pagina di benvenuto con dati dimostrativi per Fabrikam](../retail/media/demo-screen-layouts-fig-4-2a.png)

![Pagina delle transazioni con dati dimostrativi per Fabrikam](../retail/media/demo-screen-layouts-fig-4-2b.png)

### <a name="contoso"></a>Contoso

![Layout con dati dimostrativi per Contoso](../retail/media/demo-screen-layouts-fig-4-3.png)

## <a name="user-sign-in-matrix"></a>Matrice di accesso degli utenti

Degli utenti sono stati specificati per i vari layout schermo. Mediante la seguente tabella, dovrebbe essere possibile accedere a una qualsiasi delle schermate. Accedere utilizzando un ID operatore appropriato.

| Società         | ID layout schermo | Persona          | ID operatore           |
|-----------------|------------------|---------------   |------------------------|
| Adventure Works | A3MGR            | Responsabile punto vendita    | 000154, 000137, 000073 |
| Adventure Works | A3CSH            | Cassiere          | 000150, 000175, 000165 |
| Adventure Works | A3STK            | Addetto alle scorte      | 000155, 000181, 000152 |
| Fabrikam        | F3MGR            | Responsabile punto vendita    | 000160, 000168, 000163 |
| Fabrikam        | F3CSH            | Cassiere          | 000161, 000113, 000114 |
| Fabrikam        | F3STK            | Addetto alle scorte      | 000164, 000112, 000123 |
| Contoso         | C3MGR            | Responsabile punto vendita    | 000100, 000111         |
| Contoso         | C3CSH            | Cassiere          | 000110, 000120         |
| Contoso         | Non applicabile   | Addetto alle scorte      | Non applicabile         |


>[!TIP]
> Per ottenere i migliori risultati, attivare un registratore di cassa nell'ubicazione punto vendita corrispondente e impostare la società sulla società della persona che si intende utilizzare all'accesso. In questo modo, le immagini del profilo visivo e del marchio sono allineate all'esperienza. Ad esempio, se si desidera visualizzare un layout di Fabrikam per un cassiere, è necessario attivare un registratore di cassa nel punto vendita di Houston.


<!-- Hiding until the content page is available on CustomerSource -->

<!-- ## Reference icons and images -->

<!-- The screen layouts, button grids, and visual profiles were created using images and icons that can be found in **Retail > Channel setup > POS setup > POS > Images**. -->

<!-- ![Images in Dynamics 365 for Retail](../retail/media/demo-screen-layouts-fig-5-1.png) -->

<!-- Use the [POS Icon and Image Mapping](../retail/media/POS_Icon_and_Image_Mapping.xlsx) reference spreadsheet to locate operation icons, reference photos, swap logos, or provide new images of your own that can be referenced in custom designs. -->

<!-- END HIDDEN CONTENT -->

