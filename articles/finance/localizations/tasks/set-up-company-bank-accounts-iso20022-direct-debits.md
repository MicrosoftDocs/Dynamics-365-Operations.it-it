---
title: Impostare i conti bancari della società per gli addebiti diretti ISO20022
description: Questa attività descrive l'impostazione delle informazioni sui conti bancari specifici della società necessarie per la creazione dei file di pagamento cliente.
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
ms.openlocfilehash: a0f8ac369bb6b9a7a0f21c23aaddab2601ae3f8f37e2427cbb10b5509a7a2f23
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768719"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>Impostare i conti bancari della società per gli addebiti diretti ISO20022

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]