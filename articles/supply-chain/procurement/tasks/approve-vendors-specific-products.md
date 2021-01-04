---
title: Approvare fornitori per prodotti specifici
description: Questa procedura mostra come approvare i fornitori per prodotti specifici.
author: mkirknel
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fafa2f7da5575206d452f31bb297790874369dfd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431094"
---
# <a name="approve-vendors-for-specific-products"></a>Approvare fornitori per prodotti specifici

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come approvare i fornitori per prodotti specifici. Ciò consente di controllare quali fornitori possono essere utilizzati quando il prodotto viene aggiunto a un ordine fornitore. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. In genere questa attività sarà svolta da un responsabile acquisti.

1. Nel pannello di navigazione andare a **Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Espandere la Scheda dettaglio **Acquisti**. Se nel campo **Fornitore** è visualizzato un fornitore primario, è necessario aggiungere questo fornitore come fornitore approvato attenendosi ai passaggi che seguono. Prendere nota del numero fornitore, se è visualizzato.  
5. Nel riquadro azioni, fare clic su **Acquisti**.
6. Fare clic su **Impostazioni**.
7. Scegliere **Aggiungi**.
8. Nel campo Fornitore immettere o selezionare un valore. Selezionare il fornitore approvato. Almeno una delle righe deve essere il fornitore primario se ve ne era uno nel record del prodotto. Se in precedenza si è preso nota del numero fornitore, selezionarlo in questo campo.  
9. Nel campo **Scadenza** immettere una data. Selezionare una data di qualche mese prima.  
10. Scegliere **Aggiungi**.
11. Nel campo **Fornitore** immettere o selezionare un valore.
12. Nel campo **Scadenza** immettere una data. Selezionare una data diversa dalla data di scadenza precedente.  
13. Chiudere la pagina.
14. Nel riquadro azioni, fai clic su **Fornitori approvati**.
15. Nel campo **Scadenza** immettere una data. Questa data funge da filtro, pertanto è possibile visualizzare chi sono i fornitori approvati, fino a una determinata data.  
16. Chiudere la pagina.
17. Nel riquadro azioni, fai clic su **Periodo di validità**.
18. Nel campo **Mostra fornitori con scadenza entro** immettere una data. È possibile utilizzare questa pagina per identificare i fornitori il cui stato di approvazione scadrà dopo una determinata data.  
19. Chiudere la pagina.
20. Fare clic su **Modifica**.
21. Nel campo **Metodo di verifica fornitore approvato** selezionare un'opzione. Questo campo consente di selezionare i criteri per le operazioni da verificare se il prodotto viene aggiunto a una riga ordine fornitore in cui il fornitore non è un fornitore approvato.  
22. Fare clic su **Salva**.
23. Chiudere la pagina.
24. Chiudere la pagina.
25. Nel pannello di navigazione andare a **Moduli > Approvvigionamento > Fornitori > Relazioni fornitore/articolo > Elenco fornitori approvati per articolo**. Questa pagina offre una panoramica di tutti i prodotti e i fornitori approvati.  
26. Chiudere la pagina.
27. Nel pannello di navigazione andare a **Moduli > Approvvigionamento > Fornitori > Tutti i fornitori**. È inoltre possibile iniziare da un fornitore e quindi accedere all'elenco dei prodotti approvati per quel conto fornitore.  
28. Nell'elenco trovare e selezionare il record desiderato.
29. Nel riquadro azioni, fai clic su **Approvvigionamento**.
30. Fare clic su **Elenco fornitori approvati per fornitore**.
31. Chiudere la pagina.
32. Chiudere la pagina.

