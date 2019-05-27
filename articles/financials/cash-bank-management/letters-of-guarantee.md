---
title: Lettere di garanzia
description: Questo articolo fornisce informazioni sulle lettere di garanzia. In una lettera di garanzia, una banca accetta di pagare una somma di denaro specifica a una persona se uno dei clienti della banca non adempie a un pagamento o a un obbligo nei confronti di tale persona.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3146a4a910a76c21ca8c65d52748ede61220b964
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563811"
---
# <a name="letters-of-guarantee"></a>Lettere di garanzia

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sulle lettere di garanzia. In una lettera di garanzia, una banca accetta di pagare una somma di denaro specifica a una persona se uno dei clienti della banca non adempie a un pagamento o a un obbligo nei confronti di tale persona. 

La lettera di garanzia è un contratto con cui una banca (garante) si impegna a pagare una somma di denaro concordata a una persona (beneficiario) se un cliente della banca (committente) non adempie a un pagamento o a un obbligo nei confronti del beneficiario. Le lettere di garanzia non sono trasferibili. Si applicano solo al beneficiario nominato nel contratto. Il committente può richiedere un aumento o una diminuzione del valore di una lettera di garanzia, a seconda dei termini del contratto. 

Per liquidare una lettera di garanzia, il beneficiario deve inviare la lettera di garanzia originale e informare la banca dell'inadempienza del committente prima della data di scadenza. La banca paga quindi l'importo dovuto sul conto del beneficiario, in base ai termini previsti nella lettera di garanzia. La banca accantona una percentuale del pagamento come margine. La percentuale viene concordata e specificata nei termini del contratto. 

È possibile creare un codice per tenere traccia dello scopo di una lettera di garanzia. È inoltre possibile specificare i motivi che possono essere associati a una lettera di garanzia quando quest'ultima viene annullata. È possibile visualizzare i codici dello scopo e i motivi bancari nelle pagine **Codici scopo pagamento** e **Motivi bancari**. 

È possibile utilizzare la pagina **Lettera di garanzia** per completare queste attività:

-   Creare voci di contabilità generale corrette ed eliminare voci manuali.
-   Registrare tutte le transazioni monetarie e non monetarie e tenere traccia dei saldi delle lettere di garanzia.
-   Registrare e tenere traccia dello stato e della scadenza delle lettere di garanzia.
-   Generare un report in cui sono elencate le banche con lettere di garanzia.

Nella tabella riportata di seguito vengono descritte le azioni che è possibile svolgere su una lettera di garanzia.

| Azione              | Scopo                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| Invia a banca      | Consente di inviare la richiesta di lettera di garanzia alla banca.                                                                       |
| Ricevi da banca   | Dopo l'approvazione da parte della banca della richiesta inviata, consente di ritirare la lettera di garanzia dalla banca.                            |
| Assegna al beneficiario | Dopo la ricezione della lettera di garanzia dalla banca, consente di consegnare la lettera al beneficiario.              |
| Aumenta valore      | Se concordato tra il beneficiario e il committente, consente di aumentare il valore monetario.                                                  |
| Diminuisci valore      | Se concordato tra il beneficiario e il committente, consente di diminuire il valore monetario.                                                  |
| Proroga              | Dopo la consegna della lettera di garanzia al beneficiario, estendere il periodo di validità, se è necessaria un'estensione. |
| Annulla              | Quando decade lo scopo per cui è stata richiesta la lettera di garanzia, annullare il contratto.                  |
| Liquida           | Quando il beneficiario presenta la lettera di garanzia alla banca, consente di liquidare la lettera di garanzia.                      |


Per ulteriori informazioni, vedere i seguenti argomenti:

[Transazione lettera di garanzia](tasks/letter-guarantee-transaction.md)

[Impostare le linee di credito bancarie e i profili registrazione per le lettere di garanzia](tasks/set-up-bank-facilities-posting-profiles.md)


