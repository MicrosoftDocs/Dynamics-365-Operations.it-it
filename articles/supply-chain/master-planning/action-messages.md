---
title: Messaggi d'azione
description: Un messaggio di azione è un suggerimento generato dal sistema per modificare un ordine pianificato o stabilizzato.
author: t-benebo
ms.date: 03/18/2022
ms.topic: article
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: e6df6cfd038383b3eeaa3659e0af3e469429f81e
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570256"
---
# <a name="action-messages"></a>Messaggi d'azione

[!include [banner](../includes/banner.md)]

Un messaggio di azione è un suggerimento generato dal sistema per modificare un ordine pianificato,approvato o stabilizzato.

I messaggi di azione sono generati dal calcolo della pianificazione generale in seguito alle richieste modificate. Ad esempio, la data di spedizione o la quantità viene modificata in un ordine cliente dopo che è già stato creato un ordine fornitore per soddisfare la domanda di tale ordine cliente. In questo caso, il calcolo della pianificazione generale genera uno o più messaggi di azione che suggeriscono di aggiornare l'ordine fornitore. È quindi possibile decidere se effettuare le modifiche suggerite.

La modalità di calcolo dei messaggi d'azione può essere configurata per un gruppo di copertura collegato a un articolo.

## <a name="select-action-messages"></a>Selezione dei messaggi d'azione

Nella pagina **Gruppi di copertura**, è possibile selezionare i messaggi di azione che si desidera vengano generati dal sistema e i gruppi di copertura o gli articoli a cui i messaggi si riferiscono. La tabella seguente elenca il messaggio di azione che puoi selezionare.

| Messaggio | Description |
|---|---|
| Anticipa | Il sistema genera messaggi di azione, quando necessario, per spostare gli ordini a una data precedente. Nel campo **Margine di avanzamento** è possibile specificare il numero massimo di giorni tra l'entrata e l'uscita senza azioni di anticipo. |
| Posticipa | Il sistema genera messaggi di azione, quando necessario, per spostare gli ordini a una data successiva. Nel campo **Margine di posticipo** è inoltre possibile specificare il numero massimo di giorni tra l'entrata e l'uscita senza azioni di posticipo. |
| Svaluta | Il sistema genera i messaggi di azione quando gli ordini di produzione, gli ordini fornitore e altre transazioni in entrata devono essere diminuiti per impedire livelli di scorte in eccesso. |
| Incremento | Il sistema genera i messaggi di azione quando gli ordini di produzione, gli ordini fornitore e altre transazioni in entrata devono essere aumentati per impedire mancanze di scorte in inventario. |
| Azioni derivate | I messaggi di azione creati per le transazioni di entrata verranno propagati a tutti i requisiti derivati e verranno generati i messaggi di azione necessari per le transazioni di entrata che soddisfano tali requisiti. |

Le seguenti sezioni forniscono alcuni scenari dettagliati.

## <a name="increase-and-decrease-actions-with-product-default-order-quantities"></a>Aumentare e ridurre le azioni con le quantità dell'ordine predefinito del prodotto

Nella pagina **Impostazioni ordine predefinite** per un articolo, è possibile impostare una quantità minima dell'ordine, una quantità massima dell'ordine e più valori. Il sistema tiene quindi conto di queste impostazioni quando suggerisce azioni, per garantire che i suggerimenti non causino mai una fornitura insufficiente.

Ad esempio, hai un articolo che ha le seguenti impostazioni nella pagina **Impostazioni ordine predefinite**:

- **Quantità minima ordine:** *0*
- **Quantità massima ordine:** *90*
- **Multiplo:** *20*

Se è presente una domanda per una quantità di 60 di questo articolo, la pianificazione generale creerà un ordine fornitore pianificato per una quantità di 60. Se la domanda viene aumentata di 30, la pianificazione generale suggerirà un aumento di 40, perché rispetterà il multiplo di 20 e non causerà mai una fornitura insufficiente.

## <a name="action-messages-for-orders-related-to-safety-stock"></a>Messaggi di azione per ordini relativi alle scorte di sicurezza

I messaggi di azione per gli ordini che forniscono scorte di sicurezza non suggeriranno mai di ridurre la quantità al di sotto della quantità necessaria per le scorte di sicurezza. In altre parole, se è presente un ordine che fornisce scorte di sicurezza e la domanda dei clienti e la domanda viene ridotta o annullata, la pianificazione generale suggerirà di ridurre l'ordine pianificato in base alla diminuzione della domanda. Tuttavia, non suggerirà mai un valore inferiore alla scorta di sicurezza necessaria.

Il sistema non suggerirà di posticipare le azioni per la fornitura della scorta di sicurezza, poiché si presume che la scorta di sicurezza debba essere fornita all'ora e alla data richiesta.

### <a name="advance-and-postpone-actions-related-to-boms"></a>Anticipare e posticipare le azioni relative alle distinte base

Le azioni correlate ai componenti delle distinte base (DBA) devono essere applicate prima delle azioni dei relativi articoli principali, poiché potrebbero essere interessati ulteriori ordini correlati a distinte base di livello superiore. È quindi necessario eseguire nuovamente la pianificazione generale per ricalcolare e suggerire le azioni appropriate.

Per esempio, ha la seguente situazione:

- Bene finale *FG* di tipo *produzione* ha una distinta base che include la materia prima *RM*.
- La data di oggi è il 21 gennaio.
- Un ordine di produzione esistente e rilasciato per *FG* è previsto per il 25 gennaio.
- Per supportare l'ordine di produzione esistente, la pianificazione generale ha creato un ordine fornitore pianificato per la materia prima richiesta *RM*. Questo ordine ha una data richiesta del 25 gennaio.
- Oggi viene creato un nuovo ordine cliente per *FG*. Ha una data richiesta di oggi (21 gennaio).
- Il 21 gennaio è chiusa per la consegna nel calendario di *RM*, ma il 22 gennaio è aperto.

Quando viene eseguita la pianificazione generale, vengono generati messaggi di azione anticipata che suggeriscono di aumentare la produzione programmata in precedenza in modo da poter evadere l'ordine odierno.

- Per soddisfare la nuova domanda, suggerisce di spostare l'ordine di produzione per *FG* al 21 gennaio. Fornisce questo suggerimento senza considerare la data di chiusura per *RM*.
- Perché *RM* è ancora necessario per l'ordine di produzione, suggerisce di anticipare anche l'ordine fornitore pianificato. Tuttavia, questa volta, controlla il calendario *RM*. Pertanto, suggerisce di spostare l'ordine di acquisto pianificato per *RM* al 22 gennaio (perché il 21 gennaio è chiuso).

Come puoi vedere, la materia prima richiesta *RM* ora arriverà troppo tardi per la produzione programmata di *FG*. Pertanto, è necessario prima applicare l'azione anticipata all'ordine fornitore pianificato per *RM* e quindi eseguire nuovamente la pianificazione generale. A quel punto, la pianificazione generale genererà un nuovo messaggio di azione che suggerisce di spostare l'ordine di produzione *FG* al 22 gennaio.
