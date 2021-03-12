---
title: Riconciliazione finanziaria nei punti vendita al dettaglio
description: Questo argomento descrive la riconciliazione finanziaria nei punti vendita al dettaglio per POS per Microsoft Dynamics 365 Commerce.
author: anpurush
manager: AnnBe
ms.date: 06/09/2020
ms.topic: article
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
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8ddefcdc2b2bbb5fe25e9a87396802cbbbfef72c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965079"
---
# <a name="financial-reconciliation-in-retail-stores"></a>Riconciliazione finanziaria nei punti vendita al dettaglio

[!include [banner](includes/banner.md)]

In Microsoft Dynamics 365 Commerce versione 10.0.10 e precedenti, la funzionalità che il client point of sale (POS) fornisce per i processi di fine giornata nei punti vendita al dettaglio, consente agli addetti e ai responsabili del punto vendita di eseguire le operazioni di fine giornata. Ad esempio, possono eseguire riepiloghi incassi, chiusure forzate turno, riconciliare transazioni di turni e turni di chiusura. Tuttavia, in POS non è possibile finalizzare le informazioni finanziarie per i turni, in modo che possano essere utilizzate per pubblicare i dati finanziari in Commerce headquarters. In genere, i responsabili del punto vendita sono responsabili del completamento di questa attività. Prima di poter approvare un turno, devono rivedere le informazioni, apportare le correzioni necessarie e finalizzare i totali per quel turno. I totali finalizzati dovrebbero quindi essere registrati nei moduli finanziari in Commerce headquarters.

Inoltre, in Commerce versione 10.0.10 e precedenti, i responsabili del punti vendita possono rivedere e apportare alcune modifiche alle righe delle dichiarazioni in Commerce headquarters. Tuttavia, la funzionalità è limitata e i responsabili dei punti vendita raramente hanno accesso al client di Commerce headquarters. Inoltre, la revisione e l'adeguamento dei rendiconti finanziari di vendita al dettaglio possono essere effettuate solo quando i rendiconti vengono creati in Commerce headquarters. Tuttavia, tale processo è in genere un processo notturno. Pertanto, i responsabili dei punti vendita devono attendere l'approvazione del turno quando vengono creati i rendiconti finanziari di vendita al dettaglio in Commerce headquarters.

In Commerce versione 10.0.11 e successive, i responsabili dei punti vendita possono rivedere, regolare e finalizzare i loro turni nel client POS stesso. Tali dati vengono quindi utilizzati per creare e pubblicare rendiconti finanziari di vendita al dettaglio in Commerce headquarters.

> [!NOTE]
> La funzionalità correlata alla riconciliazione finanziaria nei punti vendita al dettaglio funziona solo se è attivata la creazione di ordini basata sui feed di mantenimento. Per altre informazioni, vedi [Creazione di ordini basata su inserimento continuo per le transazioni punto vendita al dettaglio](trickle-feed.md).

## <a name="set-up-financial-reconciliation"></a>Impostare la riconciliazione finanziaria

Attieniti alla seguente procedura per utilizzare la funzionalità di riconciliazione finanziaria.

1. Nell'area di lavoro **Gestione funzionalità**, abilita la funzionalità **Rendiconti di vendita al dettaglio (inserimento continuo)**.
1. Nel profilo di funzionalità POS per il punto vendita appropriato, imposta l'opzione **Abilita riconciliazione finanziaria nel punto vendita** su **Sì**.

## <a name="more-information-about-financial-reconciliation"></a>Altre informazioni sulla riconciliazione finanziaria

Quando la funzionalità di riconciliazione finanziaria è attivata, alcuni dei parametri definiti nella Scheda dettaglio **Dichiarazione/chiusura** della pagina **Punti vendita al dettaglio** di Commerce headquarters vengono sincronizzati con il database del canale. Viene applicata la stessa serie di criteri di calcolo e soglie di importo utilizzati per i rendiconti di vendita al dettaglio.

Quando viene richiamata l'operazione **Chiusura turno**, il sistema convalida che gli importi calcolati dal sistema e gli importi dichiarati corrispondano. Se differiscono e la differenza supera le soglie definite, viene inviata una richiesta all'utente che può apportare le modifiche necessarie.

Le rettifiche possono essere effettuate per ogni pagamento. Quando viene selezionato un pagamento, l'utente può visualizzare i totali per diversi tipi di transazione e modificare i totali per un tipo di transazione specifico. Durante la modifica, il sistema mostra l'importo calcolato originale e l'importo sovrascritto per quel tipo di transazione. L'utente può anche acquisire note come parte del processo di modifica. Le note possono essere utilizzate a fini di controllo.

Gli utenti possono ignorare i messaggi e le richieste di convalida e possono procedere alla chiusura del turno. Tuttavia, se un utente ignora le richieste di convalida, sorgeranno gli stessi problemi e dovranno essere risolti quando il turno pubblica i rendiconti finanziari in Commerce headquarters.

L'operazione **Chiusura turno** in POS convalida inoltre che tutte le transazioni nel database offline siano sincronizzate con il database del canale. Se le transazioni non sono sincronizzate, l'utente riceve un messaggio di avviso, poiché questa situazione può causare un calcolo errato degli importi del sistema. In questa situazione, l'utente può terminare l'operazione **Chiusura turno** e provare a sincronizzare le transazioni offline con il database del canale. In alternativa, l'utente può rettificare manualmente gli importi calcolati dal sistema per tenere conto delle transazioni che non sono sincronizzate, in modo da finalizzare e registrare l'insieme corretto di numeri finanziari. 

Quando viene utilizzata la registrazione del rendiconto a inserimento continuo, in modo che la registrazione delle transazioni sia separata dalla registrazione dei dati finanziari, è possibile scegliere di rettificare gli importi calcolati dal sistema per le transazioni offline mancanti. In questo modo, si garantisce che i dati finanziari siano sempre contabilizzati e registrati correttamente, indipendentemente dalle transazioni mancanti. Le transazioni offline possono essere sincronizzate con il database del canale e con Commerce headquarters e successivamente registrate, separatamente dalle registrazioni finanziarie.

I dettagli della riconciliazione finanziaria per un turno sono sincronizzati in Commerce headquarters utilizzando il processo P.

I rendiconti finanziari di vendita dettaglio in Commerce headquarters non calcolano i totali per mostrare i dettagli nelle righe dei rendiconti. Al contrario, gli importi finalizzati nel client POS vengono utilizzati per creare e registrare rendiconti finanziari di vendita al dettaglio.
