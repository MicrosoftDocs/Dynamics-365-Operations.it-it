---
title: Impostare buoni sconto per le vendite al dettaglio
description: In questo argomento viene fornita una panoramica dei buoni sconto e illustra come configurarli.
author: scott-tucker
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailCoupon, RetailParameters, RetailSharedParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: scotttuc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a07bed244152327047efd68cfacb329a722c0049
ms.sourcegitcommit: 97206552616b248f88e516fea08b3f059257e8d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431980"
---
# <a name="set-up-coupons-for-retail-sales"></a>Impostare buoni sconto per le vendite al dettaglio

[!include [banner](includes/banner.md)]

## <a name="overview-of-coupons"></a>Panoramica dei buoni sconto

I buoni sconto sono codici e codici a barre utilizzati per aggiungere sconti alle transazioni. Ogni buono sconto può avere più codici e ogni codice può avere una propria data di validità.

Ogni buono sconto è relativo a uno sconto. I gruppi di prezzi associati allo sconto definiscono i clienti che possono utilizzare un buono sconto o i canali in cui un buono sconto è valido.

Essenzialmente, i buoni sconto rappresentano una convalida aggiuntiva sugli sconti. Il buono sconto fornisce i codici e i codici a barre necessari dei buoni sconto, insieme a intervalli di date per tali codici. Il buono sconto fornisce inoltre i limiti facoltativi di utilizzo e le proprietà obbligatorie del cliente. Lo sconto fornisce un set di prodotti per cui il buono sconto è valido. I gruppi di prezzi per lo sconto forniscono il set di clienti, canali o cataloghi per cui il buono sconto è valido.

Per creare un buono sconto, verranno creati separatamente lo sconto e il buono sconto. Quindi vengono collegati selezionando lo sconto nella pagina dei buoni sconto in Commerce.

> [!NOTE]
> Dopo che un buono sconto è stato collegato a uno sconto, diversi campi presenti nella pagina dei buoni sconto in Commerce diventano di sola lettura, poiché vengono gestiti dalle impostazioni del buono sconto. Questi campi includono i campi per lo stato e gli intervalli di date standard.

### <a name="limited-use-coupons"></a>Buoni sconti a utilizzo limitato

I buoni sconto possono essere configurati come a utilizzo limitato. Il limite di utilizzo può essere definito per cliente o canale, o come limite globale. Questo limite viene applicato quando il codice o il codice a barre viene immesso o letto nel POS o durante la registrazione dell'ordine cliente.

Il limite viene applicato per codice buono sconto su un buono sconto. Ad esempio, un singolo buono sconto che contiene due codici buono sconto può essere utilizzato due volte: una volta per ogni codice del buono sconto. Ogni codice su un buono sconto può essere impostato indipendentemente su Attivo.

I buoni sconto non possono essere utilizzati in qualsiasi canale di vendita, tuttavia, per gli ordini servizio clienti, i coupon a utilizzo limitato possono essere utilizzati solo per gli ordini per i quali l'impostazione **Completamento ordine** è abilitata. Se questa opzione non è abilitata, è possibile utilizzare solo i buoni sconto di utilizzo non limitato negli ordini servizio clienti.

> [!NOTE]
> Dopo che un numero di buono sconto ha raggiunto il limite di utilizzo, il sistema *non* modifica automaticamente lo stato del codice del buono sconto a "Utilizzato". Tuttavia, quel numero di buono sconto ha raggiunto il limite di utilizzo e non può essere utilizzato. Se lo stato di un numero di buono sconto viene impostato manualmente su un valore diverso da **Attivo**, il codice di buono sconto non può essere utilizzato in nessun canale.  

## <a name="managing-coupons"></a>Gestione dei buoni sconto

Lo sconto e il buono sconto devono essere creati separatamente. Quindi vengono collegati selezionando lo sconto nella pagina del buono sconto. Dopo che un buono sconto è stato collegato a uno sconto, diversi campi per lo sconto diventano di sola lettura, poiché vengono gestiti dalle impostazioni del buono sconto. Questi campi includono i campi per lo stato e gli intervalli di date standard.

Essenzialmente, i buoni sconto ora rappresentano una convalida aggiuntiva sugli sconti. Il buono sconto fornisce i codici e i codici a barre necessari dei buoni sconto, insieme a intervalli di date, limite di utilizzo e la proprietà obbligatoria del cliente. Lo sconto fornisce un set di prodotti per cui il buono sconto è valido. I gruppi di prezzi dello sconto forniscono il set di clienti, canali o cataloghi per cui il buono sconto è valido.

## <a name="system-setup-for-coupons"></a>Configurazione di sistema per i buoni sconto

Prima di impostare un buono sconto, è necessario impostare il codice a barre del buono sconto e due sequenze numeriche di buoni sconto.

1. Nella pagina **Caratteri maschera**, creare un nuovo carattere maschera per il codice buono sconto. È possibile selezionare qualsiasi carattere non utilizzato.
2. Nella pagina **Impostazione maschera codice a barre**, creare una nuova maschera codice a barre. Impostare il campo **Tipo** su **Buono sconto**.
3. Nella pagina **Impostazione codice a barre**, creare un nuovo codice a barre che utilizza la maschera codice a barre appena creata.
4. Nella pagina **Sequenze numeriche**, creare due nuove sequenze numeriche. Una sequenza è per l'ID del codice di buono sconto e l'altra sequenza è per il numero di buono sconto. L'ID del codice buono sconto è l'identificatore univoco per ciascun codice buono sconto. Il numero del buono sconto è l'identificatore univoco per un buono sconto. Ciascun buono sconto può avere più codici e codici a barre che attivano il buono sconto.

    > [!NOTE]
    > Per entrambe le sequenze numeriche, è necessario impostare il campo **Ambito** su **Società**. Nella maggior parte dei casi, è necessario generare automaticamente entrambe i numeri della sequenza.

5. Nella pagina **Parametri di commercio**, nella scheda **Codici a barre**, selezionare il codice a barre creato in precedenza.
6. Nella pagina **Parametri condivisi di commercio**, nella scheda **Sequenze numeriche**, selezionare le sequenze numeriche create per il numero di buono sconto e ID codice buono sconto.
7. È ora possibile aprire la pagina **Buoni sconto** e creare nuovi buoni sconto.

## <a name="the-effect-of-partial-updates-on-coupons"></a>Effetto degli aggiornamenti parziali sui buoni sconto

La funzionalità Buono sconto include diverse funzionalità distinte. Commerce Headquarters (HQ) e il canale possono essere parzialmente aggiornati sui componenti. Di conseguenza, è importante comprendere come gli aggiornamenti parziali influiscono complessivamente sulla funzionalità dei buoni sconto.

- **HQ è parzialmente aggiornato, ma Commerce Scale Unit e POS non vengono aggiornati.** In un aggiornamento HQ, il buono sconto e le pagine di sconto vengono aggiornati e il motore dei prezzi di commercio viene aggiornato. Se uno solo di questi due componenti viene aggiornato, alcune pagine in Commerce non corrisponderanno ai dati del calcolo dei prezzi. Di conseguenza, calcoli degli sconti imprevisti o errori possono verificarsi durante i calcoli degli sconti.
- **HQ è aggiornato, ma Commerce Scale Unit e POS non vengono aggiornati (N-1).** Poiché non tutti i punti vendita possono essere aggiornati contemporaneamente, si consiglia di aggiornare HQ prima di aggiornare i punti vendita. Nello scenario N-1, le nuove funzionalità correlate ai buoni sconto non saranno disponibili nei punti vendita che non sono stati ancora aggiornati. Ad esempio, la funzionalità dei buoni sconto introduce l'esclusione delle righe. Se si utilizza l'esclusione delle righe in uno sconto, questo non verrà applicato in un punto vendita che esegue una versione precedente.
- **HQ non è aggiornato, ma Commerce Scale Unit e POS vengono aggiornati (N+1).** Poiché il motore dei prezzi aggiornato in Commerce Scale Unit è in grado di gestire i codici sconto legacy durante i calcoli dei prezzi, l'aggiornamento non dovrebbe avere alcun impatto funzionale in questo scenario.
