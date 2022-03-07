---
title: Impostare un formato per la distinta di pagamento per le fatture di progetto
description: Le aziende generalmente allegano le distinte di pagamento stampate alle fatture per comodità dei clienti e per fornire un riferimento di pagamento per la registrazione e la liquidazione.
author: EvgenyPopovMBS
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OMLegalEntity, CustFormletterParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb0d1d95013b3eac3131064992920da5fa9bea5a1f6d554e6be1d5006a9b21fb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732902"
---
# <a name="set-up-payment-slip-format-for-project-invoices"></a>Impostare un formato per la distinta di pagamento per le fatture di progetto

[!include [banner](../../includes/banner.md)]

Le aziende generalmente allegano le distinte di pagamento stampate alle fatture per comodità dei clienti e per fornire un riferimento di pagamento per la registrazione e la liquidazione. La distinta di pagamento può essere utilizzata per fatture di progetti o servizi, lettere di sollecito, note d'interesse ed estratti conto, oltre che per fatture di vendita e fatture a testo libero. Per elaborare le distinte di pagamento, impostare innanzitutto il numero di identificazione creditore e i formati degli allegati delle distinte di pagamento.

Questa procedura utilizza la società dimostrativa DEMF. 

Questa funzionalità è disponibile per le persone giuridiche il cui indirizzo principale è in Danimarca.


## <a name="set-up-a-creditor-id-number"></a>Impostare un numero ID creditore
1. Andare ad Amministrazione organizzazione > Organizzazioni > Persone giuridiche.
2. Espandere o comprimere la sezione Informazioni conto bancario.
3. Fare clic su Modifica.
4. Digitare un valore nel campo ID creditore IF.
5. Fare clic su Salva.
6. Chiudere la pagina.

## <a name="set-up-a-payment-slip-format-for-invoices-notes-letters-and-statements"></a>Impostare un formato per la distinta di pagamento per fatture, note, lettere e rendiconti
1. Passare a Contabilità clienti > Impostazioni > Moduli > Impostazione moduli.
2. Fare clic sulla scheda Fattura.
3. Nel campo Allegato pagamento associato su fattura cliente, selezionare un'opzione.
    * Nessuno: non stampare una distinta di pagamento. Scegliere questa opzione se l'importo del pagamento è in una valuta diversa dalla corona danese (DKK).   FIK 751: stampare una distinta di pagamento FIK 751 se si desidera scrivere manualmente l'importo del pagamento e la data di scadenza nella distinta di pagamento.   FIK 752: stampare una distinta di pagamento FIK 752 se si desidera utilizzare una distinta di pagamento generata dal computer con importo di pagamento e data di scadenza prestampati.  
4. Fare clic su Salva.
5. Fare clic sulla scheda Fattura a testo libero.
6. Nel campo Allegato pagamento associato su fattura a testo libero, selezionare un'opzione.
    * Nessuno: non stampare una distinta di pagamento. Scegliere questa opzione se l'importo del pagamento è in una valuta diversa dalla corona danese (DKK).   FIK 751: stampare una distinta di pagamento FIK 751 se si desidera scrivere manualmente l'importo del pagamento e la data di scadenza nella distinta di pagamento.   FIK 752: stampare una distinta di pagamento FIK 752 se si desidera utilizzare una distinta di pagamento generata dal computer con importo di pagamento e data di scadenza prestampati.  
7. Fare clic su Salva.
8. Fare clic sulla scheda Nota d'interesse.
9. Nel campo Allegato pagamento associato su nota d'interesse, selezionare un'opzione.
    * Nessuno: non stampare una distinta di pagamento. Scegliere questa opzione se l'importo del pagamento è in una valuta diversa dalla corona danese (DKK).   FIK 751: stampare una distinta di pagamento FIK 751 se si desidera scrivere manualmente l'importo del pagamento e la data di scadenza nella distinta di pagamento.   FIK 752: stampare una distinta di pagamento FIK 752 se si desidera utilizzare una distinta di pagamento generata dal computer con importo di pagamento e data di scadenza prestampati.  
10. Fare clic su Salva.
11. Fare clic sulla scheda Lettera di sollecito.
12. Nel campo Allegato pagamento associato su lettera di sollecito, selezionare un'opzione.
    * Nessuno: non stampare una distinta di pagamento. Scegliere questa opzione se l'importo del pagamento è in una valuta diversa dalla corona danese (DKK).   FIK 751: stampare una distinta di pagamento FIK 751 se si desidera scrivere manualmente l'importo del pagamento e la data di scadenza nella distinta di pagamento.   FIK 752: stampare una distinta di pagamento FIK 752 se si desidera utilizzare una distinta di pagamento generata dal computer con importo di pagamento e data di scadenza prestampati.  
13. Fare clic su Salva.
14. Fare clic sulla scheda Estratto conto.
15. Nel campo Allegato pagamento associato su estratto conto, selezionare un'opzione.
    * Nessuno: non stampare una distinta di pagamento. Scegliere questa opzione se l'importo del pagamento è in una valuta diversa dalla corona danese (DKK).   FIK 751: stampare una distinta di pagamento FIK 751 se si desidera scrivere manualmente l'importo del pagamento e la data di scadenza nella distinta di pagamento.   FIK 752: stampare una distinta di pagamento FIK 752 se si desidera utilizzare una distinta di pagamento generata dal computer con importo di pagamento e data di scadenza prestampati.  
16. Fare clic su Salva.
17. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]