---
title: Conversione di unità per varianti prodotto
description: In questo argomento viene descritto come impostare conversioni di unità per varianti prodotto.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: e50be7fa6fa686a90b2dd5c5200c881e4629f019
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204495"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Conversione di unità per varianti prodotto

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come impostare conversioni di unità per varianti prodotto. Include un esempio dell'impostazione.

Questa funzionalità consente alle società di definire differenti conversioni di unità tra le varianti dello stesso prodotto. In questo argomento viene utilizzato l'esempio seguente. Una società vende magliette nelle taglie S, M, L e XL. La maglietta è definita come prodotto e le diverse taglie sono definite come varianti del prodotto. Le magliette sono imballate in scatole e ogni scatola può contenere cinque magliette S, M o L e quattro magliette XL. La società desidera tenere traccia delle differenti varianti di magliette nell'unità **Pezzi** ma vende le magliette nell'unità **Scatole**. La conversione tra l'unità di magazzino e l'unità di vendita è 1 scatola = 5 pezzi, ad eccezione della variante XL, dove la conversione è 1 scatola = 4 pezzi.

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Configurare un prodotto per la conversione di unità per variante

Le varianti prodotto possono essere create solo per prodotti di **Sottotipo di prodotto**: **Rappresentazione generale prodotto**. Per ulteriori informazioni, vedere [Creare una rappresentazione generale prodotto](tasks/create-product-master.md).

La funzionalità non è attivata per i prodotti configurati per i processi a peso variabile. 

Quando viene creata la rappresentazione generale prodotto con varianti prodotto rilasciato, è possibile impostare conversioni di unità per varianti. È possibile trovare la voce di menu per l'apertura della pagina delle conversione di unità nel contesto di un prodotto o di una variante prodotto nelle pagine seguenti.

-   Pagina **Dettagli prodotto**
-   Pagina **Dettagli prodotti rilasciati**
-   Pagina **Varianti prodotti rilasciati**

Quando si apre la pagina **Conversione unità** nel contesto di una rappresentazione generale prodotto o di una variante prodotto rilasciato, è possibile selezionare se si desidera impostare la conversione di unità per il prodotto o per una variante prodotto. A questo proposito, selezionare **Variante prodotto** o **Prodotto** nel campo **Creare conversione per**.

### <a name="product-variant"></a>Variante prodotto

Se si seleziona **Variante prodotto**, è possibile selezionare la variante per la quale si desidera impostare la conversione di unità nel campo **Variante prodotto**.

### <a name="product"></a>Prodotto

Se si seleziona **Prodotto**, è possibile impostare una conversione di unità per la rappresentazione generale prodotto. Questa conversione di unità verrà applicata per tutte le varianti prodotto senza conversione di unità definita.

### <a name="example"></a>Esempio

Una rappresentazione generale prodotto, **Maglietta**, include quattro varianti prodotto rilasciato: S, M, L e XL. Le magliette sono imballate in scatole e ogni scatola può contenere cinque magliette S, M o L e quattro magliette XL.

Innanzitutto, aprire la pagina **Conversione unità** dalla pagina Dettagli prodotto rilasciato per **Maglietta**.

Nella pagina **Conversione unità**, impostare la conversione di unità per la variante prodotto rilasciato XL.

| **Campo**             | **Impostazione**             |
|-----------------------|-------------------------|
| Crea conversione per | Variante prodotto         |
| Variante prodotto       | Maglietta : : XL : : |
| Dall'unità             | Scatole                   |
| Fattore                | 4                       |
| All'unità               | Pezzi                  |

Le varianti prodotto rilasciato S, M e L hanno la stessa conversione di unità tra l'unità Scatola e Pezzi, a significare che è possibile definire la conversione di unità per queste varianti prodotto nella rappresentazione generale prodotto.

| **Campo**             | **Impostazione** |
|-----------------------|-------------|
| Crea conversione per | Prodotto     |
| Prodotto               | Maglietta     |
| Dall'unità             | Scatole       |
| Fattore                | 5           |
| All'unità               | Pezzi      |

### <a name="using-excel-to-update-the-unit-conversions"></a>Utilizzo di Excel per aggiornare le conversioni di unità

Se un prodotto include molte varianti prodotto con differenti conversioni di unità, è consigliabile esportare le conversioni di unità dalla pagina **Conversione unità** in un foglio di calcolo di Excel, aggiornare le conversioni e quindi pubblicarle di nuovo in Supply Chain Mangement.

L'opzione per esportare in Excel e pubblicare di nuovo le modifiche in Supply Chain Mangement viene abilitata mediante la voce di menu **Apri in Microsoft office** nel riquadro azioni della pagina **Conversione unità**.
