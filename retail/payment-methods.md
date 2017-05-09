---
title: Metodi di pagamento
description: Ogni tipo di pagamento accettato da un rivenditore deve essere configurato in Vendita al dettaglio e commercio in Microsoft Dynamics 365 for Operations quando si imposta il sistema. Questo articolo descrive i tipi di pagamento impostati e il processo per impostarli.
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: MargoC
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b887fc5d03ea8982515e92725ce98cc416e56f9e
ms.openlocfilehash: 011beec07bf1ab858892ab1c374f1acf3839e877
ms.lasthandoff: 03/31/2017


---

# <a name="payment-methods"></a>Metodi di pagamento

[!include[banner](includes/banner.md)]


Ogni tipo di pagamento accettato da un rivenditore deve essere configurato in Vendita al dettaglio e commercio in Microsoft Dynamics 365 for Operations quando si imposta il sistema. Questo articolo descrive i tipi di pagamento impostati e il processo per impostarli.

I rivenditori possono accettare diversi tipi di pagamento per i prodotti venduti e i servizi forniti. Sebbene il pagamento in contanti sia in genere la forma più comune, i rivenditori possono ricevere anche pagamenti tramite assegno, carta, buoni e altro ancora. Ogni tipo di pagamento accettato da un rivenditore deve essere configurato in Dynamics 365 for Operations - Retail quando si imposta il sistema. Nell'elenco riportato di seguito viene descritto ogni tipo di pagamento che è possibile impostare in Dynamics 365 for Operations - Retail:

-   **Contante**: denaro nella forma fisica della valuta, ad esempio banconote e monete. La valuta può essere quella della società o quella locale del punto vendita.
-   **Assegno**: titolo negoziabile per il pagamento di un importo specifico in una valuta specifica emesso da una banca specifica. In genere, un assegno è valido o per un periodo di tempo illimitato o per sei mesi dalla data di emissione, salvo diversa indicazione relativa al periodo di validità. Tale periodo può variare a seconda della banca di emissione dell'assegno. Esistono vari tipi di assegni, ad esempio all'ordine, di sportello, al portatore e del beneficiario del conto. È possibile impostare l'assegno come metodo di pagamento per ogni punto vendita. Gli assegni possono essere accettati nella valuta definita a livello aziendale o a livello di punto vendita. Prima di poter accettare un assegno per il pagamento in un punto vendita, è necessario impostare come metodo di pagamento questo tipo di titolo.
-   **Valuta**: mezzo prevalente di pagamento diverso dalla valuta predefinita della società. Monete e banconote sono entrambe formati di valuta. Il metodo di pagamento in valuta rappresenta tutte le valute utilizzate in Vendita al dettaglio e commercio. Prima di poter utilizzare questo metodo di pagamento, è necessario impostare le valute e specificare le informazioni relative al cambio delle valute.
-   **Carta**: tutti i tipi di carte utilizzate in Vendita al dettaglio e commercio, ad esempio carte di debito o di credito. È opportuno impostare un solo metodo di pagamento con carta a livello dell'organizzazione che rappresenti tutti i tipi di carte. A livello di punto vendita quindi, impostare un metodo di pagamento per ogni carta o set di carte da elaborare utilizzando le stesse impostazioni. Prima di poter accettare le carte come metodo di pagamento in un punto vendita, è necessario impostare le carte dei gestori disponibili sul mercato, ad esempio carte di debito o di credito.
-   **Nota di credito**: note di credito emesse o rimborsate nel POS. Le note di credito possono essere relative a un credito o a un reso emesso per un reso. Se le note di credito vengono rimborsate solo parzialmente, per il nuovo saldo verrà emessa automaticamente una nuova nota di credito con un nuovo numero. È possibile utilizzare una nota di credito una sola volta, nel sistema viene mantenuto un record di tutti i numeri utilizzati. Il record può essere visualizzato nella pagina **Tabella note credito**. Un cliente non può ottenere un rimborso di valore superiore a quello della nota di credito.
-   **Gift card**: rappresenta le gift card emesse o rimborsate presso il POS. L'eccedenza di pagamento non è consentita per le gift card.
-   **Conto cliente**: pagamenti che possono essere addebitati su un conto cliente al momento della vendita al registratore di cassa. È inoltre possibile utilizzare questo metodo di pagamento per acquisire informazioni di vendita o sconti specifici del cliente quando il pagamento viene effettuato tramite un metodo di pagamento diverso. In tal caso, è necessario impostare informazioni specifiche del cliente.
-   **Punti programma fedeltà** - i punti che i clienti accumulano tramite i programmi fedeltà. Se si creano i programmi fedeltà, i clienti possono guadagnare punti e quindi riscattarli in vari modi. Ad esempio, in alcuni programmi fedeltà, i clienti possono riscattare i punti fedeltà sotto forma di sconto o persino utilizzarli come mezzo di pagamento.

Per impostare i metodi di pagamento in Vendita al dettaglio e commercio, è necessario completare le attività indicate di seguito.

1.  Impostare i metodi di pagamento per un'organizzazione. Creare i metodi di pagamento accettati da tutta l'organizzazione.
2.  Creare tipi e numeri di carta a livello di organizzazione. Se le carte di credito o di debito sono accettate, è necessario creare un metodo di pagamento per carte, quindi creare i tipi e i numeri di carta a livello di organizzazione.
3.  Impostare il metodo di pagamento per punti vendita. Associare i metodi di pagamento a ogni punto vendita, quindi immettere le impostazioni specifiche del punto vendita per ogni metodo di pagamento.
4.  Impostare metodi di pagamento con carta per punti vendita. Per qualsiasi metodo di pagamento con carta accettato dal punto vendita, è necessario completare l'impostazione della carta.





