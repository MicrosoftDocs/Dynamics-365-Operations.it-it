---
title: Impostare gli assegni postdatati
description: In questo argomento viene illustrato come specificare se registrare gli inserimenti nel giornale per gli assegni postdatati e quali giornali di registrazione utilizzare per cancellare le voci e i pagamenti fornitore.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b677056f11a8733bf90f18110b8ee47f6447503b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976293"
---
# <a name="set-up-postdated-checks"></a>Impostare gli assegni postdatati

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come specificare se registrare gli inserimenti nel giornale per gli assegni postdatati e quali giornali di registrazione utilizzare per cancellare le voci e i pagamenti fornitore. È inoltre possibile specificare i conti di compensazione per gli assegni emessi, gli assegni ricevuti e la ritenuta d'acconto. Gli assegni postdatati che sono emessi per effettuare e ricevere pagamenti in una data futura. È possibile specificare se l'assegno deve essere riportato nei libri contabili prima della relativa data di scadenza.



Il ruolo di questa procedura è Tesoriere. Questa procedura utilizza la società dimostrativa USMF.


## <a name="set-up-postdated-checks"></a>Impostare gli assegni postdatati
1. Andare a Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche.
2. Fare clic sulla scheda Assegni postdatati.
3. Selezionare o deselezionare la casella di controllo Abilita assegni postdatati.
4. Selezionare o deselezionare la casella di controllo Inserimenti nel giornale di registrazione per assegni postdatati.
5. Nel campo Conto di compensazione per assegni emessi specificare i valori desiderati.
6. Nel campo Conto di compensazione per assegni ricevuti specificare i valori desiderati.
7. Nel campo Giornale di registrazione generale per voci di compensazione immettere un valore.
8. Nel campo Trasferisci assegni postdatati a questo giornale di registrazione pagamenti fornitore immettere un valore.
9. Nel campo Conto di compensazione per ritenuta d'acconto specificare i valori desiderati.
10. Fare clic su Salva.
11. Chiudere la pagina.
12. Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.
13. Fare clic su Nuovo.
14. Digitare un valore nel campo Metodo di pagamento.
15. Selezionare l'opzione Registrazione compensazione assegni postdatati per indicare che l'importo dell'assegno viene registrato in un conto di compensazione.
16. Nel campo Tipo di conto selezionare "Banca".
    * Il conto di contropartita del metodo di pagamento sarà una banca.  
17. Nel campo Conto pagamenti specificare i valori desiderati.
    * Selezionare il conto bancario utilizzato per detrarre l'importo della fattura.  
18. Fare clic su Salva.
19. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]