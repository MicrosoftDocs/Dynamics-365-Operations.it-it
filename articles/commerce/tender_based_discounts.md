---
title: Sconti basati sul metodo di pagamento
description: In questo argomento viene fornita una panoramica della funzionalità che consente ai rivenditori al dettaglio di configurare gli sconti per tipi di metodi di pagamento specifici.
author: bebeale
manager: AnnBe
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: 98631d8f9fb2c05621f69fa67c9b60472198ee6b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232569"
---
# <a name="tender-based-discounts"></a>Sconti basati sul metodo di pagamento

[!include [banner](includes/banner.md)]


È una pratica comune tra i rivenditori al dettaglio rilasciare carte di credito private con marchio. Per i rivenditori al dettaglio è un vantaggio perché ottengono commissioni migliori dalle banche. Inoltre, poiché queste carte di credito possono incoraggiare i clienti a visitare il negozio più spesso, aiutano a migliorare i profitti del rivenditore al dettaglio. Pertanto, i rivenditori al dettaglio hanno un incentivo ad aumentare l'uso da parte dei clienti delle loro carte di credito con marchio. Per ottenere questo obiettivo, spesso offrono sconti aggiuntivi ai clienti che utilizzano le carte di credito.

In alternativa, i rivenditori al dettaglio che non offrono carte di credito con marchio possono incoraggiare i clienti a pagare utilizzando altri tipi di offerte, come contanti, buoni regalo o punti fedeltà. In questo modo, possono limitare la spesa delle commissioni per le carte di credito. Di conseguenza, i rivenditori al dettaglio possono offrire gli sconti ai clienti che utilizzano questi metodi di pagamento alternativi.

In Microsoft Dynamics 365 Commerce, i rivenditori al dettaglio possono configurare una percentuale di sconto che viene applicata alle righe qualificate se il cliente paga utilizzando il metodo di pagamento preferito. Il cliente può decidere se effettuare un pagamento parziale o completo e Commerce determina lo sconto appropriato. Tenere presente che lo sconto è sempre calcolato sull'importo al lordo di imposte degli articoli idonei.

Gli sconti basati sul metodo di pagamento non competono con sconti basati sugli articoli, come gli sconti periodici o manuali. Sono sempre applicati sugli sconti per gli articoli. Pertanto, anche se uno sconto periodico esclusivo viene applicato a un articolo, lo sconto basato sul metodo di pagamento viene comunque applicato allo sconto periodico esclusivo. Analogamente, se uno sconto di soglia viene applicato alla transazione e lo sconto basato sul metodo di pagamento riduce il totale al di sotto della soglia, lo sconto di soglia viene comunque applicato alla transazione.

Anche se gli sconti basati sul metodo di pagamento riducono il totale parziale della transazione, gli addebiti automatici applicati alla transazione non sono interessati. Ad esempio, se le spese di consegna sono calcolate per 5 USD perché il subtotale era superiore a 100 USD e lo sconto basato sul metodo di pagamento riduce l'importo a un valore inferiore a 100 USD, le spese di consegna per l'ordine sono sempre 5 USD.


> [!NOTE]
> Gli sconti basati sul metodo di pagamento sono distribuiti proporzionalmente alle righe di vendita idonee e riducono l'importo al lordo di imposte delle singole righe. Se sono configurati più sconti basati sul metodo di pagamento per un tipo di metodo di pagamento (ad esempio, contanti), viene applicato solo lo sconto basato sul metodo di pagamento migliore.

Gli sconti basati sul metodo di pagamento possono essere applicati solo alle righe di vendita in cui i prezzi non sono bloccati. Se a un ordine vengono aggiunte nuove righe di vendita, lo sconto basato sul metodo di pagamento viene applicato alle nuove righe di vendita solo durante il pagamento. Se viene effettuato un ordine cliente per il prelievo o la spedizione, lo sconto basato sul metodo di pagamento viene applicato solo all'importo del deposito. Dopo aver effettuato l'ordine, durante l'esecuzione, i prezzi delle righe di vendita vengono bloccati. Pertanto, non viene applicato lo sconto basato sul metodo di pagamento ai saldi pagati durante il prelievo o autorizzati durante la spedizione. Lo sconto basato sul metodo di pagamento può essere applicato all'intero importo di un ordine cliente solo se il rivenditore al dettaglio ritira l'intero importo come deposito quando viene effettuato l'ordine.

> [!IMPORTANT]
> In Commerce, gli sconti basati sul metodo di pagamento sono attualmente limitati a due tipi di pagamento: carte di credito e contanti.

## <a name="pos-user-experience"></a>Esperienza utente per il POS

Se lo sconto basato sul metodo di pagamento è impostato per contanti e il cassiere del punto vendita (POS) seleziona un pulsante che è mappato all'operazione Pagamento in contanti, lo sconto basato sul metodo di pagamento viene automaticamente applicato alla transazione. L'importo ridotto viene quindi visualizzato come saldo. Tuttavia, se il cassiere seleziona il pulsante **Indietro** nella schermata di pagamento, lo sconto viene rimosso e l'importo originale viene visualizzato nella schermata della transazione. Lo sconto basato sul metodo di pagamento viene rimosso se la riga di pagamento viene annullata.

Per i pagamenti con carta, i rivenditori al dettaglio possono impostare lo sconto basato sul metodo di pagamento su uno o più tipi di carte di credito. Tuttavia, il sistema non può verificare il tipo di carta di credito utilizzata a meno che la carta non sia autorizzata. Se lo sconto viene applicato dopo l'autorizzazione, l'autorizzazione di pagamento sarà per un importo maggiore, ma l'acquisizione del pagamento sarà per un importo inferiore.

Per prevenire questa situazione, se un cliente paga con una carta di credito, viene visualizzata una finestra di dialogo per il cassiere che elenca le carte di credito che porteranno al cliente maggiori risparmi. Il cassiere può quindi chiedere se il cliente desidera utilizzare una delle carte preferite per ottenere uno sconto aggiuntivo. Se il cassiere utilizza una carta preferita, lo sconto basato sul metodo di pagamento viene applicato alla transazione e l'importo ridotto viene visualizzato nella schermata di pagamento. L'autorizzazione sarà per l'importo ridotto. Se il cliente usa una carta diversa dalla carta selezionata dal cassiere, viene visualizzato un messaggio di errore e l'autorizzazione viene annullata.


## <a name="call-center-user-experience"></a>Esperienza utente per il servizio clienti

Quando l'utente seleziona **Completa** nell'ordine del servizio clienti, viene visualizzata la schermata **Totali**. Inizialmente, i totali in questa schermata non includono gli sconti basati sul metodo di pagamento perché il metodo di pagamento non è stato ancora selezionato. Nella schermata **Aggiungi pagamento**, se l'utente seleziona il metodo di pagamento per cui è configurato lo sconto basato sul metodo di pagamento, l'importo del pagamento viene automaticamente modificato in modo da riflettere l'importo scontato. Come per il cliente presso il POS, il cliente del servizio clienti può decidere se pagare l'importo completo o parziale. Lo sconto basato sul metodo di pagamento viene applicato all'ordine cliente in base all'importo pagato.

> [!NOTE]
> La convalida della carta non viene effettuata per gli ordini del servizio clienti. Ad esempio, se l'utente del servizio clienti seleziona Visa come carta di credito, ma il cliente utilizza Mastercard, il sistema applica comunque lo sconto.

## <a name="exclude-items-from-discounts"></a>Escludere gli articoli dagli sconti

I rivenditori al dettaglio spesso scelgono di escludere dagli sconti alcuni prodotti, come gli articoli nuovi o più richiesti. Tuttavia, potrebbero comunque voler applicare sconti basati sul metodo di pagamento. Ad esempio, un rivenditore configura Commerce in modo da non consentire sconti basati su articoli o sconti manuali. Tuttavia, se il cliente paga utilizzando il metodo di pagamento preferito, Commerce applica comunque lo sconto basato sul metodo di pagamento. Per impostare Commerce in questo modo, i rivenditori devono andare a **Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**, selezionare l'articolo desiderato, quindi nella scheda dettaglio **Commerce**, impostare le opzioni **Impedisci tutti gli sconti** e **Impedisci sconti basati sul metodo di pagamento** su **No** e le opzioni **Impedisci sconti vendita al dettaglio** e **Impedisci sconti manuali** su **Sì**.

> [!NOTE]
> Quando la configurazione **Impedisci tutti gli sconti** è impostata su **Sì**, nessuno sconto verrà applicato al prodotto. Non verranno applicati nemmeno gli sconti basati sul metodo di pagamento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]