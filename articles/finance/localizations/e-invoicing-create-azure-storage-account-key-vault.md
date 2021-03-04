---
title: Creare un account di Archiviazione di Azure e un Azure Key Vault
description: Questo argomento spiega come creare un account di Archiviazione di Azure e Azure Key Vault.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 5a883011bbff6d82504497d739c07f1ada9e5f69
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2020
ms.locfileid: "4444961"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Creare un account di Archiviazione di Azure e un Azure Key Vault

[!include [banner](../includes/banner.md)]



Il servizio del componente aggiuntivo per la fatturazione elettronica si assume la responsabilità di archiviare tutti i dati aziendali nelle risorse di Microsoft Azure di proprietà della tua azienda. Per garantire che il servizio funzioni correttamente e che tutti i dati aziendali necessari e generati dal componente aggiuntivo per la fatturazione elettronica siano accessibili solo dal componente aggiuntivo, è necessario creare due risorse principali di Azure:

- Un account di Archiviazione di Azure (Archiviazione BLOB) per archiviare le fatture elettroniche
- Un Azure Key Vault per archiviare i certificati e l'URI (Uniform Resource Identifier) dell'account di archiviazione

> [!NOTE]
> Una risorsa per l'insieme di credenziali delle chiavi dedicata e Archiviazione BLOB del cliente devono essere allocati specificamente per l'utilizzo con il componente aggiuntivo per la fatturazione elettronica.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter completare i passaggi in questo argomento, è necessario accertarsi che le seguenti attività siano state completate:

- Crea una risorsa Azure Key Vault. Per ulteriori informazioni sulle misure, vedi [Informazioni su Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).
- Creare un account di Archiviazione di Azure (archiviazione BLOB). Per ulteriori informazioni, vedi [Gestione dell'account di Archiviazione di Azure](https://docs.microsoft.com/azure/storage/blobs/).

## <a name="overview"></a>Panoramica

In questo argomento, completerai due passaggi principali:

- Configura l'account di Archiviazione di Azure per ottenere l'URI dell'account di archiviazione.
- Configura Azure Key Vault per archiviare l'URI dell'account di archiviazione.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Configurare l'account di Archiviazione di Azure per ottenere l'URI dell'account di archiviazione

1. Apri l'account di archiviazione che intendi utilizzare con il componente aggiuntivo per la fatturazione elettronica.
2. Vai a **Servizio BLOB** \> **Contenitori** e crea un nuovo contenitore.
3. Immetti un nome per il contenitore e imposta il campo **Livello di accesso pubblico** su **Privato (nessun accesso anonimo)**.
4. Apri il contenitore e vai a **Impostazioni \> Criteri di accesso**.
5. Seleziona **Aggiungi criteri** per aggiungere un criterio di accesso archiviato.
6. Imposta i campi **Identificatore** e **Autorizzazioni** in base alle esigenze. Nel campo **Autorizzazioni**, è consigliabile selezionare tutte le autorizzazioni.

    ![Concessione dell'autorizzazione per l'archiviazione BLOB](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Immetti le date di inizio e di scadenza. La data di scadenza dovrebbe essere nel futuro.
8. Seleziona **OK** per salvare i criteri, quindi salva le modifiche nel contenitore.
9. Torna all'account di archiviazione e apri **Storage Explorer (anteprima)**.
10. Fai clic con il pulsante destro del mouse sul contenitore e quindi seleziona **Ottieni firma di accesso condiviso**.
11. Nella finestra di dialogo **Firma di accesso condiviso**, copiare e archivia il valore nel campo **URI**. Questo valore verrà utilizzato nella procedura successiva e verrà indicato come *URI della firma di accesso condiviso*.

    ![Selezione e copia del valore URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Configurare Azure Key Vault per archiviare l'URI dell'account di archiviazione

1. Apri l'Azure Key Vault che intendi utilizzare con il componente aggiuntivo per la fatturazione elettronica.
2. Vai a **Impostazioni** \> **Segreti**, quindi seleziona **Genera/Importa** per creare un nuovo segreto.
3. Nella pagina **Crea un segreto**, nel campo **Opzioni di caricamento**, seleziona **Manuale**.
4. Immettere il nome del segreto. Questo nome verrà utilizzato durante la configurazione del servizio in Regulatory Configuration Service (RCS) e verrà indicato come *nome segreto di Azure Key Vault*.
5. Nel campo **Valore**, seleziona **URI della firma di accesso condiviso** e quindi seleziona **Crea**.
6. Configura i criteri di accesso per concedere al componente aggiuntivo per la fatturazione elettronica il livello corretto di accesso protetto al segreto creato. Vai a **Impostazioni \> Criteri di accesso** e seleziona **Aggiungi criteri di accesso**.
7. Imposta le autorizzazioni segrete per le operazioni **Ottieni** ed **Elenco**.

    ![Concessione dell'accesso al servizio](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Imposta le autorizzazioni del certificato per le operazioni **Ottieni** ed **Elenco**.

    ![Concessione dell'autorizzazione al certificato](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. Nella finestra di dialogo **Entità di sicurezza**, seleziona l'entità di sicurezza aggiungendo **Componente aggiuntivo per la fatturazione elettronica**.
10. Seleziona **Aggiungi** e quindi seleziona **Salva le modifiche di Key Vault**.
11. Nella pagina **Panoramica**, copia il valore **Nome DNS** valore per il Key Vault. Questo valore verrà utilizzato durante la configurazione del servizio in RCS e verrà indicato come *URI di Key Vault*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]