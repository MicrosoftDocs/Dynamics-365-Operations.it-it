---
title: Programmare piani di manutenzione
description: In questo argomento viene descritto come programmare piani di manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6b6e5bde83474fe8971e482af518f7cee23a2220
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875731"
---
# <a name="schedule-maintenance-plans"></a>Programmare piani di manutenzione

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

La programmazione della manutenzione preventiva genera voci di calendario nei cespiti, in base ai piani di manutenzione impostati nei cespiti. È possibile programmare voci di calendario in base a piani di manutenzione, tipi di cespite e cespiti selezionati.

1. Fare clic su **Gestione cespiti** > **Periodico** > **Manutenzione preventiva** > **Programma piani di manutenzione**.

2. È possibile selezionare un intervallo di tempo nei campi **Periodo** e **Frequenza periodo**.

>[!NOTE]
>I campi **Periodo** e **Frequenza periodo** indicano fino a quale data futura si intende creare le righe di programma di manutenzione, in base ai piani di manutenzione creati (tempo o contatore). Nella figura seguente, le righe di programma di manutenzione (= proposte di ordini di lavoro) vengono create a partire dalla data corrente e per i tre mesi successivi.

3. Impostare l'interruttore **Crea automaticamente se specificato nella riga** su "Sì" se gli ordini di lavoro devono essere creati automaticamente in base alla riga di piano di manutenzione.

>[!NOTE]
>Se questo interruttore è impostato su "Sì" *e* anche la casella di controllo **Crea automaticamente** è selezionata nelle righe di piano di manutenzione in **Piani di manutenzione**, gli ordini di lavoro vengono creati in base alle righe di piano di manutenzione e vengono create anche righe di programma di manutenzione con lo stato "Ordine di lavoro creato". Se si seleziona una sola opzione (l'interruttore **Crea automaticamente se specificato nella riga** in questa finestra di dialogo o la casella di controllo **Crea automaticamente** nel modulo **Piani di manutenzione**), solo le righe di programma di manutenzione vengono create con lo stato "Creata". In tal caso, non viene creato alcun ordine di lavoro.

4. È possibile generare voci di calendario basate su piani di manutenzione (tempo o contatore), cespiti, tipi di cespite, unità funzionali e tipi di unità funzionali. Fare clic sul pulsante **Filtro** ed effettuare le selezioni come necessario.

- In relazione alla programmazione dei piani di manutenzione nelle unità funzionali: se si aggiorna l'impostazione di tipi di cespite, produttori e modelli nei piani di manutenzione in **Tutte le unità funzionali** > Scheda dettaglio **Piani di manutenzione** dopo avere programmato i piani di manutenzione, le voci del programma di manutenzione esistenti correlate a tale unità funzionale vengono eliminate automaticamente. Per creare nuove voci di calendario, corrispondenti all'impostazione aggiornata del piano di manutenzione per l'unità funzionale, è necessario eseguire una nuova programmazione del piano di manutenzione per tale unità funzionale. Per ulteriori informazioni sull'impostazione di tipi di cespite, produttori e modelli nelle unità funzionali, vedere [Creare unità funzionali](../functional-locations/create-functional-locations.md).

>*Esempio:* si desidera creare un piano di manutenzione per un'unità funzionale specifica, di modo che tutti i cespiti impostati in quell'unità funzionale in qualsiasi momento saranno inclusi quando si programma il piano di manutenzione. In tal caso, si crea un piano di manutenzione e si seleziona l'unità funzionale specifica, ma NON si aggiungono oggetti al piano di manutenzione. Il risultato è che quando si programma quel piano di manutenzione, le righe di programma di manutenzione verranno create per tutti i cespiti associati all'unità funzionale in quel momento.

- Se si apportano modifiche a tipi di cespite, produttori e modelli in **Tipi di cespite**, quelle modifiche interessano solo i nuovi cespiti che utilizzano il tipo di cespite aggiornato. Per ulteriori informazioni sull'impostazione dei tipi di cespite, leggere [Tipi di cespite](../setup-for-objects/object-types.md).  

5. Fare clic su **OK** per avviare la generazione delle voci del programma di manutenzione nei cespiti. Le voci generate saranno visualizzate nella pagina elenco **Tutti i programmi di manutenzione**.

![Figura 1](media/09-preventive-maintenance.png)

- Nella finestra di dialogo **Programma piani di manutenzione**, è possibile impostare processi batch nella Scheda dettaglio **Esecuzione in background** per generare automaticamente voci di calendario ad intervalli regolari.  
- Quando si programma la manutenzione preventiva, le righe di programma di manutenzione la cui data e ora di inizio previste sono antecedenti alla data e all'ora di sistema non verranno create.  

La figura seguente fornisce un'illustrazione grafica di un calcolo del piano di manutenzione basato su tempo.  

![Figura 2](media/10-preventive-maintenance.jpg)

Riguardo ai piani di manutenzione basati su contatore: nelle figure seguenti, sono visualizzati due differenti cicli di registrazione contatore. Questi sono basati su un piano di manutenzione impostato per il cespite "V0001", dove la percorrenza prevista del cespite (un'auto) è approssimativamente di 2.000 km ogni mese.

Nel primo esempio, i 2.000 km previsti non vengono raggiunti ogni mese. Secondo il piano di manutenzione basato su contatore, la soglia è di 2.000 km; ciò significa che quando si esegue una programmazione del piano di manutenzione, una riga di programma di manutenzione deve essere creata ogni volta che la soglia di 2.000 km viene raggiunta. Nell'esempio 1, sono presenti 4 righe di registrazione, ma la soglia di 2.000 km viene raggiunta una sola volta. Ciò significa che quando si eseguono piani di manutenzione programmati in questo cespite, ad esempio per un periodo di tre mesi, verrà creata una sola riga di programma di manutenzione.

Nella figura seguente vengono registrati 2.000 km o più ogni mese. Di conseguenza, tre righe di manutenzione vengono create se si programmano piani di manutenzione per questo cespite per un periodo di tre mesi. 

Gli esempi descritti qui mostrano che tutte le registrazioni contatore eseguite in un cespite mostrano una tendenza che descrive l'usura del cespite. Tale tendenza viene utilizzata come base di calcolo al momento della programmazione del piano di manutenzione.

![Figura 3](media/11-preventive-maintenance.png)

![Figura 4](media/12-preventive-maintenance.png)
