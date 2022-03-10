---
title: Creazione di ordini basata su inserimento continuo per le transazioni punto vendita al dettaglio
description: In questo argomento viene descritta la creazione di ordini basata su inserimento continuo per le transazioni punto vendita in Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 67b66cd4bf2a77f3ab7f33f691156e38cc13770a
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "7964631"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>Creazione di ordini basata su inserimento continuo per le transazioni punto vendita al dettaglio

[!include [banner](includes/banner.md)]

In Microsoft Dynamics 365 Commerce versione 10.0.5 e successive, si consiglia di eseguire la transizione di tutti i processi di registrazione dei rendiconti ai processi di registrazione dei rendiconti basata su inserimento continuo. L'uso della funzionalità basata su inserimento continuo è associato a prestazioni elevate e vantaggi aziendali. Le transazioni di vendita vengono elaborate durante l'intera giornata. L'elaborazione delle transazioni di gestione cassa e metodi di pagamento viene eseguita sul rendiconto finanziario a fine giornata. La funzionalità basata su inserimento continuo consente l'elaborazione continua di ordini cliente, fatture e pagamenti. Inventario, ricavi e pagamenti possono vengono aggiornati e riconosciuti quasi in tempo reale.

## <a name="use-trickle-feed-based-posting"></a>Usare la registrazione basata su inserimento continuo

> [!IMPORTANT]
> Prima di abilitare la registrazione basata su inserimento continuo, è necessario assicurarsi che non siano presenti rendiconti calcolati e non registrati. Registrare tutti i rendiconti prima di abilitare la funzionalità. È possibile controllare la disponibilità di rendiconti aperti nell'area di lavoro **Dati finanziari punto vendita**.

Per abilitare la registrazione basata su inserimento continuo delle transazioni di vendita al dettaglio, abilitare la funzionalità **Rendiconti di vendita al dettaglio (inserimento continuo)** nell'area di lavoro **Gestione funzionalità**. I rendiconti verranno suddivisi in due tipi: rendiconti transazionali e rendiconti finanziari.

### <a name="transactional-statements"></a>Rendiconti transazionali

L'elaborazione dei rendiconti transazionali deve essere eseguita con una frequenza elevata durante il giorno, in modo che i documenti vengano creati quando le transazioni vengono caricate in Commerce Headquarters. Le transazioni vengono caricate dai punti vendita in Commerce Headquarters quando si esegue il **processo P**. È anche necessario eseguire il processo **Convalida transazioni punto vendita** per convalidare le transazioni, che potranno pertanto essere rilevate tramite il rendiconto transazionale.

Programmare una frequenza di esecuzione elevata per i processi:

- Per calcolare un rendiconto transazionale, eseguire il processo **Calcola rendiconti transazionali in batch** (**Retail e Commerce \> Retail e Commerce IT \> Registrazione POS \> Calcola rendiconti transazionali in batch**). Questo processo rileverà tutte le transazioni non registrate e convalidate e le aggiungerà a un nuovo rendiconto transazionale.
- Per registrare rendiconti transazionali, eseguire il processo **Registra rendiconti transazionali in batch** (**Retail e Commerce \> Retail e Commerce IT \> Registrazione POS \> Registra rendiconti transazionali in batch**). Questo processo eseguirà il processo di registrazione e creerà ordini cliente, fatture di vendita, giornali di registrazione pagamenti, giornali di registrazione sconti e transazioni ricavi/spese per i rendiconti non registrati che non contengono errori. 

### <a name="financial-statements"></a>Rendiconti finanziari

Il processo di elaborazione dei rendiconti finanziari deve essere eseguito a fine giornata. L'elaborazione di questo tipo di rendiconto supporta solo il metodo di chiusura **Turno** e rileverà esclusivamente i turni chiusi. I rendiconti sono limitati alla riconciliazione finanziaria. Verranno creati solo i giornali di registrazione per gli importi di differenza tra l'importo conteggiato e l'importo della transazione dei metodi di pagamento e i giornali di registrazione per altre transazioni di gestione di cassa.

I rendiconti finanziari consentono inoltre di esaminare le transazioni di riepilogo incassi, pagamento, metodo di pagamento bancario e pagamento in cassaforte. La pagina dei dettagli di pagamento è visibile solo quando viene selezionato un rendiconto finanziario.

![Immagine che mostra la sezione dei dettagli di pagamento del modulo dei rendiconti registrati solo quando viene selezionato un rendiconto finanziario.](./media/Trickle-feed-posted-statements-transaction-view.png)

Programmare l'ora di inizio e di fine dei seguenti processi di rendiconto finanziario in base alla fine giornata prevista:

- Per calcolare un rendiconto finanziario, eseguire il processo **Calcola rendiconti finanziari in batch** (**Retail e Commerce \> Retail e Commerce IT \> Registrazione POS \> Calcola rendiconti finanziari in batch**). Questo processo raccoglierà tutte le transazioni finanziarie non registrate e le aggiungerà a un nuovo rendiconto finanziario.
- Per registrare i rendiconti finanziari in un batch, eseguire il processo **Registra rendiconti finanziari in batch** (**Retail e Commerce \> Retail e Commerce IT \> Registrazione POS \> Registra rendiconti finanziari in batch**).

### <a name="manually-create-statements"></a>Creare manualmente i rendiconti

I rendiconti di tipo finanziario e transazionale possono anche essere creati manualmente. 

1. Andare a **Retail e Commerce \> Canali \> Punti vendita** e selezionare **Rendiconti**. 
2. Selezionare **Nuovo** e quindi selezionare il tipo di rendiconto da creare. I campi nella pagina **Rendiconti** mostreranno i dati relativi al tipo di rendiconto selezionato, mentre le azioni nel gruppo **Rendiconto** indicheranno le azioni pertinenti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
