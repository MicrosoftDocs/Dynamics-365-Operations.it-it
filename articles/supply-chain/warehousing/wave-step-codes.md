---
title: Codici del passaggio ondata
description: Questo argomento fornisce una panoramica dei codici passaggio ondata e del modo in cui vengono utilizzati.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
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
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f89c6098db9e2e3a9aa4ee3666e4b9ae608f054
ms.sourcegitcommit: d8f1135cdbc2deca70bc4b2805a0519253c9a31f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "1992359"
---
# <a name="wave-step-codes"></a>Codici del passaggio ondata

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

## <a name="about-wave-step-codes"></a>Informazioni sui codici passaggio ondata

I codici passaggio ondata sono codici che gli utenti possono impostare e utilizzare per collegare istanze specifiche di metodi ondata a un modello corrispondente. I modelli includono modelli per rifornimento, containerizzazione, stampa di etichette, creazione di carichi e ordinamento.

Quando non vengono utilizzati i codici passaggio ondata, gli utenti devono inserire il testo libero per fare riferimento a un modello specifico dall'istanza del metodo ondata. Il testo libero è soggetto a errori, poiché gli utenti devono assicurarsi che il testo del passaggio ondata che aggiungono per un metodo di passaggio ondata specifico in un modello ondata corrisponda esattamente al testo del passaggio ondata nel modello di destinazione.

I codici passaggio ondata per uno specifico tipo di passaggio ondata vengono impostati in una pagina separata. Per ogni istanza del metodo del passaggio ondata in un modello di ondata che richiede un codice passaggio ondata, il codice passaggio ondata deve essere selezionato in un elenco a discesa. La selezione in un elenco a discesa sostituisce l'immissione di testo libero e aiuta a ridurre il rischio e l'impatto dell'errore umano. I codici di impostazione vengono utilizzati per collegare un metodo del passaggio ondata in un modello ondata a un modello di destinazione per il metodo.

> [!NOTE]
> L'uso della funzione dei codici passaggio ondata è facoltativo e l'utilizzo è per entità legale. Pertanto, se una specifica entità legale utilizza la funzione, tutti i codici passaggio ondata esistenti in tale entità legale vengono aggiornati alla nuova struttura.

## <a name="setup-demo"></a>Demo di impostazione 

Per questa demo, i dati dimostrativi devono essere installati ed è necessario utilizzare la società di dati dimostrativi **USMF**.

### <a name="enable-wave-step-codes"></a>Abilita codici del passaggio ondata

Seguire questi passaggi per attivare la funzionalità di codici passaggio ondata.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
2. Nella scheda **Generale**, nella Scheda dettaglio **Elaborazione ondata**, impostare l'opzione **Abilita codici passaggio ondata** su **Sì**.

Tutti i testi liberi del passaggio ondata esistenti vengono aggiornati alla nuova struttura. Dopo che questo aggiornamento è stato completato per una persona giuridica, l'opzione **Abilita codici passaggio ondata** non è più disponibile nella pagina **Parametri di gestione magazzino**.

Le convalide vengono eseguite durante l'aggiornamento e, se l'aggiornamento ha esito negativo, viene visualizzato un messaggio di errore. Un aggiornamento potrebbe non riuscire a causa dei seguenti conflitti:

- Esistono testi liberi con passaggi ondata duplicati.
- Esistono personalizzazioni.
- Un testo libero del passaggio ondata associato a un'istanza del metodo del passaggio ondata non corrisponde al tipo di modello previsto.

Dopo aver risolto eventuali conflitti identificati durante le convalide, è possibile rieseguire il processo di aggiornamento.

Quando l'aggiornamento viene completato, la pagina **Codici passaggio ondata** (**Gestione magazzino \> Impostazione \> Ondate \> Codici passaggio ondata**) diventa disponibile. Questa pagina elenca i codici dei passaggi ondata che sono stati aggiornati quando è stata attivata la funzione Codici passaggi ondata.

### <a name="create-new-wave-step-codes"></a>Creare nuovi codici passaggio ondata

È possibile utilizzare la pagina **Codici passaggio ondata** per creare ed eliminare i codici passaggio ondata.

Ogni nuovo codice passaggio ondata e il relativo ID associato devono essere univoci per tutti i tipi di passaggio ondata e devono essere definiti per un tipo di passaggio ondata specifico.

### <a name="apply-wave-step-codes"></a>Applicare i codici passaggio ondata

Dopo aver definito i codici passaggio ondata appropriati, possono essere applicati ai metodi di processo ondata.

Per applicare i codici passaggio ondata, andare al modello di destinazione appropriato. Di seguito vengono riportati i modelli di destinazione a cui sono designati i codici passaggio ondata:

- **Modelli rifornimento:** Gestione magazzino \> Impostazioni \> Rifornimento \> Modelli rifornimento
- **Modelli di allestimento del carico:** Gestione magazzino \> Impostazioni \> Carico \> Modelli di allestimento del carico
- **Modelli di ordinamento:** Gestione magazzino \> Impostazioni \> Imballaggio \> Modelli di ordinamento in uscita
- **Modelli di containerizzazione:** Gestione magazzino \> Impostazioni \> Contenitori \> Modelli di build contenitore
- **Modelli di stampa di etichette:** Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Modelli di etichette ondata

I modelli in questo elenco vengono applicati quando fanno riferimento a un metodo di processo ondata selezionato in un modello ondata. Quando il codice passaggio ondata su un metodo del processo ondata in un modello ondata onda corrisponde al codice passaggio ondata in uno dei tipi di modelli, il modello viene applicato.

### <a name="sample-scenario"></a>Scenario di esempio

Le seguenti procedura consente di garantire che il modello di rifornimento create verrà applicato per il modello ondata.

1. Passare a **Gestione magazzino \> Impostazioni \> Ondate \> Codici passaggio ondata** e creare un codice passaggio ondata per il tipo **Rifornimento**.
2. Andare a **Gestione magazzino \> Impostazioni \> Rifornimento \> Modelli rifornimento** e creare un modello rifornimento.
3. Nel modello di rifornimento, selezionare il codice passaggio ondata creato per il tipo **Rifornimento**.
4. Passare a **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata** e selezionare il modello ondata che si intende utilizzare.
5. Nel modello, nella Scheda dettaglio **Metodi**, selezionare il metodo **Rifornimento**.
6. Nel campo **Codice passaggio ondata**, selezionare il codice passaggio ondata selezionato nel modello rifornimento.