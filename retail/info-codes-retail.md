---
title: Codici informativi
description: Questo articolo fornisce una panoramica sui codici informazioni, sui gruppi di codici informazioni e su come utilizzarli.
author: mumani
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 22761
ms.assetid: 99877dba-a6e3-4d88-ba0a-ee5913aea17e
ms.search.region: global
ms.search.industry: Retail
ms.author: sijoshi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: aaf02ce5bf3af94dea12344c9bfc5c8e9be7abb9
ms.contentlocale: it-it
ms.lasthandoff: 04/26/2017


---

# <a name="info-codes"></a>Codici informativi

[!include[banner](includes/banner.md)]


Questo articolo fornisce una panoramica sui codici informazioni, sui gruppi di codici informazioni e su come utilizzarli.

I codici di informazioni offrono all'utente una modalità di acquisizione dei dati in un registratore di cassa POS. È possibile utilizzare i codici di informazioni per suggerire al cassiere di inserire le informazioni nelle varie azioni nel POS, ad esempio le vendite dell'articolo, i resi articolo o la selezione dei clienti. I cassieri possono selezionare l'input da un elenco o inserirlo come codice, numero, data o testo. È possibile assegnare codici di informazione ad azioni predefinite del punto vendita, articoli al dettaglio, metodi di pagamento, clienti o attività POS specifiche. È possibile utilizzare i codici informativi per effettuare le operazioni riportate di seguito:
-   Acquisire informazioni aggiuntive durante la transazione, ad esempio il numero di un volo o il motivo di un reso.
-   Fare in modo che il cassiere selezioni il prezzo da un elenco di prezzi per prodotti specifici.
-   Collegare un codice secondario a un codice informativo in modo che il cassiere debba immettere ulteriori informazioni durante l'esecuzione di un'attività specifica. Ad esempio, quando un cliente restituisce un prodotto, è possibile suggerire al cassiere di richiedere perché il prodotto è stato restituito. È quindi possibile utilizzare i sottocodici per visualizzare un elenco dei motivi tra cui il cassiere può scegliere.
-   Effettuare la vendita di un prodotto come una vendita normale, una vendita scontata o un prodotto gratuito.
-   Fare in modo che il cassiere immetta un valore o lo selezioni da un elenco di sottocodici quando viene aperto il cassetto del registratore senza eseguire un'operazione di vendita.

## <a name="info-codes-group-in-retail-and-commerce"></a>Gruppo di codici delle informazioni in Vendita al dettaglio e commercio
In Dynamics 365 for Operations - Retail,, è possibile creare gruppi di codici di informazioni. I gruppi di codici informativi aggiungono flessibilità consentendo di definire meno codici informativi e quindi utilizzandoli modi più versatili. È possibile utilizzare i gruppi di codici informativi nei modi seguenti:
-   Definire meno codici informativi e riutilizzarli facilmente. I codici di informazioni che vengono inclusi nei gruppi dei codici informativi non hanno dipendenze predefinite in altri codici informativi. È possibile includere lo stesso codice informativo in più gruppi di codici informativi e quindi utilizzare la priorità per presentare gli stessi codici informativi nell'ordine significativo in qualsiasi specifica situazione.
-   Collegare i codici informativi ad altri codici informativi o a gruppi di codici informativi per raccogliere informazioni su un prodotto o una transazione senza dover definire un codice informativo separato o un codice informativo collegato per ogni scenario.

## <a name="info-code-examples"></a>Esempi di codici informativi
**Esempio 1: riutilizzare i codici informativi** È possibile collegare i codici informativi in modo che quando un codice informativo viene attivato, ne viene attivato immediatamente un altro successivamente. Ad esempio, quando vengono venduti determinati prodotti, è possibile suggerire al cassiere di chiedere al cliente se desidera acquistare le batterie e una garanzia del prodotto. Per altri prodotti, è possibile suggerire al cassiere di chiedere al cliente se desidera acquistare le batterie e anche registrare il codice postale. Se si creano codici informativi collegati per questi scenari, è necessario impostare ogni variazione del codice informativo in modo da richiedere al cassiere le giuste informazioni. Se si utilizzano gruppi di codici informativi, codici informativi comuni, ad esempio la richiesta di batterie, possono essere impostati una volta e quindi riutilizzati in più gruppi di codici informativi. È inoltre possibile utilizzare la priorità nei gruppi di codici informativi per identificare l'ordine in cui vengono visualizzate le richieste.


**Esempio 2: collegare i codici informativi ai gruppi di codici informativi** Quando si vendono alcuni prodotti, ad esempio i dispositivi mobili, si desidera sempre raccogliere un set specifico di informazioni, ad esempio il numero di telefono, l'identificatore per l'attrezzatura mobile (MEID) e il numero di serie. Tuttavia, si desidera inoltre raccogliere informazioni diverse per un tablet rispetto a un telefono cellulare. È possibile impostare un gruppo di codici informativi che includa le richieste del numero di telefono, del MEID e del numero di serie e quindi collegare il gruppo di codici informativi a un singolo codice informativo. Quando il codice informativo specifico del prodotto viene attivato, il gruppo del codici informativo può essere attivato successivamente per consentire di raccogliere i dati comuni senza dover definire più insiemi di codici informativi collegati per ogni dispositivo.

 



