---
title: Conversione di unità di misura per varianti prodotto
description: In questo argomento viene descritto come configurare conversioni di unità di misura per varianti prodotto. Include un esempio dell'impostazione.
author: johanhoffmann
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: ed28928b0f07833d5906a68f780e3bb5bbe0bfe9
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921219"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Conversione di unità di misura per varianti prodotto

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come configurare conversioni di unità di misura per diverse varianti prodotto.

Anziché creare più dispositivi individuali che devono essere mantenuti, puoi utilizzare le varianti dei prodotti per creare variazioni di un singolo prodotto. Ad esempio, una variante prodotto potrebbe essere una maglietta di una determinata taglia e colore.

In precedenza, le conversioni delle unità potevano essere impostate solo sulla rappresentazione generale del prodotto. Pertanto, tutte le varianti del prodotto avevano le stesse regole di conversione dell'unità. Tuttavia, quando la funzionalità *Conversioni unità di misura per varianti prodotto* è attivata, se le magliette sono vendute in scatole e il numero di magliette che possono essere imballate in una scatola dipende dalle dimensioni delle magliette, ora è possibile impostare conversioni di unità tra le diverse dimensioni delle magliette e le scatole utilizzate per l'imballaggio.

## <a name="turn-on-the-feature-in-your-system"></a>Attiva la funzionalità nel tuo sistema

Se non vedi già questa funzione nel tuo sistema, vai a [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e abilita la funzionalità *Conversioni unità di misura per varianti prodotto*.

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Configurare un prodotto per la conversione di unità per variante

Le varianti prodotto possono essere create solo per i prodotti che sono rappresentazioni generali prodotto. Per ulteriori informazioni, vedere [Creare una rappresentazione generale prodotto](tasks/create-product-master.md). La funzionalità *Conversioni unità di misura per varianti prodotto* non è disponibile per i prodotti impostati per processi di peso variabile.

Per configurare una rappresentazione generale prodotto per supportare la conversione di unità per variante, attieniti alla seguente procedura.

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Rappresentazioni generali prodotto**.
1. Crea o apri una rappresentazione generale prodotto per andare alla sua pagina **Dettagli prodotto**.
1. Imposta l'opzione **Abilita conversioni unità di misura** su *Sì*.
1. Nel riquadro azioni, scheda **Prodotto**, nel gruppo **Imposta**, seleziona **Conversioni unità**.
1. Viene aperta la pagina **Conversioni unità**. Selezionare una delle schede seguenti:

    - **Conversioni in classi**: seleziona questa scheda per convertire le unità appartenenti alla stessa classe di unità di misura.
    - **Conversioni tra classi**: seleziona questa scheda per convertire le unità appartenenti a classi di unità di misura differenti.

1. Seleziona **Nuovo** per aggiungere una nuova conversione unità.
1. Imposta il campo **Crea conversione per** su uno dei seguenti valori:

    - **Prodotto**: se selezioni questo valore puoi configurare una conversione unità per la rappresentazione generale prodotto. Questa conversione di unità verrà utilizzata come fallback per tutte le varianti di prodotto per le quali non è definita alcuna conversione di unità.
    - **Variante prodotto**: se selezioni questo valore puoi configurare una conversione unità per una specifica variante prodotto. Usa il campo **Variante prodotto** per selezionare la variante.

    ![Aggiunta di una nuova conversione unità](media/uom-new-conversion.png "Aggiunta di una nuova conversione unità")

1. Utilizzare gli altri campi forniti per impostare la conversione unità.
1. Seleziona **OK** per salvare la nuova conversione unità.

> [!TIP]
> Puoi aprire la pagina **Conversioni unità** per un prodotto o una variante prodotto da una delle seguenti pagine:
> 
> - Dettagli prodotto
> - Dettagli prodotti rilasciato
> - Varianti prodotti rilasciati

## <a name="example-scenario"></a>Scenario di esempio

In questo scenario una società vende magliette di taglia S, M, L e XL. La maglietta è definita come prodotto e le diverse taglie sono definite come varianti di tale prodotto. Le magliette sono confezionate in scatole. Per la taglia S, M e L ogni scatola può contenere cinque magliette. Tuttavia, per la taglia XL, c'è spazio per solo quattro magliette in ogni scatola.

La società desidera tenere traccia delle differenti varianti nell'unità *Pezzi* ma vende le magliette nell'unità *Scatole*. Per la taglia S, M e L, la conversione tra unità di inventario e unità di vendita è 1 scatola = 5 pezzi. Per la taglia XL, la conversione è 1 scatola = 4 pezzi.

1. Dalla pagina **Dettagli prodotto rilasciato** per il prodotto **Maglietta**, apri la pagina **Conversioni unità**.
1. Nella pagina **Conversioni unità**, configurare la seguente conversione unità per la variante prodotto rilasciata **XL**.

    | Campo                 | Impostazione                 |
    |-----------------------|-------------------------|
    | Crea conversione per | Variante prodotto         |
    | Variante prodotto       | Maglietta : : XL : : |
    | Dall'unità             | Scatole                   |
    | Fattore                | 4                       |
    | All'unità               | Pezzi                  |

1. Tutte le varianti prodotto rilasciato **S**, **M** e **L** hanno la stessa conversione di unità tra l'unità *Scatola* e *Pezzi*, a significare che è possibile definire la conversione di unità seguente per queste varianti prodotto nella rappresentazione generale prodotto.

    | Campo                 | Impostazione |
    |-----------------------|---------|
    | Crea conversione per | Prodotto |
    | Prodotto               | Maglietta |
    | Dall'unità             | Scatole   |
    | Fattore                | 5       |
    | All'unità               | Pezzi  |

## <a name="using-excel-to-update-the-unit-conversions"></a>Utilizzo di Excel per aggiornare le conversioni di unità

Se un prodotto ha molte varianti di prodotto con conversioni di unità diverse, ti consigliamo di esportare le conversioni unità in una cartella di lavoro Microsoft Excel, aggiornarle e quindi pubblicarle nuovamente in Dynamics 365 Supply Chain Management.

Per esportare le conversioni unità in Excel, nella pagina **Conversioni unità**, nel riquadro azioni, seleziona **Apri in Microsoft Office**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Gestire unità di misura](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]