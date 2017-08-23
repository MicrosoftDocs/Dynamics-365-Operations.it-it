--- 
title: Impostare i clienti e i conti bancari dei clienti per gli addebiti diretti ISO20022
description: "Questa attività descrive l'impostazione di un conto bancario cliente e un mandato di addebito diretto cliente necessari per generare il file di pagamento cliente come addebito diretto ISO20022."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7aac1af99f2b5a7b1a123a8e3d3d6ddcaaa39b8d
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a>Impostare i clienti e i conti bancari dei clienti per gli addebiti diretti ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa attività descrive l'impostazione di un conto bancario cliente e un mandato di addebito diretto cliente necessari per generare il file di pagamento cliente come addebito diretto ISO20022. A seconda dei formati di pagamento del cliente impostati, informazioni aggiuntive, non coperte in questa procedura, possono essere necessarie per un cliente o conto bancario cliente. 

Questa attività è stata creata utilizzando la società di dati dimostrativi DEMF con l'indirizzo principale della persona giuridica in Germania.



Si tratta della quarta di cinque procedure che illustrano il processo di pagamento cliente utilizzando le configurazioni di creazione di report elettronici.


## <a name="set-up-a-customer-bank-account"></a>Impostare un conto bancario cliente
1. Andare a Contabilità clienti > Clienti > Tutti i clienti.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, applicare un filtro al campo Conto in base al valore "DE-010".
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nel riquadro azioni fare clic su Cliente.
5. Fare clic su Conti bancari.
6. Fare clic su Nuovo.
7. Digitare un valore nel campo Conto bancario.
8. Digitare un valore nel campo Nome.
    * Immettere ad esempio 'EUR bank'.  
9. Nel campo gruppi bancari immettere o selezionare un valore.
10. Digitare un valore nel campo IBAN.
    * Ad esempio, immettere 'DE36200400000628808808'.  
11. Digitare un valore nel campo Codice SWIFT.
    * Ad esempio, immettere "COBADEFFXXX".  Si noti che SWIFT\BIC non è obbligatorio per numerosi formati di pagamento, tuttavia è consigliabile registrarlo per un conto bancario.  
12. Fare clic su Salva.
13. Chiudere la pagina.
14. Fare clic su Modifica.
15. Espandere la sezione Impostazioni predefinite pagamento.
16. Nel campo Conto bancario immettere o selezionare un valore.

## <a name="add-a-direct-debit-mandate"></a>Aggiungere un mandato di addebito diretto
1. Espandere la sezione Mandati di addebito diretto.
2. Scegliere Aggiungi.
3. Nel campo Conto bancario del creditore immettere o selezionare un valore.
    * Selezionare, ad esempio DEMF OPER.  
4. Immettere una data nel campo Data di firma.
5. Fare clic su Sì per confermare l'aggiornamento della data.
6. Nel campo Luogo di firma immettere o selezionare un valore.
7. Nel campo Numero di pagamenti previsto immettere un numero
8. Fare clic su OK.
9. Fare clic su Salva.


