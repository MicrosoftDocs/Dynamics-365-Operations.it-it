---
title: Impostare gli effetti attivi
description: In questo argomento viene illustrata la procedura per l'impostazione degli effetti attivi.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 09/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustBillOfExchangeJour
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7f5f62d33f6ffedb3fcefcdd9a83b922c1588df0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444686"
---
# <a name="set-up-bills-of-exchange"></a>Impostare gli effetti attivi

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrata la procedura per l'impostazione degli effetti attivi.

Un effetto attivo è un ordine scritto o elettronico di un cliente in cui è specificato che un'altra parte, in genere una banca, deve pagare un determinato importo alla società. Quando si utilizza un effetto attivo come pagamento per una fattura di ordine cliente o una fattura a testo libero, si esegue un accredito sul conto cliente. Tale accredito viene garantito dall'effetto attivo finché il cliente non paga l'effetto attivo alla banca. In genere, la fattura viene liquidata con l'effetto attivo alla data di scadenza. Quando si riceve la notifica dalla banca che il pagamento è stato effettuato, l'effetto attivo può essere chiuso. È possibile emettere un effetto attivo tramite la propria banca con la seguente tempistica:

-   Alla data di scadenza. Questo approccio è conosciuto come rimessa per incasso.
-   Prima della data di scadenza, generalmente alla data dello sconto specificata nei termini di pagamento impostati per il cliente. Quando si registra la transazione, l'importo dello sconto viene registrato in un conto spese. L'importo residuo è considerato una passività finché la banca riceverà il pagamento dal cliente. Questo approccio è conosciuto come rimessa per sconto.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Impostare profili registrazione per gli effetti attivi

Utilizzare la pagina **Profili di registrazione cliente** per impostare profili di registrazione da utilizzare con effetti attivi, effetti attivi protestati, rimesse per incasso e rimesse per sconto. Nel campo **Conto riepilogativo**, selezionare il conto riepilogativo in cui registrare gli importi degli effetti attivi. Su questo conto vengono effettuati addebiti o accrediti in base al tipo di transazione di effetto attivo:
-   Per gli effetti attivi, viene eseguito un addebito sul conto quando viene registrato un effetto attivo e viene eseguito un accredito quando viene registrata una rimessa per sconto o una rimessa per incasso.
-   Per gli effetti attivi protestati, viene eseguito un addebito sul conto quando viene registrato un effetto attivo protestato.
-   Per le rimesse per incasso, viene eseguito un addebito sul conto quando viene registrata una rimessa per incasso.
-   Per le rimesse per sconto, viene eseguito un addebito sul conto quando viene registrata una rimessa per sconto.

Nel campo **Conto di liquidazione**, selezionare il conto di cassa in cui registrare gli importi degli effetti attivi. Viene eseguito un addebito sul conto quando viene liquidato un effetto attivo. Nel campo **Pagamenti anticipati IVA**, selezionare il conto riepilogativo in cui registrare gli importi IVA quando vengono utilizzati gli effetti attivi per i pagamenti anticipati. Nel campo **Conto per passività di sconto**, selezionare il conto in cui registrare l'importo dello sconto per le rimesse per sconto. Viene eseguito un accredito sul conto quando viene registrata una rimessa per sconto.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Impostare parametri della contabilità clienti per gli effetti attivi

Nella pagina **Parametri contabilità clienti**, i profili di registrazione predefiniti per gli effetti attivi sono immessi nella scheda **Contabilità generale e IVA**. Le sequenze numeriche vengono definite nella scheda **Sequenze numeriche**.

## <a name="set-up-journal-names-for-bills-of-exchange"></a>Impostare nomi di giornale di registrazione per gli effetti attivi


Nella pagina **Nomi giornali di registrazione**, creare almeno cinque nomi di giornale di registrazione da utilizzare per gli effetti attivi. Di seguito sono riportati i tipi di giornale di registrazione:
-   **Effetto attivo cliente emesso**: consente di creare un nome di giornale di registrazione per il giornale di registrazione degli effetti attivi emessi.
-   **Effetto attivo cliente protestato**: consente di creare un nome di giornale di registrazione per il giornale di registrazione degli effetti attivi protestati.
-   **Effetto attivo cliente riemesso**: consente di creare un nome di giornale di registrazione per il giornale di registrazione degli effetti attivi riemessi.
-   **Rimessa bancaria cliente**: consente di creare un nome di giornale di registrazione per il giornale di registrazione rimesse.
-   **Effetto attivo cliente liquidato**: consente di creare un nome di giornale di registrazione per il giornale di registrazione degli effetti attivi liquidati.

Nella pagina del giustificativo del giornale di registrazione di ciascun giornale di registrazione degli effetti attivi, immettere informazioni sull'effetto attivo nella scheda **Effetti attivi**. Una volta registrate le righe del giornale di registrazione degli effetti attivi, è possibile visualizzarle nelle pagine **Visualizza riichiesta informazioni su giornale di registrazione fatture effetto attivo** e nella pagina **Statistiche effetti attivi**.

## <a name="set-up-methods-of-payment-for-bills-of-exchange"></a>Impostare metodi di pagamento per gli effetti attivi

Nella pagina **Metodi di pagamento**, impostare almeno un metodo di pagamento per gli effetti attivi. Se si intrattengono relazioni commerciali con più banche, impostare un metodo di pagamento che corrisponda al formato di rimessa richiesto da ciascuna banca per gli effetti attivi.

## <a name="set-up-payment-fees-for-bills-of-exchange"></a>Impostare commissioni di pagamento per gli effetti attivi

Una commissione di pagamento è una spesa associata al processo di riscossione dei pagamenti dai clienti. È possibile associare più righe di impostazione di commissione di pagamento a ciascuna commissione di pagamento. È possibile utilizzare le righe di impostazione per controllare la modalità di calcolo degli importi predefiniti per le commissioni di pagamento. È ad esempio possibile creare righe di impostazione per metodi di pagamento, specifiche di pagamento, valute e periodi. È inoltre possibile creare righe di impostazione per una percentuale o un importo basato su intervalli di giorni. Ad esempio, è possibile impostare una percentuale di interesse basata sul tempo trascorso dalla scadenza di un pagamento. Se la banca addebita commissioni diverse in base ai tipi di rimessa, ad esempio **Incasso** o **Sconto**, impostare una riga di commissione di pagamento separata per ciascun tipo di rimessa.

## <a name="set-up-remittance-fees-for-bank-remittance-files"></a>Impostare gli addebiti di rimessa per i file rimesse bancarie

Nella pagina **Conti bancari**, è possibile impostare addebiti di rimessa addebitati da una banca per ciascun file rimesse che viene generato. Gli addebiti di rimessa vengono registrati dopo la conferma della rimessa e una volta conosciuti gli importi degli addebiti realizzati. Gli addebiti di rimessa sono diversi dalle commissioni di pagamento, che si riscuotono dai clienti e sono collegate alle righe dei giornali di registrazione.

## <a name="set-up-document-layouts-for-bills-of-exchange"></a>Impostare layout di documento per gli effetti attivi

Nella pagina **Conti bancari**, fare clic su **Impostazioni**, quindi specificare il layout di documento richiesto per ciascun conto bancario per il quale verranno generati effetti attivi stampati.

## <a name="set-up-customers-for-bills-of-exchange"></a>Impostare clienti per gli effetti attivi

Nella pagina **Clienti**, per ciascun cliente che ha accettato di effettuare i pagamenti tramite un effetto attivo, è possibile impostare un metodo di pagamento predefinito per gli effetti attivi nella scheda **Impostazioni predefinite pagamento**.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]