--- 
title: Impostare una voce di menu del dispositivo mobile per registrare gli articoli ricevuti
description: "Questa attività si basa sull'impostazione di una voce di menu per dispositivo mobile."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 642e2b05c9f9a59f6b47a22f3d92f2f6ae245039
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Impostare una voce di menu del dispositivo mobile per registrare gli articoli ricevuti

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa attività si basa sull'impostazione di una voce di menu per dispositivo mobile. Questa voce di menu viene utilizzata per la registrazione dell'entrata di articoli ordinati tramite gli ordini fornitore. 

È possibile utilizzare questa guida nella società di dati dimostrativi USMF. Questa procedura è destinata al responsabile del magazzino.


## <a name="create-a-mobile-device-menu-item"></a>Creare una voce di menu per dispositivo mobile
1. Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Voci di menu del dispositivo mobile.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome voce di menu.
    * Si tratta dell'identificatore univoco per questa voce di menu per dispositivo mobile. Ad esempio, è possibile immettere 'Registrazione PO personali'.  
4. Digitare un valore nel campo Titolo.
    * Si tratta del titolo visualizzato all'utente nel dispositivo mobile. Ad esempio, è possibile immettere 'Registrazione PO'.  
5. Selezionare "Lavoro" nel campo Modalità.
    * La registrazione delle quantità disponibili ricevute per una riga ordine fornitore creerà il lavoro per spostare gli articoli dall'area di ricevimento in magazzino. Il lavoro non viene creato finché gli articoli non sono registrati.  Pertanto, lasciare l'opzione Utilizza lavoro esistente impostata su No.  
6. Espandere o comprimere la sezione Generale.
7. Nel campo Processo di creazione lavoro, selezionare 'Ricevimento articolo ordine acquisto'.
    * Una riga ordine fornitore deve essere identificata in modo univoco prima che la disponibilità possa essere registrata nel magazzino. In questo scenario, il dispositivo mobile registrerà il numero dell'ordine fornitore e il numero di articolo e ciò permetterà al sistema di identificare la riga PO. Il lavoro di stoccaggio verrà creato e può essere prelevato da un altro lavoratore.    Il metodo della creazione di lavoro selezionato determina quali campi diventano disponibili nella Scheda dettaglio Generale.  
    * Se si seleziona l'opzione Utilizza dati predefiniti, si abilita il pulsante Dati predefiniti. Qui è possibile selezionare i campi per visualizzare i dati solitamente necessari a un lavoratore per svolgere il lavoro giornaliero, in modo che tali valori siano visualizzati sul dispositivo mobile.  
    * Il parametro Raggruppamento targa funziona congiuntamente al gruppo di sequenze unità assegnato all'articolo ricevuto. È possibile specificare se le entrate minori o maggiori di un pallet vengono raggruppate in un'unica targa o suddivise in una targa separata per ogni unità.  
    * Se si seleziona l'opzione Genera targa, questa genera un numero di identificazione univoco basato sulla selezione della sequenza numerica.   
    * È possibile selezionare il modello da utilizzare quando il lavoro viene creato. Ad esempio, se si registra un articolo per un ordine fornitore, il lavoro di stoccaggio viene generato in base al modello di lavoro. Se non si seleziona un modello di lavoro in questo campo, il sistema assegnerà un modello in base ai criteri di query associati ai modelli.  
    * Se i codici smaltimento vengono visualizzati sul dispositivo mobile, i lavoratori possono valutare lo stato o la qualità degli articoli e selezionare il codice appropriato. Le regole del codice di smaltimento determinano se gli articoli sono disponibili per altri processi di magazzino. Le regole determinano anche la direttiva ubicazione utilizzata per il lavoro creato.   
    * Se si seleziona l'opzione Codici smaltimento batch, i lavoratori possono valutare lo stato o la qualità di un batch e selezionare il codice smaltimento appropriato.  Le regole impostate per il codice di smaltimento batch determinano se il batch sarà disponibile per altri processi di magazzino.  
    * Se si seleziona l'opzione Stampa etichette, un'etichetta di targa verrà stampata automaticamente quando gli articoli vengono ricevuti.  
8. Fare clic su Salva.
9. Chiudere la pagina.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Aggiungere la voce di menu a un menu per dispositivo mobile
1. Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Menu del dispositivo mobile.
2. Utilizzare il filtro rapido per filtrare il campo Nome in base a un valore di 'inbound'.
3. Fare clic su Modifica.
4. Nella struttura selezionare 'Nella struttura Menu e voci di menu disponibili, selezionare la voce di menu creata prima'.
    * Selezionare la voce di menu creata prima.  
5. Fare clic sulla freccia rivolta verso destra.
6. Fare clic su Salva.
7. Chiudere la pagina.


