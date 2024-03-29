---
title: Impostare i conti bancari della società per i bonifici ISO20022
description: Questa procedura descrive come impostare le informazioni sui conti bancari specifici della società necessarie per la generazione del file di pagamento.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a3b3b5ce9d7e24b2b7d3f76e4d770968df897b546df507ba9e3bde5aeac91715
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780772"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a>Impostare i conti bancari della società per i bonifici ISO20022

[!include [banner](../../includes/banner.md)]

Questa procedura descrive come impostare le informazioni sui conti bancari specifici della società necessarie per la generazione del file di pagamento. Si imposteranno le informazioni richieste per generare il formato di bonifico ISO 20022 ma in base al formato potrebbero essere necessarie altre informazioni, ad esempio l'ID società o il Codice di ordinamento. 

La società di dati dimostrativi utilizzata per creare questa procedura è DEMF.

Si tratta della seconda procedura di cinque, che illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="set-up-iban-and-swift-code"></a>Impostare i codici SWIFT e IBAN
1. Andare a Gestione banche e di cassa > Conti bancari.
2. Utilizzare il filtro rapido per applicare un filtro al campo Conto bancario in base al valore "DEMF OPER".
3. Fare clic su DEMF OPER per aprire i dettagli del conto bancario.
4. Fare clic su Modifica.
5. Espandere la sezione Identificazione aggiuntiva.
6. Nel campo IBAN digitare "DE89370400440532013000".
7. Nel campo Codice SWIFT digitare "DEUTDEFF".
    * Si noti che SWIFT\BIC non è necessario per numerosi formati di pagamento, tuttavia è consigliabile registrarli per un conto bancario.  
8. Fare clic su Salva.

## <a name="set-up-bank-account-for-the-legal-entity"></a>Impostare un conto bancario per la persona giuridica
1. Andare ad Amministrazione organizzazione > Organizzazioni > Persone giuridiche.
2. Fare clic su Modifica.
3. Espandere la sezione Informazioni conto bancario.
4. Nel campo Conto bancario immettere o selezionare un valore.
5. Fare clic su Salva.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]