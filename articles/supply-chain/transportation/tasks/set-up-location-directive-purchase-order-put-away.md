---
title: Impostare una direttiva di ubicazione per lo stoccaggio dell'ordine fornitore
description: In questo argomento viene illustrato come impostare una direttiva di ubicazione semplice.
author: ShylaThompson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventFixedLocation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f02ebbb22e11b116355be42325edd041b10c5cb4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831484"
---
# <a name="set-up-a-location-directive-for-purchase-order-put-away"></a>Impostare una direttiva di ubicazione per lo stoccaggio dell'ordine fornitore

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come impostare una direttiva di ubicazione semplice. L'esempio visualizzato crea una direttiva ubicazione da utilizzare per determinare dove inserire gli articoli ricevuti per un ordine fornitore. È possibile riprodurre questa guida attività con i dati indicati usando la società di dati dimostrativi USMF. Precondizioni: è necessario creare un codice smaltimento. In questa procedura viene utilizzato un codice smaltimento denominato Nuova etichetta. Se si crea una direttiva ubicazione i propri dati, è necessario impostare gestione avanzata di magazzino per il magazzino e gli articoli. Questa procedura è destinata al responsabile del magazzino.

1. Nel pannello di navigazione andare a **Moduli > Gestione magazzino > Impostazioni > Magazzino > Direttive ubicazione**.
2. Nel campo **Tipo ordine di lavoro** selezionare **Ordini fornitori**.

## <a name="create-a-location-directive-header"></a>Creare un'intestazione direttiva ubicazione
1. Selezionare **Nuovo**.
2. Immettere un numero nel campo **Numero progressivo**. Questa è la sequenza in cui la direttiva ubicazione viene elaborata per il tipo di lavoro selezionato. Se necessario, la sequenza può essere modificata.  
3. Digitare un valore nel campo **Nome**. Questo è l'identificatore univoco per la direttiva.  
4. Nel campo **Tipo di lavoro** selezionare **Inserisci**. Selezionare il tipo di lavoro da eseguire. Per la direttiva con tipo di ordine di lavoro Ordine fornitore, **Inserisci** è l'unico valore supportato.  
5. Digitare un valore nel campo **Sito**.
6. Digitare un valore nel campo **Magazzino**. Lasciare vuoto il codice direttiva.  I codici direttiva vengono utilizzati per collegare una riga ordine di lavoro del tipo Inserimento a una direttiva specifica. Per gli ordini fornitore, l'ubicazione dell'ultima riga ordine di lavoro di tipo Inserimento è risolta prima che venga determinato il modello di lavoro. Pertanto non è possibile connettere l'ultima riga di un modello di lavoro alla direttiva specifica.   
7. Nel campo **Codice smaltimento** digitare un valore. Il codice smaltimento limita l'utilizzo della direttiva ubicazione, in modo che venga utilizzata solo se il lavoratore del magazzino inserisce questo valore specifico durante la registrazione dell'articolo tramite un dispositivo mobile.  
8. Selezionare **Salva**.

## <a name="edit-the-query-for-directive"></a>Modificare la query relativa alla direttiva
1. Selezionare **Modifica query**. L'utilizzo della direttiva è già limitato da utilizzare per gli articoli registrati nel magazzino specificato e al codice smaltimento specificato. È possibile aggiungere altri vincoli di utilizzo della query.  
2. Selezionare **OK**.

## <a name="add-directive-lines"></a>Aggiungere righe direttiva
1. Selezionare **Nuovo**. Questa è la sequenza in cui le righe della direttiva ubicazione vengono elaborate per il tipo di lavoro selezionato. Se necessario, la sequenza può essere modificata.  
2. Nel campo **Da quantità** immettere un numero. Si tratta della quantità inferiore per cui la riga direttiva è valida.  
3. Nel campo **A quantità** immettere un numero.
4. Digitare un valore nel campo **Unità**. L'unità in cui sono espressi i valori di Da quantità e A quantità. Se si lascia vuoto questo campo, verrà utilizzata l'unità di inventario dell'articolo.  
5. Selezionare un'opzione nel campo **Trova quantità**.
    - Nessuna o Quantità targa: la quantità registrata su ogni targa.  
    - Quantità in unità: l'intera quantità registrata.  
    - Quantità rimanente: la quantità ancora da registrare che è specificata nella riga dell'ordine fornitore.  
    - Quantità prevista: la quantità totale che è specificata nella riga dell'ordine fornitore  
6. Selezionare o deselezionare la casella di controllo **Limita per unità**. Se si seleziona questa opzione e si specifica l'unità sulla pagina **Limita per unità**, solo gli articoli con tale unità di misura possono essere inseriti nell'ubicazione. Ad esempio, se l'unità di misura è PL (pallet), solo gli articoli in pallet potranno essere stoccati nell'ubicazione specifica.  
7. Selezionare o deselezionare la casella di controllo **Consenti divisione**. Ciò consente alla direttiva di suddividere la quantità tra più ubicazioni.  
8. Selezionare **Salva**.

## <a name="restrict-the-directive-line-to-a-specific-unit"></a>Limitare la riga direttiva a un'unità specifica
1. Selezionare **Limita per unità**. Questo pulsante è disponibile solo quando si preme **Salva** dopo che è stata selezionata la casella di controllo **Limita per unità**.  
2. Digitare un valore nel campo **Unità**.
3. Chiudere la pagina.

## <a name="add-a-location-directive-action-line"></a>Aggiungere una riga dell'azione direttiva ubicazione
1. Selezionare **Nuovo**. Questa è la sequenza in cui le righe dell'azione direttiva ubicazione vengono elaborate per il tipo di lavoro selezionato. Se necessario, la sequenza può essere modificata.  
2. Digitare un valore nel campo **Nome**. Questo è l'identificatore univoco per l'azione direttiva.  
3. Selezionare un'opzione nel campo **Utilizzo ubicazioni fisse**.
    - Ubicazione fisse e non fisse: tutte le ubicazioni non fisse sono valide come lo è l'ubicazione fissa propria del prodotto, nell'intervallo specificato nella query.  
    - Solo ubicazioni fisse per il prodotto: le ubicazioni fisse per il prodotto sono valide e tutte le varianti prodotto condividono lo stesso insieme di ubicazione fisse.  
    - Solo ubicazioni fisse per la variante prodotto: solo le ubicazioni fisse specificate per ogni variante prodotto sono valide.  
4. Selezionare un'opzione nel campo **Strategia**. Gli ordini di lavoro di tipo Ordine fornitore supportano le seguenti strategie: 
    - Nessuno: l'articolo viene messo nella prima ubicazione che viene rilevata.  
    - Consolidato: l'articolo viene messo in un'ubicazione in cui sono già disponibili articoli simili.  
    - Ubicazione vuota senza alcun lavoro in entrata: l'articolo viene messo nella prima ubicazione vuota che viene rilevata. Un'ubicazione viene considerata vuota se non è presente un inventario fisico e non è previsto lavoro in entrata.  
5. Selezionare **Salva**.

## <a name="edit-the-query-for-directive-action-line"></a>Modificare la query relativa alla riga dell'azione
1. Selezionare **Modifica query**.
2. Selezionare **Aggiungi**.
3. Nel campo **Campo**, digitare `location profile ID`. In questo esempio le ubicazioni possibili verranno limitate utilizzando un ID profilo dell'ubicazione.  
4. Digitare un valore nel campo **Criteri**.
5. Selezionare **OK**. È possibile continuare ad aggiungere righe direttive e azioni direttive finché non sono stati coperti tutti gli scenari possibili nel magazzino.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]