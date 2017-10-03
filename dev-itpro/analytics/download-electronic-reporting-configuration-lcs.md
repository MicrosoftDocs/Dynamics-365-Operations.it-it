---
title: Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services
description: Questo argomento illustra come scaricare le configurazioni per la creazione di report elettronici da Microsoft Dynamics Lifecycle Services (LCS).
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: be77d76194e9d38589548113cc650599d5af4323
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services

[!include[banner](../includes/banner.md)]


Questo argomento illustra come scaricare le configurazioni per la creazione di report elettronici da Microsoft Dynamics Lifecycle Services (LCS).

Questa esercitazione guida l'utente nel processo di download della versione più recente delle configurazioni per la creazione di report elettronici da Microsoft Dynamics Lifecycle Services (LCS).

1.  Accedere a Finance and Operations utilizzando uno dei seguenti ruoli:
    -   Sviluppatore per la creazione di report elettronici
    -   Consulente funzionale per la creazione di report elettronici
    -   Amministratore di sistema

2.  Andare ad **Amministrazione organizzazione** &gt; **Creazione di report elettronici**.
3.  Nella sezione **Provider di configurazione** selezionare il riquadro **Microsoft**.
4.  Nel riquadro **Microsoft** fare clic su **Archivi**. [![update-er-from-lcs-for-ms-open-ms-repositories-list](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)
5.  Nella pagina **Archivi di configurazioni** selezionare nella griglia l'archivio esistente di tipo **LCS**. Se questo archivio non viene visualizzato nella griglia, effettuare le seguenti operazioni:
    1.  Fare clic su **Aggiungi** per aggiungere un nuovo archivio.
    2.  Selezionare **LCS** come tipo di archivio.
    3.  Fare clic su **Crea archivio**.
    4. Se richiesto, seguire le istruzioni di autorizzazione.
    5.  Immettere un nome e una descrizione per l'archivio.
    6.  Fare clic su **OK** per confermare la nuova voce di archivio.
    7.  Nella griglia, selezionare il nuovo archivio di tipo **LCS**.

6.  Fare clic su **Apri** per visualizzare l'elenco delle configurazioni di ER per l'archivio selezionato. [![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)
7.  Nella struttura di configurazioni nel riquadro sinistro, selezionare la configurazione per la creazione di report elettronici desiderata.
8.  Nella scheda dettaglio **Versioni** selezionare la versione richiesta della configurazione per la creazione di report elettronici.
9.  Fare clic su **Importa** per scaricare la versione selezionata da LCS nell'istanza corrente di Finance and Operations. **Nota:** il pulsante **Importa** non è disponibile per le versioni di configurazione di creazione di report elettronici già presenti nell'istanza corrente di Finance and Operations. [![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

**Nota:** a seconda delle impostazioni della creazione di report elettronici, le configurazioni vengono convalidate dopo l'importazione. È possibile ricevere una notifica per tutti i problemi di incoerenza rilevati. Risolvere i problemi prima di utilizzare la versione di configurazione importata. Per ulteriori informazioni, vedere l'elenco di articoli correlati per questo argomento.

<a name="see-also"></a>Vedere anche
--------

[Panoramica sui report elettronici](general-electronic-reporting.md)




