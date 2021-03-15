---
title: EUR-00002 Generare una dichiarazione Intrastat UE
description: Questa procedura illustra i passaggi necessari per esportare la dichiarazione Intrastat in formato di file elettronico e per visualizzare l'anteprima dei dati della dichiarazione in formato Excel.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, IntrastatParameters, IntrastatCommodityLookup, IntrastatCompressParameters, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 581a837049f239cb9b9fa41eb978304751cb3b54
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989982"
---
# <a name="eur-00002-generate-an-eu-intrastat-declaration"></a>EUR-00002 Generare una dichiarazione Intrastat UE

[!include [banner](../../includes/banner.md)]

Questa procedura illustra i passaggi necessari per esportare la dichiarazione Intrastat in formato di file elettronico e per visualizzare l'anteprima dei dati della dichiarazione in formato Excel. 

Prima di poter completare questa procedura, è necessario trasferire le transazioni a Intrastat. 

Questa procedura è stata creata utilizzando la società di dati dimostrativi DEMF.


## <a name="import-configurations-with-settings"></a>Importare le configurazioni con le impostazioni
1. Andare a Aree di lavoro > Creazione di report elettronici
2. Fare clic su Imposta attivo.
3. Fare clic su Archivi.
4. Fare clic su Apri.
5. Aprire il filtro della colonna Nome configurazione.
6. Applicare un filtro sul campo "Nome configurazione" in base a un valore "Intrastat (DE)" utilizzando l'operatore di filtro "inizia con".
    * È necessario selezionare il nome di configurazione applicabile al paese della persona giuridica. Questa procedura utilizza la persona giuridica tedesca (DEMF) come esempio, quindi deve essere scelto "Intrastat (DE)".  
    * Fare clic su Importa, quindi su Sì.  
7. Aprire il filtro della colonna Nome configurazione.
8. Applicare un filtro sul campo "Nome configurazione" in base a un valore "report Intrastat" utilizzando l'operatore di filtro "inizia con".
    * Fare clic su Importa, quindi su Sì.  

## <a name="set-up-foreign-trade-parameters"></a>Impostare Parametri per il commercio estero
1. Passare a Imposta > Impostazione > Commercio estero > Parametri per il commercio estero
2. Espandere la sezione Creazione di report elettronici.
3. Nel campo Mapping formato file immettere o selezionare un valore Intrastat (DE)
4. Nel campo Mapping formato report immettere o selezionare un valore Report Intrastat
5. Espandere la sezione Regole di arrotondamento.
    * È necessario impostare le regole di arrotondamento che sono applicabili nel paese per la dichiarazione Intrastat.  
6. Immettere un numero nel campo Regola di arrotondamento.
    * Inserire la precisione di arrotondamento, ad esempio, immettere "0,01".  
7. Nel campo Numero di decimali per l'importo immettere un numero.
    * Ad esempio, immettere "2".  
8. Nel campo Arrotondamento sotto 1 kg selezionare un'opzione.
    * Ad esempio, selezionare "Arrotondamento fino a 1 kg".  
9. Immettere un numero nel campo Regola di arrotondamento.
    * Ad esempio, impostare "1" per l'arrotondamento del peso all'intero.  
10. Espandere la sezione Limite minimo.
11. Immettere un numero nel campo Peso.
    * Ad esempio, impostare "10" come peso minimo.  
12. Nel campo Importo immettere un numero.
    * Ad esempio, impostare "200" come quantità minima.  
13. Nel campo Voce doganale immettere o selezionare un valore.

## <a name="set-up-compression-of-intrastat"></a>Impostare Compressione di Intrastat
1. Passare a Imposta > Impostazioni > Commercio estero > Compressione di Intrastat.
2. Fare clic su Rimuovi.
3. Nell'elenco trovare e selezionare il record desiderato.
    * Ad esempio, selezionare Voce doganale nella sezione Disponibile.  
4. Scegliere Aggiungi.

## <a name="generate-intrastat-declaration"></a>Generare la dichiarazione Intrastat
1. Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.
2. Fare clic su Convalida.
    * La convalida viene effettuata in base al campo Verifica impostazione nella pagina Parametri per il commercio estero.  
3. Fare clic su OK.
4. Fare clic su Aggiorna.
5. Fare clic su Limite minimo.
6. Nel campo Data di inizio, immettere una data.
    * Ad esempio, immettere 1 gennaio 2015.  
7. Selezionare Sì nel campo Comprimi.
8. Immettere una data nel campo Data di fine.
    * Ad esempio, immettere 31 gennaio 2015.  
9. Fare clic su OK.
10. Fare clic su Aggiorna.
11. Fare clic su Comprimi.
    * La compressione si verifica in base a come si configurano le impostazioni di compressione di intrastate.  
12. Nel campo Data di inizio, immettere una data.
    * Ad esempio, immettere 1 gennaio 2015.  
13. Immettere una data nel campo Data di fine.
    * Ad esempio, immettere 31 gennaio 2015.  
14. Fare clic su OK.
15. Fare clic su Aggiorna.
16. Fare clic su Rigenera numeri progressivi.
17. Fare clic su OK.
18. Fare clic su Output.
19. Fare clic su Report.
20. Nel campo Dal immettere la prima data del periodo di reporting.
    * Ad esempio, impostare la data su 1 gennaio 2015.  
21. Nel campo Data finale immettere una data.
    * Ad esempio, immettere 31 gennaio 2015.  
22. Selezionare Sì nel campo Genera file.
23. Digitare un valore nel campo Nome file.
24. Selezionare Sì nel campo Genera report.
25. Digitare un valore nel campo Nome file report.
26. Selezionare un'opzione nel campo Direzione.
    * Ad esempio, selezionare "Spedizioni".  
27. Fare clic su OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]