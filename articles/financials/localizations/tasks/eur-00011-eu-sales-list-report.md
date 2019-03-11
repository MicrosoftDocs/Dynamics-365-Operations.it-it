---
title: EUR-00011 - Generare la dichiarazione Elenco vendite UE
description: In questa procedura vengono descritti i passaggi per generare il report elenco vendite UE.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  EUSalesList, EUSalesListSelection, SysQueryForm, SysLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9fcafa2beca5d998b2556ba73e9f3cc2bdd314ba
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "370988"
---
# <a name="eur-00011-generate-the-eu-sales-list-report"></a>EUR-00011 - Generare la dichiarazione Elenco vendite UE

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per generare il report elenco vendite UE. È incluso il trasferimento delle transazioni commerciali intracomunitarie nell'elenco vendite UE e l'esecuzione del report. Questa procedura include inoltre la creazione di una transazione commerciale intracomunitaria per fini dimostrativi. Per ulteriori informazioni sulla dichiarazione elenco vendite UE, inclusi i prerequisiti necessari, vedere la Guida di Dynamics 365 for Finance and Operations.

Questa procedura si applica a tutti i paesi europei. La procedura è stata creata utilizzando la società di dati dimostrativi DEMF e di conseguenza la Germania come paese di esempio. Nella procedura si utilizza anche il Portogallo come paese UE di esempio. Prima di poter completare questa procedura, è necessario configurare la dichiarazione dell'elenco vendite UE.

Questa procedura è destinata ai contabili.


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a>Creare una transazione di vendita intracomunitaria per fini dimostrativi
1. Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente digitare 'PRT-001'.
4. Fare clic su OK.
5. Nel campo Numero articolo digitare "D0001".
6. Espandere la sezione Dettagli riga.
7. Fare clic sulla scheda Impostazioni.
8. Nel campo Fascia IVA articoli digitare 'FULL'.
9. Fare clic su Aggiungi riga.
10. Nel campo Numero articolo digitare "D0003".
11. Nel campo Fascia IVA articoli digitare 'RED'.
12. Fare clic su Salva.
13. Nel riquadro azioni fare clic su Fattura.
14. Fare clic su Fattura.
15. Espandere la sezione Parametri.
16. Nel campo Quantità selezionare "Tutto".
17. Espandere la sezione Impostazione.
18. Nel campo Data fattura impostare la data su '01/11/2016'.
19. Fare clic su OK.
20. Fare clic su OK.

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a>Trasferire le transazioni commerciali intracomunitarie nell'elenco vendite UE
1. Passare a Imposta > Dichiarazioni > Commercio estero > Elenco vendite UE.
2. Fare clic su Trasferisci.
3. Selezionare Sì nel campo Articolo per trasferire le transazioni articolo.
4. Selezionare Sì nel campo Servizio per trasferire le transazioni servizio.
    * È inoltre possibile specificare i filtri aggiuntivi per le transazioni di commercio intracomunitarie da trasferire.  
5. Fare clic su Trasferisci.
    * Verificare che la transazione di vendita intracomunitaria venga trasferita correttamente nell'elenco vendite UE.  

## <a name="generate-the-eu-sales-list-report"></a> Genera report elenco vendite UE
1. Fare clic su Dichiarazione.
2. Nel campo Periodo di reporting selezionare 'Mensile'.
3. Nel campo Data iniziale impostare la data su '01/01/2016'.
4. Selezionare Sì nel campo Genera file.
5. Selezionare Sì nel campo Genera report.
6. Nel campo Nome file digitare 'EUSalesList'.
7. Nel campo Nome file report digitare 'EUSalesList'.
8. Nel campo ID registrazione elenco vendite UE, immettere '123'.
    * Questo campo è disponibile solo per la Germania.  
    * È inoltre possibile specificare i filtri aggiuntivi per le transazioni di commercio intracomunitarie da includere nel report.  
9. Fare clic su OK.
    * Verificare che le finestre popup vengano visualizzate per confermare che il file e il report di controllo vengano scaricati.  

## <a name="mark-eu-sales-list-lines-as-reported"></a>Contrassegnare le righe dell'elenco vendite UE come dichiarate
1. Fare clic su Contrassegna.
2. Fare clic su Contrassegna come dichiarato.
3. Nell'elenco, selezionare la riga per il campo Data fattura.
4. Nel campo Criteri, immettere '01/01/2016..01/31/2016'.
5. Nell'elenco, selezionare la riga per il campo Stato relazione.
6. Nel campo Criteri, selezionare 'Incluso'.
    * È inoltre possibile specificare i filtri aggiuntivi per le transazioni di commercio intracomunitarie da contrassegnare come dichiarate.  
7. Fare clic su OK.
8. Selezionare 'Dichiarato' nel campo Selezione.

## <a name="mark-eu-sales-list-lines-as-closed"></a>Contrassegnare le righe dell'elenco vendite UE come chiuse
1. Fare clic su Contrassegna.
2. Fare clic su Contrassegna come chiuso.
3. Nell'elenco, contrassegnare la riga per il campo Data fattura.
4. Nel campo Criteri, immettere '01/01/2016..01/31/2016'.
5. Nell'elenco, contrassegnare la riga per il campo Stato relazione.
6. Nel campo Criteri, selezionare 'Dichiarato'.
    * È inoltre possibile specificare i filtri aggiuntivi per le transazioni di commercio intracomunitarie da contrassegnare come chiuse.  
7. Fare clic su OK.
8. Selezionare 'Chiuso' nel campo Selezione.

