---
title: Impostare una gerarchia di categorie di approvvigionamento
description: Questa procedura illustra come creare nuovi nodi in una gerarchia di categorie di approvvigionamento e come configurare una categoria di approvvigionamento per essere utilizzata in un processo di approvvigionamento.
author: mkirknel
manager: AnnBe
ms.date: 11/06/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01809a8a3256342682d8a9cfb296a355310fe4ed
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "334521"
---
# <a name="set-up-a-procurement-category-hierarchy"></a>Impostare una gerarchia di categorie di approvvigionamento

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura illustra come creare nuovi nodi in una gerarchia di categorie di approvvigionamento e come configurare una categoria di approvvigionamento per essere utilizzata in un processo di approvvigionamento. Queste attività verranno in genere svolte da un responsabile degli acquisti. Prima di iniziare questa procedura, deve essere presente una gerarchia di categorie di tipo approvvigionamento. Se si utilizza una società di dati dimostrativi, è possibile eseguire questa procedura nella società USMF.


## <a name="add-a-new-procurement-category"></a>Aggiungere una categoria di approvvigionamento
1. Passare a Approvvigionamento > Categorie di approvvigionamento.
2. Fare clic su Modifica gerarchia di categorie.
    * La gerarchia di categorie di approvvigionamento corrente viene visualizzata nella parte sinistra della pagina. Si sta per modificare la gerarchia.  
3. Fare clic su nodo Nuova categoria.
    * Il sistema selezionare il nodo di primo livello per impostazione predefinita. Se si esegue la procedura come guida attività, è possibile fare clic sul pulsante Sblocca e selezionare un altro nodo padre per inserire il nuovo nodo. Una volta eseguita l'operazione, bloccare ancora la guida attività e quindi fare clic sul nodo Nuova categoria.  
4. Digitare un valore nel campo Nome.
5. Nel campo Descrizione digitare un valore.
6. Digitare un valore nel campo Nome descrittivo.
    * Il nome descrittivo è facoltativo. Verrà visualizzato le ricerche di categoria insieme al nome della categoria.  
7. Fare clic su Salva.

## <a name="add-products-to-your-new-procurement-category"></a>Aggiungere prodotti alla nuova categoria di approvvigionamento
1. Passare a Approvvigionamento > Categorie di approvvigionamento.
    * Selezionare il nodo aggiunto. Se si esegue la procedura come guida attività, potrebbe essere necessario sbloccare quest'ultima per selezionare il nodo.  
2. Attivare/disattivare l'espansione della sezione Prodotti.
3. Fare clic su Aggiungi per associare i prodotti alla categoria di approvvigionamento.
4. Selezionare il prodotto che si desidera aggiungere alla categoria di approvvigionamento.
5. Fare clic sulla freccia per selezionare il prodotto.
6. Selezionare un altro prodotto da aggiungere alla categoria di approvvigionamento.
7. Fare clic sulla freccia per selezionare il prodotto.
8. Fare clic su OK.

## <a name="add-approved-and-preferred-vendors"></a>Aggiungi fornitori approvati e preferiti
1. Attiva/disattiva l'espansione della sezione Fornitori.
2. Scegliere Aggiungi.
    * È possibile aggiungere un fornitore a una categoria di approvvigionamento e specificare se un fornitore è preferito o solo approvato nella categoria. Quando si elimina un fornitore da una categoria, le transazioni storiche con il fornitore nella categoria non verranno eliminate.   
3. Trovare il fornitore che si desidera aggiungere alla categoria.
4. Fare clic sulla freccia per selezionare il fornitore.
5. Fare clic su OK.
6. Selezionare la riga fornitore da modificare.
7. Selezionare un'opzione nel campo Stato fornitore.
    * L'impostazione di selezione del fornitore nella regola dei criteri categorie determina se nelle richieste di acquisto sono disponibili tutti i fornitori o solo quelli preferiti o approvati.   

## <a name="add-additional-information-to-the-category"></a>Aggiungere informazioni supplementare alla categoria
1. Attivare/disattivare l'espansione della sezione Gruppi di criteri di valutazione fornitore.
    * La scheda consente di definire i criteri in base ai quali devono essere valutati i fornitori nella categoria di approvvigionamento. A questo scopo, fare clic su Aggiungi, quindi selezionare un gruppo di valutazione fornitore contenente i criteri desiderati.  
2. Attivare/disattivare l'espansione della sezione Questionari.
    * La scheda consente di aggiungere i questionari che verranno visualizzati nella richiesta, a condizione che si imposti il tipo di attività su Richiesta. Il richiedente deve quindi compilare un questionario prima di che venga inviata una richiesta per prodotti specifici nella categoria di approvvigionamento.  
3. Attivare/disattivare l'espansione della sezione Fasce IVA articoli.
4. Nel campo Fascia IVA articoli fare clic sul pulsante a discesa per aprire la ricerca.
5. Consente di selezionare una fascia IVA.
6. Attivare/disattivare l'espansione della sezione Pagina categoria.
    * Le pagine di categoria vengono create nella pagina Gerarchia di categorie. In tali pagine sono contenute informazioni sulla categoria di approvvigionamento, ad esempio informazioni sul tipo di prodotti in una categoria, le immagini dei prodotti in una categoria e gli annunci quali gli sconti disponibili in una categoria. Le informazioni in una pagina di categoria vengono visualizzare nelle richieste di acquisto.  
7. Chiudere la pagina.

