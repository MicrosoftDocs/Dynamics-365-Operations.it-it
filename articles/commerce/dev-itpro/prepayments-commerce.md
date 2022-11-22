---
title: Anticipi in Dynamics 365 Commerce
description: In questo articolo viene fornita una panoramica dell'elaborazione delle transazioni di anticipo in Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-06-28
ms.openlocfilehash: 8262470f83481ef8840857a52948c0833d8b278e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780361"
---
# <a name="prepayments-in-dynamics-365-commerce"></a>Anticipi in Dynamics 365 Commerce

[!include[banner](../includes/banner.md)]

In questo articolo viene fornita una panoramica dell'elaborazione delle transazioni di anticipo in Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce elabora le transazioni di pagamento anticipato per i seguenti tipi di pagamento utilizzati in Contabilità clienti o Commerce:

- **Pagamento deposito sul conto cliente** – Un cliente paga un deposito presso il punto vendita (POS). Commerce elabora il pagamento del deposito come transazione di pagamento anticipato. Quando si registra la transazione, viene creato un giornale di registrazione pagamenti che viene registrato nella pagina **Giustificativo giornale di registrazione.** in Commerce headquarters. La casella di controllo **Giustificativo giornale di registrazione per pagamento anticipato** nella scheda **Pagamento** viene selezionata automaticamente per il giornale di registrazione pagamenti. Per ulteriori informazioni, inclusi pagamenti anticipati e informazioni specifiche sulle tasse rilevanti all'area geografica di destinazione, vedere [Risorse per la globalizzazione: contenuti della guida specifici per paese/area geografica](/dynamics365/fin-ops-core/dev-itpro/lcs-solutions/country-region?context=%2Fdynamics365%2Fcontext%2Ffinance#countryregion-specific-help-content).
- **Ordine cliente con un deposito** – Un cliente crea un ordine cliente nel POS. Il cliente può pagare un deposito per l'ordine, in base alla percentuale di deposito predefinita configurata nella pagina **Ordini cliente** in Commerce headquarters (**Parametri di commercio \> Ordini cliente**). Commerce elabora il pagamento del deposito per l'ordine client come transazione di pagamento anticipato. Quando si registra la transazione, viene creato un giornale di registrazione pagamenti che viene registrato nella pagina **Giustificativo giornale di registrazione**. La casella di controllo **Giustificativo giornale di registrazione per pagamento anticipato** nella scheda **Pagamento** viene selezionata automaticamente per il giornale di registrazione pagamenti. Il pagamento viene liquidato e la fattura cliente viene emessa automaticamente al momento del ritiro o della consegna dell'ordine.
- **Ordini cliente per servizio clienti** - Un rappresentante del servizio clienti del call center crea un ordine cliente per conto di un cliente e l'attributo **pagamento anticipato** è impostato su **Sì** durante l'acquisizione del pagamento.

Commerce esegue le seguenti attività per elaborare un pagamento anticipato:

- **Elabora un pagamento di deposito del conto cliente** – Un pagamento di deposito effettuato da un cliente viene trasferito a Commerce utilizzando un servizio che sincronizza i dati. Commerce crea una transazione di pagamento al dettaglio per il pagamento. Quando si registra la transazione al dettaglio, viene registrato un giornale di cassa o un giornale di registrazione pagamenti cliente. La casella di controllo **Giustificativo giornale di registrazione per pagamento anticipato** nella scheda **Pagamento** della pagina **Giustificativo giornale di registrazione** di Commerce headquarters viene selezionata automaticamente per il giornale di registrazione pagamenti. I pagamenti anticipati non possono essere elaborati se l'importo del pagamento è negativo.
- **Elabora un ordine cliente o un ordine di vendita con un deposito** – Un cliente paga un deposito obbligatorio per un ordine cliente utilizzando Commerce Data Exchange: Servizio in tempo reale. Commerce crea un giornale di registrazione pagamenti cliente o un giornale cassa, a seconda del metodo di pagamento utilizzato dal cliente. La casella di controllo **Giustificativo giornale di registrazione per pagamento anticipato** nella scheda **Pagamento** della pagina **Giustificativo giornale di registrazione** viene selezionata automaticamente per il giornale di registrazione pagamenti in Commerce headquarters. Se un cliente utilizza più metodi di pagamento per effettuare pagamenti parziali, Commerce elabora ogni pagamento parziale, in base al metodo di pagamento utilizzato.

Per le carte di credito e per i portafogli digitali che hanno sottostanti metodi di pagamento con carta di credito, Commerce invia una richiesta di "acquisizione" dopo l'autorizzazione riuscita. (I fondi vengono acquisiti prima che l'ordine cliente venga fatturato.)

Se si annulla un ordine cliente, l'importo del pagamento anticipato viene rimborsato e viene registrato un giornale di registrazione pagamenti rimborso per l'importo del deposito. L'importo del rimborso viene calcolato e registrato in base al metodo di pagamento specificato al momento della registrazione del pagamento del rimborso. Commerce potrebbe applicare una penale di cancellazione, in base alla percentuale che hai impostato nella pagina **Parametri di commercio** in Commerce headquarters.

Se restituisci un ordine cliente, vengono creati un ordine di reso e un giornale di registrazione pagamenti rimborso. Quando si registra l'ordine di reso, Commerce crea un giornale di registrazione pagamenti cliente o un giornale cassa, a seconda del metodo di pagamento utilizzato dal cliente per la transazione originale.
