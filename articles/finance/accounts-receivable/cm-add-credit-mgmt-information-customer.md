---
title: Aggiungere informazioni sulla gestione dei crediti per i clienti
description: Questo argomento descrive come aggiungere informazioni sulla gestione dei crediti per un cliente.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: b7ad1b8ff9f00dba41c02e6426662a03c6c6211b
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015279"
---
# <a name="add-credit-management-information-for-customers"></a>Aggiungere informazioni sulla gestione dei crediti per i clienti

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Dopo aver impostato i parametri che controllano la gestione dei crediti, è possibile aggiungere ulteriori dettagli per ciascun cliente. Questi dettagli controllano i processi di gestione dei crediti e forniscono inoltre informazioni aggiuntive che assistono i membri del team riscossioni nel gestire i clienti.

## <a name="customer-information"></a>Informazioni cliente

È possibile aggiungere dettagli sui clienti nella scheda dettaglio **Credito e riscossioni** della pagina **Tutti i clienti** (**Contabilità clienti \> Clienti \> Tutti i clienti**).

1. Impostare l'opzione **Limite di credito illimitato** su **Sì** se il cliente non deve essere limitato da alcun test del limite di credito.
2. Impostare l'opzione **Escludi da gestione crediti** su **Sì** per escludere il cliente da qualsiasi azione che in genere si verifica durante i processi di gestione dei crediti.
3. Selezionare il gruppo di gestione dei crediti per il cliente.
4. Per calcolare il limite di credito nella valuta del cliente, nel campo **Limite di credito nella valuta del cliente**, immettere il limite di credito del cliente. Il limite di credito nella valuta della società verrà convertito utilizzando i tassi di cambio definiti dal tipo di tasso di cambio del limite di credito selezionato nei parametri di Gestione crediti.
5. Nel campo **Data ultima revisione**, inserire la data in cui il limite di credito del cliente è stato esaminato l'ultima volta da un responsabile crediti.
6. Nel campo **Prossima data di revisione programmata**, inserire la data alla quale verrà esaminato e aggiornato il credito del cliente.
7. Nel campo **Limite di credito idoneo**, inserire il limite di credito più alto che può essere assegnato al cliente, in base alla revisione dello storico credito di quel cliente. Il limite di credito idoneo può differire dal limite di credito visualizzato nella scheda dettaglio **Credito e riscossioni**.
8. Nel campo **Valuta limite del credito idoneo**, immettere la valuta del limite di credito idoneo.
9. Nel campo **Data limite di credito idoneo**, inserire la data in cui il limite di credito idoneo è stato creato.
10. Nel campo **Stato conti credito** inserire lo stato del conto di credito del cliente.
11. Nel campo **Motivo dello stato** inserire il motivo associato allo stato del conto.
12. Impostare l'opzione **Con agenzia** su **Sì** per indicare che il cliente è attualmente assegnato a un'agenzia di analisi di credito. Questo valore è fornito solo a scopo informativo. Non viene utilizzato in alcun processo di gestione dei crediti.
13. Impostare l'opzione **Titolo detenuto** su **Sì** per indicare che un titolo è detenuto per la società. Questo valore è fornito solo a scopo informativo. Non viene utilizzato in alcun processo di gestione dei crediti.
14. Nel campo **Data di inizio attività**, inserire la data di inizio dell'attività del cliente. Questa informazione viene utilizzata quando si creano punteggi di rischio.
15. Nel campo **Cliente dal**, inserire la data in cui le prime transazioni sono state elaborate per il cliente. Questa informazione viene utilizzata quando si creano punteggi di rischio.
16. Immettere le note che il team di gestione dei crediti può utilizzare per valutare ulteriormente l'affidabilità creditizia del cliente.

Si noti che alcune delle informazioni visualizzate nella pagina **Cliente** sono create da un altro processo:

- Il campo **Scadenza limite di credito** mostra la data di scadenza del limite di credito. Se non si imposta questo campo, il limite di credito del cliente non scadrà.
- Il campo **Data limite di credito** mostra la data di creazione del limite di credito. Questo campo viene aggiornato ogni volta che il limite di credito viene corretto.
- I limiti di credito temporanei hanno la precedenza sul limite di credito del cliente per un periodo definito. Vengono utilizzati al posto del limite di credito per calcolare il limite di credito totale. Queste informazioni vengono visualizzate solo se esiste un limite di credito attivo. È possibile aggiungere limiti di credito temporanei tramite le correzioni dei limiti di credito.
- Il campo **Assicurazione e garanzie** mostra il valore totale dell'assicurazione e delle garanzie che possono aumentare il limite di credito per il cliente.
- Il campo **Limite di credito totale** mostra il limite di credito finale per il cliente. Il limite di credito totale comprende assicurazione e garanzie e limiti di credito temporanei.

## <a name="temporary-credit-limits"></a>Limiti di credito temporanei

I limiti di credito temporanei hanno la precedenza sui limiti di credito di un cliente per un periodo definito. È possibile aggiungere limiti di credito temporanei tramite le correzioni dei limiti di credito. Le correzioni dei limiti di credito consentono ai gestori dei crediti di aggiornare i limiti di credito e le date di scadenza di un singolo cliente, un gruppo di clienti o di tutti i clienti mediante un processo di registrazione.

È possibile creare voci di correzioni dei limiti di credito nella pagina **Correzioni del limite di credito**(**Gestione crediti \> Correzioni del limite di credito \> Correzioni del limite di credito**).

## <a name="create-insurance-policies-and-guarantees"></a>Creare polizze assicurative e garanzie

È possibile creare una o più polizze assicurative e garanzie per ciascun cliente. Queste possono essere utilizzate per calcolare l'esposizione della propria azienda quando offre un credito a un cliente. Le polizze assicurative e le garanzie possono anche essere incluse nel limite di credito di un cliente.

È possibile creare polizze assicurative e garanzie nella pagina **Tutti i clienti** (**Contabilità fornitori \> Clienti \> Tutti i clienti**). Selezionare un cliente e quindi nel riquadro azioni, nella scheda **Gestione crediti**, selezionare **Assicurazione e garanzie**.

> [!NOTE]
> Nella procedura seguente, si seleziona un assicuratore o un garante dalla rubrica globale. Pertanto, prima di iniziare questa procedura, è necessario assicurarsi che gli assicuratori e i garanti siano stati aggiunti alla rubrica globale.

1. Nel campo **Identifcatore**, immettere **Garanzia** o **Assicurazione**.
2. Nel campo **Tipo di garanzia/assicurazione**, selezionare uno dei tipi di garanzia o assicurazione precedentemente impostati.
3. Nel campo **Assicuratore/garante**, selezionare l'assicuratore o il garante dalla rubrica globale. 
4. Se si è selezionato **Assicurazione** nel campo **Identificatore**, nel campo **Tipo di copertura polizza** selezionare uno dei tipi di copertura precedentemente impostati. Non è possibile selezionare un tipo di copertura polizza per una garanzia.
5. Nel campo **Identificazione** immettere l'ID della polizza. Questo ID è generalmente un numero di polizza.
6. Nel campo **Validità**, inserire la data di inizio della polizza assicurativa o della garanzia.
7. Nel campo **Scadenza**, inserire la data in cui la polizza assicurativa o la garanzia scade.
8. Nel campo **Valore**, inserire il valore della polizza assicurativa o della garanzia. Questo valore è il valore completo della polizza.
9. Nel campo **Valuta**, selezionare la valuta per il valore della polizza. 
10. Nel campo **Aggiorna limite di credito**, specificare una percentuale tra **0** e **100**. Questa percentuale verrà applicata al valore della polizza e l'importo risultante verrà utilizzato per aumentare il limite di credito utilizzato nei calcoli del limite di credito. Il valore calcolato è visualizzato sotto **Limite di credito totale, Assicurazione e garanzie** nella scheda dettaglio **Credito e riscossioni** della pagina **Clienti**.

    Ecco un esempio:

    - Il limite di credito (A) è 100.000.
    - Il valore della polizza (B) è 50.000.
    - La percentuale di **Aggiorna limite di credito** (C) è 50,00.
    
    In questo caso, il limite di credito effettivo è 125.000 (= A + \[B × C\]).

11. Selezionare la casella di controllo **Incluso nell'esposizione** per ridurre il limite di credito utilizzato nei calcoli del limite di credito dell'intero valore della polizza. Se questa casella di controllo è selezionata, il valore che viene calcolato quando la percentuale di **Aggiorna limite di credito** viene specificata non verrà utilizzato nei calcoli del limite di credito.

    Ecco un esempio:

    - Il limite di credito (A) è 100.000.
    - Il valore della polizza (B) è 50.000.
    - La percentuale di **Aggiorna limite di credito** (C) è 50,00.

    In questo caso, il limite di credito effettivo è 125.000 (= A + \[B × C\]).
    
    Tuttavia, se si seleziona la casella di controllo **Incluso nell'esposizione** il valore 50.000 di **Aggiorna limite di credito** (= 50,00 percento di 100.000) viene rimosso e il valore di esposizione è 75.000 (= A + \[B × C\] - B).
