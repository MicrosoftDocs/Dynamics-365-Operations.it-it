---
title: EUR-00015 Registrazione dell'ID IVA fornitore
description: In questa procedura viene descritto come aggiungere gli ID registrazione IVA e una partita IVA a un conto fornitore.
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddress, RegNumTaxIdLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 578f961fe1b5e3d06b624b78c278c8314df47f5e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822561"
---
# <a name="eur-00015-registration-of-vendor-vat-id"></a>EUR-00015 Registrazione dell'ID IVA fornitore

[!include [banner](../../includes/banner.md)]

In questa procedura viene descritto come aggiungere gli ID registrazione IVA e una partita IVA a un conto fornitore. Questo processo è analogo per le persone giuridiche e clienti. 

Prima di completare questa procedura è necessario impostare gli ID IVA. Questa procedura si applica a tutti i paesi europei. La procedura è stata creata utilizzando la società di dati dimostrativi DEMF con un indirizzo principale in Germania. Questa procedura è progettata per un amministratore della gestione dei dati, un responsabile della contabilità fornitori, o un responsabile della contabilità clienti. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.

1. Andare a Contabilità fornitori > Fornitori > Tutti i fornitori.
2. Nell'elenco trovare e selezionare il fornitore DE-01001
3. Fare clic su ID registrazione.
4. Scegliere Aggiungi.
5. Selezionare ID IVA.
6. Nel campo Numero di registrazione digitare un valore.
    * Specificare un'ID IVA in Germania per il fornitore selezionato. L'ID deve corrispondere al formato specificato per il tipo di registrazione.  
7. Fare clic sulla scheda Generale.
8. Nel campo Validità immettere una data.
9. Fare clic su Salva.
10. Fare clic su Nuovo.
11. Digitare un valore nel campo Nome o descrizione.
    * Ad esempio, immettere ITA.  
12. Nel campo Paese/regione, immettere o selezionare un valore.
    * Selezionare, ad esempio ITA.  
13. Selezionare Sì nel campo Principale per paese.
14. Fare clic su Salva.
15. Fare clic sulla scheda Panoramica.
16. Scegliere Aggiungi.
17. Nel campo Tipo di registrazione, immettere o selezionare un valore.
    * Selezionare, ad esempio, ID IVA.  
18. Nel campo Numero di registrazione digitare un valore.
    * Ad esempio, specificare un ID IVA in Italia.  L'ID deve avere lo stesso formato del tipo di registrazione.  
19. Fare clic su Salva.
20. Chiudere la pagina.
21. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare, ad esempio, DE-01001.  
22. Nell'elenco fare clic sul collegamento nella riga selezionata.
23. Espandere la sezione Fattura e consegna.
24. Fare clic su Modifica.
25. Nel campo Partita IVA, immettere o selezionare un valore.
26. Fare clic su Salva.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]