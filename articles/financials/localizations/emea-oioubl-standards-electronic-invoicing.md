---
title: Standard supportati per la fatturazione elettronica in Europa
description: In questo argomento viene descritto il livello di copertura della fatturazione elettronica in Microsoft Dynamics 365 for Finance and Operations nella regione europea.
author: mrolecki
manager: AnnBe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10274
ms.search.region: Austria, Denmark, Italy, Norway, Spain, France, Belgium, Netherlands
ms.search.industry: 
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 354b9fd50dbd628b91fd4d77c4cb323ddc36428f
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="supported-standards-for-electronic-invoicing-in-europe"></a>Standard supportati per la fatturazione elettronica in Europa

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto il livello di copertura della fatturazione elettronica per l'Europa. 

L'implementazione e l'adozione della fatturazione elettronica in scala comunitaria europea è disciplinata da [Direttiva del Consiglio 2010/45/UE](http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), che interessa tutti gli stati membri UE. Le società che desiderano beneficiare della fatturazione elettronica devono inviare fatture di ordini cliente, fatture a testo libero, fatture di progetto, note di accredito ordini cliente e note di accredito delle fatture di progetto come file XML al governo o ad altre parti del settore che richiedono l'utilizzo della fatturazione elettronica. Questi file XML devono rispondere a determinate regole. I requisiti specifici di un paese e la relativa implementazione possono differire tra gli stati membri UE, ma normalmente utilizzano sia Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) nelle versioni diverse con personalizzazioni che le specifiche e i punti di accesso [PEPPOL](http://www.peppol.eu) per la convalida e il trasporto. Il vantaggio principale dell'UBL è che i documenti aziendali possono essere standardizzati per diversi scopi. Poiché l'UBL è uno standard internazionale flessibile che supporta numerosi requisiti aziendali, questi documenti aziendali possono essere scambiati tra paesi diversi.

## <a name="what-electronic-invoice-formats-are-currently-available-in-finance-and-operations"></a>Quali formati di fattura elettronica sono attualmente disponibili in Finance and Operations?

Sono disponibili i seguenti formati di fatture elettroniche specifici di ciascun paese:

-   OIOUBL v.2.02 per la Danimarca
-   EHF v.2.0.8 per la Norvegia
-   PEPPOL BIS v.2 per Austria, Francia e Belgio
-   UBL-OHNL 1.9 per i Paesi Bassi
-   FacturaE v.3.2.1 per la Spagna
-   FatturaPA v.1.2 per l'Italia

La fatturazione elettronica è basata su [report elettronici](../../dev-itpro/analytics/general-electronic-reporting.md). Esistono un modello dati **Modello fattura cliente** e una serie di configurazioni di formati di report elettronici specifici di ciascun paese create per Austria (AT), Danimarca (DK), Italia (IT), Norvegia (NO), Spagna (ES), Francia (FR), Belgio (BE) e Paesi Bassi (NL).

-   Fattura vendite OIOUBL - per AT, DK e NO
-   Nota di accredito OIOUBL - per AT, DK e NO
-   Fattura di progetto OIOUBL - per AT, DK e NO
-   Nota di accredito di progetto OIOUBL - per AT, DK e NO
-   Fattura di vendita UBL FR
-   Nota di accredito vendita UBL FR
-   Fattura di progetto UBL FR
-   Nota di accredito di progetto UBL FR
-   Fattura di vendita UBL BE
-   Nota di accredito vendita UBL BE
-   Fattura di progetto UBL BE
-   Nota di accredito di progetto UBL BE
-   Fattura di vendita UBL NL
-   Nota di accredito vendita UBL NL
-   Fattura di progetto UBL NL
-   Nota di accredito di progetto UBL NL 
-   Fattura di vendita (ES)
-   Fattura di vendita (IT)
-   Fattura di progetto (ES)
-   Fattura di progetto (IT)

Le fatture e le note di accredito elettroniche che vengono generate includono informazioni obbligatorie, ad esempio un numero EAN (European Article Numbering), il contatto, il numero del conto dimensione e l'indirizzo dei cliente. Le regole di convalida vengono applicate quando le fatture vengono generate in modo che sia possibile verificare la correttezza delle informazioni immesse. Il set di dati necessari può essere diverso da paese a paese. Poiché i requisiti, così come i paesi e i formati supporti, sono soggetti a modifica, è necessario passare alla libreria Risorsa condivisa in Microsoft Dynamics Lifecycle Services (LCS) e visualizzare l'elenco più aggiornato di file disponibili con tipo di risorsa **Configurazione GER**.

## <a name="additional-information"></a>Informazioni aggiuntive
Per ulteriori informazioni su come impostare le fatture elettroniche, è possibile riprodurre le seguenti [Guide attività](../../fin-and-ops/get-started/help-overview.md#task-guides) nel riquadro della Guida:

 - Impostare la fatturazione elettronica OIOUBL
 - Importare le configurazioni della fatturazione elettronica OIOUBL
 - Impostare gli account cliente per la fatturazione elettronica OIOUBL

> [!NOTE] 
> Sebbene queste Guide attività vengano create per il formato di fatturazione elettronico *OIOUBL* specifico della Danimarca, sono applicabili agli altri paesi supportati con piccole differenze.

