---
title: Sincronizzazione dei controlli delle operazioni dei clienti nelle sedi centrali
description: Questo articolo spiega come controllare la sincronizzazione dei controlli delle operazioni dei clienti in Microsoft Dynamics 365 Commerce headquarters per aiutare a risolvere eventuali problemi degli utenti del sito.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-28
ms.openlocfilehash: c615b0b436e01a1423b5611a72f0056b5b14f8e8
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691088"
---
# <a name="audit-synchronization-of-customer-operations-in-headquarters"></a>Sincronizzazione dei controlli delle operazioni dei clienti nelle sedi centrali

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Questo articolo spiega come controllare la sincronizzazione dei controlli delle operazioni dei clienti in Microsoft Dynamics 365 Commerce headquarters per aiutare a risolvere eventuali problemi degli utenti del sito.

Man mano che le organizzazioni iniziano ad adottare la capacità di creare e modificare i clienti in modo asincrono, gli amministratori del sito hanno bisogno di un modo per visualizzare e risolvere i problemi delle operazioni, in base alle richieste degli utenti del sito o agli errori di elaborazione. In questi scenari, gli amministratori del sito devono essere in grado di controllare la creazione dei clienti e le operazioni di modifica e correggere eventuali errori utilizzando un modello self-service.

## <a name="customer-synchronization-status"></a>Stato di sincronizzazione clienti

Quando scegli la modalità sincrona di gestione dei clienti e le funzionalità corrispondenti, gli amministratori di Commerce headquarters devono creare e pianificare un processo batch ricorrente per il **processo P**, il processo **Sincronizza clienti e partner commerciali dalla modalità asincrona** e il processo **1010**, in modo che qualsiasi cliente asincrono sia convertito in cliente sincrono in Commerce headquarters. La sincronizzazione delle operazioni di gestione dei clienti avviene ogni volta che vengono eseguiti questi processi. Per ulteriori informazioni, vedi [Modalità di creazione dei clienti asincrona](async-customer-mode.md).

In qualità di imprenditore, puoi eseguire le seguenti operazioni:

- Visualizza tutte le operazioni di creazione/modifica degli utenti del sito. I dettagli includono lo stato e un timestamp.
- Filtra le operazioni utilizzando qualsiasi campo e valore della tabella cliente per restringere il registro di controllo.
- Visualizza brevi descrizioni delle modifiche insieme ai dettagli sullo stato per comprendere le operazioni ad alto livello.
- In caso di errori, modifica e correggi i campi problematici, quindi salva e sincronizza le operazioni specifiche del cliente.

### <a name="elements-on-the-customer-synchronization-status-page"></a>Elementi nella pagina di stato Sincronizzazione cliente

Per visualizzare un elenco di tutte le operazioni di sincronizzazione, in Commerce headquarters, vai a **Commerce and Retail \> Clienti \> Stato di sincronizzazione del cliente**. L'illustrazione seguente mostra un esempio della pagina **Stato di sincronizzazione clienti**.

![Pagina di stato della sincronizzazione dei clienti in Commerce headquarters.](media/D365-Commerce-Customer-Mgmt-Audi-Async-Operations.png)

Per impostazione predefinita, l'elenco delle operazioni di sincronizzazione dei clienti sul lato sinistro della pagina **Stato di sincronizzazione clienti** include le seguenti colonne:

- Nome canale
- Conto cliente
- Conto cliente asincrono
- Timestamp operazioni
- Stato di sincronizzazione clienti

L'angolo in alto a destra della pagina mostra i dettagli del conto clienti, ad esempio i valori **Conto cliente**, **Operazione Retail Async**, **Stato di sincronizzazione clienti** e **Ultimo errore conosciuto**.

La sezione **Descrizione della modifica** contiene una descrizione del tipo di operazione di gestione del cliente eseguita (ad esempio, creazione del cliente, aggiornamento dell'account o errore di sincronizzazione con i dettagli).

La sezione **Attributi cliente** contiene una griglia che mostra tutti gli attributi del cliente, insieme ai valori vecchi e nuovi. Puoi modificare questa sezione se desideri modificare i valori degli attributi del cliente per correggere i bug, quindi sincronizzare di nuovo.
