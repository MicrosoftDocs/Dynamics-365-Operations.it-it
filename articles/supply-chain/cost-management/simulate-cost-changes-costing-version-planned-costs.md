---
title: Simulare le variazioni di costo mediante una versione di determinazione costi per i costi pianificati
description: In questo articolo viene illustrato come simulare gli effetti prodotti dalle variazioni di costo sui costi calcolati di un articolo prodotto con una versione di determinazione costi separata per costi pianificati.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 78183
ms.assetid: 1e41953f-cdb9-4598-b776-46e49383a773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f6e1d52f48a6b7675fb16ccc5ecd9ba7cd25ac8b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431230"
---
# <a name="simulate-cost-changes-by-using-a-costing-version-for-planned-costs"></a>Simulare le variazioni di costo mediante una versione di determinazione costi per i costi pianificati

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come simulare gli effetti prodotti dalle variazioni di costo sui costi calcolati di un articolo prodotto con una versione di determinazione costi separata per costi pianificati.

Gli effetti prodotti dalle variazioni di costo sui costi calcolati di un articolo prodotto possono essere simulati con una versione di determinazione costi separata per costi pianificati. Utilizzare questa versione di determinazione costi separata per immettere record di costi in sospeso che riflettono variazioni di costo incrementali e per calcolare l'impatto dei costi sugli articoli prodotti. Poiché nei calcoli DBA verrà utilizzato un principio di fallback di costi attivi, è necessario immettere solo le variazioni di costo incrementali.

## <a name="guidelines-for-defining-the-simulation-costing-version"></a>Indicazioni per definire la versione di determinazione costi di simulazione.
Utilizzare le indicazioni riportate di seguito per definire la versione di determinazione costi di simulazione.

-   Assegnare un tipo di determinazione costi per **Costi pianificati**.
-   Assegnare un identificatore significativo per la versione di determinazione costi, ad esempio **Simulazione**.
-   Assicurarsi che nel contenuto siano inclusi i record dei costi.
-   Consentire l'immissione dei record costi. Non bloccare l'immissione dei costi in sospeso.
-   Consentire l'immissione di record costi per tutti i siti. Se si specifica un sito, si limita l'immissione di record costi per tale sito.
-   Impedire l'attivazione dei costi in sospeso. Devono essere immessi solo i costi in sospeso per i record dei costi nella versione di determinazione costi di simulazione.
-   Non immettere una data di inizio. Verrà immessa una data di calcolo per ciascun calcolo DBA in cui viene utilizzata la versione di determinazione costi di simulazione.
-   Specificare un principio di fallback su **Corrente attivo**. Il principio di fallback consente l'immissione di variazioni di costo incrementali per la simulazione, ma utilizza i costi correnti attivi come origine di tutti gli altri record dei costi. Si presuppone che siano disponibili tutti i costi correnti attivi per tutti gli altri record dei costi.
-   Specificare un modello di prezzo di costo su **Prezzo di costo versione**, ma non applicare restrizioni per i calcoli. È possibile ad esempio che nelle simulazioni venga utilizzato anche un modello prezzo di costo basato sul **Gruppo di calcolo DBA** per indicare l'origine dei dati di contributo costi per gli articoli acquistati.
-   Impostare la modalità di esplosione su **Multilivello**, ma non applicare restrizioni per i calcoli. È possibile che nelle simulazioni vengano utilizzate altre modalità di esplosione.

## <a name="costing-versions"></a>Versioni determinazione costi
Negli scenari descritti di seguito viene illustrato l'utilizzo della versione di determinazione costi di simulazione per simulare l'impatto delle variazioni di costo. Prima di immettere una variazione di costo simulata, eliminare i record dei costi in sospeso nella versione di determinazione costi di simulazione in modo da definire un punto di partenza integro. Utilizzare la pagina **Prezzo articolo** per visualizzare ed eliminare i record dei costi in sospeso correlati ai prezzi degli articoli e della categoria di costi.

-   Simulare la variazione di costo per un articolo acquistato. La variazione di costo ad esempio può riflettere una diminuzione o un aumento previsto dei costi di materiali acquistati importanti. Per definire il costo diverso per un articolo acquistato, utilizzare la pagina **Prezzo articolo** per immettere un record di costo in sospeso nella versione di determinazione costi di simulazione.
-   Simulare la variazione di costo per una categoria di costi. La variazione di costo ad esempio può riflettere una diminuzione o un aumento previsto delle tariffe della manodopera o delle tariffe orarie per le risorse operative. Per definire il costo diverso per una categoria di costi, utilizzare la pagina **Prezzo categoria costi** per immettere un record di costo in sospeso nella versione di determinazione costi di simulazione.
-   Simulare la variazione di costo in una formula di calcolo di costi indiretti. La variazione di costo ad esempio può riflettere una diminuzione o un aumento previsto dei costi generali di produzione. Per definire la variazione in una formula di calcolo di costi indiretti, utilizzare la pagina **Impostazione scheda di determinazione costi** per immettere un record di costo in sospeso nella versione di determinazione costi di simulazione e per convalidare e salvare la variazione.

Dopo aver immesso le variazioni di costo simulate, calcolare i costi degli articoli prodotti interessati dalle variazioni di costo. Utilizzare la pagina **Calcolo** per la versione di determinazione costi di simulazione e identificare gli articoli prodotti selezionati che saranno interessati dalle variazioni di costo. I calcoli DBA verranno applicati a tutti gli articoli prodotti, a meno che non si selezionino articoli specifici. È possibile in alternativa utilizzare l'opzione del calcolo DBA per aggiornamenti dove-usato. Visualizzare i record dei costi degli articoli nella versione di determinazione costi di simulazione per analizzare l'impatto delle variazioni di costo simulate sui costi degli articoli prodotti selezionati. Utilizzare le pagine **Prezzo articolo** e **Calcola costo articolo** per visualizzare e analizzare i costi.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]