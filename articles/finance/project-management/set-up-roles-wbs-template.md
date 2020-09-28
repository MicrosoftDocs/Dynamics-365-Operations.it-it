---
title: Impostare i ruoli sui modelli di struttura di suddivisione del lavoro
description: Questo argomento fornisce informazioni sulla configurazione delle informazioni sui ruoli nei modelli di struttura di suddivisione del lavoro.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5dfb429eae933ba4d687ec4cbd417d2f78308e47
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760586"
---
# <a name="set-up-roles-on-work-breakdown-structure-templates"></a>Impostare i ruoli sui modelli di struttura di suddivisione del lavoro

[!include [banner](../includes/banner.md)]

I manager di progetto possono impostare i modelli di struttura di suddivisione del lavoro che possono applicare quando creano una struttura di suddivisione lavoro per nuovi progetti. I manager di progetto possono aggiungere ruoli quando creano un modello. Utilizzare la procedura riportata di seguito per assegnare un ruolo a un modello WBS. 

1. Selezionare **Gestione progetti e contabilità** > **Impostazioni** > **Progetti** > **Modelli di struttura di suddivisione del lavoro**.
2. Selezionare **Dettagli** per un modello WBS selezionato.
3. Selezionare un'attività nell'elenco, quindi nel campo **Ruolo** selezionare un ruolo da assegnare all'attività.

## <a name="work-with-a-wbs"></a>Utilizzare una struttura di suddivisione del lavoro

È possibile creare una nuova struttura di suddivisione del lavoro oppure copiare una struttura di suddivisione del lavoro da un modello WBS. Un manager di progetto può gestire facilmente le risorse assegnando ruoli a nuove attività sulla struttura di suddivisione del lavoro. I ruoli possono essere sostituiti dopo l'acquisizione della risorsa o dopo l'identificazione di una risorsa confermata a lavorare sull'attività. Questa flessibilità consente ai manager di progetto di eseguire le attività seguenti:

- Identificare il numero di risorse richieste per i pacchetti di lavoro WBS.
- Stimare i costi del progetto.
- Determinare un budget preliminare.
- Stimare la durata dell'attività, in base a ruoli e risorse.
- Elaborare alcuni piani di gestione progetti, in base alle informazioni sul progetto disponibili.

Le opzioni aggiuntive sono state aggiunte nella struttura di suddivisione del lavoro per utilizzare meglio la funzionalità di assegnazione risorse.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opzione</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Assegnazioni risorse</td>
<td>Visualizzare le risorse assegnate, le date, il numero di ore e il tipo di prenotazione per le attività nella struttura di suddivisione del lavoro.</td>
</tr>
<tr class="even">
<td>Genera automaticamente team</td>
<td>Aggiungere automaticamente le risorse programmate usando i ruoli associati a un'attività. Finance suggerisce automaticamente le risorse programmate usando le analisi decisionali basate su più criteri basate su ruoli. Dopo l'impostazione dei ruoli e del lavoro (ore) per le attività in una struttura di suddivisione del lavoro e dopo che la struttura è stata rilasciata, selezionare <strong>Genera automaticamente team</strong>. Il numero obbligatorio risorse pianificate viene aggiunto alla struttura di suddivisione del lavoro e alla scheda <strong>Team progetto e programmazione</strong>.</td>
</tr>
<tr class="odd">
<td>Risorsa (elenco a discesa)</td>
<td>Nella pagina <strong>Avvia modulo di assegnazione risorse </strong>è possibile selezionare le risorse per prenotarle in modo definitivo o preliminare, in base alla durata specificata. È possibile modificare le impostazioni di visualizzazione per visualizzare e impostare la durata delle attività delle risorse. È possibile selezionare e assegnare le risorse a livello di pacchetto di lavoro usando le seguenti opzioni:
<ul>
<li><strong>Accetta</strong>: consente di confermare le modifiche alla risorsa assegnata a un'attività.</li>
<li><strong>Annulla</strong>: consente di annullare le modifiche alla risorsa assegnata a un'attività.</li>
<li><strong>Assegna automaticamente</strong>: una risorsa con personale disponibile che ha un ruolo corrispondente viene automaticamente selezionata e assegnata all'attività selezionata.</li>
</ul></td>
</tr>
</tbody>
</table>

1. Nella pagina **Tutti i progetti**, selezionare il progetto **Fase 2 di aggiornamento di XYZ**.
2. Selezionare **Pianifica** > **Attività** > **Struttura di suddivisione del lavoro**.
3. Selezionare **Nuovo** per aggiungere le seguenti  attività di livello uno a struttura di suddivisione del lavoro:

    - Inizio
    - Pianificazione
    - Esecuzione
    - Monitoraggio e controllo
    - Chiusura

4. Impostare le date e l'impegno (ore), come mostrato nell'illustrazione seguente.

    [![Impostazione delle date e dell'impegno](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Selezionare la riga attività **Avvio**, quindi, nel campo **Ruolo** selezionare **Manager di progetto principale**.
6. Selezionare **Pubblica**
7. Sulla stessa riga, nel campo **Risorsa** selezionare **Daniel Goldschmidt** e quindi **Accetta**.
8. Selezionare la riga attività **Pianificazione**, quindi, nel campo **Ruolo** selezionare **Analista aziendale**.
9. Selezionare **Pubblica**, quindi **Genera automaticamente team**.
10. Nella finestra di messaggio visualizzata selezionare **Sì**.
11. Nel campo **Risorsa** verificare che il valore sia **Analista aziendale 1**.
12. Per la risorsa **Analista aziendale 1**, aprire la ricerca e selezionare **Avvia modulo di assegnazione risorse**. Quindi selezionare un lavoratore per l'attività.
13. Selezionare **Assegna in via preliminare** &gt; **Intera capacità**.

    > [!NOTE] 
    > Non si viene avvisati che la risorsa specificata è ora 2, poiché il numero di risorse rimane 1.

14. Nella pagina **Struttura di suddivisione lavoro**, convalidare l'assegnazione delle risorse sulla WBS, quindi selezionare **Salva**.
