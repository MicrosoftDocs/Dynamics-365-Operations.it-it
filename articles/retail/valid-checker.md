---
title: Controllo di coerenza per le transazioni di vendita al dettaglio
description: In questo argomento viene descritta la funzionalità di controllo di coerenza per le transazioni di vendita al dettaglio in Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 8b373ce3cfd1183a082e2b1ebaf8c907b16e581e
ms.sourcegitcommit: ca4562fafa33b3512f0a5e246b15545fcf53e834
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2019
ms.locfileid: "379995"
---
# <a name="retail-transaction-consistency-checker"></a>Controllo di coerenza per le transazioni di vendita al dettaglio


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

In questo argomento viene descritta la funzionalità di controllo di coerenza per le transazioni di vendita al dettaglio introdotta in Microsoft Dynamics 365 for Finance and Operations, versione 8.1.3. Il controllo di coerenza identifica e isole le transazioni incoerenti prima che vengano prelevate dal processo di registrazione rendiconti.

Quando un rendiconto viene registrato in Retail, la registrare può non riuscire a causa di dati incoerenti nelle tabelle di transazioni di vendita al dettaglio. Il problema sui dati può essere causato da problemi non previsti nell'applicazione POS o da transazioni importate in modo non corretto da sistemi POS di terze parti. Esempi di come le incoerenze possono essere visualizzate includono i seguenti: 

  - Il totale delle transazioni nella tabella di intestazione non corrisponde al totale delle transazioni nelle righe.
  - Il conteggio delle righe nella tabella di intestazione non corrisponde al numero di righe nella tabella di transazioni.
  - Le imposte nella tabella di intestazione non corrispondono all'importo delle imposte nelle righe. 
  
Quando il processo di registrazione rendiconti preleva transazioni incoerenti, vengono creati giornali di registrazione pagamenti e fatture di vendita incoerenti e di conseguenza tutto il processo di registrazione rendiconti ha esito negativo. Il recupero dei rendiconti da uno stato di questo tipo prevede rettifiche complessi di dati in più tabelle di transazioni. Il controllo di coerenza per le transazioni di vendita al dettaglio consente di evitare questi problemi.

Nel grafico seguente è illustrato il processo di registrazione con il controllo di coerenza per le transazioni.

![Processo di registrazione dei rendiconto con il controllo di coerenza per le transazioni di vendita al dettaglio](./media/validchecker.png "Processo di registrazione dei rendiconto con il controllo di coerenza per le transazioni di vendita al dettaglio")

Il processo batch **Convalida transazioni punto vendita** controlla la coerenza delle tabelle di transazioni di vendita al dettaglio per gli scenari seguenti.

- Conto cliente - Verifica che il conto cliente presente nelle tabelle di transazioni di vendita al dettaglio sia presente nei dati master cliente della sede centrale.
- Conteggio righe - Verifica che il numero di righe, come acquisito nella di intestazione delle transazioni, corrisponda al numero di righe nelle tabelle di transazioni vendite.

## <a name="set-up-the-consistency-checker"></a>Impostare il controllo di coerenza
Configurare il processo batch "Convalida transazioni punto vendita" in **Vendita al dettaglio \> Vendita al dettaglio IT \> Registrazione POS** per esecuzioni periodiche. Il processo batch può essere programmato in base alla gerarchia organizzativa, in modo analogo a come vengono impostati i processi "Calcola rendiconti in batch" e "Registra rendiconti in batch". Si consiglia di configurare questo processo batch per più esecuzioni giornaliere e di programmarlo in modo che venga eseguito al termine di ogni esecuzione del processo P.

## <a name="results-of-validation-process"></a>Risultati del processo di convalida
I risultati della verifica di convalida eseguita dal processo batch sono contrassegnati sulla transazione di vendita al dettaglio appropriata. Il campo **Stato convalida** nel record di transazione di vendita al dettaglio è impostato su **Operazione completata** o **Errore** e la data dell'ultima convalida viene visualizzata nel campo **Ora ultima convalida**.

Per visualizzare più testo descrittivo dell'errore relativo a una mancata convalida, selezionare il record di transazione di punto vendita al dettaglio e fare clic sul pulsante **Errori di convalida**.

Le transazioni che non superano il controllo di convalida e quelle non ancora convalidate non verranno inserite nei rendiconti. Durante il processo di calcolo dei rendiconti, agli utenti verrà comunicato se sono presenti transazioni che sarebbe stato possibile includere nel rendiconto, ma non lo sono state.

Se viene rilevato un errore di convalida, per correggerlo è necessario contattare il servizio di supporto tecnico Microsoft. In una versione futura, verrà aggiunta la possibilità per gli utenti di correggere i record con errore nell'interfaccia utente. Verranno rese disponibili anche funzionalità di registrazione e controllo per tenere traccia dello storico delle modifiche.

> [!NOTE]
> Regole di convalida aggiuntive supportare più scenari verranno aggiunte in una versione futura.
