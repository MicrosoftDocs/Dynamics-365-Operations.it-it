---
title: Impostare l'importazione avanzata delle riconciliazioni bancarie utilizzando la Creazione di report elettronici
description: Questo articolo spiega come utilizzare la Creazione di report elettronici per impostare il processo avanzato di importazione delle riconciliazioni bancarie.
author: angelad116
ms.date: 03/30/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 46a50f4b00125656fc185ad569b94eeef00dc3c3
ms.sourcegitcommit: 649f1db26da8f20602f11180fc565b7c59eaf545
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337569"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Impostare l'importazione avanzata delle riconciliazioni bancarie utilizzando la Creazione di report elettronici

[!include [banner](../includes/banner.md)]

La funzionalità di riconciliazione bancaria avanzata consente di importare rendiconti bancari elettronici e riconciliarli automaticamente con le transazioni bancarie in Microsoft Dynamics 365 Finance. In questo articolo viene spiegato come impostare le funzionalità di importazione dei rendiconti bancari. L'impostazione dell'importazione dei rendiconti bancari varia a seconda del formato del rendiconto bancario elettronico. Microsoft Dynamics 365 Finance supporta tre formati di rendiconto bancario: ISO20022, MT940 e BAI2. 

## <a name="set-up-the-electronic-reporting-configuration"></a>Impostare la creazione di report elettronici

1. Vai in **Aree di lavoro \> Creazione di report elettronici**.
2. Nel riquadro per il provider di configurazione **Microsoft**, seleziona **Archivi**.
3. Seleziona **Globale** e quindi seleziona **Apri**.
4. Se è necessario stabilire una connessione al repository, seleziona il collegamento blu nella finestra di dialogo.
5. Nell'elenco di configurazione, trova **Modello di rendiconto bancario \> Modello di rendiconto bancario BAI2**.
6. Seleziona il formato **BAI2**.
7. Nella Scheda dettaglio **Versioni** seleziona la versione più recente, quindi selezionare **Importa**.

## <a name="set-up-the-bank-statement-format"></a>Impostare il formato dell'estratto conto bancario

1. Vai a **Gestione cassa e banche \> Impostazioni \> Impostazione riconciliazione bancaria avanzata \> Formato rendiconto bancario**.
2. Selezionare **Nuovo**.
3. Imposta i campi **Formato rendiconto** e **Nome**.
4. Seleziona la casella di controllo **Formato importazione elettronica generica**.
5. Imposta il campo **Configurazione formato importazione** sul formato **BAI2**.

## <a name="set-up-the-bank-account"></a>Impostare il conto bancario

1. Passare a **Gestione cassa e banche \> Conti bancari \> Conti bancari**.
2. Apri il conto bancario.
3. Nella scheda dettaglio **Riconciliazione**, imposta l'opzione **Riconciliazione bancaria avanzata** su **Sì**.
4. Imposta il campo **Formato rendiconto** sul formato **BAI2** creato in precedenza.

## <a name="import-the-bank-statement"></a>Importare il rendiconto bancario

1. Vai a **Gestione cassa e banche \> Riconciliazione estratti conto bancari \> Rendiconti bancari**.
2. In cima alla pagina **Rendiconti bancari** seleziona **Importa rendiconto**.
3. Imposta il campo **Conto bancario** sul conto bancario del rendiconto.
4. Imposta il campo **Formato rendiconto** sul formato **BAI2** creato in precedenza.
5. Seleziona **Sfoglia**, e seleziona il file **BAI**.
6. Selezionare **Carica**.
7. Seleziona **OK** per importare il file selezionato.


## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Esempi di formati di rendiconto bancario e di layout tecnici
Di seguito sono riportati esempi di definizioni avanzate di layout tecnici dei file di importazione di riconciliazione bancaria e tre file di esempio di rendiconto bancario: [Esempi di file di importazione](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Definizione di layout tecnico                             | File di esempio di rendiconto bancario          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)     |
| DynamicsAXISO20022Layout | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)     |

