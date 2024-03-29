---
title: Entrate acquisti per attribuzione per competenza dei costi di progetto
description: In questo articolo viene descritto come i ratei e risconti passivi di progetto provenienti dalle entrate di acquisto possono essere tracciati in Microsoft Dynamics 365 Finance.
author: mukumarm
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: twheeloc
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: mukumarm
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 56b8b5a6f91c6a18b53739b1e9369bda64131a06
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715858"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a>Entrate acquisti per attribuzione per competenza dei costi di progetto

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come i ratei e risconti passivi di progetto provenienti dalle entrate di acquisto possono essere tracciati in Microsoft Dynamics 365 Finance. 

Le fatture per un progetto spesso arrivano dopo la consegna di merci e servizi, aspetto che potrebbe avere un impatto significativo sugli indicatori di prestazione chiave (KPI) del progetto. È importante poter tenere traccia di queste transazioni sia nei report finanziari che in quelli di progetto.

Nel seguente scenario di esempio viene illustrato questo aspetto. 

Contoso Consulting ha avviato un nuovo progetto di distribuzione cloud. Un ordine fornitore viene creato per acquistare un computer per il progetto. Il computer costerà $ 1.500 e i servizi di installazione costeranno $ 150. Il fornitore ha consegnato e installato il computer ma Contoso Consulting non ha ancora ricevuto la fattura. Il manager di progetto desidera esaminare l'attribuzione dei costi per il progetto di $ 1.650 prima che la fattura venga consegnata. Questi costi devono essere riportati anche nei rendiconti finanziari di fine mese della società. 

I ratei e risconti passivi devono essere registrati sia a livello finanziario che a quello di progetto a scopo di reporting. L'aggiornamento finanziario dell'entrata prodotti può essere tracciato per l'articoloo e le categorie di approvvigionamento. 

Per gli articoli, nella pagina **Parametri contabilità fornitori**, selezionare l'opzione **Registra entrate prodotti nella contabilità generale**.
[![Pagina Parametri contabilità fornitori.](./media/accruals1-1024x409.png)](./media/accruals1.png) 

Per le categorie di approvvigionamento, nella pagina **Regola dei criteri categorie**, selezionare i criteri **Acquisto**, quindi selezionare **Accumula spese su acquisti in entrata** per ciascuna categoria di approvvigionamento.
[![Pagina Regola dei criteri categorie.](./media/accruals2-1024x569.png)](./media/accruals2.png) 

I conti **Spese acquisto non fatturate** e **Competenza acquisti** in **Impostazione di registrazione** verranno utilizzati quando i giustificativi correlati all'entrata prodotti vengono registrati.

Utilizzando questo stesso scenario, esaminiamo come la registrazione di un'entrata prodotti influirà sulla contabilità generale e sulle informazioni relative al progetto. 

**Passaggio 1:** creare e confermare un nuovo ordine fornitore per il progetto per registrare l'acquisto di un computer per $ 1.500 e i servizi di installazione pari a $ 150.
[![Creare un nuovo ordine fornitore.](./media/accruals4-1024x497.png)](./media/accruals4.png) 

Quando l'ordine fornitore viene confermato, le transazioni del costo impegnato vengono create per il progetto. 
[![Transazioni create.](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> Le transazioni per il costo impegnato avranno il campo **Origine transazione** impostato su **Ordine fornitore**. La creazione e la conferma di un ordine fornitore non creano transazioni per un progetto. 

**Passaggio 2:** le merci e i servizi vengono consegnati e un'entrata prodotti è registrata. 

La registrazione di un'entrata prodotti genera e registra un giustificativo nella contabilità generale. Il giustificativo addebiterà le spese di acquisto non fatturate e accrediterà il conto ratei di acquisto. 
[![Transazioni giustificativo.](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> La registrazione di un'entrata prodotti utilizzerà l'impostazione di registrazione per i prodotti e le categorie di approvvigionamento e non l'impostazione di registrazione per le categorie di progetto. Per riflettere correttamente l'impatto finanziario dei ratei di acquisto, questa impostazione deve essere allineata. 

È possibile mappare le categorie di approvvigionamento alle categorie di progetto nella pagina **Categoria di approvvigionamento**.
[![Pagina Categoria di approvvigionamento.](./media/accruals7-1024x390.png)](./media/accruals7.png)

**Passaggio 3:** creare una bozza della fattura fornitore. 

La registrazione di un'entrata prodotti non influisce sulle informazioni relative al progetto. Come soluzione alternativa, è possibile generare una bozza della fattura fornitore subito aver registrato l'entrata acquisti. Passare alla pagina **Ordine fornitore** &gt; **scheda Fattura** &gt; **Genera** &gt; **Fattura**. Verrà creato un documento di fattura in sospeso che aggiorna le informazioni sul progetto. 

La creazione di una bozza di fattura fornitore genera transazioni di progetto in sospeso. 
[![Transazioni progetto in sospeso.](./media/accruals8-1024x225.png)](./media/accruals8.png) 

Nella pagina **Costo impegnato**, i record creati nel passaggio 1 verranno chiusi e nuovi record verranno creati per riflettere gli impegni di costo derivanti dalla fattura fornitore in sospeso. Il campo **Origine transazione** per il costo impegnato verrà impostato su **Fattura fornitore**.
[![Pagina Costi impegnati.](./media/accruals9-1024x200.png)](./media/accruals9.png)

La fattura fornitore rimane con stato in sospeso finché non arriva la fattura fornitore effettiva.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
