---
title: Importare un formato per il consolidamento
description: In questo argomento vengono fornite informazioni dettagliate sul formato di importazione utilizzato quando si consolidano i dati finanziari di più persone giuridiche.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: e3124ac0e161e003986d7e167e292cbb374e1bfa
ms.sourcegitcommit: 2cd82983357b32f70f4e4a0c15d4d1f69e08bd54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085452"
---
# <a name="import-format-for-consolidation"></a>Importare un formato per il consolidamento

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni dettagliate sul formato di importazione utilizzato quando si consolidano i dati finanziari di più persone giuridiche. Il formato di importazione deve essere salvato come file di testo (.txt).

## <a name="import-format"></a>Formato di importazione

La tabella seguente elenca il formato di importazione da utilizzare quando si esegue un consolidamento durante un'importazione.

| Tabella dei record | Formattazione | Note |
|--------------|---------|-------|
| 1            | 170150, Avviamento, 4 | <ul><li>La tabella dei record</li><li>L'ID conto principale di origine</li><li>La riga del conto principale</li><li>Tipo di conto principale</li></ul> |
| 2            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>ID conto principale</li><li>Data della transazione</li><li>Il tipo di periodo fiscale (**0** = Apertura, **1** = Operativo e **2** = Chiusura)</li><li>Valuta della transazione</li><li>Debito o credito (**0** = Dare e **1** = Avere)</li><li>Livello di registrazione</li><li>Importi transazione</li><li>Quantità</li><li>Il RecID locale (valore int64 ambiguo e univoco per la transazione)</li></ul> |
| 3            | USMF0000009, 2017/01/01, FY2017, 1, 2017,01,01, 602200, USD, 6053.6.0 | <ul><li>Il numero della voce (numero della transazione dell'intestazione del budget)</li><li>Data predefinita dell'intestazione di budget</li><li>L'ID del modello di budget</li><li>Il valore intero dell'enumerazione per il tipo di transazione (vuoto, budget originale e così via)</li><li>Data della riga</li><li>L'ID conto principale per la riga</li><li>Codice valuta per la riga</li><li>Importo per la riga nella valuta della transazione</li><li>Il valore intero dell'enumerazione per il tipo di budget per la riga (spese o ricavi)</li></ul> |
| 4            | DEMF | RecordCompany è la persona giuridica di origine. |
| 5            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>ID conto principale</li><li>Data transazione</li><li>Tipo di periodo fiscale (0 Apertura, 1 Operativo e 2 Chiusura)</li><li>Valuta transazione</li><li>Debito o credito (0 per Dare e 1 per Avere)</li><li>Livello di registrazione</li><li>Importo transazione</li><li>Quantità</li><li>RecID locale (valore int64 ambiguo e univoco per la transazione)</li></ul>  |
| 6            | BusinessUnit, 1 Reparto, 2 | Gli attributi della dimensione finanziaria definiti nell'ordine del segmento.<p>Puoi usare la pagina **Esporta** per verificare come vengono definiti gli attributi.</p> |
| 7            | 002,1,658 | <ul><li>Il valore di dimensione finanziaria</li><li>La dimensione finanziaria, come l'indice fornito in RecordDimensions</li><li>Un ID record ambiguo e univoco associato all'ID record univoco da RecordTrans o RecordTrans2</li></ul> |
| 8            | 002,1,1 | <ul><li>Valori di dimensione associati alla transazione da RecordBudget</li><li>La dimensione finanziaria, come l'indice fornito in RecordDimensions</li><li>Un ID record di riga ambiguo allineato all'ordine delle righe di transazione nel file</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
