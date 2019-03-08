---
title: Trasferire transazioni a Intrastat
description: Questa procedura illustra come impostare i parametri Intrastat e trasferire le transazioni a Intrastat.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategory, UnitOfMeasureLookup, ProcCategoryAddCommodityCode, EcoResProductDetailsExtended, IntrastatCommodityLookup, IntrastatTransactionCode, IntrastatParameters, DeliveryMode, MarkupTable, SalesTableListPage, SalesCreateOrder, SalesTable, MarkupTrans, SalesEditLines,  Intrastat, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13cc9dc2119ad3dc85d580e92edee7bb9ef2075c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "370984"
---
# <a name="transfer-transactions-to-the-intrastat"></a>Trasferire transazioni a Intrastat

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura illustra come impostare i parametri Intrastat e trasferire le transazioni a Intrastat. Questa procedura è stata creata utilizzando la società di dati dimostrativi DEMF.


## <a name="create-new-and-update-existing-commodity-code"></a>Creare un nuovo codice voce doganale e aggiornarne uno esistente
1. Scegliere Gestione informazioni sul prodotto > Impostazioni > Categorie e attributi > Gerarchie di categorie.
2. Nell'elenco trovare o selezionare il record "Codici voci doganali Intrastat".
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nella struttura selezionare "un record".
    * Ad esempio, selezionare "Intrastat\Altoparlante".  
5. Fare clic su Modifica.
6. Espandere la sezione Commercio estero.
7. Nel campo Unità aggiuntive immettere o selezionare un valore.
    * Selezionare, ad esempio, "pz".  
8. Selezionare Sì nel campo Peso non applicabile.
9. Nella struttura selezionare "Intrastat".
10. Fare clic su nodo Nuova categoria.
11. Nel campo Nome immettere il nome della voce doganale.
    * Ad esempio, immettere "Altra merce".  
12. Nel campo Codice immettere il codice voce doganale.
    * Ad esempio, digitare "995 00 00".  
13. Digitare un valore nel campo Nome descrittivo.
    * Ad esempio, digitare "Altro".  
14. Fare clic su Salva.
15. Chiudere la pagina.

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a>Assegnare il codice voce doganale alla gerarchia di prodotti e al prodotto rilasciato
1. Utilizzare il filtro rapido per trovare i record. Ad esempio, applicare un filtro al campo Nome in base al valore "vendite".
2. Nell'elenco fare clic sul collegamento nella riga selezionata.
3. Nella struttura espandere "un nodo di categoria".
    * Ad esempio, espandere "Gerarchia di vendita\Audio home".  
4. Nella struttura selezionare "la categoria da assegnare al codice voce doganale".
    * Ad esempio, selezionare "Gerarchia di vendita\Audio home\Altoparlanti".  
5. Espandere la sezione Codici voce doganale.
6. Scegliere Aggiungi.
7. Nel campo Seleziona gerarchia selezionare "Intrastat".
8. Nell'elenco trovare e selezionare il codice voce doganale.
    * Ad esempio, selezionare "Altoparlante 920 20 34".  
9. Fare clic su SelectCodes.
10. Fare clic su OK.
11. Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.
12. Nell'elenco selezionare il prodotto rilasciato che verrà assegnato al codice voce doganale.
    * Selezionare, ad esempio, "D0001".  
13. Fare clic su Modifica.
14. Espandere la sezione Commercio estero.
15. Nel campo Voce doganale immettere il codice voce doganale.
    * Ad esempio, selezionare il valore "Altoparlante 920 20 34".    
16. Nel campo Perc. spese immettere un numero.
    * Ad esempio, immettere "3".  
17. Nel campo Paese immettere o selezionare un paese di origine
    * Selezionare, ad esempio, "AUT".  
18. Espandere la sezione Gestione articoli.
19. Immettere un peso in kg. nel campo Peso netto.
    * Ad esempio, immettere "2,5".  
20. Fare clic su Salva.

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a>Impostare i codici transazione Intrastat e i parametri per il commercio estero
1. Passare a Imposta > Impostazione > Commercio estero > Codici transazioni
2. Fare clic su Nuovo.
3. Nel campo Codice transazione digitare un valore.
    * Ad esempio, impostare "21" per il codice transazione utilizzato come reso.  
4. Nel campo Nome digitare il nome del codice transazione.
    * Ad esempio, immettere "Reso".  
5. Selezionare un'opzione nel campo Importo statistico.
    * Ad esempio, selezionare "Vuoto" che indica che il valore statistico da dichiarare per le transazioni con il codice transazione "21" sarà sempre zero.  
6. Passare a Imposta > Impostazione > Commercio estero > Parametri per il commercio estero
7. Nel campo Codice transazione immettere o selezionare un valore.
    * Ad esempio, selezionare "11".  
8. Nel campo Nota di accredito immettere o selezionare un valore.
    * Questo valore identifica anche il reso fisico. La nota di accredito per il reso fisico verrà trasferita nel giornale di registrazione Intrastat con la direzione opposta. Ad esempio, il reso di arrivo viene trasferito come spedizione.   In caso contrario, la nota di accredito viene considerata una correzione e viene trasferita con la stessa direzione e segno opposto. Ad esempio, la correzione di arrivo viene trasferita come arrivo con importo negativo e il flag attivo è impostato su "Correzione".  
9. Espandere la sezione Trasferimento.
10. Selezionare Sì nel campo Articoli con codice voce doganale.
    * Selezionare questa opzione per trasferire solo le transazioni con un codice di voce doganale assegnato. Le transazioni senza un codice di voce doganale non verranno trasferite a Intrastat.  
11. Nel campo Trasferisci se è soddisfatto il criterio per selezionare un'opzione.
    * Ad esempio, selezionare "Uno di quelli selezionati".  
12. Espandere la sezione Gerarchia di codici di voce doganale.
13. Fare clic sulla scheda Proprietà paese.
14. Fare clic su Nuovo.
15. Nel campo Paese/regione, immettere o selezionare un valore.
    * Ad esempio, selezionare il valore "FRA".  
16. Nel campo Codice Intrastat immettere il codice ISO del paese.
    * Ad esempio, digitare "FR".  
17. Nel campo Tipo di paese selezionare 'UE'.
18. Fare clic sulla scheda Sequenze numeriche.

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a>Impostare le modalità di consegna e le regole per l'inclusione delle spese in Intrastat
1. Passare a Vendite e marketing > Impostazione > Distribuzione > Modi di consegna
2. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare, ad esempio, "20 via aerea".  
3. Espandere la sezione Commercio estero.
4. Fare clic su Modifica.
5. Nel campo Trasporto immettere o selezionare un valore.
    * Ad esempio, selezionare "02".  
6. Passare a Contabilità clienti > Impostazione spese > Codice spese.
7. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare il campo Codice spese in base al valore "spese di trasporto".
8. Espandere la sezione Commercio estero.
9. Fare clic su Modifica.
10. Selezionare Sì nel campo Valore fattura Intrastat.
    * L'importo verrà trasferito nel campo Spese fattura e verrà compendiato con l'importo trasferito nel campo Importo fattura.    Selezionare Sì nel campo Valore statistico Intrastat se l'importo delle modifiche deve essere trasferito nel campo Spese statistiche e compendiato con Importo statistico.  

## <a name="sell-products-for-eu-customers"></a>Vendere prodotti per i clienti UE
1. Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente selezionare un cliente UE.
    * Ad esempio, selezionare "Litware Retail DE-012".  
4. Espandere la sezione Consegna.
5. Nel campo Modalità di consegna immettere o selezionare un valore.
    * Selezionare, ad esempio, "20 via aerea".  
6. Fare clic su OK.
7. Posizionare il cursore nella prima riga di righe di ordine cliente.
8. Nel campo Numero di articoli immettere o selezionare un valore.
    * Selezionare, ad esempio, "D001".  
9. Espandere la sezione Dettagli riga.
10. Fare clic sulla scheda Commercio estero.
    * Il trasporto viene compilato automaticamente dalla Modalità di consegna scelta.  
11. Nel campo Porto immettere o selezionare un valore.
12. Fare clic su Dati finanziari.
    * In base alle impostazioni, questo importo verrà incluso nel valore di fattura Intrastat.  
13. Fare clic su Gestisci spese.
14. Nel campo Codice spese immettere o selezionare un valore.
    * Selezionare, ad esempio, "SPESE DI TRASPORTO".  
15. Selezionare la casella di controllo Conserva.
16. Nel campo Valore spese immettere un numero.
    * Ad esempio, immettere "10".  
17. Fare clic su Salva.
18. Chiudere la pagina.
19. Nel riquadro azioni fare clic su Fattura.
20. Fare clic su Fattura.
21. Espandere la sezione Parametri.
22. Nel campo Quantità selezionare "Tutto".
23. Espandere la sezione Impostazione.
24. Immettere una data nel campo Data fattura.
    * Ad esempio, immettere "31-01-2015".  
25. Fare clic su OK.
26. Fare clic su OK.
27. Chiudere la pagina.
28. Fare clic su Nuovo.
29. Nel campo Conto cliente selezionare un cliente UE.
    * Ad esempio, selezionare "DE-013 Trey Wholesales".  
30. Fare clic su OK.
31. Nel campo Numero di articoli immettere o selezionare un valore.
    * Selezionare, ad esempio, "D0001".  
32. Fare clic su Salva.
33. Fare clic su Fattura.
34. Immettere una data nel campo Data fattura.
    * Ad esempio, immettere la data "31-01-2015".  
35. Fare clic su OK.
36. Fare clic su OK.

## <a name="transfer-transactions-to-the-intrastat"></a>Trasferire transazioni a Intrastat
1. Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.
2. Fare clic su Trasferisci.
3. Selezionare Sì nel campo Fattura cliente.
4. Fare clic su Filtro.
5. Nell'elenco contrassegnare la riga con Data.
6. Digitare un valore nel campo Criteri.
    * Ad esempio, immettere il filtro per il periodo gennaio 2015 (il valore esatto dipende dal formato della data): 1/1/2015..31/1/2015  
7. Fare clic su OK.
8. Fare clic su OK.
9. Trovare e selezionare il record trasferito nell'elenco.
10. Fare clic sulla scheda Generale.
    * Esaminare i dati del trasferimento, inclusi paese di destinazione/spedizione, paese di origine, peso, quantità, quantità di unità supplementari, voce doganale, codice transazione, importi fattura e importi statistici.   Se necessario, è possibile modificare i dati.  

