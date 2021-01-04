---
title: Definire i processi di conteggio scorte
description: In questo argomento viene descritta la configurazione dei processi di conteggio scorte di base mediante la creazione di un gruppo di conteggio e di un giornale di registrazione di conteggio.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountGroup, InventJournalName, InventParameters, EcoResProductDetailsExtended, InventItemLocation, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9df5db0e71f550e82820e15b1597d9e287071f83
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431411"
---
# <a name="define-inventory-counting-processes"></a>Definire i processi di conteggio scorte

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritta la configurazione dei processi di conteggio scorte di base mediante la creazione di un gruppo di conteggio e di un giornale di registrazione di conteggio. Viene inoltre illustrato come abilitare i criteri di conteggio a livello di articolo e di magazzino. Queste attività verranno in genere eseguite da un supervisore del magazzino. È un prerequisito per avere alcuni prodotti rilasciati e magazzini esistenti. Se si utilizza una società di dati dimostrativi, è possibile eseguire questa procedura nella società USMF con un articolo stoccato.


## <a name="create-a-counting-group"></a>Creare un gruppo di conteggio.
1. Nel pannello di navigazione andare a **Moduli > Gestione articoli > Impostazioni > Inventario > Gruppi di conteggio**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Gruppo di conteggio** della nuova riga.
4. Digitare un valore nel campo **Nome**.
5. Nel campo **Codice di conteggio** selezionare un'opzione.

    - **Manuale**: vengono incluse righe ogni volta che si esegue il processo. In altri termini, consente di stabilire l'intervallo di conteggio per il gruppo di conteggio.  
    - **Periodo**: vengono incluse righe per il periodo nel giornale di registrazione di conteggio alla scadenza dell'intervallo periodico.  
    - **Zero in magazzino**: se le scorte disponibili raggiungono 0 (zero) vengono generate righe nel giornale di registrazione di conteggio all'avvio del processo. Se le scorte disponibili raggiungono 0 dopo un conteggio, vengono generate righe al successivo avvio del conteggio.  
    - **Minimo**: vengono inserite righe nel giornale di registrazione di conteggio se le scorte disponibili sono uguali o inferiori al valore minimo specificato.  
    - Facoltativo: se nel campo **Codice di conteggio** è stata specificata l'opzione **Periodo**, è necessario digitare la durata del periodo nel campo **Periodo di conteggio**. Unità di misura dell'intervallo in giorni.  
    - Quando si esegue il processo per creare nuove righe nel giornale di registrazione di conteggio, le nuove righe vengono create nell'intervallo specificato in questo campo, indipendentemente dalla frequenza di esecuzione dello stesso processo. Ad esempio, se **Periodo di conteggio** è impostato su 7 e le righe del giornale di registrazione sono state per l'ultima volta generate per un conteggio il 1° gennaio, se a un altro processo viene avviato il 5 gennaio, sette giorni non sono trascorsi e quindi non viene generata alcuna riga nel giornale di registrazione per tale intervallo periodico. Se il processo viene avviato nuovamente l'8 gennaio, vengono generate righe per il periodo nel giornale di registrazione di conteggio, poiché sono trascorsi 7 giorni.  

6. Selezionare **Salva**.

## <a name="create-a-counting-journal-name"></a>Creare nome giornale di registrazione di conteggio
1. Nel pannello di navigazione andare a **Moduli > Gestione articoli > Impostazioni > Nomi giornale di registrazione > Inventario**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Nome**.
4. Digitare un valore nel campo **Descrizione**
5. Selezionare **Conteggio** nel campo **Tipo di giornale di registrazione**. Facoltativo: è possibile selezionare un ID serie giustificativi diverso se si desidera una sequenza numerica specifica per gli ID giustificativi generati durante la creazione dei giornali di registrazione di conteggio. Le serie giustificativi vengono creati nella pagina **Sequenze numeriche**.  
6. Selezionare un'opzione nel campo **Livello dettagli**.  

    - Si tratta del livello di dettaglio applicato quando viene registrato il giornale di registrazione.  
    - Facoltativo: è possibile modificare il valore nel campo Prenotazione. Si tratta del metodo utilizzato per prenotare gli articoli durante il conteggio.   
    - **Manuale**: gli articoli vengono prenotati manualmente nel modulo Prenotazione.  
    - **Automatico**: la quantità nell'ordine viene prenotata dalle scorte disponibili di un articolo.   
    - **Esplosione**: la prenotazione fa parte della pianificazione generale della transazione.  

7. Selezionare **Salva**.

## <a name="set-standard-counting-journal-name"></a>Impostare il nome del giornale di registrazione di conteggio standard
1. Nel pannello di navigazione, andare a **Moduli > Gestione magazzino > Impostazione > Parametri di gestione articoli e magazzino**.
2. Selezionare la scheda **Giornali di registrazione**.
3. Nel menu a discesa del campo **Conteggio**, selezionare il giornale di registrazione creato in precedenza. Il giornale di registrazione sarà quindi il nome del giornale di registrazione predefinito per i giornali di registrazione magazzino di tipo **Conteggio**.  
4. Selezionare la scheda **Generale**. Facoltativo: selezionare questa opzione per bloccare un articolo durante il processo di conteggio per evitare aggiornamenti per i documenti di trasporto, le distinte di prelievo o le registrazioni della distinta di prelievo.  

## <a name="set-the-counting-policy-for-an-item"></a>Impostare i criteri di conteggio per un articolo.
1. Nel pannello di navigazione andare a **Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.
2. Nell'elenco, selezionare il collegamento per il numero articolo del prodotto per cui si desidera impostare i criteri di conteggio. È necessario selezionare un articolo di cui viene tenuta traccia come magazzino. Un prodotto non stoccato non può essere conteggiato. Se si utilizzano i dati dimostrativi USMF, è possibile selezionare l'articolo A0001.  
3. Selezionare **Modifica**.
4. Attivare/disattivare l'espansione della sezione **Gestione articoli**.
5. Nel menu a discesa del campo **Gruppo di conteggio**, selezionare il gruppo di conteggio creato in precedenza. Questo prodotto verrà ora incluso quando le righe del giornale di registrazione conteggi scorte viene creato tramite il gruppo di conteggio.  
6. Selezionare **Salva**.

## <a name="set-the-counting-policy-for-an-item-in-a-specific-warehouse"></a>Impostare i criteri di conteggio per un articolo in un magazzino specifico
1. Nel riquadro azioni, fare clic su **Gestione articoli**.
2. Selezionare **Articoli di magazzino**.
3. Selezionare **Nuovo**.
4. Nel menu a discesa del campo **Magazzino**, selezionare il magazzino per il quale si intende impostare specifici criteri di conteggio.
5. Nel menu a discesa del campo **Gruppo di conteggio**, selezionare un gruppo di conteggio. È possibile selezionare uno specifico gruppo di conteggio da applicare all'articolo nel magazzino specifico selezionato. Quando il conteggio viene eseguito nel magazzino, questi criteri di conteggio sostituiranno i criteri di conteggio generali per l'articolo.  
6. Selezionare **Salva**.

