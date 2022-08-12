---
title: Riconciliare un conto bancario
description: In questo articolo viene descritta la riconciliazione di un conto bancario.
author: angelad116
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d36ff753d368bbbe6944aa5ae5010541ee92156d
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151253"
---
# <a name="reconcile-a-bank-account"></a>Riconciliare un conto bancario

[!include[banner](../includes/banner.md)]

Quando si riceve un rendiconto bancario, è necessario riconciliare periodicamente le transazioni bancarie della persona giuridica con le transazioni nel rendiconto bancario.

Se un assegno o una distinta di deposito bancario qualsiasi elencati sul rendiconto hanno lo stato **In attesa di annullamento**, non è possibile effettuare la riconciliazione del rendiconto bancario con un conto bancario. Dopo che un revisore registra o rifiuta uno storno di assegni o un annullamento di distinte di deposito bancario, lo stato non è più **In attesa di annullamento** e sarà possibile effettuare la riconciliazione del conto bancario.

1.  Passare a **Gestione cassa e banche** \> **Conti bancari** \> **Conti bancari**. Selezionare il conto bancario da riconciliare con il rendiconto bancario e selezionare **Riconcilia** > **Riconciliazione estratti conto**.

2.  Immettere le informazioni nei campi **Rendiconto bancario** e **Data rendiconto bancario**. Nel campo **Saldo finale** è possibile immettere il saldo del conto bancario riportato nel rendiconto bancario.

3.  Selezionare **Transazioni** per aprire la pagina **Riconciliazione estratti conto**.

4.  Per ciascuna transazione inclusa nel rendiconto bancario, selezionare la casella di controllo **Liquidato** se l'importo in Dynamics 365 Finance corrisponde a quello riportato nel rendiconto. È inoltre possibile immettere o modificare il valore nel campo **Tipo di transazione bancaria**. Questo valore è importante ai fini delle statistiche sulle transazioni bancarie e per alcuni report.
    

    > [!NOTE]
    > <P>Non selezionare la casella di controllo <STRONG>Liquidato</STRONG> per le transazioni non riportate nel rendiconto bancario. Queste transazioni continueranno a essere visualizzate in questa pagina finché non verranno riconciliate con un rendiconto bancario successivo.</P>
    > <P>La casella di controllo <STRONG>Liquidato</STRONG> non è disponibile se la transazione riporta uno stato <STRONG>In attesa di annullamento</STRONG>. Le transazioni possono avere tale stato se in Finance è impostata la revisione obbligatoria di storni e annullamenti prima della relativa registrazione. Dopo la registrazione o il rifiuto dello storno o dell'annullamento da parte di un revisore, lo stato non è più <STRONG>In attesa di annullamento</STRONG>, ed è possibile effettuare la riconciliazione del conto bancario con il rendiconto bancario.</P>

    
    Selezionare la casella di controllo **Liquidato** per un intervallo di assegni tutti presenti sul rendiconto bancario, fare clic su **Contrassegna intervallo assegni**, quindi indicare l'intervallo.

5.  Se l'importo di una transazione di conto bancario non corrisponde all'importo della transazione nel rendiconto bancario, immettere l'importo di rettifica nel campo **Importo correttivo**.
    

    > [!NOTE]
    > <P>Se il periodo fiscale della transazione da correggere è chiuso, non sarà possibile utilizzare il campo <STRONG>Importo correttivo</STRONG>. Creare pertanto una riga con una data di transazione compresa in un periodo fiscale aperto per la correzione. In questo caso, è necessario aggiungere le dimensioni finanziarie utilizzate nella transazione originaria e anche, il conto principale di contropartita.</P>



6.  Creare transazioni per le voci, quali spese e interessi, presenti nel rendiconto bancario ma non registrate in Finance. Immettere il **Tipo di transazione bancaria** e le dimensioni finanziarie appropriate.

7.  Poiché le transazioni sul rendiconto bancario sono contrassegnate come **Liquidato**, l'importo nel campo **Non riconciliato**, ricalcolato continuamente quando si apportano modifiche, si avvicina allo zero. Quando il valore diventa uguale a zero, fare clic su **Riconcilia conto** per registrare la riconciliazione, nonché le transazioni e le correzioni create.
    
    Dopo la registrazione della riconciliazione, le transazioni incluse non possono essere modificate o corrette e non vengono visualizzate per le successive riconciliazioni degli estratti conto.

8.  Per visualizzare le transazioni bancarie non ancora riconciliate, utilizzare il report **Transazioni bancarie non riconciliate**. Per visualizzare il rendiconto bancario per un conto bancario, utilizzare il report **Rendiconto bancario**.

## <a name="cancel-bank-statement-reconciliation"></a>Annulla riconciliazione rendiconti bancari 

La funzionalità Annulla riconciliazione rendiconti bancari consente di annullare la riconciliazione dei rendiconti bancari. Per utilizzare questa funzionalità, abilitare la funzionalità **Annulla riconciliazione rendiconti bancari** nell'area di lavoro **Gestione funzionalità**. È inoltre necessario abilitare il parametro **Consenti modifica rendiconto bancario**. A tale scopo, andare a **Gestione cassa e banche > Impostazioni >Parametri di gestione cassa e banche > Riconciliazione bancaria**.
 
Le riconciliazioni del rendiconto bancario possono essere annullate solo nell'ordine cronologico in cui sono state immesse. Quando una riconciliazione del rendiconto bancario viene annullata, le nuove transazioni e le rettifiche verranno stornate e tutte le altre transazioni vengono contrassegnate come non riconciliate.
 
Per annullare la riconciliazione del rendiconto bancario, selezionare il rendiconto bancario e selezionare **Rendiconto bancario > Annulla riconciliazione estratti conto**. Nella pagina **Annulla riconciliazione estratti conto**, immettere **Codice motivo**, **Commento motivo** e **Data di annullamento**. Selezionare **OK** per avviare l'annullamento. Nota, la data di annullamento di rendiconto bancario deve essere coincidente o successiva alla data del rendiconto bancario. Dopo che la riconciliazione del rendiconto bancario è annullata, il campo **Data di annullamento** per il rendiconto bancario verrà aggiornato con la **Data di annullamento** fornita. Fare clic sul pulsante **Transazioni** per visualizzare le transazioni per cui la riconciliazione è stata annullata.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
