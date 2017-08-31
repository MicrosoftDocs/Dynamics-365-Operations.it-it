--- 
title: "Impostare i conti bancari della società per gli addebiti diretti ISO20022"
description: "Questa attività descrive l'impostazione delle informazioni sui conti bancari specifici della società necessarie per la creazione dei file di pagamento cliente."
author: mrolecki
manager: AnnBe
ms.date: 11/14/2016
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 741d8ddca24e5fe083b4ddf775bb7f2d65a56fee
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>Impostare i conti bancari della società per gli addebiti diretti ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa attività descrive l'impostazione delle informazioni sui conti bancari specifici della società necessarie per la creazione dei file di pagamento cliente. In questa procedura viene utilizzato il formato di pagamento in addebito diretto ISO 20022 come esempio. Altri formati possono richiedere informazioni di impostazione aggiuntive come l'ID società o il Codice di ordinamento.



Questa attività è stata creata utilizzando la società di dati dimostrativi DEMF.



Si tratta della seconda di cinque procedure che illustrano il processo di pagamento cliente utilizzando le configurazioni di creazione di report elettronici.


## <a name="set-up-the-iban-and-swift-codes"></a>Impostare i codici IBAN e SWIFT
1. Andare a Gestione banche e di cassa > Conti bancari.
2. Utilizzare il filtro rapido per applicare un filtro al campo Conto bancario in base al valore "DEMF OPER".
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Ad esempio fare clic su 'DEMF OPER' per aprire i dettagli del conto bancario.  
4. Fare clic su Modifica.
5. Espandere o comprimere la sezione Identificazione aggiuntiva.
6. Digitare un valore nel campo IBAN.
    * Ad esempio, immettere 'DE89370400440532013000'.  
7. Digitare un valore nel campo Codice SWIFT.
    * Ad esempio, immettere 'DEUTDEFF'.    Si noti che SWIFT\BIC non è obbligatorio per numerosi formati di pagamento, tuttavia è consigliabile registrarlo per un conto bancario.  
8. Fare clic su Salva.

## <a name="set-up-a-bank-account-for-the-legal-entity"></a>Impostare un conto bancario per la persona giuridica
1. Andare ad Amministrazione organizzazione > Organizzazioni > Persone giuridiche.
2. Fare clic su Modifica.
3. Espandere o comprimere la sezione Informazioni conto bancario.
4. Nel campo Conto bancario fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Ad esempio selezionare il conto bancario "DEMF OPER".  
6. Fare clic su Salva.


