---
title: Aggiornamenti fisici e finanziari
description: In questo argomento viene fornita una panoramica dei tipi di transazioni che aumentano e riducono le quantità delle scorte.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88432b9a5e564f9e81892e0bb379f95ff40d6c9d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842155"
---
# <a name="physical-and-financial-updates"></a>Aggiornamenti fisici e finanziari

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica dei tipi di transazioni che aumentano e riducono le quantità delle scorte. 

In Dynamics 365 Supply Chain Management le transazioni di magazzino possono essere aggiornate fisicamente e finanziariamente. Alcuni tipi di transazioni di magazzino e di transazioni finanziarie determinano un incremento delle quantità di scorte, altre una riduzione.

## <a name="physical-increases"></a>Aumenti fisici
Quando viene registrata una transazione fisica, lo stato del record di transazione è **Ricevuto**. Vengono considerate aumenti fisici le seguenti transazioni:

-   Ricevimento ordini fornitore
-   Reso documento di trasporto di ordine cliente
-   Dichiarazione di un ordine di produzione come finito
-   Per prodotto su una distinta di prelievo dell'ordine di produzione

## <a name="financial-increases"></a>Aumenti finanziari
Quando viene registrata una transazione in entrata finanziaria, lo stato del record di transazione che aumenta la quantità è **Acquistato**. Vengono considerate aumenti finanziari le seguenti transazioni:

-   Fattura fornitore
-   Fatture ordine cliente per un reso
-   Determinazione costi ordine di produzione
-   Giornali di registrazione magazzino di quantità positive, ad esempio movimenti, profitti e perdite, conteggio, distinta base e trasferimento

## <a name="transactions-that-increase-quantity"></a>Transazioni che aumentano la quantità
Le transazioni che aumentano la quantità vengono registrate al prezzo di costo medio corrente. Il prezzo di costo medio corrente calcolato si basa sul costo di ciascuna transazione per ogni dimensione inventariale tracciata finanziariamente. Per informazioni sul prezzo di costo medio corrente, vedere [Informazioni sul prezzo di costo medio corrente](running-average-cost-price.md).

## <a name="transactions-that-decrease-quantity"></a>Transazioni che riducono la quantità
Viene utilizzato il prezzo di costo medio corrente calcolato quando viene registrata una transazione che riduce la quantità, indipendentemente dal modello inventariale associato a quelle scorte, purché la transazione che riduce la quantità non fosse precedentemente contrassegnata su un'altra transazione prima della registrazione. Se le scorte fisiche disponibili diventano negative, verrà utilizzato il costo di magazzino definito per l'articolo nella pagina **Articolo**. 

> [!NOTE]
> Se è attivata la funzionalità multisito, il costo sarà invece il costo di magazzino definito per un sito nella pagina **Impostazioni ordine predefinite**.

## <a name="physical-issues-vs-financial-issues"></a>Uscite fisiche e finanziarie
Quando viene registrata una transazione fisica in uscita, lo stato del record di transazione è **Detratto**. Vengono considerate uscite finanziarie le seguenti transazioni:

-   Giornale di registrazione distinte di prelievo dell'ordine di produzione
-   Documento di trasporto ordine cliente
-   Reso documento di trasporto di ordine fornitore

Quando viene registrata una transazione finanziaria, lo stato del record di transazione è **Venduto**. Vengono considerate uscite finanziarie le seguenti transazioni

-   Fine di un ordine di produzione
-   Fattura ordine cliente
-   Reso fattura fornitore
-   Giornali di registrazione magazzino di quantità negative, ad esempio movimenti, profitti e perdite, conteggio, distinta base e trasferimento

Le transazioni che riducono la quantità vengono registrate al prezzo di costo medio corrente. La procedura di chiusura dell'inventario, pertanto, è necessaria per liquidare le transazioni in uscita a fronte delle transazioni in entrata in base al modello inventariale assegnato a ciascun articolo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]