---
title: Rateo dei costi per il progetto nelle entrate di acquisto
description: "In questo argomento viene descritto come i costi di progetto accumulati in base alle entrate di acquisto è possibile eseguire in Microsoft Dynamics 365 per le operazioni."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 27a0a71095dce46c0119b32a92f8c4dce0f42e43
ms.lasthandoff: 03/31/2017


---

# <a name="project-cost-accrual-on-purchase-receipts"></a>Rateo dei costi per il progetto nelle entrate di acquisto

In questo argomento viene descritto come i costi di progetto accumulati in base alle entrate di acquisto è possibile eseguire in Microsoft Dynamics 365 per le operazioni. 

Le fatture per un progetto spesso arrivano successivamente di merci e servizi vengono concessi in prestito, che potrebbero avere un impatto significativo sugli indicatori di prestazione chiave Gestione progetti (KPIs). Importante poter utilizzare queste transazioni nei report finanziari che nei report.

Il seguente scenario di questo esempio viene illustrato. 

Il servizi di consulenza per Contoso ha avviato un nuovo progetto di distribuzione cloud. Un ordine fornitore viene creato di acquistare un computer per il progetto. Il computer costerà $1500 e i servizi dell'installazione costeranno dollari. Il fornitore ha consegnato e installato il computer, ma la fattura non è ancora raggiunto il servizi di consulenza per Contoso. Il manager di progetto Richiesta visualizzare una competenza dei costi per il progetto di $1650 prima della registrazione ottenesse consegnata. Il costo deve essere riportato nei rendiconti finanziari di fine mese della società. 

Il costo accumulato deve essere registrato sia a livello finanziario che il livello del progetto a scopo di reporting. In Dynamics 365 per le operazioni, aggiornamento finanziario dell'entrata prodotti può essere seguito per l'articolo e le categorie di approvvigionamento. 

Per gli articoli, ** parametri di contabilità fornitori ** nella pagina, selezionare ** registrare le entrate prodotti nella contabilità generale ** l'opzione.
![[] (accruals1. /media/accruals1-1024x409.png)](. /media/accruals1.png) 

Per le categorie di approvvigionamento, ** regola dei criteri categorie ** nella pagina, selezionare ** ** dei criteri e quindi selezionare ** si (l'importo dell'acquisto sulla ricevuta ** per ogni categoria di approvvigionamento.
![[] (accruals2. /media/accruals2-1024x569.png)](. /media/accruals2.png) 

** Spese di acquisto non fatturate ** e ** competenza acquisti ** i conti in ** registrazione sono ** verranno utilizzati quando i giustificativi correlati all'entrata prodotti registrati.
![[] (accruals3. /media/accruals3-1024x429.png)](. /media/accruals3.png) 

Utilizzando questo stesso scenario, vedere lascici come registrare un'entrata prodotti urterà la contabilità generale e proietterà le informazioni. 

** Passaggio 1: ** Creare e confermare un nuovo ordine fornitore per il progetto per il quale si desidera registrare l'acquisto di un computer per $1500 e i servizi dell'installazione di dollari.
![[] (accruals4. /media/accruals4-1024x497.png)](. /media/accruals4.png) 

Quando l'ordine fornitore viene confermato, le transazioni del costo impegnato vengono create per il progetto. 
![[] (accruals5. /media/accruals5-1024x219.png)](. /media/accruals5.png) 

> [!NOTE]
> Le transazioni per il costo impegnato avranno ** origine della transazione ** il campo impostato su ** ** ordine fornitore. Creazione e confermando un ordine fornitore non dà origine a transazioni per un progetto. 

** Passaggio 2: ** Il e servizi verranno consegnati e un'entrata prodotti è registrata. 

Registrare un'entrata prodotti verrà generata e registrata un giustificativo nella contabilità generale. Giustificativo addebiterà le spese di acquisto, il conto non fatturate e il conto di competenza acquisti a credito. 
![[] (accruals6. /media/accruals6-1024x214.png)](. /media/accruals6.png)

> [!NOTE]
> Registrare un'entrata prodotti verrà utilizzata la registrazione per impostare le categorie di approvvigionamento e prodotti e non le impostazioni di registrazione per le categorie di progetti. Per indicare se l'impatto finanziario dei ratei di acquisto, questa operazione deve essere linea. 

È possibile mappare le categorie di approvvigionamento alle categorie ** categoria di approvvigionamento ** nella pagina.
![[] (accruals7. /media/accruals7-1024x390.png)](. /media/accruals7.png)

** Passaggio 3: ** Creare una fattura fornitore del progetto. 

In Dynamics 365 per le operazioni, registrare un'entrata prodotti non influisce sulle informazioni sul progetto. Come soluzione alternativa, è possibile generare una fattura fornitore del progetto registrare subito dopo l'entrata di acquisto. Passare ** ** ordine fornitore nella &gt; pagina ** scheda fatture generano ** &gt; ** ** &gt; ** ** fattura. Verrà creato un documento di fattura in attesa che gli aggiornamenti delle informazioni. 

Creazione di una fattura fornitore del progetto creato in attesa delle transazioni di progetto. 
![[] (accruals8. /media/accruals8-1024x225.png)](. /media/accruals8.png) 

** Costo impegnato ** nella pagina, i record creati nel passaggio 1 verranno chiusi e nuovi record verranno creati per riflettere l'impegno di costo derivante della fattura fornitore in sospeso. ** Origine transazione ** il campo per il costo impegnato verrà impostato su ** ** fattura fornitore.
![[] (accruals9. /media/accruals9-1024x200.png)](. /media/accruals9.png)

La fattura fornitore rimane di uno con stato in sospeso finché la fattura fornitore effettivo non arrivi.


