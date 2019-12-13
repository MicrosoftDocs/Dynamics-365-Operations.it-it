---
title: Moduli Raccolta prodotti
description: Questo argomento fornisce una panoramica dei moduli Raccolta prodotti in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 44f78b55b8e67b7358be75aa63c40a0147507e26
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785469"
---
# <a name="product-collection-modules"></a>Moduli Raccolta prodotti  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Questo argomento fornisce una panoramica dei moduli Raccolta prodotti in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

L'individuazione di prodotti è uno strumento principale che i rivenditori utilizzano per interagire con i propri clienti in un sito Web di e-Commerce. I moduli Raccolta prodotti consentono ai rivenditori di creare esperienze di acquisto convincenti fornendo un'interfaccia visiva intuitiva che può essere utilizzata per generare rapidamente raccolte di prodotti.

I moduli Raccolta prodotti rappresentano servizi e prodotti fisici nel sito Web. Un modulo Raccolta prodotti è in genere collegato a una pagina dettagli dove i clienti possono acquistare un prodotto o un servizio o ottenere ulteriori informazioni sullo stesso. 

Le origini delle raccolte di prodotti possono essere elenchi di tre tipi:

- Elenchi editoriali di prodotti che sono definiti manualmente in Dynamics 365 Retail come prodotti correlati per un prodotto o elenchi di prodotti
- Elenchi algoritmici, ad esempio elenchi di prodotti nuovi, più venduti o di tendenza
- Elenchi di suggerimenti basati sul machine learning

Nella figura seguente sono illustrati i diversi tipi di raccolte di prodotti utilizzate in un sito di e-Commerce.

![Esempio dei differenti tipi di raccolte di prodotti in un sito di e-Commerce](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Utilizzare sempre moduli Raccolta prodotti per presentare un gruppo di prodotti di tipo o tema simile.

## <a name="product-collection-modules-and-types"></a>Tipi di moduli Raccolta prodotti

Nella tabella seguente vengono descritti i vari tipi di moduli Raccolta prodotti in Dynamics 365 Commerce.

| Modulo Raccolta prodotti  | Tipo | Descrizione |
|----------------------------|------|-------------|
| Sfoglia categoria            | Editoriale | Questo tipo di modulo Raccolta prodotti utilizza la gerarchia di categorie di navigazione che il rivenditore ha creato per un canale di vendita al dettaglio allo scopo di presentare un flusso di esplorazione per i prodotti offerti in una specifica categoria del sito. |
| Risultati della ricerca             | Query di ricerca | Questo tipo di modulo Raccolta prodotti presenta un elenco di prodotti che meglio corrispondono alla query di ricerca immessa dal cliente. |
| Prodotti correlati           | Editoriale | Questo tipo di modulo Raccolta prodotti presenta un elenco di prodotti che un responsabile merchandising ha configurato come prodotti correlati in Retail, per il tipo di relazione selezionato dall'autore. |
| Elenchi di prodotti curati      | Editoriale | Questo tipo di modulo Raccolta prodotti presenta elenchi personalizzati che i merchandiser e gli editori hanno creato in Retail. |
| Novità                        | Algoritmico | Questo tipo di modulo Raccolta prodotti presenta un elenco dei prodotti più nuovi assortiti in canali e cataloghi. |
| Più venduti               | Algoritmico | Questo tipo di modulo Raccolta prodotti presenta un elenco dei prodotti con il più alto numero di vendite. |
| Di tendenza                   | Algoritmico | Questo tipo di modulo Raccolta prodotti presenta un elenco dei prodotti di maggior successo in un determinato periodo. |
| Spesso acquistati insieme | Intelligenza artificiale/machine learning | Questo tipo di modulo Raccolta prodotti utilizza il machine learning per analizzare i criteri di acquisto dei consumatori e suggerisce articoli correlati che vengono spesso acquistati insieme a un determinato prodotto. |
| Alle persone piace anche           | Intelligenza artificiale/machine learning | Questo tipo di modulo Raccolta prodotti utilizza il machine learning per analizzare i criteri di acquisto dei consumatori e suggerisce articoli correlati a un determinato prodotto. |

## <a name="add-a-product-collection-module-to-a-category-page"></a>Aggiungere un modulo Raccolta prodotti a una pagina categoria

Per aggiungere un modulo Raccolta prodotti a una pagina categoria, procedere come segue.

1. In Dynamics 365 Commerce, accedere al sito e creare una pagina che utilizza lo stesso modello della pagina categoria predefinita.
1. Nella struttura delle pagine, selezionare lo slot **Piè di pagina secondario**, selezionare il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare **Contenitore** e quindi **OK**.
1. Nel modulo contenitore, selezionare il pulsante con i puntini di sospensione e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare **Raccolta prodotti** e quindi **OK**.
1. Configurare le impostazioni selezionando un'origine dati appropriata e gli input per la raccolta di prodotti.
1. Nel riquadro delle proprietà del modulo Raccolta prodotti, selezionare **Aggiungi un elenco di prodotti**.
1. Nella finestra di dialogo **Seleziona configurazione elenco di prodotti**, selezionare il tipo di elenco, immettere il numero di articoli e selezionare qualsiasi altra opzione disponibile per il tipo di elenco. Per ulteriori informazioni sui tipi di elenchi, vedere la tabella seguente. 
1. Selezionare **OK**.
1. Salvare la pagina e archiviarla.

Nella seguente tabella sono indicati i tipi di elenco selezionabili nella finestra di dialogo **Seleziona configurazione elenco di prodotti**.
   
| Tipo                       | Descrizione | Uso generale | Contesto che può essere derivato dal contesto della pagina | Contesto con cui l'autore può sostituire il contesto della pagina |
|----------------------------|-------------|------------------|-------------------------------------|-----------------------------------------------|
| Prodotti per categoria       | Un elenco di prodotti appartenenti a una specifica categoria. Questa categoria viene determinata dal contesto della pagina o dal contesto fornito dell'autore. | Migliorare la pagina categoria, l'home page, le pagine carrello e checkout e le pagine prodotto | Categoria | Categoria determinata dall'autore |
| Prodotti correlati           | Un elenco di prodotti che un responsabile merchandising ha configurato come prodotti correlati in Retail per il tipo di relazione. | Pagine prodotto, pagine checkout e carrello, pagina elenco preferenze e pagina account cliente | Prodotto, Tipo di relazione (obbligatorio)  | Prodotto, Tipo di relazione |
| Curato                    | Un elenco personalizzato che i merchandiser e gli editori hanno creato in Retail. | Migliorare la pagina categoria, l'home page, le pagine carrello e checkout e le pagine prodotto | Non applicabile | Selezione elenco |
| Algoritmico                | <ul><li>**Novità** - Un elenco dei prodotti più recenti che sono stati assortiti in canali e cataloghi.</li><li>**Più venduti** - Un elenco di prodotti classificati in base al più alto numero di vendite.</li><li>**Di tendenza** - Un elenco dei prodotti di maggior successo in un determinato periodo.</li></ul> | Home page, miglioramento della pagina categoria e pagine checkout e carrello | Categoria | Categoria determinata dall'autore |
| Spesso acquistati insieme | Un elenco che utilizza il machine learning per analizzare i criteri di acquisto dei consumatori e suggerisce articoli correlati che vengono acquistati spesso insieme a un determinato prodotto. | Pagine prodotto e pagine checkout e carrello | Prodotto, carrello | Includi carrello |
| Alle persone piace anche           | Un elenco che utilizza il machine learning per analizzare i criteri di acquisto dei consumatori e suggerisce articoli correlati a un determinato prodotto. | Pagine prodotto e pagine checkout e carrello | Prodotto, carrello | Non applicabile |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo Sequenza](add-carousel.md)

[Modulo Blocco ricco di contenuti](add-content-rich-block.md)

[Modulo Posizionamento contenuti](add-content-placement-modules.md)

[Modulo contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

