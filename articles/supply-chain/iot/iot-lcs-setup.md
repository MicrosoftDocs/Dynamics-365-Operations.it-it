---
title: Installare il componente aggiuntivo Intelligence IoT in LCS
description: In questo argomento viene descritto come installare il componente aggiuntivo Intelligence IoT in Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ae6b36c40d2f2f9e5266dfb3e2d1cbbb57755222
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "3803093"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>Installare il componente aggiuntivo Intelligence IoT in LCS

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come installare il componente aggiuntivo Intelligence IoT in Microsoft Dynamics Lifecycle Services (LCS). Si noti che i componenti aggiuntivi non possono essere installati in un ambiente demo/di prova. Prima di poter installare il componente aggiuntivo, devi [creare le risorse di Azure](iot-azure-setup.md).

## <a name="set-up-the-lcs-environment"></a>Configurare l'ambiente LCS

1. Apri LCS e vai al tuo ambiente Microsoft Dynamics 365 Supply Chain Management.
2. Scorrere fino alla sezione **Componenti aggiuntivi dell'ambiente**.
3. Seleziona **Installa un nuovo componente aggiuntivo** per mostrare l'elenco dei componenti aggiuntivi che sono stati abilitati per l'ambiente.
4. Nella finestra di dialogo **Seleziona un componente aggiuntivo da installare**, seleziona **Intelligenza IoT**.
5. Nella finestra di dialogo **Configura componente aggiuntivo**, fornisci i dettagli dell'hub IoT e della cache Redis. Puoi trovare i valori richiesti nell'insieme di credenziali chiave che hai creato in [Creare le risorse di Azure](iot-azure-setup.md).

    + **ID tenant**: nel portale Azure, vai all'insieme delle credenziali chiave quindi nel pannello di navigazione a sinistra, seleziona **Panoramica** e copia il valore **ID directory**. Incolla quel valore nella finestra di dialogo **Configura componente aggiuntivo**.
    + **URI del Key Vault dell'endpoint compatibile con hub eventi IoT**: vai all'insieme di credenziali chiave quindi, nel pannello di navigazione sinistro seleziona **Panoramica**, quindi copia il valore **Nome DNS**. Incolla quel valore nella finestra di dialogo **Configura componente aggiuntivo**.
    + **Nome segreto dell'endpoint compatibile con hub eventi IoT**: vai all'insieme di credenziali chiave, quindi nel pannello di navigazione sinistro, seleziona **Segreti** e copia il nome del segreto in cui è memorizzata la stringa di connessione dell'hub eventi per l'hub IoT. Incolla quel valore nella finestra di dialogo **Configura componente aggiuntivo**.
    + **URI dell'insieme di credenziali delle chiavi della cache Redis**: vai all'insieme di credenziali chiave quindi, nel pannello di navigazione sinistro seleziona **Panoramica** e copia il valore **Nome DNS**. Incolla quel valore nella finestra di dialogo **Configura componente aggiuntivo**.
    + **Nome segreto dell'endpoint della cache Redis**: vai all'insieme di credenziali chiave, quindi nel pannello di navigazione sinistro, seleziona **Segreti** e copia il nome del segreto in cui è memorizzata la stringa di connessione della cache Redis. Incolla quel valore nella finestra di dialogo **Configura componente aggiuntivo**.

6. Seleziona la casella di controllo per accettare i termini e le condizioni.
7. Selezionare **Installa**.
8. Viene visualizzata una finestra di messaggio che indica "Il componente aggiuntivo è stato attivato correttamente per l'installazione". Selezionare **OK**.

La configurazione LCS è ora completata. Il prossimo passo è [impostare gli scenari](iot-scenario-setup.md).

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a>Disinstallare il componente aggiuntivo

1. In Supply Chain Management, [disabilita gli scenari](iot-scenario-setup.md#how-to-disable-a-scenario).
2. In LCS, vai ai dettagli dell'ambiente Supply Chain Management.
3. Scorrere fino alla sezione **Componenti aggiuntivi dell'ambiente**.
4. Seleziona **Disinstalla** per il componente aggiuntivo Intelligence IoT.
