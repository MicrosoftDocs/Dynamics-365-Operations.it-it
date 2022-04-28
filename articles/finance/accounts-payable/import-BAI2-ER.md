---
title: Impostare l'importazione avanzata delle riconciliazioni bancarie utilizzando la Creazione di report elettronici
description: Questo argomento spiega come utilizzare la Creazione di report elettronici per impostare il processo avanzato di importazione delle riconciliazioni bancarie per i rendiconti BAI2.
author: panolte
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
ms.openlocfilehash: 39f1d8ba561ab0e36346f1dfb4f70df318c92a37
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544502"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Impostare l'importazione avanzata delle riconciliazioni bancarie utilizzando la Creazione di report elettronici

[!include [banner](../includes/banner.md)]

La funzionalità di riconciliazione bancaria avanzata consente di importare rendiconti bancari elettronici e riconciliarli automaticamente con le transazioni bancarie in Microsoft Dynamics 365 Finance. In questo argomento viene spiegato come impostare le funzionalità di importazione dei rendiconti bancari BAI2.

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
