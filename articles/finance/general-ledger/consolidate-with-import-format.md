---
title: Importare un formato per il consolidamento
description: In questo articolo vengono fornite informazioni dettagliate sul formato di importazione utilizzato quando si consolidano i dati finanziari di più persone giuridiche.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 0aee830f8fbfa384c86dc16465b202be36f07b73
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871306"
---
# <a name="import-format-for-consolidation"></a>Importare un formato per il consolidamento

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite informazioni dettagliate sul formato di importazione utilizzato quando si consolidano i dati finanziari di più persone giuridiche. Il formato di importazione deve essere salvato come file di testo (.txt).

## <a name="import-format"></a>Formato di importazione

La tabella seguente elenca il formato di importazione da utilizzare quando si esegue un consolidamento durante un'importazione.

| Tabella dei record | Formattazione | Note |
|--------------|---------|-------|
| 1            | 170150, Avviamento, 4 | <ul><li>La tabella dei record</li><li>L'ID conto principale di origine</li><li>La riga del conto principale</li><li>Tipo di conto principale</li></ul> |
| 2            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>ID conto principale</li><li>Data della transazione</li><li>Il tipo di periodo fiscale (**0** = Apertura, **1** = Operativo e **2** = Chiusura)</li><li>Valuta della transazione</li><li>Debito o credito (**0** = Dare e **1** = Avere)</li><li>Livello di registrazione</li><li>Importi transazione</li><li>Quantità</li><li>Il RecID locale (valore int64 ambiguo e univoco per la transazione)</li></ul> |
| 3            | USMF0000009, 2017/01/01, FY2017, 1, 2017,01,01, 602200, USD, 6053.6.0 | <ul><li>Il numero della voce (numero della transazione dell'intestazione del budget)</li><li>Data predefinita dell'intestazione di budget</li><li>L'ID del modello di budget</li><li>Tipo di budge (**1** - Budget originale, **2** - Trasfreimento, **3** - Revisione, **4** - Impegno di spesa, **5** - Impegno di spesa preliminare, **6** - Budget riportabile in avanti, **7** - Progetto, **8** - Cespiti, **9** - Previsione della domanda, **10** - Previsione dell'offerta, **11** - Ripartizioni, **12** - Budget preliminare.)</li><li>Data della riga</li><li>L'ID conto principale per la riga</li><li>Codice valuta per la riga</li><li>Importo per la riga nella valuta della transazione</li><li>Il valore intero dell'enumerazione per il tipo di budget per la riga (spese o ricavi)</li></ul> |
| 4            | DEMF | RecordCompany è la persona giuridica di origine. |
| 5            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>ID conto principale</li><li>Data transazione</li><li>Tipo di periodo fiscale (0 Apertura, 1 Operativo e 2 Chiusura)</li><li>Valuta transazione</li><li>Debito o credito (0 per Dare e 1 per Avere)</li><li>Livello di registrazione</li><li>Importo transazione</li><li>Quantità</li><li>RecID locale (valore int64 ambiguo e univoco per la transazione)</li></ul>  |
| 6            | BusinessUnit, 1 Reparto, 2 | Gli attributi della dimensione finanziaria definiti nell'ordine del segmento.<p>Puoi usare la pagina **Esporta** per verificare come vengono definiti gli attributi.</p> |
| 7            | 002,1,658 | <ul><li>Il valore di dimensione finanziaria</li><li>La dimensione finanziaria, come l'indice fornito in RecordDimensions</li><li>Un ID record ambiguo e univoco associato all'ID record univoco da RecordTrans o RecordTrans2</li></ul> |
| 8            | 002,1,1 | <ul><li>Valori di dimensione associati alla transazione da RecordBudget</li><li>La dimensione finanziaria, come l'indice fornito in RecordDimensions</li><li>Un ID record di riga ambiguo allineato all'ordine delle righe di transazione nel file</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
