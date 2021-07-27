---
title: Configurare i revisori spese
description: Questo argomento descrive come utilizzare i revisori spese per selezionare dinamicamente l'utente a cui è assegnata un'attività del flusso di lavoro, un'approvazione o una decisione manuale.
author: rachel-profitt
ms.date: 06/25/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2021-06-24
ms.openlocfilehash: b0de3d9280c43fc7e2bb2568d4a57250da4dfebf
ms.sourcegitcommit: 9f3b6c00f82694b5f8eb1bda75411801c0fccf4a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315681"
---
# <a name="configure-expenditure-reviewers"></a>Configurare i revisori spese
[!include[banner](../includes/banner.md)]

È possibile impostare i revisori spese dinamici in modo che le spese vengano inviate per la revisione in base all'utente assegnato a un ruolo di progetto o a una dimensione finanziaria a cui viene addebitata la spesa. Per determinare la persona cui inviare la spesa, il processo del flusso di lavoro fa riferimento al ruolo di progetto o al proprietario della dimensione finanziaria specificato.

È possibile definire una o più configurazioni del revisore spese, quindi selezionare una configurazione durante la creazione di un flusso di lavoro. È possibile configurare i valori del revisore spese per ogni persona giuridica dell'organizzazione. Dopo aver definito le configurazioni del revisore spese, è possibile assegnare la configurazione. I revisori delle spese possono essere assegnati ad attività del flusso di lavoro, approvazioni e decisioni manuali.

> [!NOTE]
> Sebbene i revisori spese non siano obbligatori, possono aiutare a semplificare la configurazione del flusso di lavoro. Ad esempio, non è necessario creare una decisione condizionale per verificare ogni dimensione del centro di costo e quindi creare un altro elemento per assegnare l'approvazione o l'attività a un utente o a gruppi di utenti specifici. È invece possibile configurare il proprietario della dimensione del centro di costo e utilizzare un revisore spese per selezionare dinamicamente l'utente corretto. In questo modo, quando cambia la proprietà o l'assegnazione dei centri di costo, non resta che aggiornare il campo **Proprietario** per la dimensione finanziaria.

## <a name="types-of-expenditure-reviewers"></a>Tipi di revisori spese

Non tutti i flussi di lavoro supportano il concetto di revisori spese. Per impostazione predefinita, è possibile configurare i revisori spese per richieste di acquisto, ordini di acquisto, fatture fornitore e note spese. Ciascuno di questi tipi di flusso di lavoro richiede la configurazione dei revisori spese in una pagina separata specifica per la funzione e il modulo. Per ogni documento supportato, i revisori spese possono essere utilizzati con flussi di lavoro a livello di intestazione o flussi di lavoro a livello di riga.

La tabella seguente mostra dove andare per configurare un revisore spese per ogni documento supportato.

| Documento | Percorso di navigazione |
|----------|-----------------|
| Note spese | Gestione spese \> Imposta \> Criteri \> Revisori spese |
| Ordine fornitore | Approvvigionamento \> Imposta \> Criteri \> Revisori spese ordini di acquisto |
| Richieste di acquisto | Approvvigionamento \> Imposta \> Criteri \> Revisori spese per la richiesta di acquisto |
| Fatture fornitore | Contabilità fornitori \> Impostazione criteri \> Fatture fornitore per revisori spese |

## <a name="expenditure-reviewer-assignments"></a>Assegnazioni dei revisori spese

Sono disponibili due tipi di incarico per ciascun revisore spese: *distribuzioni di progetti* e *distribuzioni organizzazione*. Per una distribuzione del progetto, è possibile selezionare tra autorità di progetto e dimensioni finanziarie. Per una distribuzione dell'organizzazione, è possibile selezionare le dimensioni finanziarie.

Le autorità di progetto includono il manager di progetto, il controller di progetto e il responsabile vendite di progetto. Queste autorità vengono definite direttamente sul progetto, selezionando un lavoratore nei campi appropriati.

Le dimensioni finanziarie sono controllate dalle strutture dei conti in ogni persona giuridica. Per ogni persona giuridica, è possibile selezionare quali dimensioni finanziarie verranno utilizzate con il revisore spese. Le dimensioni possono provenire sia dal progetto (in questo caso si selezionano le dimensioni nella scheda **Distribuzioni di progetti**) o dal documento (in questo caso, si selezionano le dimensioni nella scheda **Distribuzioni organizzazione**). Nel campo **Proprietario** della pagina **Valori di dimensione finanziaria** è possibile selezionare il lavoratore per ogni dimensione finanziaria.

## <a name="example-1-expenditure-reviewers-based-on-organization-distributions"></a>Esempio 1: revisori spese in base alle distribuzioni dell'organizzazione

Si lavora per Contoso Appliances e l'organizzazione ha sei reparti e 10 centri di costo. Quando viene inviata una nuova richiesta di acquisto, l'approvazione deve provenire prima dal responsabile del reparto e poi dal responsabile del centro di costo.

Per questo esempio, vengono configurati due *revisori spese per la richiesta di acquisto*:

- Per il primo revisore, si assegna un nome al reparto e poi si seleziona la dimensione finanziaria **Reparto** nella scheda **Distribuzioni organizzazione**. 
- Per il secondo revisore, si assegna un nome al centro di costo e poi si seleziona la dimensione finanziaria **Centro di costo** nella scheda **Distribuzioni organizzazione**.

Quando si configura il flusso di lavoro, si creano due fasi di approvazione. La prima è per il reparto e la seconda è per il centro di costo. Per ogni elemento di approvazione, selezionare **Partecipante** nel campo **Tipo di assegnazione** della scheda **Basato sui ruoli**, quindi **Partecipanti alla spesa** nel campo **Tipo di partecipante** e infine il partecipante appropriato nel campo **Partecipante**.

Quando viene creata la richiesta di acquisto, le dimensioni finanziarie del reparto e del centro di costo vengono assegnate alle righe della richiesta di acquisto. Quando il flusso di lavoro viene inviato, il sistema valuta prima il reparto nella richiesta di acquisto e assegna l'elemento di approvazione all'utente correlato al lavoratore selezionato per il reparto. Una volta completata la prima fase di approvazione, il sistema valuta la seconda fase di approvazione e assegna il secondo elemento di approvazione all'utente correlato al lavoratore selezionato per il centro di costo.

## <a name="example-2-expenditure-reviewers-based-on-project-distributions"></a>Esempio 2: revisori spese in base alle distribuzioni di progetti

Si lavora per la divisione servizi di Contoso Appliances. L'organizzazione richiede che il manager di progetto di ogni ordine d'acquisto approvi la spesa. Inoltre, il responsabile del centro di costo per il progetto deve approvarlo. Le approvazioni possono essere fatte contemporaneamente. In ogni caso, entrambi gli utenti devono approvare l'ordine di acquisto prima che il flusso di lavoro possa procedere.

Per questo esempio, si crei un *revisore spese ordini di acquisto* denominato **PM e centro di costo**. Selezionare la casella di controllo **Manager di progetto** e impostare l'opzione **Dimensione centro di costo** su **Sì** nella scheda **Distribuzioni di progetti** della pagina **Revisore spese ordini di acquisto**. Nell'ambito della configurazione, è necessario assicurarsi che il campo **Manager di progetto** sia impostato per tutti i progetti e che un proprietario sia specificato per tutti i centri di costo nella pagina **Valori di dimensione finanziaria**.

Quando si configura il flusso di lavoro, è necessario un elemento di approvazione. Selezionare **Partecipante** nel campo **Tipo di assegnazione**. Quindi, nella scheda **Basato sul ruolo** selezionare **Partecipanti alla spesa** nel campo **Tipo di partecipante** e infine il manager di progetto e il centro di costo nel campo **Partecipante**. Per garantire che il flusso di lavoro non possa procedere finché sia il manager di progetto che il proprietario del centro di costo non approvino il flusso di lavoro, impostare il campo **Criteri completamento** su **Tutti gli approvatori**.

Quando viene creato l'ordine di acquisto, il campo **Progetto** deve essere specificato. Se non è necessario un progetto per tutti gli ordini di acquisto, occorre aggiungere una decisione condizionale al flusso di lavoro per verificare la presenza di un progetto prima dell'esecuzione della fase di approvazione. Il sistema valuta quindi il progetto specificato per l'ordine di acquisto e assegna l'elemento di approvazione all'utente correlato al lavoratore nel campo **Manager di progetto**. Inoltre, il sistema crea un'attività e la assegna all'utente correlato al lavoratore selezionato nel campo **Proprietario** per il centro di costo del progetto. Si noti che questo esempio utilizza il centro di costo del progetto, non il centro di costo dell'ordine di acquisto.

## <a name="set-up-expenditure-reviewers"></a>Impostazione dei revisori spese

Questo esempio mostra come configurare un revisore spese per la richiesta di acquisto. Per configurare altri tipi di revisori spese, sostituire il percorso di navigazione nel passaggio 1 con il percorso appropriato dalla tabella nella precedente sezione [Tipi di revisori spese](configure-expenditure-reviewers.md#types-of-expenditure-reviewers) in questo argomento.

1. Andare ad **Approvvigionamento \> Imposta \> Criteri \> Revisori spese per la richiesta di acquisto**.
2. Nella pagina **Revisori spese per la richiesta di acquisto** selezionare **Nuovo**.
3. Nel campo **Nome** immettere un nome per la configurazione del revisore spese, ad esempio **centro di costo**.
4. Nella Scheda dettaglio **Revisori spese per persona giuridica** selezionare la persona giuridica da configurare.
5. Per la distribuzione di un progetto, selezionare la casella di controllo per ogni autorità di progetto, quindi **Sì** per ogni dimensione finanziaria che si desidera abilitare. 
6. Per una distribuzione dell'organizzazione, nella scheda **Distribuzioni organizzazione** selezionare **Sì** per ogni dimensione finanziaria che si desidera abilitare.
7. Ripeti i passaggi da 4 a 6 per ciascuna persona giuridica aggiuntiva.

## <a name="assign-owners-to-financial-dimensions"></a>Assegnare i proprietari alle dimensioni finanziarie

Per assegnare un proprietario a una dimensione finanziaria, attenersi alla procedura seguente.

1. Passare a **Contabilità generale \> Piano dei conti \> Dimensioni \> Dimensioni finanziarie**.
2. Nell'elenco selezionare la dimensione finanziaria a cui assegnare i proprietari.
3. Selezionare **Valori di dimensione**.
4. Selezionare **Modifica** per apportare modifiche ai valori di dimensione.
5. Nell'elenco selezionare il valore di dimensione a cui assegnare un proprietario.
6. Nel campo **Proprietario** selezionare il lavoratore a cui assegnare il valore di dimensione.

## <a name="configure-project-distributions"></a>Configurare le distribuzioni di progetto

Per assegnare le autorità di progetto a un progetto specifico, attenersi alla procedura che segue.

1. Passare a **Gestione progetti e contabilità \> Progetti \> Tutti i progetti**.
2. Selezionare il progetto a cui assegnare le autorità.
3. Selezionare **Modifica** per apportare modifiche al progetto.
4. Nella Scheda dettaglio **Generale** nella sezione **Responsabile** selezionare un lavoratore per i campi **Manager vendite**, **Manager di progetto** e **Controller di progetto** come richiesto.
5. Nella Scheda dettaglio **Dimensioni finanziarie** selezionare le dimensioni finanziarie richieste per il progetto.

## <a name="assign-expenditure-reviewers-to-a-workflow-task"></a>Assegnare revisori spese a un'attività del flusso di lavoro

Questo esempio mostra come configurare un flusso di lavoro di una richiesta di acquisto in modo che utilizzi un revisore spese per la richiesta di acquisto. Per configurare altri tipi di flussi di lavoro, la pagina del flusso di lavoro che è necessario aprire nel passaggio 1 potrebbe trovarsi nel modulo **Gestione spese** o **Contabilità fornitori** anziché nel modulo **Approvvigionamento**.

Per assegnare revisori spese per la richiesta di acquisto a un'attività del flusso di lavoro, attenersi ai passaggi che seguono.

1. Passare a **Approvvigionamento \> Impostazioni \> Flussi di lavoro di approvvigionamento**.
2. Toccare due volte (o fare doppio clic) su un flusso di lavoro esistente o creare un nuovo flusso di lavoro.
3. Nell'editor del flusso di lavoro, nel riquadro **Flusso di lavoro** selezionare l'attività a cui assegnare la configurazione del revisore spese. Quindi, nel **riquadro Azioni** del gruppo **Mostra** selezionare **Proprietà**.
4. Nel riquadro sinistro della pagina **Proprietà** selezionare **Assegnazione**.
5. Nella scheda **Tipo di assegnazione** selezionare **Partecipante**.
6. Nella scheda **Basato sul ruolo** del campo **Tipo di partecipante** selezionare **Partecipanti alla spesa**. Quindi, nel campo **Partecipante** selezionare la configurazione del revisore spese che si desidera utilizzare per l'attività del flusso di lavoro.
