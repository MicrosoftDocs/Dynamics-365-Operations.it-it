---
title: Creare una sequenza di lettere di sollecito
description: Utilizza questa procedura per creare una sequenza di lettere di sollecito.
author: JodiChristiansen
ms.date: 12/07/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CollectionLetterCourse
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af5d0a001fbe705834e116516933be67f2de8826
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734160"
---
# <a name="create-a-collection-letter-sequence"></a>Creare una sequenza di lettere di sollecito

[!include [banner](../../includes/banner.md)]

Utilizza questa procedura per creare una sequenza di lettere di sollecito. In questa attività viene utilizzata la società dimostrativa USMF.

1. Andare a **Crediti e riscossioni > Impostazioni > Imposta la sequenza lettere di sollecito**.
2. Fare clic su **Nuovo**.
3. Nel campo **Sequenza lettere di sollecito**, immettere un ID sequenza che rappresenterà la sequenza. Verrà utilizzato quando si imposta un profilo registrazione.
4. Digitare un valore nel campo **Descrizione** I termini di pagamento sono facoltativi. Se si immette un valore in questo campo, la fattura di addebito lettera di sollecito utilizzerà questi termini di pagamento anziché i termini di pagamento archiviati con il cliente.  
5. Nel campo **Codice lettera di sollecito** selezionare il codice per la prima lettera di sollecito che si desidera inviare. La prima nota d'interesse viene creata in base alla data di scadenza riportata sulla fattura, al valore specificato per il periodo di tolleranza nel campo Giorni e alle altre informazioni immesse in questa riga.  
6. Digitare un valore nel campo **Descrizione** 
7. La valuta predefinite della commissione è la valuta della persona giuridica. Questo codice valuta può essere diverso dalla valuta della fattura.   
8. Fare clic su **Aggiungi** per aggiungere la lettera di sollecito successiva che verrà inviata nella sequenza In molti casi, la prima lettera di sollecito è soltanto un avviso. È possibile aggiungere le commissioni se necessario.  
9. Nel campo **Codice lettera di sollecito** selezionare la lettera di sollecito successiva che verrà inviata nella sequenza.
10. Nel campo **Conto principale**, selezionare il conto ricavi che verrà utilizzato per le commissioni.
11. Immettere la commissione che verrà addebitata quando la lettera di sollecito viene registrata.
12. Nel campo **Fascia IVA articoli** fare clic sul pulsante a discesa per aprire la ricerca. Selezionare una fascia IVA articoli se l'IVA deve essere calcolata sulla commissione.  
13. Nell'elenco fare clic sul collegamento nella riga selezionata.
14. Nel campo **Saldo scaduto minimo**, immettere il saldo scaduto minimo necessario prima che una lettera di sollecito venga inviata.
15. Immettere il numero di giorni di tolleranza da consentire nel campo **Giorni**. Questo è il numero di giorni dopo la data di scadenza in cui una lettera di sollecito può essere generata. La data di scadenza utilizzata per il calcolo dipende dalla posizione della lettera di sollecito nella sequenza delle lettere di sollecito:
    - Il periodo di tolleranza della lettera di sollecito 1 è relativo alla data di scadenza della fattura.
    - Il periodo di tolleranza per le lettere di sollecito 2 e superiori è in relazione alla data di registrazione e stampa della lettera di sollecito precedente, a seconda della selezione nel campo Aggiorna codice lettera di sollecito nella pagina Parametri contabilità clienti.  
16. Fare clic su **Aggiungi** per aggiungere l'ultima lettera di sollecito nella sequenza. Per una sequenza di lettere di sollecito è possibile aggiungere fino a cinque codici lettera di sollecito.  
17. Nel campo **Codice lettera di sollecito** selezionare la lettera di sollecito successiva che verrà inviata nella sequenza.
18. Digitare un valore nel campo **Descrizione**
19. Nel campo **Conto principale**, specificare i valori desiderati.
20. Nel campo **Addebito in valuta** immettere un numero.
21. Nel campo **Fascia IVA articoli** fare clic sul pulsante a discesa per aprire la ricerca.
22. Nell'elenco fare clic sul collegamento nella riga selezionata.
23. Nel campo **Saldo scaduto minimo** immettere un numero.
24. Nel campo **Giorni** immettere un numero.
25. Selezionare la casella di controllo **Blocca** per impedire al cliente di effettuare operazioni di consegna e fatturazione aggiuntive. Per sbloccare il conto, selezionare **No** nel campo **Fatturazione e consegna in attesa** della pagina **Clienti**.  
26. Espandere la Scheda dettaglio **Nota**.
27. Immettere il testo da visualizzare sulla lettera di sollecito per il codice lettera di sollecito selezionato. È possibile tradurre il testo in più lingue utilizzando il menu **Traduzioni** sopra la casella della nota.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
