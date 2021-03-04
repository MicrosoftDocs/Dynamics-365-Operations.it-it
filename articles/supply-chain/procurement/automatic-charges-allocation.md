---
title: Allocazione automatica degli addebiti
description: La funzionalità degli addebiti in Microsoft Dynamics 365 Supply Chain Management aiuta ad allocare automaticamente gli addebiti agli ordini fornitori o agli ordini clienti.
author: dasani-madipalli
manager: tfehr
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 818affc7591577b69309928eb9b0e71130884cec
ms.sourcegitcommit: 66ecc6cb36ef4f723c77e09d6a33f9c42f8fa392
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431448"
---
# <a name="automatic-allocation-of-charges"></a>Allocazione automatica degli addebiti

[!include [banner](../includes/banner.md)]

In base al cliente con cui si sta lavorando o all'articolo che si sta vendendo, è possibile voler applicare addebiti aggiuntivi specifici. La funzionalità degli *addebiti* in Microsoft Dynamics 365 Supply Chain Management aiuta ad allocare automaticamente gli addebiti agli ordini fornitori o agli ordini clienti.

Gli addebiti automatici vengono applicati automaticamente quando si crea un ordine cliente o un ordine fornitore. È possibile definire gli addebiti automatici per fornitori, clienti, gruppi di fornitori o articoli. È inoltre possibile definire gli addebiti automatici applicabili a tutti i fornitori, clienti o articoli.

## <a name="set-up-charges-codes"></a>Impostare i codici di addebito

Per allocare gli addebiti è necessario prima definire i codici di addebito.

1. Eseguire uno dei passaggi riportati di seguito.

    - Per ordini fornitori: andare a **Contabilità fornitori \> Impostazione addebiti \> Codice di addebito**.
    - Per ordini clienti: andare a **Contabilità clienti \> Impostazione addebiti \> Codice di addebito**.

1. Nel riquadro azioni selezionare **Nuova** per creare un codice di addebito.
1. Nell'intestazione del nuovo record, impostare i seguenti campi:

    - **Codice di addebito** - Inserire un codice per gli addebiti.
    - **Descrizione** - Immettere una descrizione dell'addebito.
    - **Fascia IVA articoli** - Selezionare una fascia IVA articoli, se applicabile.
    - **Ripartizione** - Impostare questa opzione su *Sì* per ripartire gli addebiti. Questa opzione è disponibile solo per gli ordini cliente.
    - **Importo massimo** - Immettere l'importo massimo che si concede per il codice di addebito. Questo campo viene utilizzato per convalidare gli addebiti per le fatture fornitore. È disponibile solo per gli ordini fornitore.

        > [!NOTE]
        > Per attivare la funzionalità di convalida degli addebiti per gli ordini fornitore andare a **Contabilità fornitori \> Imposta \> Parametri contabilità fornitori**. Nella scheda dettaglio **Convalida fattura** nella sezione **Convalida fattura** impostare l'opzione **Abilita convalida abbinamento fatture** su *Sì*.

1. Le scheda dettaglio **Registrazione** include le sezioni **Debito** e **Credito**. Impostare i seguenti campi, a seconda della contabilità generale in cui si desidera registrare gli addebiti:

    - **Tipo** - Selezionare il tipo di conto in cui si sta registrando (*Contabilità generale*, *Cliente* o *Articolo*).
    - **Registrazione** - Selezionare il tipo di registrazione da creare (come *Commissione broker* o *Liquidazione cliente*).
    - **Conto** - Selezionare il conto in cui registrare l'addebito.

1. Nel riquadro azioni selezionare **Salva**.

## <a name="create-charge-groups"></a>Creare gruppi di addebiti

I gruppi di addebiti assegnano automaticamente addebiti specifici a un gruppo di clienti o fornitori. Le seguenti sottosezioni descrivono come creare e assegnare questi gruppi di addebiti.

### <a name="charge-groups-for-purchase-orders"></a>Gruppi di addebiti per ordini fornitore

Per creare gruppi di addebiti per ordini fornitore attenersi alla seguente procedura.

1. Andare a **Contabilità fornitori \> Impostazione addebiti \> Gruppo di addebiti fornitore**.
1. Nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia e quindi impostare i seguenti campi:

    - **Gruppo di addebiti** - Immettere il nome del gruppo di addebiti.
    - **Descrizione** - Immettere una descrizione del gruppo di addebiti.

1. Nel riquadro azioni selezionare **Salva**.
1. Andare a **Contabilità fornitori \> Fornitori \> Tutti i fornitori** e aprire un fornitore esistente o creare un nuovo fornitore.
1. Nella scheda dettaglio **Impostazioni predefinite ordine fornitore** nella sezione **Ordine fornitore** impostare il campo **Gruppo di addebiti** sul gruppo di addebiti appena creato.

### <a name="charge-groups-for-sales-orders"></a>Gruppi di addebiti per ordini cliente

Per creare gruppi di addebiti per ordini cliente attenersi alla seguente procedura.

1. Andare a **Contabilità clienti \> Impostazione addebiti \> Gruppi di addebiti cliente**.
1. Nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia e quindi impostare i seguenti campi:

    - **Gruppo di addebiti** - Immettere il nome del gruppo di addebiti.
    - **Descrizione** - Immettere una descrizione del gruppo di addebiti.

1. Nel riquadro azioni selezionare **Salva**.
1. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti** e aprire un cliente esistente o creare un nuovo cliente.
1. Nella scheda dettaglio **Impostazioni predefinite ordine fornitore** nella sezione **Ordine cliente** impostare il campo **Gruppo di addebiti** sul gruppo di addebiti appena creato.

## <a name="define-auto-charges"></a>Definire gli addebiti automatici

Dopo aver impostato i codici di addebito, seguire questi passaggi per definire gli addebiti automatici.

1. Eseguire uno dei passaggi riportati di seguito.

    - Per ordini fornitore: andare a **Approvvigionamento \> Imposta \> Addebiti \> Addebiti automatici**.
    - Per ordini clienti: andare a **Contabilità clienti \> Imposta \> Impostazione addebiti \> Addebiti automatici**.

1. Nel riquadro elenco, nel campo **Livello** selezionare il livello in cui si applicano gli addebiti automatici:

    - *Principale* – applicare gli addebiti all'intestazione dell'ordine.
    - *Riga* – applicare gli addebiti alle righe ordine.

1. Selezionare un addebito automatico esistente per modificarlo oppure selezionare **Nuovo** per definire un nuovo addebito automatico.
1. Nell'elenco **Codice conto** selezionare uno dei seguenti valori per specificare l'ambito dei conti che saranno interessati:

    - *Tabella* – assegnare gli addebiti a un cliente o a un fornitore specifico.
    - *Gruppo* – assegnare gli addebiti a un gruppo di addebiti vari.
    - *Tutto* – assegnare gli addebiti a tutti i clienti o i fornitori.

1. Nel campo **Relazione cliente** o **Relazione fornitore** selezionare un fornitore o cliente specifico se si imposta il campo **Codice conto** su *Tabella*. Se si imposta il campo **Codice conto** su *Gruppo*, selezionare un gruppo di addebiti cliente o fornitore.
1. Nel campo **Codice articolo** selezionare uno dei seguenti valori per specificare l'ambito degli articoli che saranno interessati. È possibile selezionare un codice articolo solo quando si definiscono gli addebiti automatici a livello di riga.

    - *Tabella* – assegnare gli addebiti a un articolo specifico.
    - *Gruppo* – assegnare gli addebiti a un gruppo di addebiti articoli.
    - *Tutti* – assegnare gli addebiti a tutti gli articoli.

1. Nel campo **Relazione articolo** selezionare un articolo specifico se il campo **Codice articolo** è stato impostato su *Tabella*. Se il campo **Codice articolo** è stato impostato su *Gruppo*, selezionare un gruppo di addebiti articolo.
1. **Solo per ordini cliente:** nel campo **Codice modalità di consegna** selezionare uno dei seguenti valori per specificare l'ambito delle modalità di consegna interessate:

    - *Tabella* – assegnare gli addebiti a una modalità di consegna specifica.
    - *Gruppo* – assegnare gli addebiti a un gruppo di modalità di consegna.
    - *Tutti* – assegnare gli addebiti a tutte le modalità di consegna.

1. **Solo per ordini cliente:** nel campo **Relazione tra modalità di consegna** selezionare una specifica modalità di consegna se il campo **Codice modalità di consegna** è stato impostato su *Tabella*. Se il campo **Codice modalità di consegna** è stato impostato su *Gruppo*, selezionare un gruppo di modalità di consegna.
1. Nella Scheda dettaglio **Righe** definire gli addebiti e le tariffe di addebito da utilizzare quando viene applicato l'addebito automatico. È possibile utilizzare la barra degli strumenti in questa scheda dettaglio per aggiungere tutte le righe necessarie. Per ciascuna riga, impostare i seguenti campi:

    - **Valuta** - Selezionare la valuta da utilizzare per calcolare l'addebito.
    - **Codice di addebito** - Selezionare il codice per l'addebito.
    - **Categoria** – Selezionare uno dei seguenti valori:

        - *Fisso* – l'addebito viene immesso come importo fisso della riga. Le spese fisse possono essere utilizzate per gli addebiti specificati nell'intestazione e nelle righe dell'ordine.
        - *Pzi* – l'addebito è basato sull'unità. Tali addebiti possono essere utilizzati solo nelle righe ordine. Vengono visualizzati quando si calcola il totale dell'ordine.
        - *Percentuale* – l'addebito viene immesso come percentuale della riga. Gli addebiti in percentuale possono essere utilizzati per gli addebiti specificati nell'intestazione e nelle righe dell'ordine.
        - *Percentuale interaziendale* – l'addebito viene immesso come percentuale della riga per gli ordini interaziendali. Gli addebiti in percentuale interaziendali possono essere utilizzati solo nelle righe ordine.
        - *Esterno* – l'addebito viene calcolato da un servizio di terze parti associato a uno o più vettori di spedizione.

    - **Valore spese** - Immettere il valore dell'addebito, in base alla categoria selezionata.
    - **Codice valuta addebito** - Specificare una valuta per l'addebito se si desidera utilizzare una valuta diversa da quella specificata nel campo **Valuta**. È possibile usare una valuta differente solo se il **tipo di addebito** o di **accredito** per il codice spese selezionato è impostato su *Conto CoGe* o *Articolo*.
    - **Da importo** – Specificare l'importo iniziale a cui applicare l'addebito automatico. In questo contesto l'importo fa riferimento al totale dell'ordine.
    - **A importo** – Specificare l'importo finale a cui applicare l'addebito automatico. In questo contesto l'importo fa riferimento al totale dell'ordine.
    - **Gruppo IVA** - Specificare una fascia IVA.
    - **Sito** e **Magazzino** - Specificare un sito e un magazzino se gli addebiti devono essere applicati solo per un sito e un magazzino specifici.
    - **Conserva** – Selezionare questa casella di controllo per conservare le transazioni addebiti dopo il completamento della fatturazione, in modo che l'addebito venga applicato ogni volta che si crea una nuova fattura per il conto cliente selezionato.

1. **Solo per ordini di vendita:** Se si desidera calcolare gli addebiti a più livelli, vedere [Addebiti a più livelli sugli ordini cliente](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/about-tiered-charges-on-sales-orders) per informazioni.

## <a name="allocate-charges-from-the-header-to-a-line"></a>Allocare gli addebiti dall'intestazione a una riga

La procedura seguente mostra come allocare gli addebiti a livello di intestazione a una riga. Prima di iniziare questa procedura, si deve già avere un addebito a livello di intestazione di tipo *importo fisso* e un ordine in cui viene applicato tale addebito. Inoltre, l'ordine deve già includere almeno una voce.

1. Aprire l'ordine fornitore o l'ordine di addebito.
1. Nel riquadro azioni, seguire uno di questi passaggi:

    - Per ordini fornitore: nella scheda **Acquisto** nel gruppo **Addebiti** selezionare **Alloca addebiti**.
    - Per ordini cliente: nella scheda **Vendita** nel gruppo **Addebiti** selezionare **Alloca addebiti**.

1. Nella finestra di dialogo **Alloca addebiti a righe ordine** impostare i seguenti campi:

    - **Allocazione addebiti** - Selezionare uno dei seguenti valori per specificare come devono essere allocati gli addebiti:

        - *Importo netto* - Allocare gli addebiti in base all'importo di ciascuna riga rispetto all'importo netto totale.
        - *Quantità* - Allocare gli addebiti in base al numero di unità per ogni riga rispetto al numero totale di unità.
        - *Per riga* – Allocare gli addebiti equamente in base al numero totale di righe.

    - **Alloca addebiti a righe** - Selezionare un valore per specificare se gli addebiti devono essere allocati a tutte le righe, solo alle righe positive o solo alle righe negative.
    - **Alloca tutto** – Selezionare questa casella di controllo per allocare le spese alle righe ordine fornitore, anche se il tipo di addebito del codice spese è diverso da *Articolo*.
    - **Ricevuto** – Selezionare questa casella di controllo per allocare le spese solo alle righe ordine ricevuto.
    - **Stoccato** – Selezionare questa casella di controllo per allocare le spese solo alle righe ordine inventariate.
    - **Mostra selezioni e cancella righe specifiche** - Selezionare questa casella di controllo per escludere righe specifiche da questa allocazione. Quando si seleziona questa casella di controllo, la griglia **Scegli le righe da escludere dall'allocazione** viene aperta. Questa griglia include solo le righe che soddisfano i criteri definiti nelle impostazioni **Assegna gli addebiti alle righe** e **Stoccato**. Ad esempio, se si imposta il campo **Assegna gli addebiti alle righe** su *Righe positive* e si seleziona la casella di controllo **Stoccato**, solo le righe che sono positive e inventariate vengono visualizzate nella griglia. Inoltre, la griglia filtra automaticamente tutte le righe per cui è già stata ricevuta l'intera quantità. Con la griglia aperta, deselezionare la casella di controllo **Includi** per ogni riga che deve essere esclusa dall'allocazione. 

        > [!IMPORTANT]
        > Quando si utilizza la griglia **Scegli le righe da escludere dall'allocazione** assicurarsi di lasciare la griglia aperta finché non si seleziona **Alloca**. Se si chiude la griglia prima di selezionare **Alloca**, le impostazioni nella griglia andranno perse. Pertanto, gli addebiti verranno allocati in base ai criteri definiti in precedenza.

1. Selezionare **Alloca** per applicare le impostazioni e chiudere la finestra di dialogo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]