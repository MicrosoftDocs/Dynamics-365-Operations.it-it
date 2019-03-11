---
title: Implementare correzioni manuali nella previsione di base
description: Questo argomento illustra come apportare correzioni manuali a una previsione di base e visualizzare i dettagli della previsione.
author: roxanadiaconu
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7c7d1fcaaeef7a01b43886e4d69458dbd942439
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "315891"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a>Implementare correzioni manuali nella previsione di base

[!include [banner](../includes/banner.md)]

Questo argomento illustra come apportare correzioni manuali a una previsione di base e visualizzare i dettagli della previsione. 

Prima di apportare correzioni manuali, è importante comprendere alcuni concetti relativi alle varie pagine.

## <a name="grid-on-the-adjusted-demand-forecast-page"></a>Griglia della pagina Previsione della domanda modificata
La pagina **Previsione della domanda modificata** include una griglia con la seguente struttura:

-   La prima colonna mostra gli articoli, le chiavi di allocazione articolo, le società, e così via, per cui la previsione è stata generata. Il sottotitolo della pagina fornisce una descrizione delle dimensioni di previsione correnti visualizzate nella griglia. Ad esempio, se il sottotitolo della pagina è **Società/sito/chiave di allocazione articolo** e una delle intestazioni della riga nella griglia è **USMF / 1 / D\_Alloc**, la riga mostra la previsione per la società USMF, il sito 1 e la chiave di allocazione articolo **D\_Alloc**.
-   Le colonne successive rappresentano gli intervalli di previsione per cui la previsione è stata generata. Ogni intestazione di colonna corrisponde alla data dell'intervallo di previsione che mostra la colonna.
-   I valori delle celle rappresentano la previsione per un articolo, chiave di allocazione articolo, e altri valori specifici di tale intervallo di previsione.

## <a name="forecast-aggregation-and-de-aggregation"></a>Aggregazione e annullamento dell'aggregazione di previsione
Il sottotitolo della pagina mostra il livello di aggregazione della previsione. 

Ad esempio, se il sottotitolo della pagina è **Società/sito/chiave di allocazione/numero articolo/colore/dimensioni/configurazione/stile**, non esiste alcuna aggregazione di previsione e la previsione viene visualizzata a livello di articolo e delle relative dimensioni. Per modificare l'aggregazione, utilizzare la pagina **Modifica dimensioni previsione** che è possibile aprire dal menu dell'applicazione. 

Per modificare la previsione, fare clic su qualsiasi cella disponibile e digitare il valore corretto della previsione. La cella modificata viene immediatamente evidenziata in grassetto per indicare che la previsione mostrata non corrisponde alla previsione creata dal servizio di previsione della domanda, ma al valore corretto manualmente. 

Se si modifica l'aggregazione affinché la pagina visualizzi ulteriori dati aggregati, è possibile utilizzare la pagina **Righe di previsione della domanda** per visualizzare le singole righe di previsione che costituiscono la previsione aggregata. 

Ad esempio, è stata generata la previsione a livello di articolo, ma si sa che la domanda per l'articolo aumenterà in tutti i siti a causa di una promozione o di un altro evento simile. In questo caso, è possibile impostare l'aggregazione su **Società / Chiave di allocazione articolo / Articolo** nella pagina **Modifica dimensioni previsione**. È possibile correggere la previsione globale per l'articolo in tutti i siti nella griglia **Previsione della domanda modificata**. Per visualizzare l'effetto della modifica in tutti i siti, aprire la pagina **Righe di previsione della domanda**. In questa pagina, sarà possibile visualizzare una riga per l'articolo per ogni sito, la quantità di previsione corretta e la quantità di previsione originale. 

Quando la correzione della quantità programmata viene effettuata a livello aggregato, il sistema utilizza un metodo di allocazione pesato per distribuire la modifica tra le righe che creano l'aggregazione. 

È inoltre possibile apportare correzioni manuali nella pagina **Righe di previsione della domanda** modificando il valore della **Quantità totale** o le celle della **Quantità** nella griglia di annullamento della aggregazione.

## <a name="viewing-details-of-the-forecast"></a>Visualizzazione dei dettagli della previsione
È possibile aprire la pagina **Dettagli di previsione della domanda** per visualizzare ulteriori informazioni sulla previsione. 

La pagina **Dettagli di previsione della domanda** visualizza le informazioni seguenti in formati grafici e tabulari:

-   La domanda storica su cui si basano le previsioni.
-   La previsione corrente utilizzata dalla pianificazione generale.
-   I nuovi valori di previsione della domanda e gli importi manualmente corretti.
-   L'intervallo di fiducia per i valori futuri.
-   Il modello previsionale utilizzato per generare la previsione. Se si visualizzano i dati aggregati, è possibile ottenere l'elenco di tutti i metodi utilizzati per tutte le serie cronologiche aggregate.
-   La precisione del modello interno (Errore medio assoluto percentuale). Per ulteriori informazioni sulla precisione di previsione, vedere [Monitoraggio della precisione previsione](monitor-forecast-accuracy.md).

**Note:**

-   L'intervallo di fiducia visualizzato nella sezione **Previsione** della pagina rappresenta la differenza tra il limite superiore dell'intervallo di fiducia e il limite minimo dell'intervallo di fiducia. Per visualizzare i valori dei limiti superiori e inferiori, passare il mouse sul grafico nella sezione **Domanda e previsioni storiche in formato grafico**.
-   Se si utilizza il servizio di Microsoft Azure Machine Learning della previsione della domanda di Finance and Operations, è possibile specificare la percentuale del livello di fiducia che la previsione generata deve avere. Un intervallo di fiducia è costituito da un intervallo di valori che fungono da stime affidabili per la previsione della domanda. Un livello di fiducia del 95% indica ad esempio che è presente una possibilità del 5% che il risultato di previsione della domanda previsto non sia compreso nell'intervallo stabilito.

È inoltre possibile apportare correzioni manuali alla previsione nella pagina **Dettagli previsione della domanda** modificando i valori della riga **Previsione** nella sezione **Previsione**.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Monitoraggio della precisione previsione](monitor-forecast-accuracy.md)

[Generazione di una previsione di base statistica](generate-statistical-baseline-forecast.md)



