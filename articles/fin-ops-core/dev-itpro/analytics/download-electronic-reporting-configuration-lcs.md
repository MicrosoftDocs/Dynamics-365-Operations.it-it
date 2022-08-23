---
title: Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services
description: Questo articolo illustra come scaricare le configurazioni per la creazione di report elettronici da Microsoft Dynamics Lifecycle Services (LCS).
author: kfend
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.form: ERSolutionImport, ERWorkspace
ms.openlocfilehash: f48dd14bc3009550d78bd71db030c172d2ef6450
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277818"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services

[!include [banner](../includes/banner.md)]

Questo articolo spiega come scaricare la versione più recente di [Configurazioni per la creazione di report elettronici](general-electronic-reporting.md#Configuration) dalla [libreria di risorse condivise](../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).

> [!IMPORTANT]
> L'utilizzo di LCS come repository di archiviazione per le configurazioni ER è stato [deprecato](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). Per ulteriori informazioni vedi [Regulatory Configuration Service (RCS) – Deprecazione dell'archiviazione di Lifecycle Services (LCS)](../../../finance/localizations/rcs-lcs-repo-dep-faq.md)

1. Accedere all'applicazione utilizzando uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

2. Andare a **Amministrazione organizzazione** &gt; **Aree di lavoro** &gt; **Creazione di report elettronici**.
3. Nella sezione **Provider di configurazione** selezionare il riquadro **Microsoft**.
4. Nel riquadro **Microsoft** selezionare **Archivi**.

    [![Riquadro Microsoft nella pagina delle configurazioni di localizzazione.](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. Nella pagina **Archivi di configurazioni** selezionare nella griglia l'archivio esistente di tipo **LCS**. Se questo archivio non viene visualizzato nella griglia, effettuare le seguenti operazioni:

    1. Selezionare **Aggiungi** per aggiungere un archivio.
    2. Selezionare **LCS** come tipo di archivio.
    3. Selezionare **Crea archivio**.
    4. Se viene richiesta l'autorizzazione, seguire le istruzioni sullo schermo.
    5. Immettere un nome e una descrizione per l'archivio.
    6. Selezionare **OK** per confermare la nuova voce di archivio.
    7. Nella griglia, selezionare il nuovo archivio di tipo **LCS**.

6. Selezionare **Apri** per visualizzare l'elenco delle configurazioni ER per l'archivio selezionato.

    [![Pagina Archivi di configurazione.](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

    > [!TIP]
    > Se si verificano problemi con l'accesso all'archivio LCS per scaricare le configurazioni dalla libreria di risorse condivise in LCS, è possibile scaricare le configurazioni dal [repository globale](er-download-configurations-global-repo.md).

7. Nella struttura di configurazioni nel riquadro sinistro, selezionare la configurazione per la creazione di report elettronici desiderata.
8. Nella scheda dettaglio **Versioni** selezionare la versione richiesta della configurazione ER.
9. Selezionare **Importa** per scaricare la versione selezionata da LCS nell'istanza corrente.

    > [!NOTE]
    > Il pulsante **Importa** non è disponibile per le versioni di configurazione di creazione di report elettronici già presenti nell'istanza corrente.

    [![Pagina Archivio di configurazione.](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> A seconda delle impostazioni ER, le configurazioni vengono convalidate dopo l'importazione. È possibile ricevere una notifica per tutti i problemi di incoerenza rilevati. Risolvere i problemi prima di utilizzare la versione di configurazione importata. Per ulteriori informazioni, vedere l'elenco di articoli correlati per questo articolo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della creazione di report elettronici](general-electronic-reporting.md)

[Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
