---
title: Definire il metodo di pagamento del cliente
description: In questo argomento viene illustrato come creare un metodo di pagamento per i pagamenti dei clienti.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a948bf772e55f20c7010101fd11da83940a0b268
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990968"
---
# <a name="establish-customer-method-of-payment"></a>Definire il metodo di pagamento del cliente

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come creare un metodo di pagamento per i pagamenti dei clienti. In questa attività viene utilizzata la società dimostrativa USMF.

1. Nel pannello di navigazione andare a **Moduli > Crediti e riscossioni > Impostazione pagamenti > Metodi di pagamento**.
2. Selezionare **Nuovo**.
3. Nel campo **Metodo di pagamento** immettere un ID per il metodo di pagamento. L'ID relativo al metodo di pagamento viene visualizzato nelle fatture e nei pagamenti, quindi fare in modo che sia abbastanza descrittivo per comprendere il tipo di pagamento registrato e per quale conto bancario.  
4. Nel campo **Descrizione** immettere una descrizione.
5. Selezionare lo stato del pagamento richiesto per la registrazione dei pagamenti. Quando si crea un pagamento cliente, può essere registrato solo quando lo stato di pagamento corrisponde allo stato di pagamento definito in questo campo.  
6. Selezionare la modalità di creazione dei pagamenti dei clienti per le fatture. Questa opzione viene utilizzata solo quando si esegue una proposta di pagamento. Una proposta di pagamento potrebbe essere utilizzata per i pagamenti cliente quando si effettuano addebiti diretti e il pull dei fondi dai conti bancari dei clienti.  
7. Selezionare il tipo di pagamento. Il tipo di pagamento contribuirà a determinare se verrà eseguita una certa convalida sul pagamento.  
8. Selezionare il tipo di conto in cui verranno registrati i pagamenti. In genere per questa opzione verrà selezionato il valore Banca.  
9. Selezionare il conto bancario in cui il pagamento verrà registrato.
10. Immettere il tipo di transazione bancaria per identificare il tipo di pagamento utilizzato dalla banca. Il tipo di transazione bancaria viene utilizzato durante il processo di riconciliazione bancaria e può semplificare la riconciliazione.  
11. Selezionare se il pagamento verrà temporaneamente registrato in un conto provvisorio. Se si desidera provare il periodo fondo di cassa per un pagamento per cancellare la banca, utilizzare la funzionalità Registrazione compensativa. Il pagamento verrà temporaneamente registrato in un conto CoGe finché non cancella la banca, momento in cui il pagamento verrà trasferito nel conto bancario definito in questo campo.  
12. Immettere il conto principale utilizzato per la registrazione provvisoria. Si tratta del conto principale in cui il pagamento verrà temporaneamente registrato se si utilizza la registrazione compensativa.  
13. Utilizzare la scheda **Formato file** per definire l'impostazione dei pagamenti elettronici.
14. Utilizzare la scheda **Controllo pagamenti** per definire i campi obbligatori. Ad esempio, se si richiede che tutti i pagamenti con questo metodo di pagamento vengano depositati, è possibile selezionare tale opzione nella scheda.  
15. Utilizzare la scheda **Attributi di pagamento** per definire gli attributi di pagamento che si desidera utilizzare per il metodo di pagamento.
16. Selezionare **Salva**.

