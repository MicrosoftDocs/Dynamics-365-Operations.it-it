---
title: Modificare i formati per la creazione di report elettronici riapplicando modelli di Excel
description: Questo articolo descrive come modificare il formato di creazione di report elettronici (ER) utilizzato per generare documenti aziendali riapplicando un modello di Excel modificato.
author: kfend
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
ms.openlocfilehash: 02423a75d96bef0452b8555f8c7a9f0aca0b6771
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283530"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a>Modificare i formati per la creazione di report elettronici riapplicando i modelli di Excel

[!include [banner](../includes/banner.md)]

Lo strumento di creazione di report elettronici viene utilizzato per generare documenti aziendali in formato elettronico. Per generare un documento aziendale, è necessario creare un formato ER e quindi utilizzare la finestra di progettazione ER per definire il layout del documento aziendale e specificare i dati da includere nello stesso. È quindi possibile eseguire il formato ER per generare il documento aziendale.

Lo strumento di creazione di report elettronici può essere utilizzato per generare documenti aziendali come file di Microsoft Excel. È possibile utilizzare un documento di Excel come modello per tali documenti. Per definire il layout di documento nella finestra di progettazione ER, è possibile importare il contenuto del documento di Excel che si desidera utilizzare come modello nel formato ER definito. Per ulteriori dettagli e per acquisire familiarità con questo scenario, riprodurre la guida attività **Creazione di report elettronici: progettare una configurazione per la generazione di report in formato OPENXML** (parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)). Nel passaggio della guida alle attività in cui si importa un modello Excel, utilizza il modello iniziale del file Excel del report di pagamento, [SampleVendPaymWsReport](https://download.microsoft.com/download/e/6/b/e6bb79f0-cc08-44af-96fa-49c7929d4fb8/SampleVendPaymWsReport.xlsx).

Se si modifica il documento di Excel utilizzato come modello per un documento aziendale, la nuova funzionalità ER consente di riapplicare il modello aggiornato al formato ER. Il formato ER viene quindi aggiornato in modo che sia conforme al modello aggiornato. Per ulteriori informazioni su questa funzionalità, riprodurre la guida attività **Modificare un formato per la creazione di report elettronici riapplicando un modello di Excel** (parte del processo aziendale 7.5.5.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10683)). Nel passaggio della guida attività per importare un modello aggiornato, utilizza il modello modificato del file di Excel Report di pagamento, [SampleVendPaymWsReport2](https://download.microsoft.com/download/3/1/0/3104d397-c9c5-4227-b68e-f98625313801/SampleVendPaymWsReport2.xlsx).

## <a name="additional-resources"></a>Risorse aggiuntive

[Aggiorna un modello](er-fillable-excel.md#update-a-template)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
