---
title: Impostare gli assegni postdatati
description: In questo articolo viene illustrato come specificare se registrare gli inserimenti nel giornale per gli assegni postdatati e quali giornali di registrazione utilizzare per cancellare le voci e i pagamenti fornitore.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a5ef9aa6b67eb630713dd1f15b2ae49c358edae9
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804184"
---
# <a name="set-up-postdated-checks"></a>Impostare gli assegni postdatati

[!include [banner](../../includes/banner.md)]

In questo articolo viene illustrato come specificare se registrare gli inserimenti nel giornale per gli assegni postdatati e quali giornali di registrazione utilizzare per cancellare le voci e i pagamenti fornitore. È inoltre possibile specificare i conti di compensazione per gli assegni emessi, gli assegni ricevuti e la ritenuta d'acconto. Gli assegni postdatati che sono emessi per effettuare e ricevere pagamenti in una data futura. È possibile specificare se l'assegno deve essere riportato nei libri contabili prima della relativa data di scadenza.



Il ruolo di questa procedura è Tesoriere. Questa procedura utilizza la società dimostrativa USMF.


## <a name="set-up-postdated-checks"></a>Impostare gli assegni postdatati
1. Andare a **Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche**.
2. Fare clic sulla scheda **Assegni postdatati**.
3. Seleziona o deseleziona la casella di controllo **Abilita assegni postdatati**.
4. Selezionare o deselezionare la casella di controllo **Inserimenti nel giornale di registrazione per assegni postdatati**.
5. Nel campo **Conto di compensazione per assegni emessi** specificare i valori desiderati.
6. Nel campo **Conto di compensazione per assegni ricevuti** specificare i valori desiderati.
7. Nel campo **Giornale di registrazione generale per voci di compensazione** immettere un valore.
8. Nel campo **Trasferisci assegni postdatati a questo giornale di registrazione pagamenti fornitore** immettere un valore.
9. Nel campo **Conto di compensazione per ritenuta d'acconto** specificare i valori desiderati.
10. Fare clic su **Salva**.
11. Chiudere la pagina.
12. Andare a **Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento**.
13. Fare clic su **Nuovo**.
14. Digitare un valore nel campo **Metodo di pagamento**.
15. Selezionare l'opzione **Registrazione compensazione assegni postdatati** per indicare che l'importo dell'assegno viene registrato in un conto di compensazione.
16. Nel campo **Tipo di conto** selezionare **Banca**.
    * Il conto di contropartita del metodo di pagamento sarà una banca.  
17. Nel campo **Conto pagamenti** specificare i valori desiderati.
    * Selezionare il conto bancario utilizzato per detrarre l'importo della fattura.  
18. Fare clic su **Salva**.
19. Chiudere la pagina.
> [!NOTE]
> Per poter registrare un assegno postdatato in un conto bancario quando la data della sessione è successiva o uguale alla data di scadenza, è necessario abilitare la funzionalità **Convalida della data di scadenza della registrazione del giornale di registrazione pagamenti con assegni postdatati sul conto bancario**. Questa funzionalità consente di registrare giornali di registrazione pagamenti per fornitori o clienti con assegni postdatati, quando la data della sessione è successiva o uguale alla data di scadenza.
> 
> Quando si imposta il **Metodo di pagamento** (**Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento**), non riempire il campo **Conto provvisorio**. In questo caso, il conto di contropartita viene compilato con il conto bancario, impostato in **Metodo di pagamento**.
>  
> Quando la funzionalità è abilitata e la data della sessione è antecedente alla data di scadenza, viene visualizzato il seguente messaggio di errore durante la registrazione di un giornale di registrazione pagamenti: **La data di scadenza deve essere antecedente o uguale alla data della sessione se il tipo di conto di contropartita è Banca**. Se la funzionalità non è abilitata, è possibile registrare un giornale di registrazione pagamenti con un assegno postdatato quando la data della sessione è inferiore alla data di scadenza.
> Questa funzionalità è disponibile nella versione 10.0.21 o successiva.    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
