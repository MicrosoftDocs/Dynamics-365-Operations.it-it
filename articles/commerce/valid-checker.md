---
title: Controllo di coerenza per le transazioni di vendita al dettaglio
description: In questo argomento viene descritta la funzionalità di controllo di coerenza per le transazioni in Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/07/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: cce0d408ac6d372fb726eff8fa4b0358ec200243
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210997"
---
# <a name="retail-transaction-consistency-checker"></a>Controllo di coerenza per le transazioni di vendita al dettaglio

[!include [banner](includes/banner.md)]

In questo argomento viene descritta la funzionalità di controllo di coerenza per le transazioni in Microsoft Dynamics 365 Commerce. Il controllo di coerenza identifica e isole le transazioni incoerenti prima che vengano prelevate dal processo di registrazione rendiconti.

Quando un rendiconto viene registrato, la registrazione può non riuscire a causa di dati incoerenti nelle tabelle di transazioni di commercio. Il problema sui dati può essere causato da problemi non previsti nell'applicazione POS o da transazioni importate in modo non corretto da sistemi POS di terze parti. Esempi di come le incoerenze possono essere visualizzate includono i seguenti: 

- Il totale delle transazioni nella tabella di intestazione non corrisponde al totale delle transazioni nelle righe.
- Il conteggio delle righe nella tabella di intestazione non corrisponde al numero di righe nella tabella di transazioni.
- Le imposte nella tabella di intestazione non corrispondono all'importo delle imposte nelle righe. 

Quando il processo di registrazione rendiconti preleva transazioni incoerenti, vengono creati giornali di registrazione pagamenti e fatture di vendita incoerenti e di conseguenza tutto il processo di registrazione rendiconti ha esito negativo. Il recupero dei rendiconti da uno stato di questo tipo prevede rettifiche complessi di dati in più tabelle di transazioni. Il controllo di coerenza per le transazioni consente di evitare questi problemi.

Nel grafico seguente è illustrato il processo di registrazione con il controllo di coerenza per le transazioni.

![Processo di registrazione dei rendiconto con il controllo di coerenza per le transazioni](./media/validchecker.png "Processo di registrazione dei rendiconto con il controllo di coerenza per le transazioni di vendita al dettaglio")

Il processo batch **Convalida transazioni punto vendita** controlla la coerenza delle tabelle di transazioni di commercio per gli scenari seguenti.

- **Conto cliente** - Verifica che il conto cliente presente nelle tabelle di transazioni sia presente nei dati master cliente della sede centrale.
- **Conteggio righe** - Verifica che il numero di righe, come acquisito nella tabella di intestazione delle transazioni, corrisponda al numero di righe nelle tabelle di transazioni vendite.
- **Prezzo IVA inclusa**: Verifica che il parametro **Prezzo IVA inclusa sia coerente nelle righe di transazione e Il prezzo include le tasse** il parametro è coerente tra le righe di transazione e che il prezzo sulla riga di vendita sia conforme al prezzo comprensivo di IVA e la configurazione esentasse.
- **Importo del pagamento**: verifica che i record di pagamento corrispondano all'importo del pagamento nell'intestazione, tenendo conto anche della configurazione per l'arrotondamento in centesimi in Contabilità generale.
- **Importo lordo**: verifica che l'importo lordo nell'intestazione sia la somma degli importi netti nelle righe più l'importo dell'IVA, tenendo conto anche della configurazione per l'arrotondamento in centesimi in Contabilità generale.
- **Importo netto**: verifica che l'importo netto nell'intestazione sia la somma degli importi netti nelle righe, tenendo conto anche della configurazione per l'arrotondamento in centesimi in Contabilità generale.
- **Insufficienza/Eccedenza pagamento**: verifica che la differenza tra l'importo lordo presente nell'intestazione e l'importo del pagamento non superi la configurazione massima di insufficienza/eccedenza pagamento, tenendo conto anche della configurazione per l'arrotondamento in centesimi in Contabilità generale.
- **Importo sconto**: verifica che l'importo di sconto presente nelle tabelle di sconto e quello presente nelle tabelle di righe transazioni di vendita al dettaglio siano coerenti e che l'importo dello sconto nell'intestazione sia la somma degli importi di sconto nelle righe, tenendo conto anche della configurazione per l'arrotondamento in centesimi in Contabilità generale.
- **Sconto riga** - Verifica che lo sconto presente nella riga di transazione sia la somma di tutte le righe nella tabella sconti corrispondente alla riga di transazione.
- **Articolo gift card** - In Commerce la restituzione di articoli con gift card non è supportata. Il saldo di una gift card, tuttavia, può essere liquidato. Qualsiasi articolo con gift card elaborato come riga di reso anziché come riga di liquidazione provoca un errore nel processo di registrazione rendiconti. Il processo di convalida per gli articoli con gift card garantisce che solo le voci di reso relative alla gift card presenti nella tabella di transazioni siano righe di liquidazione gift card.
- **Prezzo negativo** - Verifica che non sia presente alcuna riga di transazione prezzo negativo.
- **Articolo e variante** - Verifica che gli articoli e le varianti nelle righe di transazione siano presenti nel file master relativo.
- **Importo imposta** - Verifica che i record di imposta corrispondano agli importi nelle righe.
- **Numero di serie** - Verifica che il numero di serie sia presente nelle righe di transazione per gli articoli controllati dal numero di serie.
- **Segno** - Verifica che il segno della quantità e dell'importo netto sia lo stesso in tutte le righe di transazione.
- **Data attività** - Verifica che i periodi finanziari per tutte le date di attività delle transazioni siano aperti.
- **Addebiti**: verifica che l'importo dell'intestazione e dell'addebito sulla riga sia conforme al prezzo, inclusa l'IVA e la configurazione di esenzione fiscale.

## <a name="set-up-the-consistency-checker"></a>Impostare il controllo di coerenza

Configurare il processo batch "Convalida transazioni punto vendita" in **Retail e Commerce \> Retail e Commerce IT \> Registrazione POS** per esecuzioni periodiche. Il processo batch può essere programmato in base alla gerarchia organizzativa, in modo analogo a come vengono impostati i processi "Calcola rendiconti in batch" e "Registra rendiconti in batch". Si consiglia di configurare questo processo batch per più esecuzioni giornaliere e di programmarlo in modo che venga eseguito al termine di ogni esecuzione del processo P.

## <a name="results-of-validation-process"></a>Risultati del processo di convalida

I risultati della verifica di convalida eseguita dal processo batch sono contrassegnati sulla transazione appropriata. Il campo **Stato convalida** nel record di transazione è impostato su **Operazione completata** o **Errore** e la data dell'ultima convalida viene visualizzata nel campo **Ora ultima convalida**.

Per visualizzare più testo descrittivo dell'errore relativo a una mancata convalida, selezionare il record di transazione di punto vendita e fare clic sul pulsante **Errori di convalida**.

Le transazioni che non superano il controllo di convalida e quelle non ancora convalidate non verranno inserite nei rendiconti. Durante il processo di calcolo dei rendiconti, agli utenti verrà comunicato se sono presenti transazioni che sarebbe stato possibile includere nel rendiconto, ma non lo sono state.

Se viene rilevato un errore di convalida, per correggerlo è necessario contattare il servizio di supporto tecnico Microsoft. In una versione futura, verrà aggiunta la possibilità per gli utenti di correggere i record con errore nell'interfaccia utente. Verranno rese disponibili anche funzionalità di registrazione e controllo per tenere traccia dello storico delle modifiche.

> [!NOTE]
> Regole di convalida aggiuntive supportare più scenari verranno aggiunte in una versione futura.


[!INCLUDE[footer-include](../includes/footer-banner.md)]