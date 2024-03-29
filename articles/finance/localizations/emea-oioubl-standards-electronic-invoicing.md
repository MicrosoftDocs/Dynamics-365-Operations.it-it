---
title: Standard supportati per la fatturazione elettronica in Europa
description: In questo articolo viene descritto il livello di copertura della fatturazione elettronica per l'Europa.
author: mrolecki
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 10274
ms.search.region: Austria, Denmark, Italy, Norway, Spain, France, Belgium, Netherlands
ms.search.industry: ''
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 6bbd2acc879447bd7a5883abffdfe0582f6f7554
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906257"
---
# <a name="supported-standards-for-electronic-invoicing-in-europe"></a>Standard supportati per la fatturazione elettronica in Europa

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto il livello di copertura della fatturazione elettronica per l'Europa. 

L'implementazione e l'adozione della fatturazione elettronica in scala comunitaria europea è disciplinata da [Direttiva del Consiglio 2010/45/UE](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), che interessa tutti gli stati membri UE. Le società che desiderano beneficiare della fatturazione elettronica devono inviare fatture di ordini cliente, fatture a testo libero, fatture di progetto, note di accredito ordini cliente e note di accredito delle fatture di progetto come file XML al governo o ad altre parti del settore che richiedono l'utilizzo della fatturazione elettronica. Questi file XML devono rispondere a determinate regole. I requisiti specifici di un paese e la relativa implementazione possono differire tra gli stati membri UE, ma normalmente utilizzano sia Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) nelle versioni diverse con personalizzazioni che le specifiche e i punti di accesso [PEPPOL](https://www.peppol.eu) per la convalida e il trasporto. Il vantaggio principale dell'UBL è che i documenti aziendali possono essere standardizzati per diversi scopi. Poiché l'UBL è uno standard internazionale flessibile che supporta numerosi requisiti aziendali, questi documenti aziendali possono essere scambiati tra paesi diversi.

## <a name="electronic-invoice-formats-currently-available-in-dynamics-365-finance"></a>Formati di fattura elettronica attualmente disponibili in Dynamics 365 Finance

Sono disponibili i seguenti formati di fatture elettroniche specifici di ciascun paese:

-   OIOUBL v.2.02 per la Danimarca
-   EHF v.3.0 per la Norvegia
-   PEPPOL BIS v.2 per Austria, Francia e Belgio
-   UBL-OHNL 1.9 per i Paesi Bassi
-   FacturaE v.3.2.1 per la Spagna
-   FatturaPA v.1.2 per l'Italia
-   xRechnung v.1.2 per la Germania
-   Aprire PEPPOL BIS Billing v.3.0 per Unione Europea
-   Formato specifico estone versione 1.2
-   Finvoice 3.0 per la Finlandia

La fatturazione elettronica è basata sulla [creazione di report elettronici (ER)](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md). Un modello di dati **Modello di fattura**, un mapping modello di fattura e varie configurazioni di formati di report elettronici (ER) specifici di ciascun paese/area geografica sono state create per i seguenti paesi/aree geografiche: 

- Austria (AT)
- Danimarca (DK)
- Italia (IT)
- Norvegia (NO)
- Spagna (ES)
- Francia (FR)
- Belgio (BE)
- Paesi Bassi (NL)
- Germania (DE)
- Estonia (EE)
- Finlandia (FI)
- Unione Europea (UE)

Il modello di dati **Modello di fattura**, il mapping di modello di fattura e le configurazioni di formati di report elettronici (ER) specifici di ciascun paese/area geografica includono:

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
-   Fattura di vendita DE
-   Fattura progetto DE
-   Fattura di vendita Peppol - per l'UE
-   Nota di credito vendita Peppol - per l'UE
-   Fattura progetto Peppol - per l'UE
-   Nota di credito progetto Peppol - per l'UE
-   Fattura di vendita (EE)
-   Fattura di progetto (EE)
-   Fattura di vendita (FI)
-   Fattura di progetto (FI)

Le fatture e le note di accredito elettroniche che vengono generate includono informazioni obbligatorie, ad esempio un numero EAN (European Article Numbering), il contatto, il numero del conto dimensione e l'indirizzo dei cliente. Le regole di convalida vengono applicate quando le fatture vengono generate in modo che sia possibile verificare la correttezza delle informazioni immesse. Il set di dati necessari può essere diverso da paese a paese. Poiché i requisiti, così come i paesi e i formati supporti, sono soggetti a modifica, è necessario passare alla libreria Risorsa condivisa in Microsoft Dynamics Lifecycle Services (LCS) e visualizzare l'elenco più aggiornato di file disponibili con tipo di risorsa **Configurazione GER**.

## <a name="electronic-invoice-configuration"></a>Configurazione fattura elettronica
La configurazione e le specifiche delle fatture elettroniche variano in base al paese/area geografica per cui sono implementate. Per ulteriori informazioni su come configurare e utilizzare le fatture elettroniche dei clienti, vedere gli argomenti specifici del paese correlati:

- [Italia](emea-ita-e-invoices.md)
- [Norvegia](emea-nor-e-invoices.md)
- [Danimarca](emea-dnk-e-invoices.md)
- [Germania](emea-deu-e-invoices.md)
- [Finlandia](https://support.microsoft.com/help/4559937)
- [Estonia](https://support.microsoft.com/help/4552679)
- [PEPPOL](https://support.microsoft.com/help/4490320)

## <a name="additional-resources"></a>Risorse aggiuntive
Per ulteriori informazioni su come impostare le fatture elettroniche, è possibile riprodurre le seguenti [Guide attività](../../fin-ops-core/fin-ops/get-started/help-overview.md#task-guides) nel riquadro della Guida:

 - Impostare la fatturazione elettronica OIOUBL
 - Importare le configurazioni della fatturazione elettronica OIOUBL
 - Impostare gli account cliente per la fatturazione elettronica OIOUBL

> [!NOTE] 
> Sebbene queste Guide attività vengano create per il formato di fatturazione elettronico *OIOUBL* specifico della Danimarca, sono applicabili agli altri paesi/aree geografiche supportati con piccole differenze.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
