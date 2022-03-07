---
title: Impostare una voce di menu del dispositivo mobile per registrare gli articoli ricevuti
description: Questo argomento descrive l'impostazione di una voce di menu per dispositivo mobile.
author: ShylaThompson
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFMenu, WHSRFDefaultData
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d9dc74d51dae4af21679ed71b68286ca29ff6201977242490fb749364a223f64
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764670"
---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Impostare una voce di menu del dispositivo mobile per registrare gli articoli ricevuti

[!include [banner](../../includes/banner.md)]

Questo argomento descrive l'impostazione di una voce di menu per dispositivo mobile. Questa voce di menu viene utilizzata per la registrazione dell'entrata di articoli ordinati tramite gli ordini fornitore. 

È possibile utilizzare questa guida nella società di dati dimostrativi USMF. Questa procedura è destinata al responsabile del magazzino.


## <a name="create-a-mobile-device-menu-item"></a>Creare una voce di menu per dispositivo mobile
1. Nel pannello di navigazione, andare a **Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Voci di menu del dispositivo mobile**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Nome voce di menu**. Si tratta dell'identificatore univoco per questa voce di menu per dispositivo mobile. Ad esempio, è possibile immettere `My PO registration`.  
4. Digitare un valore nel campo **Titolo**. Si tratta del titolo visualizzato all'utente nel dispositivo mobile. Ad esempio, è possibile immettere `PO registration`.  
5. Selezionare **Lavoro** nel campo **Modalità**. La registrazione delle quantità disponibili ricevute per una riga ordine fornitore creerà il lavoro per spostare gli articoli dall'area di ricevimento in magazzino. Il lavoro non viene creato finché gli articoli non sono registrati. Pertanto, lasciare l'opzione **Utilizza lavoro esistente** impostata su **No**.
6. Nel campo **Processo di creazione lavoro**, nella sezione **Generale**, selezionare **Ricevimento articolo ordine acquisto**.
    - Una riga ordine fornitore deve essere identificata in modo univoco prima che la disponibilità possa essere registrata nel magazzino. In questo scenario, il dispositivo mobile registrerà il numero dell'ordine fornitore e il numero di articolo e ciò permetterà al sistema di identificare la riga PO. Il lavoro di stoccaggio verrà creato e può essere prelevato da un altro lavoratore. Il metodo della creazione di lavoro selezionato determina quali campi diventano disponibili nella Scheda dettaglio **Generale**.  
    - Se si seleziona l'opzione **Utilizza dati predefiniti**, si abilita il pulsante **Dati predefiniti**. Qui è possibile selezionare i campi per visualizzare i dati solitamente necessari a un lavoratore per svolgere il lavoro giornaliero, in modo che tali valori siano visualizzati sul dispositivo mobile.  
    - Il parametro **Raggruppamento targa** funziona congiuntamente al gruppo di sequenze unità assegnato all'articolo ricevuto. È possibile specificare se le entrate minori o maggiori di un pallet vengono raggruppate in un'unica targa o suddivise in una targa separata per ogni unità.  
    - Se si seleziona l'opzione **Genera targa**, questa genera un numero di identificazione univoco basato sulla selezione della sequenza numerica.  
    - È possibile selezionare il modello da utilizzare quando il lavoro viene creato. Ad esempio, se si registra un articolo per un ordine fornitore, il lavoro di stoccaggio viene generato in base al modello di lavoro. Se non si seleziona un modello di lavoro in questo campo, il sistema assegnerà un modello in base ai criteri di query associati ai modelli.  
    - Se i codici smaltimento vengono visualizzati sul dispositivo mobile, i lavoratori possono valutare lo stato o la qualità degli articoli e selezionare il codice appropriato. Le regole del codice di smaltimento determinano se gli articoli sono disponibili per altri processi di magazzino. Le regole determinano anche la direttiva ubicazione utilizzata per il lavoro creato.   
    - Se si seleziona l'opzione **Codici smaltimento batch**, i lavoratori possono valutare lo stato o la qualità di un batch e selezionare il codice smaltimento appropriato. Le regole impostate per il codice di smaltimento batch determinano se il batch sarà disponibile per altri processi di magazzino.  
    - Se si seleziona l'opzione **Stampa etichette**, un'etichetta di targa verrà stampata automaticamente quando gli articoli vengono ricevuti.  
7. Selezionare **Salva**.
8. Chiudere la pagina.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Aggiungere la voce di menu a un menu per dispositivo mobile
1. Nel pannello di navigazione, andare a **Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Voci di menu del dispositivo mobile**.
2. Utilizzare il **filtro rapido** per filtrare il campo **Nome** in base a un valore di `inbound`.
3. Selezionare **Modifica**.
4. Nella struttura Menu e voci di menu disponibili, selezionare la voce di menu creata prima.
5. Selezionare la freccia rivolta verso destra.
6. Selezionare **Salva**.
7. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]