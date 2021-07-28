---
title: Moduli Raccolta prodotti
description: Questo argomento fornisce una panoramica dei moduli Raccolta prodotti in Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 206f0096f481fc37d05a8258535c016e2834e732
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352206"
---
# <a name="product-collection-modules"></a>Moduli raccolta prodotti

[!include [banner](includes/banner.md)]

Questo argomento fornisce una panoramica dei moduli Raccolta prodotti in Microsoft Dynamics 365 Commerce.

L'individuazione di prodotti è uno strumento principale che i rivenditori utilizzano per interagire con i propri clienti in un sito Web di e-Commerce. I moduli Raccolta prodotti consentono ai rivenditori di creare esperienze di acquisto convincenti fornendo un'interfaccia visiva intuitiva che può essere utilizzata per generare rapidamente raccolte di prodotti.

I moduli Raccolta prodotti rappresentano servizi e prodotti fisici nel sito Web. Un modulo Raccolta prodotti è in genere collegato a una pagina dettagli dove i clienti possono acquistare un prodotto o un servizio o ottenere ulteriori informazioni sullo stesso. 

Le origini delle raccolte di prodotti possono essere elenchi dei seguenti tre tipi:

- Elenchi editoriali di prodotti che sono definiti manualmente in Dynamics 365 Commerce come prodotti correlati per un prodotto o elenchi di prodotti
- Elenchi algoritmici, ad esempio elenchi di prodotti nuovi, più venduti o di tendenza
- Elenchi di suggerimenti basati sul machine learning
- Elenchi di personalizzazione che supportano risultati personalizzati per un cliente. I clienti devono aver effettuato l'accesso al sito di e-Commerce per visualizzare risultati personalizzati. Gli utenti guest non visualizzano i risultati personalizzati. I clienti possono rifiutare esplicitamente la personalizzazione dalla [pagina di gestione account](account-management.md).

Nella figura seguente sono illustrati i diversi tipi di raccolte di prodotti utilizzate in un sito di e-Commerce.

![Esempio dei differenti tipi di raccolte di prodotti in un sito di e-Commerce.](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Utilizzare sempre moduli Raccolta prodotti per presentare un gruppo di prodotti di tipo simile.

## <a name="product-collection-modules-and-types"></a>Tipi di moduli Raccolta prodotti

Nella tabella seguente vengono descritti i vari tipi di moduli Raccolta prodotti in Dynamics 365 Commerce.

| Modulo Raccolta prodotti  | Tipo | Descrizione |
|----------------------------|------|-------------|
| Categoria                   | Categoria | Questo modulo mostra un elenco di prodotti in una categoria, come definito dalla gerarchia di categorie di navigazione creata dal rivenditore per un canale. |
| Prodotti correlati           | Editoriale | Questo presenta un elenco di prodotti che un responsabile merchandising ha configurato come prodotti correlati in Commerce, per il tipo di relazione selezionato dall'autore. |
| Risultati della ricerca             | Query di ricerca | Questo tipo di modulo Raccolta prodotti presenta un elenco di prodotti che meglio corrispondono alla query di ricerca immessa dal cliente. |
| Elenchi di prodotti curati      | Editoriale | Questo modulo mostra elenchi personalizzati che i merchandiser e gli editori hanno creato in Commerce. |
| Nuove                        | Algoritmico | Questo modulo mostra un elenco dei prodotti più recenti che sono stati assortiti in canali e cataloghi. Questo elenco può mostrare risultati personalizzati per un utente che ha effettuato l'accesso se l'autore del sito sceglie tale opzione. |
| Più venduti               | Algoritmico | Questo modulo mostra un elenco di prodotti classificati in base al più alto numero di vendite. Questo elenco può mostrare risultati personalizzati per un utente che ha effettuato l'accesso se l'autore del sito sceglie tale opzione. |
| Di tendenza                   | Algoritmico | Questo modulo mostra un elenco dei prodotti di maggior successo in un determinato periodo. Questo elenco può mostrare risultati personalizzati per un utente che ha effettuato l'accesso se l'autore del sito sceglie tale opzione. |
| Spesso acquistati insieme | Intelligenza artificiale/machine learning | Questo modulo utilizza l'apprendimento automatico per analizzare i criteri di acquisto dei consumatori e suggerisce articoli correlati che vengono acquistati spesso insieme a un determinato prodotto. Questo elenco può mostrare risultati personalizzati per un utente che ha effettuato l'accesso se l'autore del sito sceglie tale opzione. |
| Alle persone piace anche           | Intelligenza artificiale/machine learning | Questo modulo utilizza l'apprendimento automatico per analizzare i criteri di acquisto dei consumatori e suggerisce articoli correlati a un determinato prodotto. Questo elenco può mostrare risultati personalizzati per un utente che ha effettuato l'accesso se l'autore del sito sceglie tale opzione. |
| Selezioni personalizzate              | Intelligenza artificiale/machine learning | Questo modulo utilizza l'apprendimento automatico per analizzare i modelli di acquisto dell'utente che ha effettuato l'accesso e fornire consigli personalizzati basati su tali modelli di acquisto. Per un utente guest, questo elenco verrà compresso. |

## <a name="supported-modules"></a>Moduli supportati 

Il modulo di raccolta del prodotto supporta il [modulo di visualizzazione rapida](quick-view-module.md), che consente agli utenti di visualizzare le informazioni sul prodotto e aggiungere articoli al carrello da una pagina di raccolta del prodotto.

## <a name="add-a-product-collection-module-to-a-category-page"></a>Aggiungere un modulo Raccolta prodotti a una pagina categoria

Per aggiungere un modulo Raccolta prodotti a una pagina categoria, procedere come segue.

1. Andare a **Pagine** e quindi selezionare **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Scegli un modello**, seleziona lo stesso modello utilizzato dalla pagina della categoria predefinita. In **Nome pagina**, immetti un nome appropriato quindi seleziona **OK**.
1. Nello slot **Piè di pagina secondario** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, seleziona il modulo **Raccolta prodotti** e quindi **OK**.  
1. Nel riquadro delle proprietà del modulo Raccolta prodotti, selezionare **Aggiungi un elenco di prodotti**.
1. Nella finestra di dialogo **Seleziona configurazione elenco di prodotti**, seleziona il tipo di elenco, l'origine dell'elenco quindi immetti il numero di articoli. Configura eventuali altre opzioni disponibili per il tipo di elenco. Per ulteriori informazioni sui tipi di elenchi, vedere la tabella seguente. 
1. Selezionare **OK**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

Nella seguente tabella sono indicati i tipi di elenco selezionabili nella finestra di dialogo **Seleziona configurazione elenco di prodotti**.

| Tipo                       | Descrizione | Uso | Contesto della pagina | Contesto specifico | Personalizzazione |
|----------------------------|-------------|-------|--------------|------------------|-----------------|
| Prodotti per categoria       | Un elenco di prodotti appartenenti a una specifica categoria. Questa categoria viene determinata dal contesto della pagina o dal contesto fornito dell'autore. | Questo tipo di elenco può essere utilizzato su qualsiasi pagina (ad esempio, una home page, una pagina di categoria, una pagina di marketing o una pagina dei dettagli del prodotto \[PDP\]) per promuovere una specifica categoria di prodotti. | Categoria dal contesto della pagina, ove disponibile (ad esempio, una pagina di categoria) | L'autore può fornire una categoria specifica come contesto per l'elenco. | Non applicabile |
| Prodotti correlati           | Un elenco di prodotti che un responsabile merchandising ha configurato come prodotti correlati in Commerce per il tipo di relazione. | Questo tipo di elenco viene utilizzato principalmente sui PDP, ma può essere utilizzato su qualsiasi pagina se viene fornito un prodotto principale. | Prodotto dalla pagina, tipo di relazione (obbligatorio) | Il prodotto può essere selezionato nel selettore e viene utilizzato il tipo di relazione. | Non applicabile |
| Curato                    | Un elenco personalizzato che i merchandiser e gli editori hanno creato in Commerce. | Migliorare la pagina categoria, l'home page, le pagine carrello e checkout e le pagine prodotto | Non applicabile | Non applicabile | Non applicabile |
| Algoritmico                | <ul><li>**Novità** - Un elenco dei prodotti più recenti che sono stati assortiti in canali e cataloghi.</li><li>**Più venduti** - Un elenco di prodotti classificati in base al più alto numero di vendite.</li><li>**Di tendenza** - Un elenco dei prodotti di maggior successo in un determinato periodo.</li></ul> | Home page, miglioramento della pagina categoria e pagine checkout e carrello | Categoria dal contesto della pagina (ad esempio, una pagina di categoria) | La categoria determinata dall'autore del sito | Supportata |
| Spesso acquistati insieme | Un elenco che utilizza il machine learning per analizzare i criteri di acquisto dei consumatori e suggerisce articoli correlati che vengono acquistati spesso insieme a un determinato prodotto. | Questo tipo di elenco è applicabile solo alla pagina del carrello. | Carrello | Non applicabile | Supportata |
| Alle persone piace anche           | Un elenco che utilizza il machine learning per analizzare i criteri di acquisto dei consumatori e suggerisce articoli correlati a un determinato prodotto. | Questo tipo di elenco viene utilizzato sui PDP per mostrare i prodotti acquistati da altri clienti. | Contesto del prodotto dalla pagina | Il prodotto fornito dall'autore del sito | Supportata |
| Selezioni personalizzate              | Un elenco che utilizza l'apprendimento automatico per determinare le preferenze del cliente. | Questo tipo di elenco può essere utilizzato su qualsiasi pagina. | Non applicabile| Non applicabile | Supportata | 

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo sequenza](add-carousel.md)

[Modulo blocco contenuto formattato](add-content-rich-block.md)

[Modulo contenitore](add-container-module.md)

[Modulo casella acquisti](add-buy-box.md)

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Modulo visualizzazione rapida](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
