---
title: " Configurazioni dei pagamenti per rendiconti di vendita al dettaglio"
description: In questa procedura sono illustrate le configurazioni per i metodi di pagamento di punto vendita di commercio che interessano la modalità di creazione e registrazione dei rendiconti.
author: jashanno
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3c8c7678d88b3c01138aa098b8830336885e6445fb41931b19bcda2b95b86b5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712359"
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]