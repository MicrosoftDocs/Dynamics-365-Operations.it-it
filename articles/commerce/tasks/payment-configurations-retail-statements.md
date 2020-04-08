---
title: " Configurazioni dei pagamenti per rendiconti di vendita al dettaglio"
description: In questa procedura sono illustrate le configurazioni per i metodi di pagamento di punto vendita di commercio che interessano la modalità di creazione e registrazione dei rendiconti.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 390ccdfde3f9bb93770d456af7532a42e81955a1
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140809"
---
# <a name="payment-configurations-for-retail-statements"></a> Configurazioni dei pagamenti per rendiconti di vendita al dettaglio

[!include [banner](../includes/banner.md)]

In questa procedura sono illustrate le configurazioni per i metodi di pagamento di punto vendita di commercio che interessano la modalità di creazione e registrazione dei rendiconti.

Questa registrazione utilizza la società dimostrativa USRT.

1. Passare a Retail e Commerce > Canali > Punti vendita > Tutti i punti vendita.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nel riquadro azioni, fare clic su Imposta.
5. Fare clic su Metodi di pagamento.
6. Espandere o comprimere la sezione Registrazione.
7. Fare clic su Modifica.
    * Selezionare se gli importi ricevuti per il metodo di pagamento devono essere registrati in un conto CoGe o in un conto bancario.  
    * Selezionare il conto in cui dovranno essere registrati gli importi ricevuti per il metodo di pagamento.  
    * Selezionare un conto per registrare le possibili differenze tra l'importo totale della transazione ricevuto e l'importo conteggiato per il metodo di pagamento.  
    * In questo campo è possibile immettere un importo per verificare se l'importo della differenza deve essere registrato in un altro conto di differenza. È possibile utilizzare questa opzione per tenere traccia delle grandi differenze.  
    * Selezionare un conto per registrare le possibili differenze tra l'importo totale della transazione ricevuto e l'importo conteggiato, quando supera il valore specificato nel campo "Importo massimo di differenza".  
    * Selezionare "Sì" per registrare gli importi di deposito bancario in un conto separato.  
    * In questo campo è possibile selezionare se gli importi di deposito bancario devono essere registrati in un conto CoGe o in un conto bancario.  
    * Selezionare il conto in cui registrare gli importi di deposito bancario.  
    * Selezionare il tipo di transazione bancaria da utilizzare per la registrazione degli importi di deposito bancario nel conto bancario.  
    * Selezionare "Sì" per registrare gli importi di deposito in cassaforte in un conto separato.  
    * Selezionare se gli importi di deposito in cassaforte devono essere registrati nel conto CoGe o nel conto bancario.  
    * Selezionare il conto in cui registrare gli importi di deposito in cassaforte.  
8. Fare clic su Salva.

