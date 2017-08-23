--- 
title: Impostare una voce di menu del dispositivo mobile per completare il lavoro in un ordine fornitore
description: Questa procedura mostra come impostare una voce di menu Dispositivo mobile.
author: BibiSp
manager: AnnBe
ms.date: 08/25/2016
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
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 7ce132b590fffb753948e663763b8f3ef576ac36
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-in-a-purchase-order"></a>Impostare una voce di menu del dispositivo mobile per completare il lavoro in un ordine fornitore

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come impostare una voce di menu Dispositivo mobile. In questo esempio, la voce di menu è utilizzata per eseguire lavori di tipo ordine fornitore. Il lavoro valido è determinato dalla classe di lavoro associata alla voce di menu. È possibile utilizzare questa guida nella società di dati dimostrativi USMF. In genere, questa procedura viene eseguita da un responsabile del magazzino.


## <a name="create-a-mobile-device-menu-item"></a>Creare una voce di menu per dispositivo mobile
1. Passare alle voci di menu del dispositivo mobile.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome voce di menu.
    * Immettere un valore univoco. Ad esempio, è possibile immettere POMove. Memorizzare il valore, sarà necessario più tardi.  
4. Digitare un valore nel campo Titolo.
    * Si tratta del titolo visualizzato nel dispositivo mobile. Ad esempio, è possibile immettere POMove.  
5. Selezionare "Lavoro" nel campo Modalità.
6. Selezionare Sì nel campo Utilizza lavoro esistente.
    * Questa voce di menu per dispositivo mobile viene utilizzata per eseguire il lavoro esistente. Pertanto è necessario impostare questo valore su Sì.  
    * Il campo Visualizza stato inventario determina se verrà visualizzato lo stato di inventario del magazzino scorte all'addetto magazzino sul dispositivo mobile.  
7. Nel campo Diretto da, selezionare 'Raggruppamento sistema'.
    * Quando selezionate qualcosa nel campo Diretto da, campi supplementari compaiono nella sezione Generale di questa pagina. I campi che compaiono dipendono da cosa avete selezionato. Quando si seleziona Raggruppamento sistema 2 nuovi campi vengono aggiunti. Questi sono descritti di seguito.  
8. Nel campo Raggruppamento sistema, selezionare 'WorkPoolId'.
    * Quando gli addetti magazzino aprono questa voce di menu, verrà loro richiesto di eseguire la scansione di un ID di pool di lavoro. Tutti gli ordini di lavoro con questo ID pool di lavoro e le righe degli ordini di lavoro aperti con una delle classi di lavoro aggiunte a questa voce di menu verranno presentati all'utente.  
9. Nel campo Etichetta di raggruppamento sistema, digitare un valore.
    * Questo è il testo visualizzato all'utente sul dispositivo mobile. Ad esempio, è possibile immettere Pool lavoro.  
10. Selezionare Sì nel campo Ignora targa durante inserimento.
    * Questa opzione consente agli addetti al magazzino di ignorare la targa di destinazione quando gli articoli vengono posati in un'ubicazione controllata da targa.  
11. Selezionare Sì nel campo Stoccaggio di gruppo.
    * Se tutte le righe di inserimento nell'ordine di lavoro condividono la stessa ubicazione, l'utente riceverà un'istruzione Put combinata per tutte le righe.  
    * ID modello di controllo: un modello di controllo di lavoro consente di specificare che il processo di lavoro per una voce di menu deve essere interrotto in modo che sia possibile eseguire un'altra operazione. Ad esempio, se la voce di menu è per un lavoro in entrata, il modello di controllo può richiedere che il lavoratore controlli la temperatura. Il punto in cui il processo viene interrotto è specificato nel modello di audit e può essere, ad esempio, quando il lavoro viene avviato o completato oppure quando cambia lo stato.  
12. Espandere la sezione Classi di lavoro.
13. Fare clic su Nuovo.
14. Nel campo ID classe lavoro, digitare 'Acquisto'.
    * Il pool di lavoro limita le operazioni per cui è possibile utilizzare la voce di menu. In questo caso verrà utilizzato per le righe di ordine di lavori aperti con ID classe di lavoro Acquisto.  
15. Fare clic su Salva.

## <a name="set-up-work-confirmation"></a>Impostare la conferma di lavoro
1. Fare clic su Impostazione conferma lavoro.
2. Nel campo Tipo di lavoro, selezionare 'Preleva'.
3. Selezionare la casella di controllo Conferma automatica.
    * L'istruzione di lavoro con il tipo di lavoro prelievo sarà confermata automaticamente. Questa istruzione non verrà presentata all'utente.  
4. Fare clic su Nuovo.
5. Nel campo Tipo di lavoro selezionare "Inserisci".
6. Selezionare la casella di controllo Conferma ubicazione.
    * L'addetto magazzino verrà richiesto di eseguire un'analisi di conferma dell'ubicazione, quando l'articolo viene posato.  
7. Fare clic su Salva.
8. Chiudere la pagina.
9. Chiudere la pagina.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Aggiungere la voce di menu a un menu per dispositivo mobile
1. Passare al menu Dispositivo mobile.
2. Fare clic su Modifica.
3. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare il campo Nome con il valore 'inbound'.
    * Si desidera trovare il menu che si utilizza per voci di menu in entrata. In USMF si chiama Inbound.  
4. Nella struttura, selezionare 'un valore'.
5. Fare clic sulla freccia rivolta verso destra.
6. Fare clic su Salva.
7. Chiudere la pagina.


