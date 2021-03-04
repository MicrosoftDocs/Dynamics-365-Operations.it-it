---
title: Configurazione delle risorse Azure per Intelligence IoT
description: Questo argomento spiega come creare e configurare le risorse Microsoft Azure necessarie per l'Intelligence IoT.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1277d2ab8bb1f2925874f7469250e164f6bde62d
ms.sourcegitcommit: 092ef6a45f515b38be2a4481abdbe7518a636f85
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431462"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a>Configurazione delle risorse Azure per Intelligence IoT

[!include [banner](../../includes/banner.md)]

Questo argomento spiega come creare e configurare le risorse Microsoft Azure necessarie per l'Intelligence IoT.

## <a name="create-azure-resources"></a>Creare risorse Azure

Seguire questi passaggi per creare un hub IoT, una cache Redis e un vault chiave a cui può accedere Microsoft Dynamics 365 Supply Chain Management.

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a>Verificare che l'app del produttore dell'ERP Microsoft Dynamics Microservices sia nel tuo tenant

Per verificare che l'ID dell'app per l'app del produttore dell'ERP Microsoft Dynamics Microservices sia nel tuo tenant, segui questi passaggi.

1. Accedere al portale Azure all'indirizzo <https://portal.azure.com>.
2. Accedere a **Azure Active Directory**.
3. Vai ad **Applicazioni aziendali**.
4. Nel campo **Tipo di applicazione**, seleziona **Applicazioni Microsoft**.
5. Nel campo di ricerca, immetti **Microsoft Dynamics ERP Microservices**.
6. Verifica che **Microsoft Dynamics ERP Microservices** sia nell'elenco. Altre applicazioni hanno nomi simili. È pertanto importante accertarsi di trovare l'applicazione corretta. L'ID app è **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Se l'applicazione non è nell'elenco, è necessario aggiungerla al tenant:

    1. Nel portale di Azure, sulla barra degli strumenti, seleziona il pulsante per aprire Azure Cloud Shell.
    2. Esegui il comando **Install-Module AzureAD**. Immetti **Y** per installare il modulo.
    3. Esegui il comando **Get-InstalledModule -Name "AzureAD"** per verificare che il modulo sia installato.
    4. Esegui il comando **Connect-AzureAD -Confirm** per eseguire l'autenticazione.
    5. Esegui il comando **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Ora puoi ripetere i passaggi da 1 a 6 per verificare che l'ID dell'app sia nel tuo titolare.

### <a name="create-a-key-vault-resource"></a>Creare una risorsa insieme di credenziali

Per creare una risorsa insieme di credenziali chiave, completa i passaggi seguenti:

1. Nel portale di Azure, creare o andare a un gruppo di risorse.
2. Selezionare **Aggiungi**.
3. Nella pagina **Nuovo**, nel campo di ricerca, inserisci **Insieme di credenziali chiave**. Selezionare **Crea**.
4. Nella pagina **Crea insieme di credenziali chiave**, nel campo **Nome insieme di credenziali chiave**, inserisci un nome.
5. Rivedi i valori predefiniti, quindi seleziona **Rivedi + crea**.
6. Selezionare **Crea**.

L'insieme di credenziali chiave viene creato in background.

### <a name="create-an-iot-hub-resource"></a>Creare una risorsa dell'hub IoT

Per creare una risorsa dell'hub IoT, completa i passaggi seguenti:

1. Crea o vai a un gruppo di risorse.
2. Selezionare **Aggiungi**.
3. Nella pagina **Nuovo**, nel campo di ricerca, inserisci **Hub IoT**. Selezionare **Crea**.
4. Nel campo **Nome hub IoT** immetti un nome.
5. Rivedi i valori predefiniti, quindi seleziona **Rivedi + crea**.
6. Selezionare **Crea**.

L'hub IoT viene creato in background.

> [!NOTE]
> Ti consigliamo di creare una sola risorsa hub IoT per ambiente.

### <a name="create-a-redis-cache-resource"></a>Creare una risorsa cache Redis

Per creare una risorsa cache Redis, completa i passaggi seguenti:

1. Crea o vai a un gruppo di risorse.
2. Selezionare **Aggiungi**.
3. Nella pagina **Nuovo**, nel campo di ricerca, inserisci **Cache di Azure per Redis**. Selezionare **Crea**.
4. Nel campo **Nome DNS** immetti un nome.
5. Rivedi i valori predefiniti, quindi seleziona **Crea**.

La cache Redis viene creato in background.

> [!NOTE]
> Ti consigliamo di creare una sola cache Redis per ambiente.

Tutte le risorse sono state ora create.

## <a name="configure-the-azure-resources"></a>Configura le risorse di Azure

### <a name="configure-the-iot-hub"></a>Configura l'hub IoT

Per configurare l'hub IoT, attieniti a questa procedura.

1. Nelle risorse, seleziona la risorsa dell'hub IoT.
2. Nel riquadro di navigazione sinistro, seleziona **Endpoint predefiniti**.
3. In **Gruppi di consumer**, incolla i seguenti gruppi di consumatori. Questi gruppi di consumatori corrispondono agli scenari predefiniti.

    + microsoft.dynamics.iotintelligence-1
    + microsoft.dynamics.iotintelligence-2
    + microsoft.dynamics.iotintelligence-3

### <a name="configure-the-key-vault"></a>Configura l'insieme di credenziali chiave

Per configurare l'insieme di credenziali chiave, segui questa procedura.

1. Nelle risorse, seleziona la risorsa dell'insieme di credenziali chiave.
2. Nel riquadro di spostamento sinistro, seleziona **Criteri di accesso**.
3. Seleziona **Aggiungi un nuovo criterio di accesso**.
4. Nella pagina **Aggiungi un criterio di accesso**, nel campo **Autorizzazioni segrete**, seleziona **Ottieni** ed **Elenco**.
5. Fai clic su **Seleziona un'entità**.
6. Nella finestra di dialogo **Entità di protezione**, cerca e seleziona **Microsoft Dynamics ERP Microservices**. Quindi seleziona **Seleziona**.
7. Selezionare **Aggiungi**.
8. Selezionare **Salva**.

L'app ora ha accesso ai segreti nell'insieme di credenziali chiave.

### <a name="save-the-iot-hub-connection-string-secret"></a>Salva il segreto della stringa di connessione dell'hub IoT

Per salvare il segreto per la stringa di connessione dell'hub IoT, attieniti alla seguente procedura.

1. Nelle risorse, seleziona la risorsa dell'hub IoT.
2. Nel riquadro di navigazione sinistro, seleziona **Endpoint predefiniti**.
3. Copia il valore nel campo **Endpoint compatibile con hub eventi**.
4. Vai alla risorsa dell'insieme di credenziali chiave.
5. Nel pannello di navigazione a sinistra, selezionare **Segreti**.
6. Seleziona **Genera/Importa**.
7. Nel campo **Nome** immettere un nome.
8. Nel campo **Valore**, incolla il valore dell'endpoint che hai copiato in precedenza.
9. Selezionare **Crea**.

### <a name="save-the-redis-cache-connection-string-secret"></a>Salva il segreto della stringa di connessione della cache Redis

Per salvare il segreto per la stringa di connessione della cache Redis, attieniti alla seguente procedura.

1. Nelle risorse, seleziona la risorsa della cache Redis.
2. Seleziona **Chiavi di accesso**.
3. Copia il valore nel campo **Stringa di connessione primaria**.
4. Vai alla risorsa dell'insieme di credenziali chiave.
5. Nel pannello di navigazione a sinistra, selezionare **Segreti**.
6. Seleziona **Genera/Importa**.
7. Nel campo **Nome** immettere un nome.
8. Nel campo **Valore**, incolla la stringa di connessione che hai copiato in precedenza.
9. Selezionare **Crea**.

> [!NOTE]
> Ogni volta che aggiorni una delle stringhe di connessione, devi anche aggiornare i valori segreti.

Ora hai completato il provisioning delle risorse di Azure richieste. Il prossimo passo è [Installare l'add-in Intelligence IoT in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]