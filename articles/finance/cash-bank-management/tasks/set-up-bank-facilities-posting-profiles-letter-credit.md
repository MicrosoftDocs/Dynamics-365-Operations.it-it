---
title: Impostare le linee di credito bancarie e i profili registrazione per la lettera di credito
description: Questa procedura consente di creare una linea di credito bancaria e di registrare un profilo necessari per elaborare le lettere di credito.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7fe5b2ba43c4fcb4855c742bdb6f8209ebd92d68
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779464"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Impostare le linee di credito bancarie e i profili registrazione per la lettera di credito

[!include [banner](../../includes/banner.md)]

Questa procedura consente di creare una linea di credito bancaria e di registrare un profilo necessari per elaborare le lettere di credito. 

In questa attività viene utilizzata la società dimostrativa "USMF".


## <a name="general-ledger-parameter"></a>Parametro di contabilità generale
1. Andare a **Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche**.
2. Espandere la sezione **Documento bancario**.
3. Selezionare l'opzione **Abilita lettera di credito di importazione**.
4. Selezionare l'opzione **Abilita lettera di credito di esportazione**.
5. Fare clic su **Salva**.
6. Chiudere la pagina.

## <a name="create-bank-facility"></a>Creare una linea di credito bancaria
1. Andare a **Gestione cassa e banche > Impostazioni > Linee di credito bancarie**.
2. Fare clic su **Nuovo**.
3. Nel campo **Gruppo di linee di credito** immettere il nome del gruppo di linee di credito bancarie.
4. Nel campo **Descrizione** immettere la descrizione del gruppo di linee di credito bancarie.
5. Fare clic su **Salva**.
6. Fare clic sulla scheda **Tipi di linee di credito**.
7. Fare clic su **Nuovo**.
8. Nel campo **Tipi di linee di credito** immettere un codice univoco.
9. Digitare un valore nel campo **Descrizione**
10. Nel campo **Gruppo di linee di credito** fare clic sul pulsante a discesa per aprire la ricerca.
11. Trovare e selezionare il record desiderato nell'elenco.
12. Nell'elenco fare clic sul collegamento nella riga selezionata.
13. Nel campo **Natura linea di credito** selezionare la natura della linea di credito bancaria.
14. Fare clic su **Salva**.
15. Chiudere la pagina.

## <a name="bank-posting-profile"></a>Profilo di registrazione bancaria
1. Andare a **Gestione cassa e banche > Impostazioni > Profilo di registrazione documenti bancari**.
2. Fare clic su **Nuovo**.
3. Nel campo **Numero conto/gruppo** fare clic sul pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Selezionare il conto principale per la liquidazione.
    * Tale conto viene utilizzato per il calcolo della previsione di cassa.  
7. Nel campo **Conto spese** selezionare il conto per le transazioni di spesa.
8. Nel campo **Conto a margine** selezionare il conto per le transazioni a margine.
    * Su questo conto viene effettuato un addebito quando il margine iniziale viene registrato e accreditato al momento della registrazione del pagamento.  
9. Fare clic su **Salva**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
