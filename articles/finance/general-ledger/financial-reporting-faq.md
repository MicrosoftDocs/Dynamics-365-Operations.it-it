---
title: Domande frequenti sulla creazione di report finanziari
description: In questo argomento vengono riportate le domande relative alla creazione di report finanziari poste da altri utenti.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a0718db77399901acc8c88278c5b373b77b3cb16
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811312"
---
# <a name="financial-reporting-faq"></a>Domande frequenti sulla creazione di report finanziari 

In questo argomento vengono riportate le domande relative alla creazione di report finanziari poste da altri utenti. 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Come si limita l'accesso a un report utilizzando la sicurezza dell'albero?

Scenario: la società dimostrativa USMF dispone di un report stato patrimoniale che non desidera rendere visibile a tutti gli utenti dei report finanziari in D365. Soluzione: è possibile utilizzare la sicurezza dell'albero per limitare l'accesso a un singolo report in modo che solo determinati utenti possano utilizzarlo. 

1.  Accedere a Progettazione report dello strumento di creazione report finanziari

2.  Creare una nuova definizione dell'albero (File | Nuovo | Definizione di albero) a.    Fare doppio clic sulla riga **Riepilogo** nella colonna **Sicurezza unità**.
  i.    Fare clic su Utenti e gruppi.  
          1. Selezionare il gruppo o gli utenti che possono accedere a questo report. 
          
[![Schermata dell'utente](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)

[![Schermata della sicurezza](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)

  b.    Fare clic su **Salva**.
  
[![Pulsante salva](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)

3.  Nella definizione del report, aggiungere la nuova definizione di albero

[![Modulo di definizione di albero](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)

A.  Nella definizione di albero, fare clic su Impostazioni e in "Selezione unità gerarchica" selezionare "Includi tutte le unità"

[![Modulo di selezione dell'unità gerarchica](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)

**Prima:** [![Screenshot della schermata prima](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)

**Dopo:** [![Screenshot della schermata dopo](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)

Nota: il motivo del messaggio precedente è che l'utente non ha accesso al report dopo l'applicazione di Sicurezza unità



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a>Come si determina quali conti non corrispondono ai saldi in D365?

Quando si dispone di un report che non corrisponde a quello che ci si aspetterebbe in D365, ecco alcuni passaggi che è possibile eseguire per identificare i conti e gli scostamenti. 

### <a name="in-financial-reporter-report-designer"></a>In Progettazione report dello strumento di creazione report finanziari

1.  Creare una nuova definizione di riga a.    Fare clic su Modifica | Inserisci righe da dimensioni i.  Seleziona MainAccount [![Schermata della selezione di Conto principale_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)
    
    ii. Fare clic su OK b.    Salvare la definizione di riga

2.  Creare una nuova definizione di colonna     [![Creare una nuova definizione di colonna](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)

3.  Creare una nuova definizione di report a.    Fare clic su Impostazioni e deselezionare [![Modulo Impostazioni](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)
   
4.  Generare il report. 

5.  Esportare il report in Excel.

### <a name="in-d365"></a>In D365: 
1.  Fare clic su Contabilità generale | Richieste di informazioni e report | Bilancio di verifica a.    Parametri i.  Dal: inizio dell'anno fiscale ii. Al: data per cui è stato generato il report iii.    Set di dimensioni finanziarie "Set di conti principali" [![Modulo conto principale](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)
      
  b.    Fare clic su Calcola

2.  Esportare il report in Excel

Ora si possono copiare i dati dal report di Excel della creazione di report finanziari e nel report D365 Bilancio di verifica e confrontare le colonne "Saldo finale".


[!INCLUDE[footer-include](../../includes/footer-banner.md)]