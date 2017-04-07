---
title: Aggiornamenti fisici e finanziari
description: "In questo argomento viene fornita una panoramica dei tipi di transazioni che aumentano e riducono le quantità delle scorte."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d68006c756f6b29804cad1d05db9ced2bd33897d
ms.lasthandoff: 03/31/2017


---

# <a name="physical-and-financial-updates"></a>Aggiornamenti fisici e finanziari

In questo argomento viene fornita una panoramica dei tipi di transazioni che aumentano e riducono le quantità delle scorte. 

Le transazioni di magazzino possono essere aggiornate fisicamente e finanziariamente in Microsoft Dynamics 365 per le operazioni. Alcuni tipi di transazioni di magazzino e di transazioni finanziarie determinano un incremento delle quantità di scorte, altre una riduzione.

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
Le transazioni che aumentano la quantità vengono registrate al prezzo di costo medio corrente. Dynamics 365 per le operazioni viene calcolato un prezzo di costo medio corrente basato sul costo di ciascuna transazione per ogni dimensione inventariale tracciata finanziariamente. Per informazioni sul prezzo di costo medio corrente, vedere [Informazioni sul prezzo di costo medio corrente](running-average-cost-price.md).

## <a name="transactions-that-decrease-quantity"></a>Transazioni che riducono la quantità
Dynamics 365 per le operazioni utilizza il prezzo di costo medio corrente calcolato quando una transazione che riduce la quantità viene registrata, indipendentemente dal modello inventariale associato a quelle scorte. purché la transazione che riduce la quantità non fosse precedentemente contrassegnata su un'altra transazione prima della registrazione. Se le scorte fisiche disponibili negative, diventa Dynamics 365 per le operazioni utilizza il costo di magazzino definito per l'articolo ** ** articolo nella pagina. **Nota**: se è attivata la funzionalità multisito, il costo sarà invece il costo di magazzino definito per un sito nella pagina **Impostazioni ordine predefinite**.

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


