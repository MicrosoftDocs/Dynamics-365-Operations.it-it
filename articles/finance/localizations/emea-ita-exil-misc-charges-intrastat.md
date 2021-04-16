---
title: Spese varie per chilogrammo in una dichiarazione Intrastat
description: Questo argomento spiega come attivare, configurare e utilizzare la funzionalità per le spese varie per chilogrammo in una dichiarazione Intrastat.
author: ilkond
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: c0ccba4a5a377f6cff2e7324d7840dc056b6013a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814932"
---
# <a name="miscellaneous-charges-per-kilogram-in-an-intrastat-declaration"></a>Spese varie per chilogrammo in una dichiarazione Intrastat

[!include [banner](../includes/banner.md)]

Intrastat è il sistema utilizzato per la raccolta di informazioni e la generazione di statistiche sugli scambi commerciali tra paesi dell'Unione Europea (UE). Per ulteriori informazioni, vedere [Panoramica Intrastat](emea-intrastat.md).

Tra gli altri elementi di segnalazione, una dichiarazione Intrastat contiene informazioni sulle spese varie. Le spese varie sono di solito calcolate come percentuale dell'importo della fattura. Tuttavia, in Italia, vengono spesso calcolati moltiplicando il costo di ciascun chilogrammo e il peso delle merci in chilogrammi.

## <a name="prerequisites"></a>Prerequisiti

- L'indirizzo principale della persona giuridica deve essere in Italia.
- Nell'area di lavoro **Gestione funzionalità** attivare la funzionalità **Spese varie per chilogrammo in una dichiarazione Intrastat**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-miscellaneous-charges-per-kilogram"></a>Impostare le spese varie per chilogrammo

Sulla pagina **Dati master prodotti rilasciati**, sulla Scheda dettaglio **Commercio estero**, nella sezione **Intrastat** nel campo **Spese per chilogrammo**, inserire l'importo delle spese per chilogrammo.

![Campo Spese per chilogrammo](media/emea-ita-exil-misc-charge-kg-pic1.jpg)

> [!NOTE]
> Verificare che il peso del prodotto sia definito in chilogrammi.

## <a name="calculation-of-miscellaneous-charges"></a>Calcolo delle spese varie

Quando le transazioni vengono trasferite a una dichiarazione Intrastat, il valore **Importo spese statistico** viene calcolato utilizzando la seguente formula:

*Importo spese statistico* = *Costo di ogni chilogrammo* × *Peso netto (in chilogrammi)*

Se viene anche inserito un valore **Percentuale spese**, nel calcolo vengono utilizzati entrambi i tipi di spese varie:

*Importo spese statistico* = ( *Importo fattura* × *Percentuale spese*) + ( *Costo di ogni chilogrammo* × *Peso netto \[in chilogrammi\]*)

![Calcolo spese](media/emea-ita-exil-misc-charge-kg-pic2.jpg)

Per ulteriori informazioni, vedere [Trasferire le transazioni a Intrastat](tasks/transfer-transactions-intrastat.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]