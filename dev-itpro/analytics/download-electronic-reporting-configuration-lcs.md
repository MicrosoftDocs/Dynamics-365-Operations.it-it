---
title: Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services
description: Questo argomento illustra come scaricare le configurazioni per la creazione di report elettronici da Microsoft Dynamics Lifecycle Services (LCS).
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 9dca5dec846670da25926826f59d7bce0fa0dcea
ms.lasthandoff: 03/31/2017


---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services

Questo argomento illustra come scaricare le configurazioni per la creazione di report elettronici da Microsoft Dynamics Lifecycle Services (LCS).

Questa esercitazione guida l'utente nel processo di download della versione più recente delle configurazioni per la creazione di report elettronici da Microsoft Dynamics Lifecycle Services (LCS).

1.  Accedere a Dynamics  365 for Operations utilizzando uno dei seguenti ruoli:
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
    4.  Immettere un nome e una descrizione per l'archivio.
    5.  Fare clic su **OK** per confermare la nuova voce di archivio.
    6.  Nella griglia, selezionare il nuovo archivio di tipo **LCS**.

6.  Fare clic su **Apri** per visualizzare l'elenco delle configurazioni di ER per l'archivio selezionato. [![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)
7.  Nella struttura di configurazioni nel riquadro sinistro, selezionare la configurazione per la creazione di report elettronici desiderata.
8.  Nella scheda dettaglio **Versioni** selezionare la versione richiesta della configurazione per la creazione di report elettronici.
9.  Fare clic su **Importa** per scaricare la versione selezionata da LCS nell'istanza corrente di Microsoft Dynamics 365 for Operations. **Nota:** il pulsante **Importa** non è disponibile per le versioni di configurazione di creazione di report elettronici già presenti nell'istanza corrente di Dynamics 365 for Operations. [![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

**Nota:** a seconda delle impostazioni della creazione di report elettronici, le configurazioni vengono convalidate dopo l'importazione. È possibile ricevere una notifica per tutti i problemi di incoerenza rilevati. Risolvere i problemi prima di utilizzare la versione di configurazione importata. Per ulteriori informazioni, vedere l'elenco di articoli correlati per questo argomento.

<a name="see-also"></a>Vedere anche
--------

[Panoramica sui report elettronici](general-electronic-reporting.md)


