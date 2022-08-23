---
title: Mostrare sconti in POS
description: Questo articolo spiega come Microsoft Dynamics 365 Commerce aiuta gli addetti alle vendite a conoscere le promozioni e come possono essere utilizzate per i movimenti di cross-sell e upsell.
author: ShalabhjainMSFT
ms.date: 07/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2020-02-28
ms.dyn365.ops.version: Application update 10.0.10
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail, Commerce
ms.search.form: ''
ms.openlocfilehash: 706c13bf090b2ad3826d17bbbeda8a2fa7733f2f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287710"
---
# <a name="show-discounts-in-pos"></a>Mostrare gli sconti nel POS

[!include [banner](includes/banner.md)]

Le promozioni svolgono un ruolo importante nel motivare i clienti che stanno prendendo decisioni di acquisto. Ad esempio, le vacanze possono produrre il maggior numero di vendite per i rivenditori, perché l'intero mercato al dettaglio è invaso da promozioni e sconti allettanti. Se i collaboratori del negozio conoscono e comprendono le promozioni disponibili, possono facilmente trarre vantaggio da tali promozioni per il cross-sell e l'upsell degli articoli. Questo articolo spiega come Microsoft Dynamics 365 Commerce aiuta gli addetti alle vendite a conoscere le promozioni e come possono essere utilizzate per i movimenti di cross-sell e upsell.

## <a name="learn-about-store-discounts"></a>Informazioni sugli sconti dei negozi

Commerce include un'operazione denominata "Visualizza tutti gli sconti". Questa operazione mostra tutti gli sconti che sono attualmente in corso in un negozio. L'operazione "Visualizza tutti gli sconti" può essere associata a un pulsante nel punto vendita (POS) e il pulsante può essere aggiunto alla pagina di **benvenuto** o della **transazione**. Nella figura seguente è illustrato un esempio della pagina **Tutti gli sconti** aperta.

![Pagina Tutti gli sconti.](./media/View_all_discounts.png "Pagina Tutti gli sconti")

Per mostrare gli sconti, il sistema cerca tutti gli sconti che soddisfano una o più delle seguenti condizioni:

- Il gruppo di prezzi dello sconto corrisponde al gruppo di prezzi del negozio.
- Il gruppo di prezzi dello sconto è associato a un programma di affiliazione o fedeltà.
- Il gruppo di prezzi dello sconto è associato a un catalogo collegato al negozio.

La pagina **Tutti gli sconti** mostra solo alcuni sconti basati su buono sconto, poiché i rivenditori in genere creano migliaia di buoni sconto e sconti corrispondenti per clienti unici e questa pagina non intende mostrare gli sconti specifici per cliente. Gli sconti basati su coupon vengono visualizzati solo se l'opzione **Applica senza buono sconto** è attivata in ciascuna intestazione del buono sconto. In tal caso, i cassieri possono applicare il buono sconto senza dover inserire o scansionare alcun codice buono sconto o codice a barre.

Quando l'opzione **Applica senza buono sconto** è attivata, sono disponibili vari scenari. Ad esempio, i cassieri possono offrire ulteriori sconti ai clienti per pacificare i clienti o per difetti del prodotto. I codici buono sconto stampati o i codici a barre non devono essere distribuiti ai cassieri. I cassieri possono selezionare il pulsante **Applica buono sconto**. Il buono sconto viene quindi automaticamente applicato alla transazione. Se esistono più buoni sconto per un'intestazione buono sconto, il sistema seleziona automaticamente il primo buono sconto attivo sulla transazione.

Nella pagina **Tutti gli sconti**, gli addetti alle vendite possono anche cercare sconti per parole chiave. La ricerca per parola chiave viene eseguita nei campi che contengono il nome e la descrizione dello sconto. Gli addetti alle vendite possono anche filtrare gli sconti in base al fatto che uno sconto richieda un codice buono sconto.

## <a name="cross-sell-and-upsell-by-using-discounts"></a>Cross-selling e upselling utilizzando gli sconti

Gli sconti multilinea, come gli sconti sulle quantità, gli sconti gamma e gli sconti soglia, sono un ottimo modo per motivare i clienti ad acquistare più prodotti per ottenere sconti maggiori. Pertanto, aiutano anche ad aumentare le dimensioni del carrello di un cliente e le entrate del rivenditore. Questi sconti possono essere pubblicizzati sui siti Web di e-commerce, sui social media e sui banner nel negozio.

Tuttavia, anche quando vengono utilizzati tutti questi metodi di pubblicità, i clienti potrebbero perdere l'opportunità di usufruire delle promozioni. Per facilitare agli addetti alle vendite l'apprendimento delle promozioni applicabili a una linea selezionata o persino all'intero carrello, i rivenditori possono aggiungere il pulsante per l'operazione **Visualizza sconti disponibili** alla griglia dei pulsanti nella pagina **Transazione**. In questo modo, un addetto alle vendite può selezionare una riga di transazione e quindi selezionare il pulsante per mostrare tutti gli sconti disponibili per la riga selezionata. L'addetto alle vendite può anche selezionare un'altra scheda per mostrare gli sconti applicabili all'intera transazione. È importante notare che **Visualizza sconti disponibili** non mostra gli sconti che sono già applicati sulla riga di vendita perché le informazioni sullo sconto sono già visualizzate sulla riga di vendita. Lo scopo di questo scenario è mostrare solo gli sconti non ancora applicati. L'eccezione è costituita dagli sconti applicati in base a un buono sconto contrassegnato come "Applica senza un codice buono sconto". In questo modo l'addetto alle vendite può rimuovere facilmente il buono sconto applicato.

La pagina **Tutti gli sconti** mostra solo gli sconti che non competono con nessuno degli sconti applicati. Questo comportamento aiuta a garantire che, se un addetto alle vendite informa un cliente di uno sconto e il cliente intraprende l'azione richiesta (ad esempio, il cliente acquista un altro articolo per ottenere uno sconto del 10%), lo sconto viene applicato alla transazione. Gli sconti basati su buono sconto vengono visualizzati solo quando l'opzione **Applica senza buono sconto** è attivata.

In un semplice scenario in cui tutti gli sconti hanno la stessa priorità, la modalità di concorrenza degli sconti è **Composti** e il controllo della concorrenza dello sconto è impostato su **Il miglior prezzo e composto in base alla priorità, mai composto tra le priorità**, la pagina **Tutti gli sconti** mostra tutti gli sconti disponibili per un prodotto, perché tutti gli sconti sono composti e non competono tra loro.

Le seguenti illustrazioni mostrano la logica che determina quali sconti sono mostrati negli scenari avanzati, come uno scenario in cui la modalità di concorrenza degli sconti è **Miglior prezzo** o **Esclusivo** e vengono utilizzate due o più priorità. In questi scenari, gli sconti visualizzati vengono ulteriormente influenzati in base all'impostazione del controllo della concorrenza degli sconti su **Il miglior prezzo e composto in base alla priorità, mai composto tra le priorità** o **Il miglior prezzo solo in base alla priorità, sempre composto tra le priorità**.

La seguente illustrazione mostra la logica utilizzata quando il controllo della concorrenza degli sconti è impostato su **Il miglior prezzo e composto in base alla priorità, mai composto tra le priorità**.

![Logica per il miglior prezzo e composto in base alla priorità, mai composto tra le priorità.](./media/Model_1.png "Logica per il miglior prezzo e composto in base alla priorità, mai composto tra le priorità").

La seguente illustrazione mostra la logica utilizzata quando il controllo della concorrenza degli sconti è impostato su **Il miglior prezzo solo in base alla priorità, sempre composto tra le priorità**.

![Logica per il miglior prezzo solo in base alla priorità, sempre composto tra le priorità.](./media/Model_2.png "Logica per il miglior prezzo solo in base alla priorità, sempre composto tra le priorità").


[!INCLUDE[footer-include](../includes/footer-banner.md)]
