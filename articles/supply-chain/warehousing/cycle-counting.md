---
title: Conteggio ciclo
description: "Questo articolo descrive come utilizzare il conteggio ciclo con la soluzione di immagazzinaggio disponibile in Gestione magazzino. Questo articolo non è applicabile alla soluzione di immagazzinaggio disponibile in Gestione inventario."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 50671
ms.assetid: 49f5c431-b043-4170-aa24-b7d5d1ee063e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ddb035eaa496a7c84f117f0523d509eccdf58505
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="cycle-counting"></a>Conteggio ciclo

[!INCLUDE [banner](../includes/banner.md)]

Questo articolo descrive come utilizzare il conteggio ciclo con la soluzione di immagazzinaggio disponibile in Gestione magazzino. Questo articolo non è applicabile alla soluzione di immagazzinaggio disponibile in Gestione inventario.

Il conteggio ciclo è un processo di magazzino che è possibile utilizzare per controllare gli articoli di magazzino disponibili. Il processo di conteggio ciclo può essere descritto in tre passaggi:

1.  **Creare il lavoro di conteggio ciclo**: il lavoro di conteggio ciclo può essere creato automaticamente in base ai parametri di soglia per gli articoli o tramite un piano di conteggio ciclo. In alternativa, è possibile creare manualmente il lavoro di conteggio ciclo tramite l'articolo o i parametri di magazzino nella pagina **Lavoro conteggio ciclo per articolo** o **Lavoro conteggio ciclo per ubicazione**.
2.  **Elaborare il conteggio ciclo**: una volta creato il lavoro di conteggio ciclo, è possibile eseguirlo contando gli articoli in un'ubicazione magazzino e utilizzando un dispositivo mobile per inserire il risultato in Microsoft Dynamics 365 for Finance and Operations. In alternativa, è possibile contare gli articoli in un'ubicazione magazzino senza creare il lavoro di conteggio ciclo. Questo processo viene definito *conteggio ciclo a campione*.
3.  **Risolvere le differenze nel valore conteggiato**: dopo un conteggio ciclo, per tutti gli articoli con differenze nel valore conteggiato sarà impostato lo stato di lavoro **Revisione in sospeso** nel modulo **Tutto il lavoro**. È possibile risolvere le differenze nella pagina **Lavoro conteggio ciclo con revisione in sospeso**.

Nella seguente illustrazione viene mostrato il processo di conteggio ciclo. ![Elabora flusso per conteggio ciclo](./media/performcyclecountinginawarehouselocation.jpg)

## <a name="cycle-counting-prerequisites"></a>Prerequisiti di conteggio ciclo
Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di utilizzare il conteggio ciclo.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Articolo</td>
<td>Gli articoli devono essere abilitati per i processi di gestione magazzino.</td>
</tr>
<tr class="even">
<td>Magazzino</td>
<td>Il magazzino deve essere abilitato per i processi di gestione magazzino. Per abilitare il magazzino per i processi di gestione magazzino, nella pagina <strong>Magazzino</strong> selezionare il magazzino, quindi selezionare l'opzione <strong>Usa processi di gestione magazzino</strong>. Per consentire ai lavoratori di spostare i pallet durante un conteggio ciclo, nella Scheda dettaglio <strong>Gestione magazzino</strong> selezionare l'opzione <strong>Consenti movimento pallet durante il conteggio ciclo</strong>.</td>
</tr>
<tr class="odd">
<td>Pool lavoro</td>
<td>Facoltativo: creare un pool di lavoro per separare il lavoro del magazzino, in base al tipo di lavoro (in questo caso, lavoro di conteggio ciclo).</td>
</tr>
<tr class="even">
<td>Percorsi</td>
<td>Occorre abilitare il conteggio ciclo per le ubicazioni. Per abilitare il conteggio ciclo per un'ubicazione magazzino, selezionare l'opzione <strong>Consenti conteggio ciclo</strong> nella pagina <strong>Profili ubicazione</strong>.</td>
</tr>
<tr class="odd">
<td>Parametri di gestione magazzino</td>
<td>Impostare i parametri per il conteggio ciclo. Nella pagina <strong>Parametri di gestione magazzino</strong> specificare il codice per il tipo di rettifica predefinito, l'ID della classe lavoro e la priorità di lavoro per il conteggio ciclo.</td>
</tr>
<tr class="even">
<td>Dispositivo mobile</td>
<td><ul>
<li>Creare una voce di menu per uno dei seguenti metodi nella pagina <strong>Voci di menu del dispositivo mobile</strong>:
<ul>
<li>Conteggio ciclo diretto dall'utente</li>
<li>Conteggio ciclo diretto dal sistema</li>
<li>Raggruppamento conteggio ciclo</li>
<li>Conteggio ciclo a campione</li>
</ul>
</li>
<li>Impostare un menu per il dispositivo mobile.</li>
<li>Creare un account utente di lavoro e assegnare un menu del dispositivo mobile all'ID utente di lavoro.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Attività di impostazione correlata</td>
<td>Impostare un piano di conteggio ciclo per un'ubicazione magazzino.</td>
</tr>
</tbody>
</table>

## <a name="automatically-create-cycle-counting-work"></a>Creare automaticamente un lavoro di conteggio ciclo
Sono disponibili due metodi per programmare la creazione ricorrente del lavoro di conteggio di ciclo: impostare le soglie di conteggio ciclo o i piani di conteggio ciclo.

-   Una soglia di conteggio ciclo indica la quantità o il limite di percentuale degli articoli di magazzino. Il lavoro del conteggio ciclo viene automaticamente creato quando viene raggiunto il limite della soglia.
-   Un piano di conteggio ciclo crea lavoro di conteggio ciclo immediatamente o periodicamente attraverso un processo batch. Quando viene creato un lavoro di conteggio ciclo, la riga di lavoro di conteggio include informazioni sull'ubicazione da conteggiare. Le scorte disponibili associate all'ubicazione non vengono bloccate e sono pertanto disponibili per la prenotazione e l'elaborazione in uscita anche se esiste un lavoro di conteggio aperto.

### <a name="create-cycle-counting-work-based-on-threshold-parameters-for-items"></a>Creare il lavoro di conteggio ciclo in base a parametri di soglia per gli articoli

Il lavoro di conteggio ciclo può essere creato quando il numero di articoli scende al di sotto di un valore di soglia specifico in un'ubicazione. Ad esempio, sono presenti 60 articoli in una ubicazione con una soglia di conteggio ciclo di 40. Durante la transazione di ordini cliente, 25 articoli vengono prelevati dalla ubicazione e collocati in una ubicazione temporanea. Poiché il nuovo conteggio articoli di 35 è inferiore alla quantità soglia, il lavoro di conteggio ciclo viene creato automaticamente per l'ubicazione.

### <a name="schedule-cycle-counting-work"></a>Programmare un lavoro di conteggio ciclo

È possibile programmare piani di conteggio ciclo per creare immediatamente o periodicamente il lavoro di conteggio ciclo. Impostando i piani di conteggio ciclo, è possibile controllare il pool di lavoro per cui viene creato il lavoro di conteggio ciclo, il numero massimo di conteggi ciclo creati per gli articoli in ubicazioni diverse e il numero di giorni prima che venga conteggiata di nuovo un'ubicazione magazzino. Ad esempio, un articolo è disponibile in tre ubicazioni nel magazzino e il numero massimo di conteggi ciclo è impostato su **2**. In questo caso, quando si esegue il piano di conteggio ciclo, vengono creati due conteggi ciclo per le due ubicazioni in cui è presente l'articolo. In un altro esempio si imposta il numero di giorni tra i conteggi ciclo su **5**. In questo caso, il lavoro di conteggio ciclo viene creato ogni cinque giorni. Tuttavia, se il lavoro di conteggio ciclo viene elaborato il terzo giorno, il lavoro di conteggio ciclo successivo verrà creato cinque giorni dopo l'elaborazione dell'ultimo conteggio ciclo, l'ottavo giorno.

## <a name="create-cycle-counting-work-manually"></a>Creare un lavoro di conteggio ciclo manualmente
Per creare il lavoro di conteggio ciclo manualmente, è possibile utilizzare la pagina **Lavoro conteggio ciclo per articolo** o **Lavoro conteggio ciclo per ubicazione**. È possibile specificare il numero massimo di conteggi ciclo da creare. Ad esempio, se il responsabile del magazzino specifica un valore di **5**, il lavoro di conteggio ciclo viene creato per cinque ubicazioni anche se l'articolo è presente in 10 ubicazioni differenti. È anche possibile selezionare un ID di pool di lavoro a cui assegnare gli ID di lavoro di conteggio ciclo creati. Quando un ID di pool di lavoro viene elaborato per il conteggio ciclo, gli ID di lavoro di conteggio ciclo assegnati al pool di lavoro vengono elaborati in gruppo.

## <a name="perform-a-cycle-count-by-using-a-mobile-device"></a>Eseguire un conteggio ciclo tramite un dispositivo mobile
Sono disponibili diversi metodi per elaborare il lavoro di conteggio ciclo utilizzando Finance and Operations in un dispositivo mobile:

-   **Diretto dall'utente**: il lavoratore può specificare un ID di lavoro di conteggio ciclo che è nello stato **Aperto**.
-   **Diretto dal sistema**: al lavoratore viene assegnato un ID di lavoro di conteggio ciclo da Finance and Operations.
-   **Raggruppamento conteggio ciclo**: il lavoratore può raggruppare degli ID di lavoro di conteggio ciclo che sono specifici di un'ubicazione, una zona o un pool di lavoro.
-   **Conteggio ciclo a campione**: il lavoratore può contare gli articoli in un'ubicazione magazzino in qualsiasi momento, senza creare un lavoro di conteggio ciclo. Per eseguire il conteggio ciclo a campione in un'ubicazione, il lavoratore immette l'ID ubicazione.

Nel seguente esempio viene illustrato come eseguire il conteggio ciclo a campione utilizzando un dispositivo mobile. Le istruzioni che il lavoratore vede nel dispositivo variano a seconda dell'impostazione della voce di menu per il conteggio ciclo a campione.

1.  Nel dispositivo mobile selezionare la voce di menu per elaborare il lavoro di conteggio ciclo a campione.
2.  Registrare l'ubicazione per la quale eseguire il conteggio ciclo a campione.
3.  Registrare e confermare il numero di articolo e la quantità di articoli conteggiata. **Nota:** lo stato del lavoro di conteggio ciclo viene aggiornato a **Revisione in sospeso** o **Chiuso** nella pagina **Tutto il lavoro**, a seconda dei parametri impostati nella pagina **Lavoratore**.
4.  Facoltativo: ripetere il passaggio 3 per gli articoli rimanenti nell'ubicazione e verificare che non siano presenti articoli aggiuntivi disponibili al conteggio.

## <a name="resolve-cycle-counting-differences"></a>Risolvere differenze di conteggio ciclo
Una differenza di conteggio ciclo si verifica negli scenari seguenti se l'opzione **Supervisore conteggio ciclo** è impostata su **No** per un ID utente di lavoro:

-   Il valore conteggiato non è compreso nei limiti di deviazione specificati nel campo **Limite percentuale massima** o **Limite quantità massima** della pagina **Utenti di lavoro**. Ad esempio, la quantità di scorte disponibile in una ubicazione è 50 e il limite di deviazione per l'utente di lavoro è 10. Se l'utente di lavoro immette un valore che non è compreso tra 40 e 60, una differenza si verifica.
-   Il valore conteggiato differisce dalla quantità di scorte disponibili e non ci sono limiti di deviazione impostati.

È possibile rettificare le differenze nel valore conteggiato e quindi accettare il valore conteggiato nella pagina **Conteggio ciclo con revisione in sospeso**. È possibile verificare il conteggio modificato della quantità dell'articolo nella pagina **Disponibili per ubicazione**. Il valore conteggiato viene rifiutato se la differenza non può essere approvata.

## <a name="see-also"></a>Vedere anche
[Configurare i dispositivi mobili per il lavoro di magazzino](configure-mobile-devices-warehouse.md)




