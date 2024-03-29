---
title: Spese varie per chilogrammo in una dichiarazione Intrastat
description: Questo articolo spiega come attivare, configurare e utilizzare la funzionalità per le spese varie per chilogrammo in una dichiarazione Intrastat.
author: mrolecki
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: mrolecki
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.search.form: ''
ms.openlocfilehash: 1954eebbae7f49e9a55149b5d185a60d9c105ed9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287002"
---
# <a name="miscellaneous-charges-per-kilogram-in-an-intrastat-declaration"></a>Spese varie per chilogrammo in una dichiarazione Intrastat

[!include [banner](../includes/banner.md)]

Intrastat è il sistema utilizzato per la raccolta di informazioni e la generazione di statistiche sugli scambi commerciali tra paesi dell'Unione Europea (UE). Per ulteriori informazioni, vedere [Panoramica Intrastat](emea-intrastat.md).

Tra gli altri elementi di segnalazione, una dichiarazione Intrastat contiene informazioni sulle spese varie. Le spese varie sono di solito calcolate come percentuale dell'importo della fattura. Tuttavia, in Italia, vengono spesso calcolati moltiplicando il costo di ciascun chilogrammo e il peso delle merci in chilogrammi.

## <a name="prerequisites"></a>Prerequisiti

- L'indirizzo principale della persona giuridica deve essere in Italia.
- Nell'area di lavoro **Gestione funzionalità** attivare la funzionalità **Spese varie per chilogrammo in una dichiarazione Intrastat**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-miscellaneous-charges-per-kilogram"></a>Impostare le spese varie per chilogrammo

Sulla pagina **Dati master prodotti rilasciati**, sulla Scheda dettaglio **Commercio estero**, nella sezione **Intrastat** nel campo **Spese per chilogrammo**, inserire l'importo delle spese per chilogrammo.

![Campo Spese per chilogrammo.](media/emea-ita-exil-misc-charge-kg-pic1.jpg)

> [!NOTE]
> Verificare che il peso del prodotto sia definito in chilogrammi.

## <a name="calculation-of-miscellaneous-charges"></a>Calcolo delle spese varie

Quando le transazioni vengono trasferite a una dichiarazione Intrastat, il valore **Importo spese statistico** viene calcolato utilizzando la seguente formula:

*Importo spese statistico* = *Costo di ogni chilogrammo* × *Peso netto (in chilogrammi)*

Se viene anche inserito un valore **Percentuale spese**, nel calcolo vengono utilizzati entrambi i tipi di spese varie:

*Importo spese statistico* = ( *Importo fattura* × *Percentuale spese*) + ( *Costo di ogni chilogrammo* × *Peso netto \[in chilogrammi\]*)

![Calcolo spese.](media/emea-ita-exil-misc-charge-kg-pic2.jpg)

Per ulteriori informazioni, vedere [Trasferire le transazioni a Intrastat](tasks/transfer-transactions-intrastat.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
