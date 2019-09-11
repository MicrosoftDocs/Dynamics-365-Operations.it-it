---
title: Analisi degli errori dei cespiti
description: In questo argomento viene descritta l'analisi degli errori di cespite in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c9330cc7b3a8839d94c8945418548033254786b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918443"
---
# <a name="asset-fault-analysis"></a>Analisi degli errori dei cespiti

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

In Gestione cespiti, è possibile analizzare le registrazioni di errore di cespite per ottenere una panoramica del numero totale di errori registrati durante un periodo specifico. Le registrazioni di errore possono essere analizzate da varie prospettive, ad esempio in relazione cespiti, tipi di cespite, unità funzionali, sintomi di errore o tipi di errore.

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Analisi degli errori dei cespiti**.

2. Nella finestra di dialogo **Calcolo analisi errori dei cespiti**, è possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe degli errori di cespite in relazione alle unità funzionali. Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe degli errori di cespite per un'unità funzionale verranno visualizzate nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali situate a un livello inferiore. Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe degli errori di cespite in tutti i livelli di unità funzionali a cui sono correlate.

3. Se si desidera limitare la ricerca, è possibile selezionare specifici cespiti, date di errore, cause di errore e rimedi agli errori nella Scheda dettaglio **Record da includere**.

4. Fare clic su **OK** per avviare il calcolo.

5. Nella scheda **Analisi degli errori dei cespiti**, fare clic su uno o più pulsanti nei gruppi di riquadri azioni **Raggruppa per** per visualizzare il livello di dettagli desiderato. I pulsanti attivati sono evidenziati. Fare clic sui pulsanti per attivarli o disattivarli.

6. Fare clic su **Aggiorna calcoli** per visualizzare le selezioni sullo schermo. 

>[!NOTE]
>Ogni volta che si attivano o si disattivano i pulsanti nei gruppi di riquadri azioni **Raggruppa per**, ricordarsi di fare clic sul pulsante **Aggiorna calcoli** dopo aver modificato le selezioni. Ciò è necessario in quanto una grande quantità di dati viene elaborata durante il ricalcolo della probabilità di errore.

Esistono vari modi di analizzare le registrazioni di errore. Di seguito sono illustrate cinque schermate di esempio su come differenti selezioni di dati forniscono informazioni differenti. Sarà possibile osservare come differenti selezioni forniscono più informazioni e dettagli durante l'analisi delle registrazioni di errore di cespite.

Nel schermata seguente, solo il pulsante **Sintomo** è selezionato.

- Le registrazioni di errore sono state effettuate per tre sintomi di errore: "Perdita d'aria", "Fusibile bruciato" e "attrezzatura inceppata".  
- Nella colonna **% probabilità**, la somma di tutte le percentuali equivale al 100%. La probabilità è basata su tutte le registrazioni di **Sintomi** in questa analisi degli errori.

![Figura 1](media/06-controlling-and-reporting.png)


Nella schermata seguente, sono stati aggiunti **Anno** e **Mese** per mostrare come è possibile visualizzare le registrazioni di errore durante un periodo selezionato.

- I sintomi di errore sono ora visualizzati come registrazioni per anno/mese.  
- Nella colonna **% probabilità**, se si sommano le percentuali di ogni mese, si ottiene 100%. La probabilità è basata su tutte le registrazioni di **Sintomi** in questa analisi degli errori. Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un sintomo di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quel sintomo di errore.

![Figura 2](media/07-controlling-and-reporting.png)


- La combinazione di cespiti e un tipo di cespite sono utilizzati come base per i calcoli visualizzati nelle tre schermate seguenti, in cui il livello di dettagli aumenterà.  
- In genere, i pulsanti nei gruppi di riquadri azioni **Raggruppa per data** **Raggruppa per cespite**, **Raggruppa per unità funzionale** nonché il pulsante **Errore** (ID errore), contengono periodi o relazioni cespiti. I pulsanti **Sintomo**, **Area**, **Tipo**, **Causa** e **Rimedio** sono categorizzazioni utilizzate nella gestione degli errori per analizzare le registrazioni di errore di cespite e individuare le aree con problemi.  

Nella schermata seguente, **Cespite** e **Tipo di cespite** sono stati aggiunti per offrire un maggiore livello di dettagli nelle registrazioni di errore.

- I sintomi di errore sono ora suddivisi nelle combinazioni **Cespite** / **Tipo di cespite** / **Sintomo**.  
- Nella colonna **% probabilità**, se si sommano le percentuali della combinazione di rispettivamente **Cespite** / **Tipo di cespite** / **Sintomo**, si ottiene 100%. La probabilità è basata su tutte le registrazioni di **Sintomi** in questa analisi degli errori. Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un sintomo di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quel sintomo di errore.

![Figura 3](media/08-controlling-and-reporting.png)


Nella schermata seguente, **Area** è stato aggiunto a **Sintomo**, **Cespite** e **Tipo di cespite** per offrire un maggiore livello di dettagli nelle registrazioni di errore.

- Nella colonna **% probabilità**, se si sommano le percentuali della combinazione di **Cespite** / **Tipo di cespite** / **Sintomo**, si ottiene 100%. La probabilità è basata sulla combinazione di **Sintomo** e **Area** in questa analisi degli errori. Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un'area di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quell'area di errore.  

![Figura 4](media/09-controlling-and-reporting.png)


Nel schermata seguente, è stato aggiunto **Tipo** e viene visualizzato il calcolo più dettagliato in questo esempio.
 
- Nella colonna **% probabilità**, se si sommano le percentuali della combinazione di **Cespite** / **Tipo di cespite** / **Sintomo**, si ottiene 100%. La probabilità è basata sulla combinazione di **Sintomo**, **Area** e **Tipo** in questa analisi degli errori. Se il numero di righe in un cespite è elevato, ma una forte percentuale spicca in una riga, sarebbe un'indicazione di un tipo di errore da esaminare più attentamente per trovare il modo di limitare il numero di registrazioni per quel tipo di errore.

![Figura 5](media/10-controlling-and-reporting.png)


>[!NOTE]
>Per una panoramica di tutte le registrazioni di errore create negli ordini di lavoro e nelle richieste di intervento di manutenzione, fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Errori di cespite**. Nella pagina **Errori di cespite**, selezionare una registrazione ed espandere il riquadro **Informazioni correlate** per visualizzare informazioni relative alla richiesta di intervento di manutenzione o all'ordine di lavoro associato.

