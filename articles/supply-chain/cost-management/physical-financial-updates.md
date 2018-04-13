---
title: Aggiornamenti fisici e finanziari
description: "In questo argomento viene fornita una panoramica dei tipi di transazioni che aumentano e riducono le quantità delle scorte."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e62bdbfb7b88f66ea1f6e4d57b6150c8b0bffb04
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="physical-and-financial-updates"></a>Aggiornamenti fisici e finanziari

[!INCLUDE [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica dei tipi di transazioni che aumentano e riducono le quantità delle scorte. 

In Microsoft Dynamics 365 for Finance and Operations le transazioni di magazzino possono essere aggiornate fisicamente e finanziariamente. Alcuni tipi di transazioni di magazzino e di transazioni finanziarie determinano un incremento delle quantità di scorte, altre una riduzione.

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
Le transazioni che aumentano la quantità vengono registrate al prezzo di costo medio corrente. Finance and Operations calcola un prezzo di costo medio corrente basato sul costo di ciascuna transazione per ogni dimensione inventariale tracciata finanziariamente. Per informazioni sul prezzo di costo medio corrente, vedere [Informazioni sul prezzo di costo medio corrente](running-average-cost-price.md).

## <a name="transactions-that-decrease-quantity"></a>Transazioni che riducono la quantità
In Finance and Operations viene utilizzato il prezzo di costo medio corrente calcolato quando viene registrata una transazione che riduce la quantità, indipendentemente dal modello inventariale associato a quelle scorte, purché la transazione che riduce la quantità non fosse precedentemente contrassegnata su un'altra transazione prima della registrazione. Se le scorte fisiche disponibili diventano negative, in Finance and Operations verrà utilizzato il costo di magazzino definito per l'articoloo nella pagina **Articolo**. **Nota**: se è attivata la funzionalità multisito, il costo sarà invece il costo di magazzino definito per un sito nella pagina **Impostazioni ordine predefinite**.

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




