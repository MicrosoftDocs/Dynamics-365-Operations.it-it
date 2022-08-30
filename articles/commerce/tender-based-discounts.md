---
title: Sconti basati sul metodo di pagamento
description: In questo articolo viene descritta la funzionalità Sconti basati sul metodo di pagamento che consente ai rivenditori di configurare gli sconti per tipi di metodi di pagamento specifici in Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/19/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.openlocfilehash: 3c28297e62e5b2880a7a39381702d5a1448c91ac
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336731"
---
# <a name="tender-based-discount"></a>Sconto basato sul metodo di pagamento

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

In questo articolo viene descritta la funzionalità Sconti basati sul metodo di pagamento che consente ai rivenditori di configurare gli sconti per tipi di metodi di pagamento specifici in Microsoft Dynamics 365 Commerce.

È una pratica comune tra i rivenditori al dettaglio rilasciare carte di credito private con marchio. Per i rivenditori al dettaglio è un vantaggio perché ottengono commissioni migliori dalle banche. Inoltre, poiché queste carte di credito possono incoraggiare i clienti a visitare il negozio più spesso, aiutano a migliorare i profitti del rivenditore al dettaglio. Pertanto, i rivenditori al dettaglio hanno un incentivo ad aumentare l'uso da parte dei clienti delle loro carte di credito con marchio. Per ottenere questo obiettivo, spesso offrono sconti aggiuntivi ai clienti che utilizzano le carte di credito.

In alternativa, i rivenditori al dettaglio che non offrono carte di credito con marchio possono incoraggiare i clienti a pagare utilizzando altri tipi di offerte, come contanti, buoni regalo o punti fedeltà. In questo modo, possono limitare la spesa delle commissioni per le carte di credito. Di conseguenza, i rivenditori al dettaglio possono offrire gli sconti ai clienti che utilizzano questi metodi di pagamento alternativi.

## <a name="tender-based-discount"></a>Sconto basato sul metodo di pagamento

Commerce supporta uno *sconto basato sul metodo di pagamento* che consente ai rivenditori di configurare una percentuale di sconto che viene applicata a una transazione se il totale di questa supera un importo specifico e il cliente paga utilizzando il tipo di pagamento preferito. Lo sconto basato sul metodo di pagamento è basato su livelli, di modo che diverse percentuali di sconto possano essere associate a soglie di importo differenti. Il cliente può decidere se effettuare un pagamento parziale o completo e il motore di determinazione dei prezzi determina l'importo dello sconto appropriato. Lo sconto basato sul metodo di pagamento viene sempre applicato all'importo al lordo di imposte delle righe di vendita.

Gli sconti basati sul metodo di pagamento possono essere applicati solo alle righe di vendita i cui prezzi non sono bloccati e vengono distribuiti proporzionalmente alle righe di vendita idonee. Se a un ordine vengono aggiunte nuove righe di vendita, lo sconto basato sul metodo di pagamento viene applicato solo alle nuove righe di vendita durante il pagamento. Quando viene effettuato un ordine cliente per il prelievo o la spedizione, lo sconto basato sul metodo di pagamento viene applicato solo all'importo del deposito. Dopo aver effettuato l'ordine, durante l'esecuzione, i prezzi delle righe di vendita vengono bloccati. Nessuno sconto basato sul metodo di pagamento viene applicato ai saldi pagati durante il prelievo o autorizzati durante la spedizione. Lo sconto basato sul metodo di pagamento può essere applicato all'intero importo di un ordine cliente solo se il rivenditore al dettaglio ritira l'intero importo come deposito quando viene effettuato l'ordine.

Gli sconti basati sul metodo di pagamento non competono con gli sconti basati su articoli come sconti semplici, sconti quantità, sconti soglia, sconti gamma e sconti manuali. Gli sconti basati sul metodo di pagamento sono sempre cumulati agli sconti basati sugli articoli. Pertanto, anche se uno sconto esclusivo viene applicato a un articolo, lo sconto basato sul metodo di pagamento può essere sempre applicato allo sconto esclusivo. Analogamente, se uno sconto di soglia viene applicato alla transazione e lo sconto basato sul metodo di pagamento riduce il totale al di sotto della soglia, lo sconto di soglia viene comunque applicato alla transazione.

Anche se gli sconti basati sul metodo di pagamento riducono il totale parziale di una transazione, le spese automatiche applicate alla transazione non sono interessate. Ad esempio, se le spese di consegna calcolate sono 5 USD in quanto il subtotale era superiore a 100 USD e lo sconto basato sul metodo di pagamento riduce l'importo a un valore inferiore a 100 USD, le spese di consegna per l'ordine sono sempre 5 USD.

Lo sconto basato sul metodo di pagamento è attualmente limitato a due tipi di pagamento: carte di credito e contanti. Se sono configurati più sconti basati sul metodo di pagamento per un tipo di pagamento, viene applicato solo lo sconto basato sul metodo di pagamento migliore.

## <a name="pos-user-experience"></a>Esperienza utente per il POS

Se uno sconto basato sul metodo di pagamento è impostato su contanti e un cassiere presso il punto vendita (POS) seleziona il pulsante **Pagamento in contanti** per eseguire il checkout di una transazione cash-and-carry, lo sconto basato sul metodo di pagamento viene automaticamente applicato alla transazione. L'importo ridotto viene quindi visualizzato come saldo. Tuttavia, se il cassiere seleziona il pulsante **Indietro** nella schermata di pagamento, lo sconto viene rimosso e l'importo originale viene visualizzato nella schermata della transazione. Lo sconto basato sul metodo di pagamento viene rimosso se la riga di pagamento viene annullata.

Per pagamenti con carta di credito, i rivenditori possono impostare lo sconto basato sul metodo di pagamento su uno o più tipi di carte di credito. Tuttavia, il sistema non può verificare il tipo di carta di credito utilizzata a meno che la carta non sia autorizzata. Se lo sconto viene applicato dopo l'autorizzazione, l'autorizzazione di pagamento sarà per un importo maggiore, ma l'acquisizione del pagamento sarà per un importo inferiore. Per prevenire questa situazione, se un cliente paga con una carta di credito, viene visualizzata una finestra di dialogo che elenca le carte di credito preferite che concederanno al cliente un ulteriore sconto. Il cassiere può quindi chiedere se il cliente desidera utilizzare una delle carte preferite per ottenere uno sconto aggiuntivo. Se il cassiere seleziona una carta preferita, lo sconto basato sul metodo di pagamento viene applicato alla transazione e l'importo ridotto viene visualizzato nella schermata di pagamento. L'autorizzazione sarà per l'importo ridotto. Se il cliente usa una carta diversa dalla carta selezionata dal cassiere, viene visualizzato un messaggio di errore e l'autorizzazione viene annullata.

## <a name="call-center-user-experience"></a>Esperienza utente per il servizio clienti

Se un utente del servizio clienti seleziona **Completa** durante un ordine del servizio clienti, viene visualizzata la schermata **Totali**. Inizialmente, i totali in questa schermata non includono gli sconti basati sul metodo di pagamento perché il metodo di pagamento non è stato ancora selezionato. Nella schermata **Aggiungi pagamento**, se l'utente seleziona il metodo di pagamento per cui è configurato lo sconto basato sul metodo di pagamento, l'importo del pagamento viene automaticamente modificato in modo da riflettere l'importo scontato. Come un cliente presso il POS, il cliente del servizio clienti può decidere se pagare l'importo completo o parziale. Lo sconto basato sul metodo di pagamento viene applicato all'ordine cliente in base all'importo pagato.

> [!NOTE]
> La convalida della carta non viene effettuata per gli ordini del servizio clienti. Ad esempio, se l'utente del servizio clienti seleziona Visa come carta di credito, ma il cliente utilizza Mastercard, il sistema applica comunque lo sconto.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
