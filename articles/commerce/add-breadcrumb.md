---
title: Modulo Percorso di navigazione
description: In questo argomento vengono descritti i moduli Percoso di navigazione e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
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
ms.openlocfilehash: 38efc3a60ae0ba49db2036dc84c49e4896727d94
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621062"
---
# <a name="breadcrumb-module"></a>Modulo Percoso di navigazione

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Percoso di navigazione e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

I moduli Percoso di navigazione sono utilizzati per fornire una navigazione secondaria nelle pagine di sito. In genere sono visualizzati nella parte superiore di una pagina, sotto l'intestazione. Sebbene i moduli Percoso di navigazione possano essere aggiunti a qualsiasi pagina, vengono spesso utilizzati nelle pagine dettagli prodotto (PDP), per mostrare la gerarchia di categorie di prodotti e fornire un modo rapido di navigare in un sito. Un modulo Percoso di navigazione può anche essere usato per mostrare un collegamento "Torna ai risultati" quando gli utenti aprono una PDP da una pagina di ricerca o elenco. In questo modo, gli utenti possono tornare rapidamente alla loro pagina elenco filtrata per continuare a fare acquisti.

Nelle pagine con contesto categoria di prodotto, ad esempio le PDP e le pagine di categorie, i moduli Percoso di navigazione mostrano la gerarchia di categorie. Nelle pagine che non hanno contesto di categoria, per impostazione predefinita i moduli Percoso di navigazione visualizzano **&lt;Radice sito&gt; / &lt;Pagina corrente&gt;**. I moduli Percoso di navigazione possono anche essere configurati manualmente in altri tipi di pagine di sito per mostrare collegamenti a pagine specifiche del sito.

L'immagine seguente illustra un esempio di modulo Percoso di navigazione che mostra la gerarchia di categorie in una PDP.

![Esempio di modulo Percoso di navigazione](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a>Impostazioni del modulo Percorso di navigazione

Il modulo Percorso di navigazione si basa sull'impostazione **Tipo di visualizzazione percorso di navigazione in PDP**, definita in **Impostazioni sito \> Estensioni** in Creazione di siti Web. Questa impostazione ha tre valori possibili:

- **Mostra gerarchia di categorie** - Quando si seleziona questo valore, il modulo Percorso di navigazione mostrerà l'intera gerarchia di categorie del prodotto visualizzato nella PDP.
- **Mostra di nuovo i risultati** - Quando si seleziona questo valore, il modulo Percorso di navigazione mostrerà un collegamento "Torna ai risultati" in una PDP se l'utente ha aperto la PDP da un modulo che consente un collegamento "Torna ai risultati". Questa funzionalità è disponibile quando gli utenti navigano tra le pagine di categorie, ricerca, elenco e elenchi di suggerimenti. Per supportare questa funzionalità, i moduli Raccolta prodotti e Risultati ricerca hanno una proprietà denominata **Consenti di tornare a risultati in PDP**. Questa proprietà offre la flessibilità di definire i moduli che devono supportare la funzionalità "Torna ai risultati" nella PDP. Ad esempio, quando l'opzione **Mostra di nuovo i risultati** è selezionata in **Tipo di visualizzazione percorso di navigazione in PDP** nel modulo Percorso di navigazione e l'opzione **Consenti di tornare ai risultati in PDP** è selezionata per il modulo Risultati ricerca della pagina di ricerca, verrà visualizzato un collegamento "Torna ai risultati" quando gli utenti passano dalla pagina di ricerca a una pagina PDP.
- **Mostra gerarchia di categorie e torna ai risultati** - Questo valore è una combinazione dei due precedenti. Quando viene selezionato questo valore, il modulo Percorso di navigazione mostrerà sia la gerarchia di categorie completa sia un collegamento "Torna ai risultati" (se configurato) in una PDP.

## <a name="breadcrumb-module-properties"></a>Proprietà del modulo Percorso di navigazione

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Radice | Testo o collegamento| Questa proprietà facoltativa specifica il testo del collegamento e una destinazione del collegamento per la radice sito del percorso di navigazione. Se questa proprietà non è configurata, non verrà definita alcuna radice. |
| Collegamento percorso di navigazione | Collega | Questa proprietà facoltativa specifica i collegamenti per un percorso di navigazione configurato manualmente, se questi collegamenti sono necessari. I collegamenti sono visualizzati nell'ordine in cui sono elencati. |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a>Aggiungere un modulo Percorso di navigazione a una nuova pagina

Per aggiungere un modulo Percorso di navigazione a una pagina PDP e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Impostazioni sito /> Estensioni**, quindi per l'impostazionze **Tipo di visualizzazione percorso di navigazione in PDP**, selezionare **Mostra gerarchia di categorie**.
1. Andare a **Modelli** e selezionare il modello PDP.
1. Nello slot **Contenitore**  che contiene il modulo Casella acquisti, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Percorso di navigazione** e quindi **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare a **Pagine** e aprire una PDP che utilizza il modello PDP. Se una PDP non esiste ancora, crearne una.
1. Nello slot **Contenitore**  che contiene il modulo Casella acquisti, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Percorso di navigazione** e quindi **OK**.
1. Nel riquadro delle proprietà dello slot **Percorso di navigazione**, sotto **Radice**, selezionare **Testo collegamento**.
1. Nella finestra di dialogo **Testo collegamento**, immettere **Home** e sotto **Destinazione collegamento**, selezionare **Aggiungi un collegamento**.
1. Nella finestra di dialogo **Aggiungi un collegamento**, selezionare un collegamento per la radice del percorso di navigazione, quindi selezionare **OK**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Panoramica della pagina di destinazione di categoria e della pagina dei risultati della ricerca predefinite](category-search-page-overview.md)

[Moduli Raccolta prodotti](product-collection-module-overview.md)

[Modulo Casella acquisti](add-buy-box.md)
