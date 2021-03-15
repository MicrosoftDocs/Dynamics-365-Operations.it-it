---
title: Specificare il tasso di cambio incrociato
description: Questo argomento include informazioni sui tassi di cambio incrociato in Microsoft Dynamics 365 Finance.
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 317cad877cec4d9f02f53762af65f0b226d0aad6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979390"
---
# <a name="specify-the-cross-rate"></a>Specificare il tasso di cambio incrociato

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato lo scopo di un tasso di cambio incrociato e come specificare il tasso di cambio incrociato quando viene liquidato un pagamento con una fattura. Utilizzare un tasso di cambio incrociato quando sono applicabili tutti i criteri seguenti: 
-   Si liquida un pagamento con una fattura. 
-   La riga di pagamento e la riga fattura utilizzano valute diverse. 
-   Nessuna valuta è quella di contabilizzazione. 

Il tasso di cambio incrociato non viene utilizzato per calcolare la conversione di valuta di transazione di pagamento nella valuta di contabilizzazione pagamento. I tassi di cambio delle tabelle del tasso di cambio vengono invece recuperati per calcolare il valore dell'importo valuta della transazione di pagamento e dell'importo nella valuta di contabilizzazione pagamento. 

Ad esempio, la valuta di contabilizzazione è USD, la valuta della fattura è CAD e la valuta del pagamento è EUR. Il tasso di cambio incrociato consente di immettere un tasso di cambio per passare direttamente dal CAD all'EUR senza che sia necessario passare attraverso USD. Al momento della selezione dei una fattura e di un pagamento primario è possibile immettere un tasso di cambio incrociato per la riga di fattura. Questo tasso è il tasso di cambio tra le valute di queste transazioni alla data della liquidazione.

1.  Passare a una delle pagine seguenti:
- **Contabilità clienti > Comune > Clienti > Tutti i clienti** 
- **Contabilità fornitori > Comune > Fornitori > Tutti i fornitori** 
- **Approvvigionamento > Comune > Fornitori > Tutti i fornitori**
2.  Selezionare il cliente o il fornitore di cui si desidera compensare le transazioni aperte. 
3.  Per un cliente, nella pagina elenco **Tutti i clienti**, passare a **Raccolta > Liquida transazioni aperte**. Per un fornitore, nella pagina elenco **Tutti i fornitori**, passare a **Fattura > Liquida transazioni aperte**. 
4.  Selezionare la transazione corrispondente al pagamento primario, quindi fare clic su **Contrassegna pagamento**. Verrà selezionata la casella di controllo nella colonna **Contrassegna** e verrà visualizzata un'icona informativa nella colonna **Pagamento primario**. 
5.  Nel campo **Tasso di cambio incrociato**, immettere il tasso di cambio tra la valuta della fattura e la valuta del pagamento alla data di liquidazione. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]