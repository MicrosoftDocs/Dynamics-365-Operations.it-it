---
title: Impostazione informazioni di consegna
description: In questo argomento viene descritto come impostare le informazioni di consegna per il modulo Costo sbarcato.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMPortTable, ITMLeadTimeTable, ITMLegTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 5d20f732f02140204d67e5602acaf42f9d9df424
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021590"
---
# <a name="delivery-information-setup"></a>Impostazione informazioni di consegna

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come impostare le informazioni di consegna per il modulo **Costo sbarcato**.

## <a name="shipping-ports"></a>Porti di spedizione

I porti di spedizione identificano il luogo da e verso cui vengono spedite le merci. Per ogni viaggio vengono definiti un porto di destinazione e un porto di origine, in base al percorso selezionato per la nave in viaggio. I porti di spedizione sono utilizzati per creare le tappe di un percorso nonché le attività di viaggio. Questi sono in genere definiti utilizzando il nome della città e il paese o la regione in cui si trova il porto di spedizione fisico.

Per utilizzare i porti di spedizione, selezionare **Costo sbarcato \> Configurazione informazioni di consegna \> Porti di spedizione**. In questo campo, è possibile visualizzare, aggiungere e rimuovere i record dei porti di spedizione. Nella seguente tabella sono descritti i campi disponibili per ogni record.

| Campo | Descrizione |
|---|---|
| Porto di spedizione | Immettere un nome/numero di identificazione univoco per il porto di spedizione. |
| Descrizione | Immettere una descrizione del porto di spedizione. |

## <a name="tracking-control-center"></a><a name="tracking-control-center"></a>Centro di controllo tracciabilità

Il Centro di controllo tracciabilità consente di impostare i lead time, gli aggiornamenti dello stato e il flusso di informazioni associato a un viaggio quando i contenitori di spedizione si spostano da uno scalo all'altro. Quando si crea un record del controllo tracciabilità, viene associato a uno scalo specifico di un percorso per un viaggio. Quando un viaggio aggiorna uno scalo, il record associato verrà aggiornato e compilato come definito. È possibile aggiornare le informazioni di tracciabilità per singoli viaggi nella pagina **Tutti i viaggi**.

Per aprire il Centro di controllo tracciabilità, selezionare **Costo sbarcato \> Configurazione informazioni di consegna \> Centro di controllo tracciabilità**.

Il Centro di controllo tracciabilità mostra una delle tre visualizzazioni di pagina, a seconda del valore selezionato nel campo **Tipo di creazione** nel riquadro elenco: *Vuoto*, *Lead time* o *Aggiornamento stato*. Ogni campo Tipo di creazione aggiorna un diverso insieme di informazioni associate all'avanzamento di un viaggio dal punto di origine alla destinazione finale.

### <a name="common-rule-settings"></a>Impostazioni di regole comuni

La tabella seguente mostra i campi disponibili per tutti e tre i tipi di creazione nel Centro di controllo tracciabilità.

| Campo | Descrizione |
|---|---|
| Tabella di origine, Campo di origine | Questi campi identificano una tabella e un campo di origine nel database. La regola caricherà il valore nel campo e quindi lo utilizzerà nel modo definito dalle altre impostazioni della regola. |
| Tabella di destinazione, Campo di destinazione | Questi campi identificano una tabella e un campo di destinazione nel database. La regola caricherà il valore nel campo e quindi lo utilizzerà (o lo sovrascriverà) nel modo definito dalle altre impostazioni della regola. |
| Attività | Questo campo identifica il tipo di attività da applicare a un contenitore di spedizione a cui corrisponde una regola. |
| Criteri di corrispondenza | Questo campo determina il modo in cui il sistema identifica una corrispondenza per una regola. In ogni istanza, il sistema esamina i dati nelle tabelle di origine e di destinazione per determinare se e quando un campo deve essere aggiornato nella tabella di destinazione.<p>Ad esempio, la tabella di origine è *Viaggi* e la tabella di destinazione è *Intestazione di acquisto* o *Righe acquisti*. Nella tabella *Viaggi* il valore di **Porto di origine** è *Hong Kong* e nella tabella *Intestazione di acquisto* il valore di **Porto di origine** è *Shanghai*. Viene quindi creata una regola dove *Hong Kong* è il porto di origine. In questo caso, i valori del campo **Criteri di corrispondenza** funzioneranno nel modo seguente:</p><ul><li>**Entrambi** - Il campo di destinazione non verrà aggiornato, perché uno dei due porti non corrisponde.</li><li>**Origine** - Il campo di destinazione verrà aggiornato, perché il porto di origine della tabella di origine è *Hong Kong*.</li><li>**Destinazione** - Il campo di destinazione non verrà aggiornato, perché il porto di destinazione della tabella di destinazione è *Shanghai* (non *Hong Kong*).</li></ul> |
| Azione copia | I valori disponibili sono *Copia* e *Predefinito*. Selezionare *Copia* per copiare il valore del campo di origine nel campo di destinazione. Selezionare *Predefinito* per impostare un valore statico per il campo di destinazione. |
| Predefinito | Quando il campo **Azione copia** è impostato su *Predefinito*, il campo **Predefinito** definisce il valore predefinito del campo di destinazione. Ad esempio, se l'azione è correlata a un aggiornamento del porto e il campo **Azione copia** è impostato su *Predefinito*, il campo **Predefinito** identifica un porto. |
| Scalo | Questo campo identifica lo scalo del percorso per il quale si verifica l'azione specificata, ad esempio il carico o la dogana. |
| Provider di servizi | Se un provider di servizi specifico viene utilizzato per l'aggiornamento dello stato/scalo corrente del percorso, questo campo identifica il provider di servizi. I provider di servizi sono definiti nel conto fornitore. |

### <a name="lead-time-rules"></a>Regole lead time

Il lead time è il tempo stimato che un viaggio richiederà per completare uno scalo definito di un percorso per un viaggio. Il lead time di ciascun scalo di un percorso viene utilizzato per calcolare la data di consegna stimata del viaggio. Tale data viene quindi inserita nel campo **Data di consegna confermata** in ogni riga acquisto nel viaggio.

Le regole di lead time vengono utilizzate per gestire gli aggiornamenti delle date. Le attività vengono generate automaticamente quando un modello di percorso viene utilizzato per un viaggio.

Per aggiungere una regola di lead time al Centro di controllo tracciabilità, seguire questi passaggi.

1. Eseguire uno dei passaggi riportati di seguito.

    - Selezionare **Costo sbarcato \> Configurazione percorso con più scali \> Scali**. Selezionare lo scalo per il quale si desidera impostare i lead time, quindi, nel riquadro Azioni, selezionare **Centro di controllo tracciabilità**. Il Centro di controllo tracciabilità viene precaricato con le informazioni sullo scalo selezionato.
    - Selezionare **Costo sbarcato \> Impostazione informazioni di consegna \> Centro di controllo tracciabilità**. È quindi necessario selezionare manualmente uno scalo nel passaggio 4 di questa procedura.

1. Nel riquadro elenco, impostare il campo **Tipo di creazione** su *Lead time*.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Se si è iniziata la procedura dal Centro di controllo tracciabilità nel passaggio 1, impostare il campo **Scalo** per il quale si desidera creare una regola di lead time. Se si è iniziata la procedura dalla pagina **Scali**, il campo **Scalo** è preimpostato sullo scalo selezionato prima di aprire il Centro di controllo tracciabilità.

    In base al valore del campo **Scalo**, diversi campi vengono impostati automaticamente, come mostrato di seguito:

    - **Tabella di origine:** *Attività contenitore*
    - **Campo di origine:** *Data d'inizio*
    - **Tabella di destinazione:** *Attività contenitore*
    - **Campo di destinazione:** *Data di fine stimata*

1. Nel campo **Attività** selezionare l'attività a cui deve essere applicata la regola corrente.
1. Nel campo **Lead time**, immettere il lead time (in giorni) da applicare quando viene attivata la regola corrente.

### <a name="status-update-rules"></a>Regole di aggiornamento dello stato

I record in cui il campo **Tipo di creazione** è impostato su *Aggiornamento stato* aggiorneranno lo stato delle righe di ordine fornitore o lo stato a livello di viaggio, contenitore di spedizione o registrazione. Gli stati possono essere impostati indipendentemente. Usarli per informare l'utente o il reparto sulla fase di un viaggio (come i documenti ricevuti o le merci in transito).

Quando il campo **Tipo di creazione** è impostato su *Aggiornamento stato*, il Centro di controllo tracciabilità include una Scheda dettaglio **Righe** in cui è possibile definire un'area di costo e lo stato aggiornato del viaggio. Ad esempio, si ha una riga in cui il campo **Area di costo** è impostato su *Contenitore*, e il campo **Stato viaggio** è impostato su *Merci in transito*. In questo caso, quando un ordine completa lo scalo specificato, il campo **Stato viaggio** del contenitore di spedizione verrà aggiornato a *Merci in transito*.

Gli aggiornamenti dello stato forniscono lo stato di un viaggio attraverso le righe di viaggio e le righe di ordine fornitore associate a quel viaggio. A mano a mano che un viaggio passa attraverso il relativo percorso dal porto, dalla navigazione e dalla dogana, al magazzino di destinazione, il campo **Stato viaggio** del record viaggio fornisce una visualizzazione rapida della fase in cui si trovano gli articoli.

Per aggiungere una regola di aggiornamento dello stato al Centro di controllo tracciabilità, seguire questi passaggi.

1. Eseguire uno dei passaggi riportati di seguito.

    - Selezionare **Costo sbarcato \> Configurazione percorso con più scali \> Scali**. Selezionare lo scalo per il quale si desidera impostare un aggiornamento dello stato, quindi, nel riquadro Azioni, selezionare **Centro di controllo tracciabilità**. Il Centro di controllo tracciabilità viene precaricato con le informazioni sullo scalo selezionato.
    - Selezionare **Costo sbarcato \> Impostazione informazioni di consegna \> Centro di controllo tracciabilità**. È quindi necessario selezionare manualmente uno scalo nel passaggio 4 di questa procedura.

1. Nel riquadro elenco, impostare il campo **Tipo di creazione** su *Aggiornamento stato*.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Se si è iniziata la procedura dal Centro di controllo tracciabilità nel passaggio 1, impostare il campo **Scalo** per il quale si desidera creare una regola di aggiornamento dello stato. Se si è iniziata la procedura dalla pagina **Scali**, il campo **Scalo** è preimpostato sullo scalo selezionato prima di aprire il Centro di controllo tracciabilità.

    In base al valore del campo **Scalo**, diversi campi vengono impostati automaticamente, come mostrato di seguito:

    - **Tabella di origine:** *Attività contenitore*
    - **Campo di origine:** *Data di fine effettiva*
    - **Tabella di destinazione:** questo campo è lasciato vuoto.
    - **Campo di destinazione:** questo campo è lasciato vuoto.

1. Nel campo **Attività** selezionare l'attività a cui deve essere applicata la regola.
1. Nella Scheda dettaglio **Righe**, immettere gli aggiornamenti dello stato per ogni area di costo.

### <a name="blank-type-rules"></a>Regole di tipo vuoto

Per sostituire o immettere un valore di campo, si utilizzano record il cui campo **Tipo di creazione** è *Vuoto*, in base ai dati di un altro campo. Un campo di Costo sbarcato sovrascriverà i dati in altre aree di Microsoft Dynamics 365 Supply Chain Management, in base alle regole impostate nel Centro di controllo tracciabilità.

1. Selezionare **Costo sbarcato \> Impostazione informazioni di consegna \> Centro di controllo tracciabilità**.
1. Nel riquadro elenco, impostare il campo **Tipo di creazione** su *Vuoto*.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Definire i valori di origine e destinazione, i criteri di corrispondenza, l'azione di copia e altri parametri pertinenti, come richiesto per la regola.

### <a name="required-tracking-control-setup"></a>Configurazione del controllo tracciabilità

Per ogni modello di percorso, devono essere impostati due record nel Centro di controllo tracciabilità. Entrambi questi record hanno il campo **Tipo di creazione** impostato su *Vuoto* e sono utilizzati in tutte le implementazioni di Costo sbarcato. Contribuiscono a garantire che la data confermata di acquisto e le date previste per le merci in transito siano aggiornate per i viaggi e nelle relative righe dell'ordine fornitore nel modo previsto.

Il primo record è necessario per aggiornare le righe di acquisto. Deve avere le seguenti impostazioni:

- **Tabella di origine:** *Attività contenitore*
- **Campo di origine:** *Data di fine stimata*
- **Tabella di destinazione:** *Righe di acquisto*
- **Campo di destinazione:** *Data confermata o di consegna*

Il secondo record è necessario per aggiornare le transazioni delle merci in transito. Deve avere le seguenti impostazioni:

- **Tabella di origine:** *Attività contenitore*
- **Campo di origine:** *Data di fine stimata*
- **Tabella di destinazione:** *Ordine merci in transito*
- **Campo di destinazione:** *Data prevista*
