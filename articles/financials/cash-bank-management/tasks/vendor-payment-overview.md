--- 
title: Panoramica pagamenti fornitore
description: "Questa guida attività descrive i vari metodi utilizzati per creare i pagamenti fornitore, ad esempio come utilizzare una proposta di pagamento o immettere manualmente un pagamento occasionale."
author: kweekley
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cafd499e849570cae7b7f58bf2d487a7ac0093e6
ms.openlocfilehash: e9a94231f755ff23bb442d62e90daff8f2d1f4fb
ms.contentlocale: it-it
ms.lasthandoff: 10/30/2017

---
# <a name="vendor-payment-overview"></a>Panoramica pagamenti fornitore

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida attività descrive i vari metodi utilizzati per creare i pagamenti fornitore, ad esempio come utilizzare una proposta di pagamento o immettere manualmente un pagamento occasionale. Questa procedura utilizza la società dimostrativa USMF.

1. Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.
2. Fare clic su Nuovo.
3. Selezionare il giornale di registrazione pagamenti in cui salvare i pagamenti fornitore. 
4. Selezionare il giornale di registrazione o immetterlo manualmente.
5. Fare clic su Righe.
6. Fare clic su Proposta di pagamento.
7. Fare clic su Crea proposta di pagamento.
    * La proposta di pagamento è una query utilizzata per selezionare le fatture per il pagamento. È possibile modificare l'elenco delle fatture da pagare prima della creazione o della generazione dei pagamenti fornitore.  
8. Selezionare le fatture per il pagamento in base alla data di scadenza, allo sconto di cassa oppure a entrambi. 
9. Immettere la data da confrontare con la data di scadenza o con lo sconto di cassa. 
10. Facoltativo: immettere una data di pagamento utilizzata per tutti i pagamenti.
    * La data immessa in questo punto verrà utilizzata come data di pagamento per tutti i pagamenti creati, indipendentemente dalla data di scadenza o dello sconto di cassa.  
11. Facoltativo: immettere una data di pagamento minimo che può essere utilizzata come data di pagamento.
    * La data di pagamento minima sarà la prima data utilizzata durante la creazione dei pagamenti. Ad esempio, se una fattura ha una data di scadenza dopo la data di pagamento minima, la data di scadenza diventerà la data di pagamento anziché quella di pagamento minima per il pagamento della fattura alla data più lontana possibile.  
12. Immettere le restrizioni aggiuntive alle query in Record da includere.
    * Il filtro viene usato spesso per limitare le fatture selezionate per il pagamento in base al gruppo di fornitori o al metodo di pagamento. Ad esempio, è possibile aggiungere un filtro per pagare solo le fatture tramite assegno in questo ciclo di pagamenti.  
13. Immettere i valori predefiniti delle restrizioni aggiuntive alle query o dei pagamenti. 
    * I parametri aggiuntivi possono essere utilizzati per definire la valuta di pagamento o per attivare i pagamenti centralizzati per il ciclo di pagamenti.  
14. Fare clic su OK.
    * Dopo aver fatto clic su OK, i risultati della query verranno visualizzati. Se non si desidera visualizzare in anteprima l'elenco delle fatture selezionate da pagare, è possibile tornare alla scheda dettaglio Parametri e modificare l'impostazione Crea pagamenti senza anteprima fattura = Sì.  
15. Scegliere il pulsante Mostra panoramica pagamenti per visualizzare i pagamenti che verranno creati per il fornitore sulla fattura selezionata.
16. Scegliere il pulsante Nascondi panoramica pagamenti per nascondere i pagamenti. 
17. Fare clic su Crea pagamenti.
    * Prima di scegliere Crea pagamenti, è possibile fare clic con il pulsante destro del mouse sulla griglia ed esportare l'elenco delle fatture in Excel. Il pulsante Crea pagamenti creerà i pagamenti fornitore nel giornale di registrazione pagamenti.  
18. Eseguire la scansione dei pagamenti e assicurarsi che il metodo di pagamento sia definito per tutti i pagamenti. 
    * Se si generano i pagamenti, ad esempio la stampa di un assegno o un pagamento elettronico, il metodo di pagamento deve essere definito. Il metodo di pagamento imposterà inoltre come valore predefinito il conto bancario per il pagamento stesso.  
19. Fare clic su Nuovo per creare un pagamento occasionale.
    * Un pagamento occasionale può essere aggiunto al giornale di registrazione pagamenti in qualsiasi momento prima della registrazione. A tale scopo, fare clic sul pulsante Nuovo e aggiungere le informazioni di pagamento manualmente, anziché utilizzare la proposta di pagamento.  
20. Selezionare il fornitore a cui il pagamento verrà effettuato.
21. Se esiste una fattura da pagare, selezionare Liquida transazioni per selezionarla.
    * Se si sceglie un pagamento anticipato, questo passaggio è facoltativo. È possibile creare il pagamento senza selezionare alcuna fattura.  
22. Contrassegnare tutte le fatture che verranno pagate.
    * Se si utilizzano le transazioni di liquidare per selezionare le fatture per il pagamento, l'importo del pagamento verrà calcolato automaticamente in base alle fatture contrassegnate per il pagamento e all'importo immesso in Importo da liquidare.  
23. Fare clic su OK.
24. Se si desidera eliminare un pagamento, contrassegnare la riga.
25. Fare clic su Elimina.
    * L'eliminazione di un pagamento viene applicata solo al pagamento. Tutte le fatture contrassegnate per il pagamento saranno comunque disponibili per un altro pagamento.  
26. Fare clic su Sì.
27. Selezionare Genera pagamenti per stampare gli assegni o creare il file di pagamento elettronico.
28. Selezionare il metodo di pagamento da generare.
    * Il giornale di registrazione pagamenti può contenere pagamenti per assegni e pagamenti elettronici, ma è possibile generare un solo tipo di pagamento per volta.  
29. Selezionare il conto bancario da cui generare i pagamenti.
30. Fare clic su OK.
    * I pagamenti verranno generati solo per i pagamenti che corrispondono al metodo di pagamento e al conto bancario selezionati.  
31. Se si generano assegni, selezionare Documento per garantire la corretta destinazione di stampa per gli assegni.
32. Fare clic su OK.
33. Fare clic su OK per generare i pagamenti.
34. Fare clic su Registra se tutti i pagamenti sono approvati e generati. 


