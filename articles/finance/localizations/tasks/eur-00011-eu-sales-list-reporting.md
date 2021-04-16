---
title: EUR-00011 - Imposta dichiarazioni elenco vendite UE
description: Questa attività illustra una panoramica dei prerequisiti necessari per la dichiarazione dell'elenco vendite UE.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e53fd323f44eadba73a3b596faacd8eaeb60c62f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826058"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a>EUR-00011 - Imposta dichiarazioni elenco vendite UE

[!include [banner](../../includes/banner.md)]

Questa attività illustra una panoramica dei prerequisiti necessari per la dichiarazione dell'elenco vendite UE. Per ulteriori informazioni sulla dichiarazione elenco vendite UE, inclusi i prerequisiti necessari, consultare la Guida.

Questa attività si applica a tutti i paesi europei. La guida è stata creata utilizzando la società di dati dimostrativi DEMF e di conseguenza la Germania come paese di esempio. Nella guida si utilizza anche il Portogallo come paese UE di esempio.

Queste attività sono destinate agli amministratori di sistema.


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a>Importare configurazioni di report elettronici per la dichiarazione dell'elenco vendite UE
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic su Imposta attivo.
3. Fare clic su Archivi.
4. Fare clic su Apri.
5. Nel riquadro azioni fare clic su Opzioni.
6. Fare clic su Filtro/ordinamento avanzato.
7. Scegliere Aggiungi.
8. Nel campo Campo selezionare 'Nome configurazione'.
9. Nel campo Criteri, immettere 'Elenco vendite UE (DE)'.
10. Fare clic su OK.
11. Fare clic su Importa.
12. Fare clic su Sì.
13. Nel riquadro azioni fare clic su Opzioni.
14. Fare clic su Filtro/ordinamento avanzato.
15. Fare clic su Reimposta.
16. Scegliere Aggiungi.
17. Nel campo Campo selezionare 'Nome configurazione'.
18. Nel campo Criteri, immettere 'Elenco vendite UE per report righe'.
19. Fare clic su OK.
20. Fare clic su Importa.
21. Fare clic su Sì.

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a>Impostare codici IVA per la dichiarazione dell'elenco vendite UE
1. Andare a Imposta > Imposte indirette > IVA > Codici IVA.
2. Utilizzare il filtro rapido per filtrare il campo Codice IVA in base a un valore di 'VAT19'.
3. Espandere la sezione Impostazione report.
    * Verificare che la selezione Escluso sia impostata su No.  
    * Può essere necessario sbloccare la guida di attività per modificare questa impostazione.  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a>Impostare fasce IVA per la dichiarazione dell'elenco vendite UE
1. Passare a Imposta > Imposte indirette > IVA > Fasce IVA.
2. Utilizzare il filtro rapido per filtrare il campo Fascia IVA in base a un valore di 'AR-DOM'.
3. Fare clic su Modifica.
4. Espandere la sezione Impostazione.
5. Nell'elenco selezionare la prima riga.
6. Selezionare la casella di controllo Esente.
7. Nell'elenco selezionare la seconda riga.
8. Selezionare la casella di controllo Esente.
9. Nell'elenco selezionare la terza riga.
10. Selezionare la casella di controllo Esente.

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a>Impostare fasce IVA articoli per la dichiarazione dell'elenco vendite UE
1. Passare a Imposta > Imposte indirette > IVA > Fasce IVA.
2. Utilizzare il filtro rapido per filtrare il campo Fascia IVA articoli in base a un valore di 'FULL'.
    * Verificare che la selezione Tipo di dichiarazione sia impostata su 'Articolo'.  
    * Può essere necessario sbloccare la guida di attività per modificare il valore in questo campo.  
3. Utilizzare il filtro rapido per filtrare il campo Fascia IVA articoli in base a un valore di 'RED'.
    * Verificare che la selezione Tipo di dichiarazione sia impostata su 'Servizio'.  
    * Può essere necessario sbloccare la guida di attività per modificare il valore in questo campo.  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a>Impostare parametri paese per la dichiarazione dell'elenco vendite UE
1. Passare a Imposta > Impostazione > IVA > Parametri paese.
2. Fare clic su Nuovo.
3. Nel campo Paese, digitare 'PRT'.
4. Nel campo IVA, immettere 'PT'.

## <a name="create-tax-exempt-numbers"></a>Creare partite IVA
1. Passare a Imposta > Impostazione > IVA > Partite IVA.
2. Fare clic su Nuovo.
3. Nel campo Paese, digitare 'PRT'.
4. Nel campo Partita IVA digitare 'PT12345'.

## <a name="set-up-eu-sales-list-reporting-parameters"></a>Impostare parametri per la dichiarazione dell'elenco vendite UE
1. Passare a Imposta > Impostazione > Commercio estero > Parametri per il commercio estero.
2. Fare clic sulla scheda Elenco vendite UE.
3. Selezionare Sì nel campo Trasferisci acquisti.
4. Espandere la sezione Regole di arrotondamento.
5. Impostare Regola di arrotondamento su '0.1'.
6. Selezionare Sì nel campo Utilizzare il valore minimo.
7. Immettere '2' nel campo Numero di decimali.
8. Espandere la sezione Creazione di report elettronici.
9. Nel campo Mapping formato file, selezionare 'Elenco vendite UE (DE)'.
10. Nel campo Mapping formato report, selezionare 'Elenco vendite UE per report righe'.
11. Fare clic sulla scheda Proprietà paese.
    * Verificare che il campo Tipo di paese sia impostato su 'Nazionale' per Paese DEU.  
    * Può essere necessario sbloccare la guida di attività per modificare il valore in questo campo.  
12. Fare clic su Nuovo.
13. Nel campo Paese, digitare 'PRT'.
14. Digitare 'PT' nel campo Codice Intrastat.
15. Nel campo Tipo di paese selezionare 'UE'.
16. Fare clic sulla scheda Sequenze numeriche.
    * Verificare che un codice di sequenza numerica sia specificato per l'elenco vendite UE di riferimento.  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a>Creare un cliente a scopo dimostrativo della dichiarazione dell'elenco vendite UE
1. Andare a Contabilità clienti > Clienti > Tutti i clienti.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente digitare 'PRT-001'.
4. Nel campo Nome digitare 'Cliente dal Portogallo'.
5. Nel campo Gruppo di clienti, selezionare '10'.
6. Nel campo Fascia IVA selezionare 'AR-DOM'.
7. Nel campo Partita IVA selezionare 'PT12345'.
8. Nel campo Paese, digitare 'PRT'.
9. Fare clic su Salva.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]