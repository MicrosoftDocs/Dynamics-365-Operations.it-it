---
title: Distribuire una soluzione IoT in Azure
description: Intelligence dei dati del sensore utilizza i dati dei sensori connessi a Microsoft Azure. Questo articolo spiega come distribuire una soluzione Internet delle cose (IoT) nella sottoscrizione di Azure.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreAzureResourceDeploymentWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 284aba91aa436ed1dfc02b5a93b4358ffc518017
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428393"
---
# <a name="deploy-an-iot-solution-on-azure"></a>Distribuire una soluzione IoT in Azure

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Intelligence dei dati del sensore utilizza i dati dei sensori connessi a Microsoft Azure. Per consentire ad Azure di recuperare i dati dai sensori e condividerli con Dynamics 365 Supply Chain Management, devi distribuire una soluzione Internet delle cose (IoT) nella tua sottoscrizione di Azure. Il diagramma dell'architettura seguente fornisce una panoramica della soluzione e dei suoi componenti.

![Diagramma dell'architettura di Intelligence dei dati del sensore.](media/sdi-architecture.png "Diagramma dell'architettura di Intelligence dei dati del sensore")

Segui questi passaggi per distribuire le risorse necessarie in Azure.

1. Accedi a Supply Chain Management come amministratore.
1. Vai ad **Amministrazione di sistema \> Impostazioni \> Intelligence dei dati del sensore \> Distribuisci e connetti risorse di Azure** per aprire la procedura guidata di distribuzione.
1. Sulla pagina di **benvenuto** leggi le informazioni e quindi seleziona **Avanti**.
1. Sulla pagina **Distribuisci la soluzione IoT di esempio in Azure**, leggi le informazioni, quindi, nella sezione **Istruzioni** seleziona **Distribuisci**.
1. Viene aperta una nuova scheda del browser e si viene indirizzati al portale di Azure in modo da poter distribuire le risorse di Azure. Se ti viene richiesto, accedi usando le tue credenziali per la sottoscrizione di Azure.
1. Sulla pagina **Distribuzione personalizzata** nel campo **Sottoscrizione** seleziona la tua sottoscrizione.
1. Sotto il campo **Gruppo di risorse** seleziona **Crea nuovo** per creare un gruppo di risorse per i componenti di Azure che verranno distribuiti.
1. Nella finestra di dialogo a discesa che appare, nel campo **Nome** immetti un nome per il nuovo gruppo di risorse (ad esempio, *Demo IoT*). Selezionare **OK**.
1. Impostare i seguenti campi:

    - **Gruppo di risorse** – Seleziona il gruppo di risorse che hai appena creato.
    - **Area** – Seleziona un'area, idealmente quella in cui è distribuito l'ambiente Supply Chain Management. Tieni presente che le aree di Azure hanno prezzi diversi. Puoi visualizzare i costi stimati per la tua area utilizzando il [Calcolatore dei prezzi di Intelligence dei dati del sensore](https://azure.com/e/c36c4947ebff4215b2e62590c2a24c68).
    - **URL dell'ambiente Supply Chain Management** – Immetti l'URL per l'ambiente Supply Chain Management.
    - **Riutilizza l'hub IoT di Azure esistente** – Lascia deselezionata questa casella di controllo.

1. Seleziona **Successivo: Rivedi e crea**.
1. Sulla pagina **Distribuzione personalizzata** verifica che la convalida sia stata superata, quindi seleziona **Crea**.
1. La pagina **Distribuzione in corso** tiene traccia dello stato di avanzamento della distribuzione. Il processo di distribuzione può richiedere fino a 30 minuti. Quando la pagina **Distribuzione in corso** indica che la distribuzione è stata completata, seleziona il collegamento per il nome del gruppo di risorse per aprire una pagina che mostra l'elenco delle risorse distribuite nel gruppo.
1. Nell'elenco delle risorse, trova il record in cui il campo **Tipo** è impostato su *Identità gestita*. Nella colonna **Nome**, seleziona il nome per aprire la pagina dei dettagli della risorsa.
1. Copia il valore nel campo **ID client** (ad esempio, selezionando il pulsante **Copia negli appunti**).
1. Torna alla scheda del browser in cui è in esecuzione Supply Chain Management, *ma non chiudere la scheda del portale di Azure*. La pagina della procedura guidata **Distribuisci la soluzione IoT di esempio in Azure** deve essere ancora aperta. 
1. Selezionare **Avanti**.
1. Sulla pagina **Connetti le risorse di Azure** nel campo **ID client dell'applicazione Azure AD** incolla il valore **ID client** che hai copiato.
1. Torna alla scheda del browser in cui è aperto il portale di Azure, *ma non chiudere la scheda di Supply Chain Management*. La pagina dei dettagli della risorsa deve ancora essere aperta.
1. Seleziona il pulsante **Indietro** del browser per tornare all'elenco delle risorse nel nuovo gruppo di risorse.
1. Nell'elenco delle risorse, trova il record in cui il campo **Tipo** è impostato su *Cache di Azure per Redis*. Nella colonna **Nome**, seleziona il nome per aprire la pagina dei dettagli della risorsa.
1. Nel riquadro di spostamento sinistro, seleziona **Chiavi di accesso**.
1. Sulla pagina **Chiavi di accesso** copia il valore mostrato per **Stringa di connessione primaria (StackExchange.Redis)** (ad esempio, selezionando il pulsante **Copia negli appunti**).
1. Torna alla scheda del browser in cui è in esecuzione Supply Chain Management. La pagina **Connetti le risorse di Azure** deve essere ancora aperta.
1. Nel campo **Stringa di connessione archivio metriche di Redis**, incolla il valore **Stringa di connessione primaria (StackExchange.Redis)** che hai copiato.
1. Selezionare **Fine**.

Le risorse di Azure per Intelligence dei dati del sensore sono ora distribuite nella sottoscrizione di Azure.

> [!NOTE]
> In qualsiasi momento è possibile visualizzare o modificare le informazioni di connessione salvate in Supply Chain Management aprendo la pagina **Parametri di Intelligence dei dati del sensore**. - Per ulteriori informazioni, vedi [Parametri di Intelligence dei dati del sensore](sdi-parameters.md).
