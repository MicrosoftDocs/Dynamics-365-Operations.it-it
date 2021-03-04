---
title: Scaricare configurazioni ER dall'archivio globale del servizio di configurazione
description: In questo argomento viene descritto come scaricare le configurazioni per la creazione di report elettronici (ER) dall'archivio globale del servizio di configurazione.
author: NickSelin
manager: AnnBe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a96e78a64fe0559ae5f3bfddabf3fe1cad8a3dcb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679560"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a>Scaricare configurazioni ER dall'archivio globale del servizio di configurazione

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come scaricare le [configurazioni per la creazione di report elettronici (ER)](general-electronic-reporting.md#Configuration) dall'archivio globale del servizio di configurazione. Per ulteriori informazioni, vedere [Microsoft Dynamics 365 for Finance and Operations - Regulatory services, Servizio di configurazione](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="open-configurations-repository"></a>Aprire l'archivio delle configurazioni

1. Accedere all'applicazione Dynamics 365 Finance utilizzando uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

2. Andare ad **Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici**.
3. Nella sezione **Provider di configurazione** selezionare il riquadro **Microsoft**.
3. Nel riquadro **Microsoft** selezionare **Archivi**.

    ![Area di lavoro Creazione di report elettronici](./media/er-download-configurations-global-repo-er-workspace.png)

4. Nella pagina **Archivi di configurazioni** selezionare nella griglia l'archivio esistente di tipo **Globale**. Se questo archivio non viene visualizzato nella griglia, effettuare le seguenti operazioni:

    1. Selezionare **Aggiungi** per aggiungere un nuovo archivio.
    2. Selezionare **Globale** come tipo di archivio, quindi selezionare **Crea archivio**.
    3. Se richiesto, seguire le istruzioni di autorizzazione.
    4. Immettere un nome e una descrizione per l'archivio e quindi selezionare **OK** per confermare il nuovo archivio.
    5. Nella griglia, selezionare il nuovo archivio di tipo **Globale**.

5. Selezionare **Apri** per visualizzare l'elenco delle configurazioni ER per l'archivio selezionato.

    ![Pagina Archivi di configurazione](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a>Importare un'unica configurazione

1. Nella pagina **Archivi di configurazioni**, nella struttura delle configurazioni, selezionare la configurazione ER desiderata.
2. Nella scheda dettaglio **Versioni** selezionare la versione richiesta della configurazione ER.
3. Selezionare **Importa** per scaricare la versione selezionata dall'archivio Globale nell'istanza corrente di Finance.

    > [!NOTE]
    > Il pulsante **Importa** non è disponibile per le versioni di configurazione ER già presenti nell'istanza corrente di Finance.

    ![Configurazione della pagina dell'archivio](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a>Importare configurazioni filtrate

1. Nella pagina **Archivi di configurazione**, nella struttura delle configurazioni, espandere la Scheda dettaglio **Filtro**.
2. Nella griglia **Tag**, aggiungere eventuali tag necessari.
3. Nel campo **Applicabilità paese**, selezionare i codici paese appropriati, quindi selezionare **Applica filtro**.

    > [!NOTE]
    > La Scheda dettaglio **Configurazioni** mostra tutte le configurazioni che soddisfano le condizioni di selezione specificate.

4. Nella Scheda dettaglio **Configurazioni**, selezionare **Importa** per scaricare le configurazioni filtrate dall'archivio globale nell'istanza corrente.
5. Nella Scheda dettaglio **Configurazioni**, selezionare **Reimposta filtro** per ripulire le condizioni di selezione specificate.

    ![Configurazione della pagina dell'archivio](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> A seconda delle impostazioni ER, le configurazioni vengono convalidate dopo l'importazione. È possibile ricevere una notifica per tutti i problemi di incoerenza rilevati. Prima di utilizzare la versione di configurazione importata, è necessario risolvere i problemi. Per ulteriori informazioni, vedere l'elenco delle risorse correlate per questo argomento.

> [!NOTE]
> Le configurazioni ER possono essere configurate come dipendenti da altre configurazioni. Pertanto, insieme a una configurazione selezionata, altre configurazioni potrebbero essere importate automaticamente. Per ulteriori informazioni sulle dipendenze delle configurazioni, vedere [Definire la dipendenza delle configurazioni ER in altri componenti](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei report elettronici](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]