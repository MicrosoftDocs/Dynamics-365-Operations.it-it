---
title: Creare una richiesta per il consumo
description: In questo argomento viene descritto il processo per creare una richiesta.
author: mkirknel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acc2cdb9b74cccaefe565b0e2ae8ec4c5f2401c4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204725"
---
# <a name="create-a-requisition-for-consumption"></a>Creare una richiesta per il consumo

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto il processo per creare una richiesta. Vengono visualizzati i diversi modi di individuare i prodotti nel catalogo di approvvigionamento e come aggiungere un prodotto non in catalogo. Prima di iniziare questa procedura, è necessario disporre di criteri di acquisto configurati con Consumo come tipo predefinito di richiesta. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati. La procedura può essere eseguita solo da un profilo utente impostato come lavoratore. Questa attività in genere sarà svolta da un dipendente. Il **Dipendente** impiega il ruolo di sicurezza che permetterà di svolgere le attività, o se si utilizza USMF, è possibile aprire la sessione come **Alicia**.


## <a name="create-a-new-requisition"></a>Crea una nuova richiesta
1. Passare ad **pannello di navigazione > Moduli > Approvvigionamento > Richieste di acquisto > Richieste di acquisto preparate dall'utente**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome** immettere un nome per la richiesta.
4. Nel campo **Data richiesta** immettere una data. Per impostazione predefinita, la data richiesta e la data di registrazione vengono copiate nelle righe della richiesta di acquisto. Le date possono essere modificate a livello di riga. La data richiesta corrisponde alla data di consegna richiesta.  
5. Immettere una data nel campo **Data di registrazione**. La data di contabilizzazione viene utilizzata per registrare la voce contabile nella contabilità generale e per convalidare la disponibilità dei fondi di budget.  
6. Selezionare **OK**.
7. Nel campo **Motivo**, selezionare un'opzione dall'menu a discesa. Per impostazione predefinita, la motivazione aziendale selezionata viene visualizzata nelle righe della richiesta di acquisto, tuttavia è possibile modificarla a livello di riga.  
8. Selezionare il motivo
9. Nel campo **dettagli** immettere una motivazione più descrittiva della richiesta di acquisto.

## <a name="add-a-line-to-the-requisition"></a>Aggiungi una riga alla richiesta
1. Selezionare **Aggiungi riga**. Sono disponibili due metodi di aggiunta delle righe alla richiesta di acquisto. Se si conosce già il numero del prodotto o si sa che il prodotto richiesto non è in catalogo, è possibile aggiungere la riga direttamente con **Aggiungi riga**. L'altro modo è utilizzare **Aggiungi prodotti** nei casi in cui è possibile utilizzare la ricerca e il filtro per individuare gli articoli del catalogo prodotti.    
2. Selezionare la riga creata.
    - Il richiedente è il lavoratore che ha formulato la richiesta.   
    - Per impostazione predefinita la persona che prepara la richiesta è il lavoratore che l'ha formulata. È necessario ricevere l'autorizzazione per preparare una riga di richiesta per conto di un altro lavoratore. Se si è in possesso di tali autorizzazioni, altri lavoratori verranno messi in luce in questa ricerca.  
3. Nel campo **Numero articolo**, digitare un valore. Gli articoli disponibili per la scelta vengono limitati in base ai criteri di accesso alle categorie e al catalogo di approvvigionamento per la persona giuridica acquirente.   
4. Nel campo **Quantità** immettere un numero.

## <a name="add-more-products-to-the-requisition"></a>Aggiungi altri prodotti alla richiesta
1. Selezionare **Aggiungi prodotti**. Si tratta dell'opzione tramite la quale è possibile cercare i prodotti nel catalogo dei prodotti.    
2. Nel campo **Trova nodo categoria di approvvigionamento** immettere la prima parte del nome della categoria che si ricerca e quindi fare clic su **Immetti**. Ad esempio, immettere `comput`.  
3. Utilizzare il collegamento **InvokeDefaultButton**.
4. Utilizzare il **filtro** per filtrare l'elenco di prodotti nella categoria selezionata.
5. Selezionare la scheda del prodotto che si desidera aggiungere alla richiesta.
6. Selezionare **Aggiungi a righe**.
7. Nel campo **Quantità** immettere un numero.
8. Nel campo **Trova nodo categoria di approvvigionamento** immettere la prima parte del nome della categoria che si ricerca e quindi fare clic su **Immetti**. Ad esempio, immettere `High` (per highlighter, evidenziatori).  
9. Utilizzare il collegamento **InvokeDefaultButton**.
10. Fare clic su **Aggiungi prodotti non in elenco a righe** per aggiungere un prodotto non elencato nel catalogo di approvvigionamento.
11. Digitare un valore nel campo **Nome prodotto**.
12. Digitare un valore nel campo **Unità**.
13. Selezionare **OK**.
14. Nel campo **Descrizione articolo** aggiungere una descrizione del prodotto.
15. Nel campo **Quantità** immettere un numero.
16. Immettere un numero nel campo **Prezzo unitario**. Se si sa il prezzo di un fornitore specifico (che si seleziona nel campo conto fornitore), quel prezzo può essere inserito   
17. Nel campo **Conto fornitore** fare clic sull'elenco a discesa per selezionare un'opzione. I fornitori disponibili in questo campo dipendono dai criteri di acquisto e dallo stato che il fornitore ha per la categoria di approvvigionamento corrente. In alternativa a selezionare un fornitore in questo campo, è possibile fare clic su **Suggerisci fornitore**.    
18. Selezionare dall'elenco il fornitore desiderato.
19. Nel campo **Numero articolo esterno** digitare un valore. Si tratta di un numero di riferimento per il prodotto che è noto al fornitore. Ad esempio, potrebbe essere il numero di articolo del prodotto nel catalogo personale del fornitore.  
20. Selezionare **OK**.

## <a name="distribute-amounts"></a>Distribuisci importi
1. Selezionare **Dati finanziari**.
2. Selezionare **Distribuisci importi**. Questo processo mostra come distribuire il costo della prima riga tra 2 conti. Può essere effettuato anche quando la richiesta è in fase di revisione.  
3. Fare clic su **Dividi** per creare una nuova riga di distribuzione.
4. Nel campo **Conto CoGe** selezionare il primo centro di costo che deve partecipare al costo.
5. Selezionare l'altra riga di distribuzione.
6. Nel campo Conto CoGe specificare l'altro centro di costo.
7. Selezionare **Distribuisci equamente**.
8. Chiudere la pagina.

## <a name="view-line-details"></a>Visualizza dettagli riga
1. Attivare/disattivare l'espansione della sezione **Dettagli riga**.

## <a name="submit-the-requisition"></a>Invia la richiesta
1. Fare clic su **Flusso di lavoro** per aprire la finestra di dialogo a discesa.
2. Selezionare **Invia**.
3. Chiudere la pagina.
4. Nel campo **Commento** immettere una nota per l'approvatore della richiesta.
5. Selezionare **Invia**.
6. Chiudere la pagina.
7. Aggiorna la pagina.

