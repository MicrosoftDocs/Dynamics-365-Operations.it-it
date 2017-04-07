---
title: Impostare gli effetti attivi
description: Viene descritta la procedura per l&quot;impostazione degli effetti attivi.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: abruer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ce2142d946085d8bfc577accf1bb31a89ea29156
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bills-of-exchange"></a>Impostare gli effetti attivi

Viene descritta la procedura per l'impostazione degli effetti attivi.

Un effetto attivo è un ordine scritto o elettronico di un cliente in cui è specificato che un'altra entità, in genere una banca, deve pagare un determinato importo alla società. Quando si utilizza un effetto attivo come pagamento per una fattura di ordine cliente o una fattura a testo libero, si esegue un accredito sul conto cliente. Tale accredito viene garantito dall'effetto attivo finché il cliente non paga l'effetto attivo alla banca. In genere, sistemerete la fattura liquidata con l'effetto attivo alla data di scadenza. Quando si riceve la notifica dalla banca che il pagamento è stato effettuato, l'effetto attivo può essere chiuso. È possibile emettere un effetto attivo tramite la banca all'uno o nelle seguenti fasi:

-   Alla data di scadenza. Questo metodo è noto anche come rimessa per incasso.
-   Prima della scadenza, in genere alla data sconto specificata in termini di pagamento impostati per il cliente. Quando si registra la transazione, l'importo dello sconto viene registrato in un conto spese. L'importo residuo è considerato una passività finché la banca riceverà il pagamento dal cliente. Questo metodo è noto anche come rimessa per sconto.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Impostare profili registrazione per gli effetti attivi
** Utilizzare profili registrazione dei clienti ** impaginano per impostare i profili di registrazione da utilizzare con gli effetti attivi, effetti attivi protestati, le rimesse per incasso e le rimesse per sconto. In ** conto riepilogativo ** sistemi, selezionare il conto riepilogativo in cui registrare gli importi degli effetti attivi. Questo conto viene effettuato l'accredito in o, a seconda del tipo di transazione effetto attivo:
-   Per gli effetti attivi, viene eseguito un addebito sul conto quando viene registrato un effetto attivo e viene effettuato quando una rimessa per sconto o viene registrata una rimessa per incasso.
-   Per gli effetti attivi protestati, viene eseguito un addebito sul conto quando viene registrato un effetto attivo protestato.
-   Per le rimesse per incasso, viene eseguito un addebito sul conto quando viene registrata una rimessa per incasso.
-   Per le rimesse per sconto, viene eseguito un addebito sul conto quando viene registrata una rimessa per sconto.

In ** conto liquidità ** sistemi, selezionare il conto di cassa per registrare gli importi degli effetti attivi. Viene eseguito un addebito sul conto quando viene liquidato un effetto attivo. In ** pagamenti anticipati VAT ** sistemi, selezionare il conto riepilogativo in cui registrare gli importi VAT quando vengono utilizzati gli effetti attivi per i pagamenti anticipati. ** Nel conto per passività di sconto ** sistemi, selezionare il conto in cui registrare l'importo dello sconto per le rimesse per sconto. Viene eseguito un accredito sul conto quando viene registrata una rimessa per sconto.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Impostare i parametri di contabilità clienti per gli effetti attivi
** Parametri contabilità clienti ** nella pagina, i profili di registrazione predefinito per gli effetti attivi immessi ** contabilità generale e VAT ** nella scheda. Le sequenze numeriche vengono definite sequenze numeriche ** ** nella scheda.
Impostare nomi di giornale di registrazione per gli effetti attivi
------------------------------------------

** Nomi dei giornali di registrazione ** nella pagina, è necessario creare almeno cinque nomi di giornale di registrazione da utilizzare per gli effetti attivi. Di seguito vengono riportati i tipi di giornale di registrazione:
-   ** Effetti attivi cliente emessi ** consente di creare un nome di giornale di registrazione per il giornale di registrazione effetti attivi emessi.
-   ** Effetti attivi cliente protestati ** consente di creare un nome di giornale di registrazione per il giornale di registrazione effetti attivi protestati.
-   ** Il cliente riemessi l'effetto attivo ** consente di creare un nome del giornale di registrazione effetti attivi riemessi.
-   ** Rimessa bancaria cliente ** consente di creare un nome di giornale di registrazione per il giornale di registrazione rimesse.
-   ** Effetti attivi cliente liquidati ** consente di creare un nome di giornale di registrazione per il giornale di registrazione effetti attivi liquidati.

Nella pagina Giustificativo giornale di registrazione per ciascun giornale di registrazione effetti attivi, immettere le informazioni sull'effetto attivo ** effetto attivo ** nella scheda. Dopo che le righe del giornale di registrazione effetti attivi, è possibile visualizzarli ** indagine del giornale di registrazione effetti attivi ** nella pagina ed ** Statistiche effetti attivi ** nella pagina.
Impostare metodi di pagamento per gli effetti attivi
-----------------------------------------------

** Metodi di pagamento ** nella pagina, impostare almeno un metodo di pagamento per gli effetti attivi. Se si intrattengono relazioni commerciali con più banche, impostare un metodo di pagamento che corrisponda al formato di rimessa che ogni banca richiede per gli effetti attivi.
Impostare commissioni di pagamento per gli effetti attivi
-----------------------------------------

Una commissione di pagamento è una spesa associata al processo di riscossione dei pagamenti dai clienti. Le più righe di impostazione della commissione di pagamento è possibile associare ogni commissione di pagamento. È possibile utilizzare le righe di impostazione per controllare il modo in cui gli importi predefiniti per le commissioni di pagamento vengono calcolati. È ad esempio possibile creare righe di impostazione per metodi di pagamento, specifiche di pagamento, valute e periodi. È anche possibile creare righe di impostazione per percentuali o un importo basato su intervalli di giorni. Ad esempio, è possibile impostare una percentuale di interesse basata su una durata del pagamento. Se commissioni diverse la banca addebita tipi di rimessa, ad esempio ** sollecito ** o ** ** sconto, impostare una riga di commissione di pagamento separata per ciascun tipo di rimessa.
Impostare gli addebiti di rimessa per i file rimesse bancarie
------------------------------------------------

** Conti bancari ** nella pagina, è possibile impostare addebiti di rimessa che le competenze relative a ogni file rimesse generata. Gli addebiti di rimessa vengono registrati dopo la conferma della rimessa e una volta conosciuti gli importi degli addebiti realizzati. Gli addebiti di rimessa diversi dalle commissioni di pagamento, che si riscuotono dai clienti e sono collegate alle righe.
Impostare layout di documento per gli effetti attivi
---------------------------------------------

** Conti bancari ** alla pagina, fare clic su ** impostazione ** e specificare il layout di documento richiesto per ciascun conto bancario di generare i documenti effetti attivi stampati.
Impostare clienti per gli effetti attivi
--------------------------------------

Nel cliente ** ** impaginivi, per ciascun cliente che ha accettato di effettuare i pagamenti tramite un effetto attivo, può impostare un metodo di pagamento predefinito per gli effetti attivi ** standard di pagamento ** nella scheda.




