---
title: Aggregazioni del riconoscimento dei ricavi
description: In questo argomento viene descritta la funzionalità di aggregazione inclusa nella funzionalità di riconoscimento dei ricavi nella contabilità clienti. Un'aggregazione comprende un articolo padre e più articoli componente.
author: kweekley
ms.date: 01/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 9afc7786de16cb1cada982f43beb956e062777a4
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347784"
---
# <a name="revenue-recognition-bundles"></a>Aggregazioni del riconoscimento dei ricavi

[!include [banner](../includes/banner.md)]

In questo argomento viene descritta la funzionalità di aggregazione inclusa nella funzionalità di riconoscimento dei ricavi nella contabilità clienti. Un'aggregazione comprende un articolo padre e più articoli componente. L'articolo padre viene immesso in un ordine cliente in modo che la registrazione ordine sia più efficiente. Tuttavia, viene esploso negli articoli componente. I documenti interni, come il documento di trasporto, elencano gli articoli componente. I documenti esterni mostrano solo l'articolo padre.

> [!NOTE]
> I canali di Microsoft Dynamics 365 Commerce, come online, POS e servizio clienti, non supportano il riconoscimento dei ricavi (inclusa la funzionalità di aggregazione). Ciò include anche la soluzione Prospect per uno scenario di liquidazione per Dynamics 365 Supply Chain Management e Dynamics 365 Sales. Gli articoli configurati per utilizzare il riconoscimento dei ricavi non devono essere aggiunti agli ordini o alle transazioni creati nei canali di Commerce o nella soluzione Prospect per uno scenario di liquidazione.

Per impostare le aggregazioni è necessario immettere le chiavi di configurazione per il riconoscimento dei ricavi. Tuttavia, è possibile utilizzare le aggregazioni anche se il riconoscimento dei ricavi non è impostato. Analogamente, è possibile utilizzare il riconoscimento dei ricavi se le aggregazioni non sono impostate. Se è impostato il riconoscimento dei ricavi, gli articoli componente determinano il prezzo dei ricavi e la programmazione dei ricavi utilizzata per il riconoscimento o il differimento dei ricavi quando viene fatturato un ordine cliente.

L'impostazione delle aggregazioni utilizza la funzionalità della distinta base (DBA). Per informazioni su come impostare un articolo di aggregazione, vedere [Impostazione del riconoscimento ricavi](revenue-recognition-setup.md). Se l'articolo padre è contrassegnato come aggregazione, viene trattato in modo diverso rispetto ad altri articoli DBA. Ecco un elenco delle differenze:

- Le aggregazioni devono essere esplose tramite la conferma dell'ordine cliente, selezionando **Conferma ordine cliente** nella scheda **Vendi** del riquadro Azioni nella pagina dell'ordine cliente. Gli articoli di aggregazione non devono mai essere esplosi selezionando **Riga DBA** sotto **Esplodi** nel menu **Riga ordine cliente** della Scheda dettaglio **Righe ordine cliente**. In caso contrario, l'articolo verrà considerato come una distinta base e non come un'aggregazione.
- Un ordine cliente che contiene un articolo di aggregazione deve essere confermato prima di creare il documento di trasporto o la fattura.
- Quando un'aggregazione viene esplosa tramite la conferma dell'ordine cliente, l'articolo padre viene annullato e il prezzo unitario e gli sconti vengono allocati agli articoli componente dell'aggregazione.
- La somma degli articoli componente deve sempre essere uguale al prezzo dell'articolo padre. Pertanto, esistono limitazioni sui campi che possono essere aggiornati o modificati per gli articoli componente. Ad esempio, il prezzo unitario non può essere modificato manualmente. Inoltre, non può essere modificato indirettamente facendo entrare in vigore un nuovo accordo sui prezzi. Per evitare un nuovo accordo sui prezzi, le dimensioni inventariali non possono essere modificate sugli articoli componenti.
- Quando viene stampato un documento per l'esterno, come la conferma dell'ordine cliente o la fattura, viene stampato l'articolo padre e non gli articoli componente.

## <a name="bundles-on-sales-orders"></a>Aggregazioni negli ordini cliente

La società dimostrativa USMF include la seguente configurazione di aggregazione. Si noti che tutte le impostazioni per il riconoscimento dei ricavi, come l'impostazione della programmazione dei ricavi, sono state rimosse dagli articoli inclusi in questo scenario.

**Articolo padre:** aggregazione laptop

- **Articolo componente:** quantità di 1 articolo 1000
- **Articolo componente:** quantità di 1 articolo S0021
- **Articolo componente:** quantità di 1 articolo Support

Il *prezzo di vendita base* degli articoli componente è una parte essenziale della configurazione dei componenti. Il prezzo di vendita base è definito nella Scheda dettaglio **Vendi** di un articolo. Viene utilizzato per calcolare il fattore di allocazione quando il prezzo unitario dell'articolo padre viene allocato agli articoli componente. I prezzi di vendita degli accordi commerciali non vengono mai utilizzati per questo scopo.

I seguenti prezzi di vendita base sono definiti per gli articoli componenti:

- **1000:** $1.900,00
- **S0021:** $150,00
- **Support:** $500,00

Viene immesso un ordine cliente per il cliente US-004, Cave Wholesales. L'unica riga immessa è per l'articolo aggregazione laptop. Il prezzo unitario predefinito per la riga padre può essere preso da numerosi punti, come l'accordo commerciale o il prezzo di vendita di base. In questo esempio, $2.300 è stato inserito manualmente come prezzo unitario.

[![Articolo aggregazione laptop in un ordine cliente.](./media/bundle-01.png)](./media/bundle-01.png)

Dal momento che l'ordine cliente contiene un'aggregazione, deve essere confermato. La finestra di dialogo di conferma mostra i componenti dell'aggregazione.

[![Finestra di dialogo Conferma ordine cliente che mostra gli articoli componente.](./media/bundle-02.png)](./media/bundle-02.png)

Tuttavia, il report di conferma stampato mostrerà solo l'articolo padre dell'aggregazione perché è il documento per l'esterno, per il cliente.

[![Report di conferma che mostra solo l'articolo padre.](./media/bundle-03.png)](./media/bundle-03.png)

Dopo la conferma dell'ordine cliente, l'articolo padre viene ancora visualizzato nell'ordine cliente, ma il suo stato è stato modificato in **Annullato**. Inoltre, l'importo netto viene registrato nel campo **Importo netto aggregazione**. Questo importo è necessario per stampare la fattura, poiché la fattura mostra l'articolo padre e non gli articoli componente.

La somma degli articoli componente deve essere uguale al valore **Importo netto aggregazione** dell'articolo padre perché tale valore è l'importo presentato al cliente sulla fattura stampata. Per garantire che la fattura corrisponda agli importi registrati nella contabilità generale, le modifiche agli articoli componente sono limitate. Ad esempio, il sito e il magazzino non possono essere modificati, perché le modifiche potrebbero attivare una variazione di prezzo, in base a un accordo commerciale.

Il prezzo unitario della riga dell'articolo padre viene allocato ai componenti nel modo seguente:

**Prezzi di vendita base totali dei componenti:** $1.900 + $500 + $150 = $2.550

- **Componente 1:** $2.300 × (1.900 ÷ 2.550) = $1.713,73
- **Componente 2:** $2.300 × (500 ÷ 2.550) = $450,98
- **Componente 3:** $2.300 × (150 ÷ 2.550) = $135,29

La somma dei componenti deve essere uguale a $2.300 e lo è ($1.713,73 + $450,98 + $135,29 = $2.300).

Se sono necessarie modifiche per tutti gli articoli componente, l'articolo padre può essere rimosso. In questo caso, vengono rimossi anche gli articoli componente. L'articolo padre può quindi essere aggiunto di nuovo e le modifiche richieste possono essere completate prima della conferma dell'ordine cliente.

[![Articolo di aggregazione che include modifiche agli articoli componente.](./media/bundle-04.png)](./media/bundle-04.png)

Quando l'ordine cliente viene ritirato e imballato, i documenti includono solo i componenti dell'aggregazione. Il documento di trasporto e la fattura devono includere un'aggregazione completa. In caso contrario, non possono essere registrati. Ad esempio, la finestra di dialogo mostra tre articoli componente. Se si tenta di eliminarne uno, viene visualizzato un messaggio di errore che indica che tutti i prodotti dell'aggregazione devono essere spediti prima di poter essere fatturati.

Un'aggregazione deve essere spedita e fatturata come aggregazione completa. Ad esempio, se si modifica la quantità dell'articolo 1000 in 4, ma si lascia la quantità degli altri articoli componente su 5, il documento di trasporto e la fattura non possono essere registrati.

Un importo parziale può essere spedito e fatturato solo se la quantità viene ridotta per tutti i componenti dell'aggregazione. Ad esempio, in un ordine cliente viene immessa una quantità di 5 articoli dell'aggregazione laptop. Dopo la conferma dell'ordine cliente, i tre articoli componente vengono visualizzati nell'ordine cliente e la quantità di ciascuno è 5. Per impostazione predefinita, durante la spedizione e la fatturazione, la quantità sarà impostata su 5 per ogni componente. Tuttavia, è possibile regolare la quantità fino a 3 per tutti e tre gli articoli componente. In questo caso, verranno spediti e fatturati tre aggregazioni complete. I restanti due articoli di aggregazione (una quantità di 2 di ciascuno dei tre articoli componente) possono essere spediti e fatturati in un secondo momento.

L'ultimo passaggio consiste nella fatturazione dell'ordine cliente. Durante la fatturazione, la finestra di dialogo della fattura mostrerà gli articoli componente.

[![Finestra di dialogo Fattura che mostra gli articoli componente.](./media/bundle-06.png)](./media/bundle-06.png)

La fattura stampata mostra solo l'articolo padre.
 
[![Fattura stampata che mostra solo l'articolo padre.](./media/bundle-07.png)](./media/bundle-07.png)

Il giornale di registrazione fatture creato dopo la registrazione non include l'articolo padre dell'aggregazione perché l'articolo ha lo stato di **Annullato**.

[![Giornale di registrazione fatture che non include l'articolo padre.](./media/bundle-08.png)](./media/bundle-08.png)

È importante che il giornale di registrazione fatture non includa l'articolo padre dell'aggregazione perché tutti i processi eseguiti dopo la registrazione della fattura si basano su quel giornale di registrazione fatture. Ad esempio, se si crea una nota di credito nella scheda **Vendi** del riquadro Azioni, la nota di credito creata include gli articoli componente ma non l'articolo padre.

[![Nota di credito che mostra gli articoli componente ma non l'articolo padre.](./media/bundle-09.png)](./media/bundle-09.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]