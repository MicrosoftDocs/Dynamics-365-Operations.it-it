---
title: Prelievo cluster diretto dal sistema
description: In questo argomento viene fornita una panoramica del prelievi cluster diretto dal sistema in Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 390e0a3379a6482e99a13f4f7835b5264e3747ac
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217243"
---
# <a name="system-directed-cluster-picking"></a>Prelievo cluster diretto dal sistema

[!include [banner](../includes/banner.md)]

Il prelievo cluster è un processo di prelievo dei pezzi che consente di prelevare gli articoli per più ordini contemporaneamente raggruppandoli in cluster di prelievo. Pertanto è necessario visitare il luogo di prelievo solo una volta. In genere, questa funzionalità viene utilizzata con prelievi di ordini di piccole dimensioni o quantità inferiori alle quantità del caso.

Quando viene configurato il prelievo cluster diretto dal sistema, è possibile prelevare in cluster le intestazioni di lavoro in base a un cluster generato dal sistema. Il sistema preleva in cluster gli ordini fino al numero di ubicazioni specificato nel profilo del cluster. Pertanto, è possibile prelevare più ordini contemporaneamente senza dover creare manualmente un cluster.

Il prelievo cluster diretto dal sistema offre un'alternativa alla creazione manuale dei cluster, in cui un profilo cluster viene utilizzato per creare un cluster. Diverse righe relative alla configurazione devono essere definite nel profilo del cluster prima di essere utilizzate:

- **Numero di posizioni** corrisponde al numero di ordini che verranno inseriti in un cluster. Pertanto, corrisponde al numero di totali.
- **Suddividi cluster** determina in che modo il cluster deve essere suddiviso.
- **Genera ID cluster** controlla se l'ID cluster verrà generato dal sistema o immesso dall'utente.
- **Ordina tipo di verifica** determina se la verifica della posizione è obbligatoria.

Una nuova voce di menu del dispositivo mobile viene utilizzata per il prelievo cluster diretto dal sistema. L'ID profilo cluster deve essere specificato per l'opzione **Diretto da**. Inoltre, l'ordine di query diretto al sistema può raggruppare gli ordini, in base a criteri specifici dell'azienda. Pertanto, è possibile ottimizzare ulteriormente l'assegnazione degli ordini di lavoro specificando criteri di ordinamento personalizzati sull'ordine di query diretto dal sistema.

Al termine del prelievo cluster diretto dal sistema, ai magazzinieri viene presentato un cluster in cui gli ordini di prelievo sono stati preassegnati alle posizioni del cluster. Pertanto, gli addetti possono iniziare a prelevare un articolo per più ordini di lavoro visitando la posizione di prelievo una sola volta. Il processo di prelievo per il prelievo cluster diretto dal sistema è uguale al processo di prelievo cluster diretto dall'utente.

## <a name="set-up-system-directed-cluster-picking"></a>Configurare il prelievo cluster diretto dal sistema

### <a name="create-cluster-profiles"></a>Creare profili cluster

I profili cluster controllano il modo in cui il sistema crea ciascun cluster. Se sono richiesti cluster diversi, è necessario creare un profilo cluster diverso per ciascuna voce di menu del dispositivo mobile.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Profili cluster**.
2. Selezionare **Nuovo**.
3. Nel campo **ID profilo cluster**, immetti **2 posizioni**.
4. Nel campo **Nome** immettere **2 posizioni**.
5. Nella scheda dettaglio **Generale**, impostare i seguenti campi:

    - **Genera ID cluster:** impostare questa opzione su **Sì**. Questa opzione determina se l'ID cluster viene creato automaticamente dal sistema o se l'utente lo creerà all'inizio del prelievo.
    - **Attiva posizioni:** impostare questa opzione su **Sì**. Questa opzione determina se i nomi delle posizioni vengono generati automaticamente in base all'impostazione del nome della posizione. Se l'opzione è impostata su **No**, viene utilizzato l'ID della targa per la posizione.
    - **Numero di posizioni:** immettere **2**. Questo campo determina il numero massimo di posizioni che il cluster può avere (ovvero il numero massimo di caselle, totali e così via).
    - **Nome posizione:** selezionare **Numerico**, in modo che le posizioni vengano denominate utilizzando numeri continui. Se si seleziona **Alfabetico**, le posizioni sono denominate in ordine alfabetico.
    - **Suddividi cluster a:** selezionare **Inserisci**. Questo campo determina quando il cluster viene suddiviso.
    - **Ordina tipo di verifica:** selezionare **Scansione di posizione**. Questo campo determina se il passaggio di inserimento in posizione è verificato.

6. Nella scheda dettagli **Ordinamento cluster**, è possibile definire i criteri di ordinamento creando una nuova riga e impostando i seguenti campi:

    - **Numero progressivo:** questo campo determina la sequenza in base alla quale il sistema ordina. Un valore viene inserito automaticamente, ma è possibile modificarlo in base alle esigenze.
    - **Nome campo:** selezionare **WMSLocationId**. Questo campo determina il campo utilizzato dalla riga per i criteri di ordinamento.
    - **Ordinamento:** selezionare **Crescente**. Questo campo definisce se l'ordinamento viene eseguito in ordine crescente o decrescente.

### <a name="create-a-mobile-device-menu-item"></a>Creare una voce di menu per dispositivo mobile

Per creare una nuova voce di menu del dispositivo mobile per il prelievo cluster diretto dal sistema e collegare l'ID profilo del cluster alla voce di menu del dispositivo mobile, attenersi alla seguente procedura.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome voce di menu**, immettere **Cluster SD**.
4. Nel campo **Titolo**, immettere **Cluster SD**.
5. Selezionare **Lavoro** nel campo **Modalità**.
6. Impostare l'opzione **Utilizza lavoro esistente** su **Sì**.
7. Nella scheda dettaglio **Generale**, impostare i seguenti campi:

    - **Diretto da:** selezionare **Diretto dal sistema**.
    - **Genera targa:** impostare questa opzione su **Sì**.
    - **ID profilo cluster:** selezionare **2 posizioni**.

8. Nella Scheda dettaglio **Classi di lavoro**, impostare la classe di lavoro valida per questa voce di menu del dispositivo mobile impostando i seguenti campi:

    - **ID classe lavoro:** verificare che sia immesso un valore per **Vendite**.
    - **Tipo di ordine di lavoro:** verificare che sia immesso un valore per **Ordini cliente**.

9. Seguire questi passaggi per specificare una nuova query della sequenza di lavoro diretta dal sistema:

    1. Selezionare **Nuovo**.
    2. Nel campo **Numero progressivo** immettere **1**.
    3. Nel campo **Descrizione**, selezionare **Priorità lavoro - ID lavoro**.

10. Nel menu, selezionare **Modifica query**.
11. Nella scheda **Ordinamento** impostare i campi seguenti:

    - **Tabella:** selezionare **Lavoro**.
    - **Tabella derivata:** selezionare **Lavoro**.
    - **Campo:** selezionare **Priorità lavoro**.
    - **Direzione di ricerca:** selezionare **Crescente**.
    - **Tabella:** selezionare **Lavoro**.
    - **Tabella derivata:** selezionare **Lavoro**.
    - **Campo:** selezionare **ID lavoro**.
    - **Direzione di ricerca:** selezionare **Crescente**.

Il sistema ordinerà ora gli ID lavoro nel cluster, prima per priorità di lavoro e poi per ID lavoro.

### <a name="set-up-a-mobile-device-menu"></a>Configurare un menu per dispositivo mobile

1. Accedere a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu del dispositivo mobile**.
2. Aggiungere la voce di menu appena creata al menu desiderato.

## <a name="example"></a>Esempio

### <a name="create-picking-work"></a>Creare il lavoro di prelievo

Prima di poter impostare il prelievo cluster diretto al sistema, è necessario creare del lavoro in uscita idonei. Il profilo cluster creato in precedenza specifica due posizioni cluster. Pertanto, è necessario creare almeno due ID lavoro.

1. Accedere a **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
2. Selezionare **Nuovo** per creare un ordine cliente.
3. Nel campo **Conto cliente** selezionare qualsiasi cliente.
4. Nel campo **Magazzino** della Scheda dettaglio **Generale**, selezionare il magazzino **62**.
5. Selezionare **OK**.
6. Nella Scheda dettaglio **Righe ordine cliente**, selezionare **Aggiungi riga**.
7. Nel campo **Numero articolo** selezionare **A0001**.
8. Nel campo **Quantità** immettere **1**
9. Selezionare **Aggiungi riga** per aggiungere una seconda riga.
10. Nel campo **Numero articolo** selezionare **A0002**.
11. Nel campo **Quantità** immettere **3**
12. Ripetere i passaggi da 2 a 6.
13. Nel campo **Numero articolo** selezionare **A0001**.
14. Nel campo **Quantità** immettere **4**
15. Selezionare **Aggiungi riga** per aggiungere una seconda riga.
16. Nel campo **Numero articolo** selezionare **A0002**.
17. Nel campo **Quantità** immettere **2**

Prenotare le scorte e rilasciarle al magazzino. Vengono creati due diversi ID lavoro. Ogni ID lavoro ha due righe di prelievo.

### <a name="run-the-mobile-device-flow"></a>Eseguire il flussi del dispositivo mobile

1. Sul dispositivo mobile, selezionare il menu che include la nuova voce di menu del dispositivo mobile.
2. Selezionare la voce di menu **Cluster SD** e avviare il prelievo. Viene creato un cluster e i due ID lavoro creati in precedenza vengono collegati ad esso. Se sono stati creati più di due ID lavoro, solo i primi due vengono aggiunti al cluster. Si noti che gli ID lavoro vengono aggiunti al cluster in ordine crescente, come specificato nell'impostazione della query.

    > [!NOTE]
    > Il nuovo cluster viene creato automaticamente solo se in precedenza sono stati creati abbastanza ID lavoro aggiuntivi. In caso contrario, viene visualizzato il seguente messaggio: "Impossibile trovare lavoro sufficiente per il cluster".

    Dopo aver selezionato il menu, viene visualizzata la prima schermata di prelievo. Il sistema aggrega tutte le righe di prelievo corrispondenti dai due ID lavoro e suggerisce di visitare una volta il luogo di prelievo, in modo da poter soddisfare entrambi gli ordini utilizzando un solo prelievo. Questo processo viene eseguito allo stesso modo del processo per il prelievo cluster diretto dall'utente.

3. Conferma il primo prelievo. È quindi necessario immettere il nome della posizione per confermare che gli articoli sono stati inseriti nella posizione corretta.
4. Ripetere questo processo fino a quando tutti articoli sono stati prelevati e messi nella posizione corretta.
5. L'ultimo passaggio sul dispositivo mobile è l'inserimento del cluster nella posizione finale. Quando questa operazione di inserimento viene confermata, il cluster viene chiuso e suddiviso, in base al valore impostato per il campo **Suddividi il cluster a** nel profilo cluster. Anche gli ID lavoro vengono chiusi.
6. Sul dispositivo mobile viene visualizzato il messaggio "Cluster completato".
