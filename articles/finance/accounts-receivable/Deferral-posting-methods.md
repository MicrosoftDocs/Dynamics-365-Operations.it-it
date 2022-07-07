---
title: Metodi di registrazione differimento
description: In questo articolo vengono descritte le differenze tra i metodi di registrazione differimento per differimenti di ricavi e spese nella Fatturazione abbonamento.
author: JodiChristiansen
ms.date: 6/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: c66ed1c38251140dd798c39797873ceb5f7121a4
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9019097"
---
# <a name="deferral-posting-methods"></a>Metodi di registrazione differimento

In questo articolo vengono descritte le differenze tra i metodi di registrazione differimento per differimenti di ricavi e spese nella Fatturazione abbonamento.

Sulla pagina **Parametri di differimento di ricavi e spese**, le opzioni per i metodi di registrazione differimento sono **Stato patrimoniale** e **Profitti e perdite**. L'esempio in questo articolo aiuterà a spiegare le differenze tra i due metodi e i motivi per cui potresti utilizzare un metodo o l'altro.

Il metodo **Stato patrimoniale** utilizza solo due conti. Pertanto, è necessaria una minore configurazione. Il metodo **Profitti e perdite** ha due conti aggiuntivi, **Riconoscimento iniziale** e **Contropartita di riconoscimento**, per ricavi, sconti e costi, a seconda del tipo di transazione. Questi conti sono impostati sulla pagina **Valori predefiniti differimento** (**Fatturazione abbonamento \> Differimenti ricavi e spese \> Impostazione**). Sebbene l'esempio sia incentrato sui ricavi differiti, lo stesso concetto può essere applicato agli sconti differiti e ai costi differiti.

## <a name="example"></a>Esempio

La fattura di vendita 1 ha un totale di 3.000 USD e ha ricavi differiti. Le tabelle seguenti mostrano le distribuzioni al momento della registrazione di questa fattura di vendita.

**Metodo stato patrimoniale**

| Tipo | Conto | Dare | Credito|
|---|---|---|---|
| Dare | Contabilità clienti | 3,000.00 | |
| Credito | Ricavi differiti | | 3,000.00 |

**Metodo profitti e perdite**

| Tipo | Conto | Dare | Credito |
|---|---|---|---|
| Dare | Contabilità clienti | 3,000.00 | |
| Dare | Contropartita riconoscimento ricavi | 3,000.00 | |
| Credito | Ricavi differiti | | 3,000.00 |
| Credito | Riconoscimento ricavi iniziale | | 3,000.00 |

La fattura di vendita 2 ha un totale di 2.000 USD e non ha ricavi differiti.

| Tipo | Conto | Importo |
|---|---|---|
| Dare | Contabilità clienti | 3,000.00 |
| Credito | Ricavi | 3,000.00 |

**Totali del metodo stato patrimoniale per la fattura di vendita 1 e 2 combinate**

| Conto | Dare | Credito |
|---|---|---|
| Contabilità clienti | 5,000.00 | |
| Ricavi | | 2,000.00 |
| Ricavi differiti | | 3,000.00 |

Quando il metodo **stato patrimoniale** viene utilizzato non è così facile vedere i ricavi lordi per un periodo. Una parte delle entrate viene registrata nel conto **ricavi differiti**. Tieni presente che, poiché i ricavi vengono rilevati in ogni periodo, ci sono più debiti e crediti nel conto **ricavi differiti**. I ricavi lordi per un determinato periodo saranno combinati con le entrate/uscite del riconoscimento ricavi.

**Totali del metodo profitti e perdite per la fattura di vendita 1 e 2 combinate**

| Conto | Dare | Credito |
|---|---|---|
| Contabilità clienti | 5,000.00 | |
| Ricavi | | 5,000.00 |
| Contropartita ricavi | 3,000.00 | |
| Ricavi differiti | | 3,000.00 |

Tutti i ricavi vanno nel conto **Ricavi** profitti e perdite. Quindi il ricavo differito viene spostato dal rendiconto profitti e perdite allo stato patrimoniale. Puoi facilmente vedere le entrate lorde, perché tutto è registrato sul conto **Ricavi**. Tuttavia, parte di tali entrate lorde viene differita. Pertanto, è stata spostata nel conto **Ricavi differiti** e riconosciuto successivamente.

Nel metodo **Profitti e perdite** puoi guardare il conto **Ricavi** e il conto **Contropartita ricavi** per vedere i ricavi lordi di 5.000 USD e i ricavi netti (al netto dei differimenti) di 2.000 USD. Sebbene il metodo **Profitti e perdite** può semplificare la dichiarazione ci sono più conti da configurare.
