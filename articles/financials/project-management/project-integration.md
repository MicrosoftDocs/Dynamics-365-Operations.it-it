---
title: Integrazione client Microsoft Project
description: "La pianificazione e la gestione della programmazione di un progetto possono essere complesse, per questo i manager di progetto devono utilizzare strumenti che agevolano queste attività. L'integrazione con il client Microsoft Project offre supporto per aprire e gestire una struttura di suddivisione del lavoro del progetto."
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: a72963f755f8eddb19b8526d2938eff039ab7df2
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---

# <a name="microsoft-project-client-integration"></a>Integrazione client Microsoft Project

[!include[banner](../includes/banner.md)]

La pianificazione e la gestione della programmazione di un progetto possono essere complesse, per questo i manager di progetto devono utilizzare strumenti che agevolano queste attività. L'integrazione con il client Microsoft Project offre supporto per aprire e gestire una struttura di suddivisione del lavoro del progetto. Il manager di progetto può pubblicare tutte le modifiche apportate nella struttura di suddivisione del lavoro di progetto di Finance and Operations.

> [!NOTE]
> Se si utilizza l'aggiornamento di luglio di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, è necessario installare KB 4054797 e 4055884.

## <a name="configure-the-microsoft-project-client-add-in"></a>Configurare il componente aggiuntivo del client Microsoft Project
Per abilitare l'integrazione con il client Microsoft Project, è necessario istallare un componente aggiuntivo di Microsoft Dynamics 365 nell'applicazione client di Microsoft Project dell'utente. A tale scopo, aprire l'area di lavoro **Gestione progetti**.

•   Fare clic su **Configurare il componente aggiuntivo del client Microsoft Project** nella sezione **Collegamenti** > **Impostazioni** dell'area di lavoro.

•   Fare clic su **Apri**, quindi su **esegui** quando richiesto.

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a>Aprire e modificare la bozza di una struttura di suddivisione del lavoro esistente nel client Microsoft Project
Se in un progetto di Finance and Operations è già stata creata una struttura di suddivisione del lavoro, la struttura di suddivisione del lavoro può essere aperta nell'applicazione client Microsoft Project se la struttura di suddivisione del lavoro è in stato di bozza. Per aprire la struttura dalla pagina **Project**, fare clic sul collegamento **Apri in Microsoft Project** nella scheda **Piano**. Questa pagina può anche essere aperta dall'interno dell'applicazione client di Microsoft Project facendo clic su **Apri** nella scheda **Microsoft Dynamics 365**. Selezionare la **persona giuridica** e il **progetto** dall'elenco.

> [!NOTE]
> Se si utilizza Internet Explorer come browser, sarà necessario fare clic su **Salva** per aprire la struttura manualmente dalla posizione in cui il file viene scaricato. In alternativa, fare clic su **Salva e apri** per aprire il file nel client Microsoft Project. Non rinominare il file durante il salvataggio.

Prima di apportare modifiche al file utilizzando il client Microsoft Project, è necessario estrarre il file. Fare clic su **Estrai** nella scheda **Microsoft Dynamics 365**. Ciò impedirà ad altri utenti di modificare la struttura di suddivisione del lavoro da Finance and Operations in contemporanea. Per pubblicare la struttura di suddivisione del lavoro dopo il completamento delle eventuali modifiche, fare clic su **Archivia** nella scheda **Microsoft Dynamics 365**.

Se un team di progetto è già stato aggiunto al progetto in Finance and Operations, l'elenco delle risorse verrà popolato con i membri del team. Se un team di progetto non è stato ancora aggiunto al progetto, è possibile selezionare le risorse e creare il team all'interno del client Microsoft Project facendo clic sul pulsante **Risorse** nella scheda **Microsoft Dynamics 365**. 

I seguenti dati verranno sincronizzati Finance and Operations come parte del processo di archiviazione:

•   Nome compito

•   Data di inizio

•   Data di completamento

•   Attività precedenti

•   Nomi risorse

•   Categoria:

•   Categoria di risorsa

•   Ore lavorate

•   Note

•   Priorità

> [!NOTE]
> Se si aggiungono altre colonne al file del client Microsoft Project, non verranno salvate nel file e non verranno visualizzate quando il file viene nuovamente aperto.

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Creare la struttura di suddivisione del lavoro per un progetto esistente utilizzando il client Microsoft Project
Per creare una nuova struttura di suddivisione del lavoro utilizzando il client Microsoft Project, , attenersi alla seguente procedura:


1.  Aprire il client Microsoft Project.

2.  Nella scheda **Microsoft Dynamics 365** fare clic su **Apri**.

3.  Selezionare la **persona giuridica** per il progetto

4.  Selezionare il **progetto**.

5.  Nella scheda **Microsoft Dynamics 365** fare clic su **Estrai**.

6.  Quando si è pronti a pubblicare in Finance and Operations, fare clic su **Archivia** nella scheda **Microsoft Dynamics 365**.

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Sostituire la struttura di suddivisione del lavoro esistente per un progetto esistente utilizzando il client Microsoft Project
Per creare una nuova struttura di suddivisione del lavoro utilizzando il client Microsoft Project e sostituire una struttura di suddivisione del lavoro esistente per un progetto esistente, attenersi alla seguente procedura:

1.  Aprire il client Microsoft Project.

2.  Creare la programmazione nel client Microsoft Project.

3.  Nella scheda **Microsoft Dynamics 365**, fare clic su **Salva modifiche** > **Sostituisci progetto esistente**.

4.  Selezionare la **persona giuridica** per il progetto

5.  Selezionare il **progetto**.

6.  Fare clic su **OK**.

## <a name="create-a-new-project-from-within-microsoft-project-client"></a>Creare un nuovo progetto nel client Microsoft Project


1.  Aprire il client Microsoft Project.

2.  Creare la programmazione nel client Microsoft Project.

3.  Nella scheda **Microsoft Dynamics 365**, fare clic su **Salva modifiche** > **Salva in nuovo progetto**.

4.  Selezionare la **persona giuridica** per il progetto

5.  Se necessario, immettere l'**ID progetto**.

6.  Immettere il **Nome progetto**.

7.  Selezionare il **Tipo di progetto**, il **Gruppo di progetti** e l'**ID contratto di progetto**. In alternativa, è possibile creare un nuovo contratto di progetto facendo clic su **Nuovo**.

8.  Selezionare il **Calendario** da utilizzare per le risorse.

11. Fare clic su **OK**.

