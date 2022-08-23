---
title: Modulo percorso di navigazione
description: In questo articolo vengono descritti i moduli Percorso di navigazione e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: fe5dfea7e579d54d11be35eb657a1c1f617a5724
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277087"
---
# <a name="breadcrumb-module"></a>Modulo percorso di navigazione

[!include [banner](includes/banner.md)]

In questo articolo vengono descritti i moduli Percorso di navigazione e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

I moduli Percorso di navigazione sono utilizzati per fornire una navigazione secondaria nelle pagine di sito. In genere sono visualizzati nella parte superiore di una pagina, sotto l'intestazione. Sebbene i moduli Percorso di navigazione possano essere aggiunti a qualsiasi pagina, vengono spesso utilizzati nelle pagine dettagli prodotto (PDP), per mostrare la gerarchia di categorie di prodotti e fornire un modo rapido di navigare in un sito. Un modulo Percorso di navigazione può anche essere usato per mostrare un collegamento "Torna ai risultati" quando gli utenti aprono una PDP da una pagina di ricerca o elenco. In questo modo, gli utenti possono tornare rapidamente alla loro pagina elenco filtrata per continuare a fare acquisti.

Nelle pagine con contesto categoria di prodotto, ad esempio le PDP e le pagine di categorie, i moduli Percorso di navigazione mostrano la gerarchia di categorie. Nelle pagine che non hanno contesto di categoria, per impostazione predefinita i moduli Percorso di navigazione visualizzano **&lt;Radice sito&gt; / &lt;Pagina corrente&gt;**. I moduli Percorso di navigazione possono anche essere configurati manualmente in altri tipi di pagine di sito per mostrare collegamenti a pagine specifiche del sito.

> [!NOTE]
> Il modulo breadcrumb è disponibile in Dynamics 365 Commerce versione 10.0.12.

L'immagine seguente illustra un esempio di modulo Percorso di navigazione che mostra la gerarchia di categorie in una PDP.

![Esempio di modulo Percorso di navigazione.](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a>Impostazioni del modulo Percorso di navigazione

Il modulo Percorso di navigazione si basa sull'impostazione **Tipo di visualizzazione percorso di navigazione in PDP**, definita in **Impostazioni sito \> Estensioni** in Creazione di siti Web. Questa impostazione ha tre valori possibili:

- **Mostra gerarchia di categorie** - Quando si seleziona questo valore, il modulo Percorso di navigazione mostrerà l'intera gerarchia di categorie del prodotto visualizzato nella PDP.
- **Mostra di nuovo i risultati** - Quando si seleziona questo valore, il modulo Percorso di navigazione mostrerà un collegamento "Torna ai risultati" in una PDP se l'utente ha aperto la PDP da un modulo che consente un collegamento "Torna ai risultati". Questa funzionalità è disponibile quando gli utenti navigano tra le pagine di categorie, ricerca, elenco e elenchi di suggerimenti. Per supportare questa funzionalità, i moduli Raccolta prodotti e Risultati ricerca hanno una proprietà denominata **Consenti di tornare a risultati in PDP**. Questa proprietà offre la flessibilità di definire i moduli che devono supportare la funzionalità "Torna ai risultati" nella PDP. Ad esempio, quando l'opzione **Mostra di nuovo i risultati** è selezionata in **Tipo di visualizzazione percorso di navigazione in PDP** nel modulo Percorso di navigazione e l'opzione **Consenti di tornare ai risultati in PDP** è selezionata per il modulo Risultati ricerca della pagina di ricerca, verrà visualizzato un collegamento "Torna ai risultati" quando gli utenti passano dalla pagina di ricerca a una pagina PDP.
- **Mostra gerarchia di categorie e torna ai risultati** - Questo valore è una combinazione dei due precedenti. Quando viene selezionato questo valore, il modulo Percorso di navigazione mostrerà sia la gerarchia di categorie completa sia un collegamento "Torna ai risultati" (se configurato) in una PDP.

> [!IMPORTANT]
> Queste impostazioni sono disponibili in Dynamics 365 Commerce versione 10.0.12. Se stai aggiornando da una versione precedente di Dynamics 365 Commerce, devi aggiornare manualmente il file appsettings.json. Per istruzioni sull'aggiornamento del file appsettings.json, vedi [Aggiornamenti dell'SDK e della libreria dei moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="breadcrumb-module-properties"></a>Proprietà del modulo Percorso di navigazione

| Nome proprietà | Valori | Descrizione |
|---------------|--------|-------------|
| Radice | Testo o collegamento| Questa proprietà facoltativa specifica il testo del collegamento e una destinazione del collegamento per la radice sito del percorso di navigazione. Se questa proprietà non è configurata, non verrà definita alcuna radice. |
| Collegamento percorso di navigazione | Collega | Questa proprietà facoltativa specifica i collegamenti per un percorso di navigazione configurato manualmente, se questi collegamenti sono necessari. I collegamenti sono visualizzati nell'ordine in cui sono elencati. |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a>Aggiungere un modulo Percorso di navigazione a una nuova pagina

Per aggiungere un modulo Percorso di navigazione a una pagina PDP e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Impostazioni sito \> Estensioni**, quindi per l'impostazionze **Tipo di visualizzazione percorso di navigazione in PDP** selezionare **Mostra gerarchia di categorie**.
1. Andare a **Modelli** e selezionare il modello PDP.
1. Nello slot **Contenitore** che contiene il modulo Casella acquisti, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Breadcrumb** e quindi **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare a **Pagine** e aprire una PDP che utilizza il modello PDP. Se una PDP non esiste ancora, crearne una.
1. Nello slot **Contenitore** che contiene il modulo Casella acquisti, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Breadcrumb** e quindi **OK**.
1. Nel riquadro delle proprietà dello slot **Percorso di navigazione**, sotto **Radice**, selezionare **Testo collegamento**.
1. Nella finestra di dialogo **Testo collegamento**, immettere **Home** e sotto **Destinazione collegamento**, selezionare **Aggiungi un collegamento**.
1. Nella finestra di dialogo **Aggiungi un collegamento**, selezionare un collegamento per la radice del percorso di navigazione, quindi selezionare **OK**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Modulo menu di spostamento](nav-menu-module.md)

[Modulo di selezione sito](site-selector.md)

[Panoramica della pagina di destinazione di categoria e della pagina dei risultati della ricerca predefinite](category-search-page-overview.md)

[Moduli raccolta prodotti](product-collection-module-overview.md)

[Modulo casella acquisti](add-buy-box.md)

[SDK e aggiornamenti libreria dei moduli](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
