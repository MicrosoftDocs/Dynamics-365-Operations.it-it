--- 
title: Definire il metodo di pagamento del cliente
description: Creare un metodo di pagamento per i pagamenti cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: bfafcccb12112ca7cceefb65be3f942bfc307751
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="establish-customer-method-of-payment"></a>Definire il metodo di pagamento del cliente

[!include[task guide banner](../../includes/task-guide-banner.md)]

Creare un metodo di pagamento per i pagamenti cliente. In questa attività viene utilizzata la società dimostrativa USMF.

1. Andare a Contabilità clienti > Impostazione pagamenti > Metodi di pagamento.
2. Fare clic su Nuovo.
3. Nel campo Metodo di pagamento immettere un ID per il metodo di pagamento.
    * L'ID relativo al metodo di pagamento viene visualizzato nelle fatture e nei pagamenti, quindi fare in modo che sia abbastanza descrittivo per comprendere il tipo di pagamento registrato e per quale conto bancario.  
4. Nel campo Descrizione immettere una descrizione.
5. Selezionare lo stato del pagamento richiesto per la registrazione dei pagamenti.
    * Quando si crea un pagamento cliente, può essere registrato solo quando lo stato di pagamento corrisponde allo stato di pagamento definito in questo campo.  
6. Selezionare la modalità di creazione dei pagamenti dei clienti per le fatture.
    * Questa opzione viene utilizzata solo quando si esegue una proposta di pagamento. Una proposta di pagamento potrebbe essere utilizzata per i pagamenti cliente quando si effettuano addebiti diretti e il pull dei fondi dai conti bancari dei clienti.  
7. Selezionare il tipo di pagamento.
    * Il tipo di pagamento contribuirà a determinare se verrà eseguita una certa convalida sul pagamento.  
8. Selezionare il tipo di conto in cui verranno registrati i pagamenti.
    * In genere per questa opzione verrà selezionato il valore Banca.  
9. Selezionare il conto bancario in cui il pagamento verrà registrato.
10. Immettere il tipo di transazione bancaria per identificare il tipo di pagamento utilizzato dalla banca.
    * Il tipo di transazione bancaria viene utilizzato durante il processo di riconciliazione bancaria e può semplificare la riconciliazione.  
11. Selezionare se il pagamento verrà temporaneamente registrato in un conto provvisorio.
    * Se si desidera provare il periodo fondo di cassa per un pagamento per cancellare la banca, utilizzare la funzionalità Registrazione compensativa. Il pagamento verrà temporaneamente registrato in un conto CoGe finché non cancella la banca, momento in cui il pagamento verrà trasferito nel conto bancario definito in questo campo.  
12. Immettere il conto principale utilizzato per la registrazione provvisoria.
    * Si tratta del conto principale in cui il pagamento verrà temporaneamente registrato se si utilizza la registrazione compensativa.  
13. Utilizzare la scheda Formato file per definire l'impostazione dei pagamenti elettronici.
14. Utilizzare la scheda Controllo pagamenti per definire i campi obbligatori.
    * Ad esempio, se si richiede che tutti i pagamenti con questo metodo di pagamento vengano depositati, è possibile selezionare tale opzione nella scheda.  
15. Utilizzare la scheda Attributi di pagamento per definire gli attributi di pagamento che si desidera utilizzare per il metodo di pagamento.
16. Fare clic su Salva.


