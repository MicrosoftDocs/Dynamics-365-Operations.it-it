---
title: Stati del ciclo di vita di ordine di lavoro
description: In questo argomento vengono descritti gli stati del ciclo di vita di ordine di lavoro.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderLifecycleState, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b6e96f2f6b324ffe44e8684d9bd2a42fb52d0aed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431203"
---
# <a name="work-order-lifecycle-states"></a>Stati del ciclo di vita di ordine di lavoro


[!include [banner](../../includes/banner.md)]

 

Gli stati del ciclo di vita di ordine di lavoro definiscono gli stati che può avere un ordine di lavoro. Ad esempio **Creato**, **Programmato**, **In corso** e **Finito**. Gli stati del ciclo di vita di ordine di lavoro possono essere aggiornati manualmente in un ordine di lavoro, oppure automaticamente (ad esempio, durante la programmazione degli ordini di lavoro).

Lo stato del ciclo di vita di ordine di lavoro necessari per gli ordini di lavoro devono essere associati alle fasi di progetto corrispondenti nella pagina **Parametri Gestione progetti e contabilità** (**Gestione progetti e contabilità** \> **Parametri Gestione progetti e contabilità**). Innanzitutto, è necessario impostare le fasi di progetto in Gestione progetti e contabilità. Successivamente si impostano gli stati del ciclo di vita di ordine di lavoro e i modelli del ciclo di vita di ordine di lavoro in Gestione cespiti.

La tabella seguente descrive le opzioni nelle sezione **Ordine di lavoro** e **Programma** della Scheda dettaglio **Generale** nella pagina **Stato del ciclo di vita ordine di lavoro** (**Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Stati del ciclo di vita**).

![Pagina Stato del ciclo di vita ordine di lavoro](media/09-setup-for-work-orders.png)

| Nome opzione                   | Descrizione |
|-------------------------------|-------------|
| Attivi                        | Impostare questa opzione su **Sì** se l'ordine di lavoro deve essere attivo quando è in questo stato del ciclo di vita. |
| Aggiungi riga                      | Impostare questa opzione su **No** se i processi di ordine di lavoro possono essere aggiunti a un ordine di lavoro quando è in questo stato del ciclo di vita. |
| CANC                        | Impostare questa opzione su **Sì** se un ordine di lavoro può essere definito quando è in questo stato del ciclo di vita. |
| Elimina riga                   | Impostare questa opzione su **Sì** se i processi di ordine di lavoro possono essere eliminati da un ordine di lavoro quando è in questo stato del ciclo di vita. |
| Consenti la programmazione              | Impostare questa opzione su **Sì** se un ordine di lavoro può essere programmato quando è in questo stato del ciclo di vita. |
| Imposta l'inizio effettivo              | Impostare questa opzione su **Sì** se all'utente deve essere richiesto di selezionare una data e un'ora di inizio effettive per un ordine di lavoro quando viene aggiornato a questo stato del ciclo di vita. |
| Imposta la fine effettiva                | Impostare questa opzione su **Sì** se all'utente deve essere richiesto di selezionare una data e un'ora di fine effettive per un ordine di lavoro quando viene aggiornato a questo stato del ciclo di vita. |
| Registra giornali                 | Impostare questa opzione su **Sì** se i giornali di registrazione di ordine di lavoro devono essere registrati quando un ordine di lavoro viene aggiornato a questo stato del ciclo di vita. Se si verifica un errore durante la registrazione di un giornale di registrazione, viene visualizzato un messaggio e l'aggiornamento dello stato del ciclo di vita di ordine di lavoro viene annullato. Per visualizzare le righe del giornale di registrazione relative a un ordine di lavoro, selezionare **Gestione cespiti** \> **Comune** \> **Ordini di lavoro** \>, **Tutti gli ordini di lavoro**, **Ordini di lavoro attivi** o **Ordini di lavoro personali attivi**, selezionare l'ordine di lavoro nell'elenco e quindi selezionare **Giornali di registrazione**. Questa impostazione della registrazione automatica dei giornali di registrazione di ordine di lavoro con uno specifico stato del ciclo di vita è la stessa di quando si seleziona **Registra giornali** nella pagina **Giornali di registrazione ordine di lavoro**.<p>**Nota:** se si imposta questa opzione su **Sì**, i giornali di registrazione vengono automaticamente registrati se non è stato impostato alcun flusso di lavoro di approvazione. Se la propria società utilizza l'impostazione di approvazione dei giornali di registrazione configurata nella pagina **Approvazione giornale di registrazione** (**Gestione progetti e contabilità** \> **Impostazione** \> **Giornali di registrazione** \> **Approvazione giornale di registrazione**), un responsabile o un impiegato deve convalidare e registrare le registrazioni del consumo.</p> |
| Elabora elenco di controllo di manutenzione | Impostare questa opzione su **Sì** se tutti gli elenchi di controllo di manutenzione associati devono essere elaborati quando un ordine di lavoro viene aggiornato a questo stato del ciclo di vita. Nel quadro di tale elaborazione, vengono registrate tutte le registrazioni contatore effettuate in un elenco di controllo di manutenzione e viene valutato il risultato dell'intero elenco di controllo di manutenzione. Vengono analizzate le righe di elenco di controllo di manutenzione il cui risultato è **Superato** e **Errore** e se almeno una riga presenta un errore, l'intero elenco di controllo di manutenzione viene contrassegnato come **Non riuscito** in Gestione cespiti. |
| Pronto                         | Impostare questa opzione su **Sì** se lo stato di programmazione di tutti i processi di ordine di lavoro creati in un ordine di lavoro deve essere aggiornato automaticamente a **Pronto** quando l'ordine di lavoro viene aggiornato a questo stato del ciclo di vita. |
| Avvio                         | Impostare questa opzione su **Sì** se lo stato di programmazione di tutti i processi di ordine di lavoro creati in un ordine di lavoro deve essere aggiornato automaticamente a **Avviato** quando l'ordine di lavoro viene aggiornato a questo stato del ciclo di vita. |
| Fine periodo                           | Impostare questa opzione su **Sì** se lo stato di programmazione di tutti i processi di ordine di lavoro creati in un ordine di lavoro deve essere aggiornato automaticamente a **Finito** quando l'ordine di lavoro viene aggiornato a questo stato del ciclo di vita. |
| Elimina righe della programmazione         | Impostare questa opzione su **Sì** se la programmazione di tutti i processi di ordine di lavoro creati in un ordine di lavoro che è già stato programmato deve essere eliminata automaticamente quando l'ordine di lavoro viene aggiornato a questo stato del ciclo di vita. In altre parole, le prenotazioni della capacità per il cespite, l'addetto alla manutenzione associato e gli strumenti correlati verranno eliminati. Ad esempio, se si imposta questa opzione su **Sì** in uno stato del ciclo di vita di ordine di lavoro lo stato è **Stimato**. Quindi, quando si esegue il rollback di un ordine di lavoro a questo stato del ciclo di vita in quanto una riprogrammazione è necessaria, la programmazione può essere eliminata nell'ordine di lavoro. |

## <a name="set-up-project-stages-and-work-order-lifecycle-states"></a>Impostare fasi di progetto e stati del ciclo di vita di ordine di lavoro

1. Selezionare **Gestione progetti e contabilità** \> **Impostazione** \> **Parametri Gestione progetti e contabilità**.
2. Nella scheda **Fase progetto**, per ogni fase che si intende utilizzare, selezionare la casella di controllo di ogni tipo di progetto necessario per gli ordini di lavoro. I tipi di progetto definiscono le regole relative alle attività finanziarie consentite. Esempi di attività finanziarie sono la creazione di una previsione, di stime e di saldi iniziali.

    > [!IMPORTANT]
    > Se una fase di progetto non è selezionata per un tipo di progetto, ma la fase viene utilizzata per uno stato del ciclo di vita di ordine di lavoro, i progetti di ordine di lavoro non verranno aggiornati nel modo appropriato.

3. Chiudere la pagina **Parametri Gestione progetti e contabilità**.
4. Selezionare **Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Stati del ciclo di vita**.
5. Selezionare **Nuovo** per creare uno stato del ciclo di vita di ordine di lavoro.
6. Nel campo **Stato del ciclo di vita**, immettere l'ID dello stato del ciclo di vita.
7. Nel campo **Nome** immettere un nome.

    Nella Scheda dettaglio **Dettagli** il campo **Modelli del ciclo di vita** visualizza il numero di modelli del ciclo di vita di ordine di lavoro che utilizzano questo stato del ciclo di vita.

8. Nella Scheda dettaglio **Generale**, nella sezione **Ordine di lavoro**, selezionare le funzioni che devono essere disponibili per questo stato del ciclo di vita impostando le opzioni appropriate su **Sì**. Per le descrizioni delle opzioni, vedere la tabella vista precedentemente in questo argomento.
9. Nella sezione **Progetto**, nel campo **Fase**, selezionare la fase di progetto che deve essere associata a questo stato del ciclo di vita.
10. Nella sezione **Progetto**, impostare l'opzione **Chiudi attività** su **Sì** se le attività di progetto associate a ciascun processo di ordine di lavoro devono essere chiuse automaticamente quando l'ordine di lavoro è in questo stato del ciclo di vita.

    > [!NOTE]
    > Per trovare il numero dell'attività di progetto associata a un processo di ordine di lavoro, selezionare **Gestione cespiti** \> **Comune** \> **Ordini di lavoro** \>, **Tutti gli ordini di lavoro**, **Ordini di lavoro attivi** o **Ordini di lavoro personali attivi**. Aprire l'ordine di lavoro e quindi selezionare il processo relativo all'ordine di lavoro. Il numero di attività è visualizzato nel campo **Numero attività** della sezione **Progetto** nella scheda **Generale** della Scheda dettaglio **Dettagli riga**.

11. Nella sezione **Previsione**, impostare l'opzione **Copia previsione ore**, **Copia previsione articoli** e/o **Copia previsione spese** su **Sì** se le previsioni del progetto di ordine di lavoro vengono automaticamente copiate nei giornali di registrazione di ordine di lavoro quando l'ordine di lavoro è in questo stato del ciclo di vita.
12. Nella sezione **Programma**, impostare una delle opzioni su **Sì** se lo stato di programmazione dei processi di ordine di lavoro viene aggiornato quando l'ordine di lavoro è in questo stato del ciclo di vita. Per le descrizioni delle opzioni **Pronto**, **Inizio**, **Fine** e **Elimina righe di programmazione**, vedere la tabella esposta in precedenza in questo argomento.

    > [!NOTE]
    > Per visualizzare le righe di programmazione associate ai processi di ordine di lavoro, selezionare **Gestione cespiti** \> **Comune** \> **Ordini di lavoro** \>, **Tutti gli ordini di lavoro**, **Ordini di lavoro attivi** o **Ordini di lavoro personali attivi**. Aprire l'ordine di lavoro, selezionare il processo relativo all'ordine di lavoro nella Scheda dettaglio **Processi di ordine di lavoro** e visualizzare le informazioni correlate nella Scheda dettaglio **Dettagli riga**. Nel campo **Stato** della scheda **Programma** è visualizzato lo stato del processo di ordine di lavoro. Il campo **Stato** può avere i seguenti valori: **Programmato**, **Pronto**, **Iniziato**, **Interrotto** e **Finito**.

13. Nella sezione **Richieste di intervento di manutenzione**, nel campo **Stato del ciclo di vita**, selezionare lo stato del ciclo di vita a cui le richieste di intervento di manutenzione associate devono essere aggiornate. Questo aggiornamento viene eseguito automaticamente. Può essere eseguito solo se lo stato del ciclo di vita di richiesta di intervento di manutenzione è selezionato nel modello del ciclo di vita utilizzato per la richiesta di intervento di manutenzione.
14. Nella sezione **Cespite**, impostare l'opzione **Aggiorna DBA cespiti** su **Sì** se tutti gli articoli utilizzati in un ordine di lavoro devono essere aggiornati automaticamente nella pagina **DBA cespiti** quando l'ordine di lavoro viene aggiornato a questo stato del ciclo di vita. Questa impostazione potrebbe essere utile se, ad esempio, lo stato del ciclo di vita di ordine di lavoro definisce l'ordine di lavoro come completato o finito.
15. Nella sezione **Pool di ordini di lavoro**, impostare **Elimina riferimento pool** su **Sì** se gli ordini di lavoro in questo stato del ciclo di vita devono essere eliminati automaticamente dai pool di ordini di lavoro.
16. Nella Scheda dettaglio **Convalida**, selezionare i tipi di convalida che devono essere attivati in questo stato del ciclo di vita impostando le opzioni appropriate su **Sì**. Quindi, nel campo **Tipo** di ogni tipo di convalida selezionato, selezionare il tipo di messaggio da visualizzare se i campi obbligatori relativi al tipo di convalida non sono stati convalidati. Se si seleziona **Errore**, l'aggiornamento dello stato del ciclo di vita di ordine di lavoro viene annullato fino a che i campi obbligatori correlati non vengono aggiornati nell'ordine di lavoro.

    - Le opzioni **Tempi di fermo per la manutenzione**, **Elenco di controllo di manutenzione**, **Sintomo errore**, **Causa errore** e **Rimedio a errore** sono correlate alle opzioni disponibili nell'area **Obbligatorio** della pagina **Tipi di ordine di lavoro** (**Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Tipi di ordine di lavoro**). Per attivare tali convalide, le opzioni correlate devono essere impostate su **Sì** nel tipo di ordine di lavoro utilizzato per l'ordine di lavoro.
    - Se l'opzione **Elenco di controllo di manutenzione** è impostata su **Sì** per lo stato del ciclo di vita a cui un ordine di lavoro viene aggiornato, la convalida viene effettuata per verificare che le righe di elenco di controllo di manutenzione contrassegnate come **Obbligatorie** siano state registrate come **Verificata** o **Non applicabile**. Se nessuna di queste registrazioni è stata eseguita nelle righe obbligatorie, viene visualizzato un messaggio informativo, di errore o di avviso quando l'ordine di lavoro viene aggiornato a questo stato del ciclo di vita.
    - Se l'opzione **Costo impegnato** è impostata su **Sì** per lo stato del ciclo di vita a cui un ordine di lavoro viene aggiornato, l'importo totale dei costi impegnati (ovvero l'importo totale delle spese che la persona giuridica si è impegnata a pagare) viene calcolato per ciascun processo di ordine di lavoro. Un messaggio viene visualizzato se l'importo del costo impegnato è superiore a 0 (zero). Selezionare i tipi di impegno di costo inclusi nella Scheda dettaglio **Impegni costi** della scheda **Controllo costi** della pagina **Parametri Gestione progetti e contabilità** (**Gestione progetti e contabilità** \> **Impostazione** \> **Parametri Gestione progetti e contabilità**).
    - Se l'opzione **Tempi di fermo per la manutenzione** è impostata su **Sì** per lo stato del ciclo di vita a cui un ordine di lavoro viene aggiornato, la convalida dei tempi di fermo per la manutenzione viene eseguita nel cespite associato all'ordine di lavoro. Se è stata eseguita una registrazione di tempi di fermo per la manutenzione, ma non esiste alcuna registrazione **Finita**, viene visualizzato un messaggio quando l'ordine di lavoro viene aggiornato a questo stato del ciclo di vita.
    - Se l'impostazione di progetto standard non include tutte le fasi necessarie per la configurazione di Gestione cespiti, è possibile impostare fasi di progetto definite dall'utente nella scheda **Fase progetto** della pagina **Parametri Gestione progetti e contabilità**. Nella seguente figura è illustrata la scheda **Fase progetto** nella pagina **Parametri Gestione progetti e contabilità**.

    ![Pagina Impostare le fasi del progetto per diversi tipi di progetto](media/10-setup-for-work-orders.png)

> [!NOTE]
> Se lo stato del ciclo di vita a cui un ordine di lavoro viene aggiornato è inattivo, i giornali di registrazione associati all'ordine di lavoro che non sono stati ancora registrati verranno eliminati automaticamente. Questo comportamento garantisce l'eliminazione automatica dei dati non utilizzati Uno stato del ciclo di vita è inattivo se l'opzione **Attivo** è impostata su **No** nella Scheda dettaglio **Generale** della pagina **Stato del ciclo di vita ordine di lavoro**.
>
> Tuttavia, se si imposta manualmente un ordine di lavoro di modo che sia inattivo, i giornali di registrazione associati all'ordine di lavoro che non sono stati ancora registrati **non** verranno eliminati automaticamente. Per rendere inattivo un ordine di lavoro manualmente, selezionare **Gestione cespiti** \> **Comune** \> **Ordini di lavoro** \> **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**. Aprire l'ordine di lavoro e passare alla visualizzazione **Intestazione**. Nella Scheda dettaglio **Generale** selezionare **Modifica**, quindi impostare **Attivo** su **No**.

## <a name="relations-among-work-order-lifecycle-models-work-order-types-and-work-order-lifecycle-states"></a>Relazioni tra modelli del ciclo di vita di ordine di lavoro, tipi di ordine di lavoro e stati del ciclo di vita di ordine di lavoro

I modelli del ciclo di vita fanno riferimento a flussi di lavoro e gli stati del ciclo di vita sono selezionati in un modello del ciclo di vita in ordine sequenziale. I modelli del ciclo di vita sono impostati nei tipi di ordine di lavoro. I tipi di ordine di lavoro determinano le dimensioni o l'estensione dei flussi di lavoro e dei processi di lavoro. Ad esempio, **Manutenzione**, ovvero un tipo di ordine di lavoro standard, può essere associato a un modello del ciclo di vita di ordine di lavoro che include molti stati del ciclo di vita. Di contro, è possibile avere un tipo di ordine di lavoro **Correttivo** che viene utilizzato per gli ordini di lavoro non programmati o in cui il processo viene completato prima della creazione dell'ordine di lavoro a eseguito di una situazione urgente. Questo tipo di ordine di lavoro può essere associato a un modello del ciclo di vita di ordine di lavoro che ha solo stati del ciclo di vita.

Il motivo di utilizzare i tipi di ordine di lavoro è dato dal fatto che quando un tipo viene definito in, ad esempio, un ordine di lavoro o un cespite, i processi di lavoro associati (stati del ciclo di vita) vengono definiti automaticamente. Per ulteriori informazioni su come impostare i tipi di ordine di lavoro, vedere [Tipi di ordine di lavoro](../setup-for-work-orders/work-order-types.md).

> [!NOTE]
> Gli stati del ciclo di vita, i modelli del ciclo di vita e i tipi sono applicabili a unità funzionali, cespiti e richieste di intervento di manutenzione, oltre che a ordini di lavoro.

Nella figura seguente viene illustrata la relazione tra tipi di ordine di lavoro, modelli del ciclo di vita e stati del ciclo di vita.

![Pagina Tipo di ordine di lavoro rispetto alla pagina Modelli del ciclo di vita dell'ordine di lavoro](media/11-setup-for-work-orders.png)

## <a name="work-order-lifecycle-models"></a>Modelli del ciclo di vita dell'ordine di lavoro

Dopo aver creato gli stati del ciclo di vita necessari per gli ordini di lavoro, questi possono essere suddivisi in modelli del ciclo di vita di ordine di lavoro. È necessario creare almeno un modello del ciclo di vita standard.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Modelli del ciclo di vita**.
2. Selezionare **Nuovo** per creare un modello del ciclo di vita di ordine di lavoro.
3. Nel campo **Modello del ciclo di vita**, immettere un ID del modello del ciclo di vita.
4. Nel campo **Nome** immettere un nome.

    Nella Scheda dettaglio **Dettagli**, il campo **Stati del ciclo di vita** mostra il numero di stati del ciclo di vita selezionati in questo modello del ciclo di vita. Nel campo **Tipi di ordine di lavoro** viene visualizzato il numero di tipi di ordine di lavoro che utilizzano questo modello del ciclo di vita.

5. Nella Scheda dettaglio **Stati del ciclo di vita**, selezionare gli stati del ciclo di vita che devono essere inclusi nel modello:

    - Per includere uno stato del ciclo di vita nel modello, selezionarlo nella sezione **Stati del ciclo di vita rimanenti** e quindi fare clic sul pulsante freccia destra ![Freccia destra](media/12-setup-for-work-orders.png) per spostarlo nella sezione **Stati del ciclo di vita selezionati**.
    - Per includere tutti gli stati del ciclo di vita disponibili nel modello del ciclo di vita, selezionare il pulsante **Seleziona tutte le fasi disponibili** ![Seleziona tutte le fasi disponibili](media/13-setup-for-work-orders.png). Tutti gli stati del ciclo di vita verranno spostati nella sezione **Stati del ciclo di vita selezionati**.
    - Per rimuovere uno stato del ciclo di vita dal modello, selezionarlo nella sezione **Stati del ciclo di vita selezionati** e quindi fare clic sul pulsante freccia sinistra ![Freccia sinistra](media/14-setup-for-work-orders.png) per spostarlo nella sezione **Stati del ciclo di vita rimanenti**.

6. Selezionare **Aggiornamenti stati del ciclo di vita** per definire quali stati del ciclo di vita possono seguire uno stato del ciclo di vita selezionato.
7. Nella Scheda dettaglio **Aggiornamenti**, nel campo **Stato programmato**, selezionare lo stato del ciclo di vita che deve essere sempre selezionato per un ordine di lavoro per il quale è stata completata la programmazione, indipendentemente dallo stato del ciclo di vita precedente dell'ordine di lavoro.
8. Nel campo **Stato del ciclo di vita non programmato**, selezionare lo stato del ciclo di vita che deve essere sempre selezionato per un ordine di lavoro se la programmazione dell'ordine di lavoro viene eliminata.
9. Salvare il modello del ciclo di vita di ordine di lavoro.

![Pagina Modelli del ciclo di vita dell'ordine di lavoro](media/15-setup-for-work-orders.png)
