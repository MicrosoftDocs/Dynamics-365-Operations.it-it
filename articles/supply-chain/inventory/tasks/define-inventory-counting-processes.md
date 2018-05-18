---
title: Definire i processi di conteggio scorte
description: In questa procedura viene illustrata la configurazione dei processi di conteggio scorte di base mediante la creazione di un gruppo di conteggio e di un giornale di registrazione di conteggio.
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c14c846c55a3d821945160835817cd4f467deda9
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="define-inventory-counting-processes"></a>Definire i processi di conteggio scorte

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrata la configurazione dei processi di conteggio scorte di base mediante la creazione di un gruppo di conteggio e di un giornale di registrazione di conteggio. Viene inoltre illustrato come abilitare i criteri di conteggio a livello di articolo e di magazzino. Queste attività verranno in genere eseguite da un supervisore del magazzino. È un prerequisito per avere alcuni prodotti rilasciati e magazzini esistenti. Se si utilizza una società di dati dimostrativi, è possibile eseguire questa procedura nella società USMF con un articolo stoccato.


## <a name="create-a-counting-group"></a>Creare un gruppo di conteggio.
1. Andare a Gestione articoli > Impostazioni > Inventario > Gruppi di conteggio.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Gruppo di conteggio.
4. Digitare un valore nel campo Nome.
5. Nel campo Codice di conteggio selezionare un'opzione.
    * Manuale: vengono incluse righe ogni volta che si esegue il processo. In altri termini, consente di stabilire l'intervallo di conteggio per il gruppo di conteggio.  Periodo: vengono incluse righe per il periodo nel giornale di registrazione di conteggio alla scadenza dell'intervallo periodico.   Zero in magazzino: se le scorte disponibili raggiungono 0 (zero) vengono generate righe nel giornale di registrazione di conteggio all'avvio del processo. Se le scorte disponibili raggiungono 0 dopo un conteggio, vengono generate righe al successivo avvio del conteggio.   Minimo: vengono inserite righe nel giornale di registrazione di conteggio se le scorte disponibili sono uguali o inferiori al valore minimo specificato.  
    * Facoltativo: se nel campo Codice di conteggio è stata specificata l'opzione Periodo, è necessario digitare la durata del periodo nel campo Periodo di conteggio. Unità di misura dell'intervallo in giorni.  
    * Quando si esegue il processo per creare nuove righe nel giornale di registrazione di conteggio, le nuove righe vengono create nell'intervallo specificato in questo campo, indipendentemente dalla frequenza di esecuzione dello stesso processo. Ad esempio, se Periodo di conteggio è impostato su 7 e le righe del giornale di registrazione sono state per l'ultima volta generate per un conteggio il 1° gennaio, se a un altro processo viene avviato il 5 gennaio, sette giorni non sono trascorsi e quindi non viene generata alcuna riga nel giornale di registrazione per tale intervallo periodico. Se il processo viene avviato nuovamente l'8 gennaio, vengono generate righe per il periodo nel giornale di registrazione di conteggio, poiché sono trascorsi 7 giorni.  
6. Fare clic su Salva.

## <a name="create-a-counting-journal-name"></a>Creare nome giornale di registrazione di conteggio
1. Andare a Gestione articoli > Impostazioni > Nomi giornale di registrazione > Inventario.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Nel campo Descrizione digitare un valore.
5. Selezionare "Conteggio" nel campo Tipo di giornale di registrazione.
    * Facoltativo: è possibile selezionare un ID serie giustificativi diverso se si desidera una sequenza numerica specifica per gli ID giustificativi generati durante la creazione dei giornali di registrazione di conteggio. Le serie giustificativi vengono creati nella pagina Sequenze numeriche.  
6. Selezionare un'opzione nel campo Livello dettagli.
    * Si tratta del livello di dettaglio applicato quando viene registrato il giornale di registrazione.  
    * Facoltativo: è possibile modificare il valore nel campo Prenotazione. Si tratta del metodo utilizzato per prenotare gli articoli durante il conteggio.   
    * Manuale: gli articoli vengono prenotati manualmente nel modulo Prenotazione.   Automatico: la quantità nell'ordine viene prenotata dalle scorte disponibili di un articolo.   Esplosione: la prenotazione fa parte della pianificazione generale della transazione.  
7. Fare clic su Salva.

## <a name="set-standard-counting-journal-name"></a>Impostare il nome del giornale di registrazione di conteggio standard
1. Fare clic su Gestione magazzino > Impostazioni > Parametri di gestione articoli e magazzino.
2. Fare clic sulla scheda Giornali di registrazione.
3. Nel campo Conteggio fare clic sul pulsante a discesa per aprire la ricerca.
4. Selezionare il tipo di giornale di registrazione creato in precedenza.
    * Il giornale di registrazione sarà quindi il nome del giornale di registrazione predefinito per i giornali di registrazione magazzino di tipo Conteggio.  
5. Fare clic sulla scheda Generale.
    * Facoltativo: selezionare questa opzione per bloccare un articolo durante il processo di conteggio per evitare aggiornamenti per i documenti di trasporto, le distinte di prelievo o le registrazioni della distinta di prelievo.  

## <a name="set-the-counting-policy-for-an-item"></a>Impostare i criteri di conteggio per un articolo.
1. Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.
2. Nell'elenco, fare clic sul collegamento per il numero articolo del prodotto per cui si desidera impostare i criteri di conteggio.
    * Si noti che è necessario selezionare un articolo di cui viene tenuta traccia come magazzino. Un prodotto non stoccato non può essere conteggiato. Se si utilizzano i dati dimostrativi USMF, è possibile selezionare l'articolo A0001.  
3. Fare clic su Modifica.
4. Attivare/disattivare l'espansione della sezione Gestione articoli.
5. Nel campo Gruppo di conteggio fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco, fare clic su nel gruppo di conteggio creato in precedenza.
    * Questo prodotto verrà ora incluso quando le righe del giornale di registrazione conteggi scorte viene creato tramite il gruppo di conteggio.  
7. Fare clic su Salva.

## <a name="set-the-counting-policy-for-an-item-in-a-specific-warehouse"></a>Impostare i criteri di conteggio per un articolo in un magazzino specifico
1. Nel riquadro azioni, fare clic su Gestione articoli.
2. Fare clic su Articoli di magazzino.
3. Fare clic su Nuovo.
4. Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco, selezionare il magazzino per cui si desidera impostare criteri di conteggio specifici.
6. Nel campo Gruppo di conteggio fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco selezionare un gruppo di conteggio.
    * In questo campo è possibile selezionare un gruppo di conteggio specifico da applicare all'articolo nel magazzino specifico selezionato. Quando il conteggio viene eseguito nel magazzino, questi criteri di conteggio sostituiranno i criteri di conteggio generali per l'articolo.  
8. Fare clic su Salva.

