---
title: Certificati e segreti del cliente
description: Questo articolo spiega come configurare i certificati e i segreti del cliente nella fatturazione elettronica.
author: gionoder
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 3943e7cb43cc6bf93995f0b3957766227cc3ec99
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279842"
---
# <a name="customer-certificates-and-secrets"></a>Certificati e segreti del cliente

[!include [banner](../includes/banner.md)]

Se hai già un riferimento Microsoft Azure Key Vault in Regulatory Configuration Service (RCS), è possibile creare riferimenti ai certificati e ai segreti di Key Vault. Se non si dispone ancora di un riferimento Key Vault, vedere [Ambienti di servizio](e-invoicing-service-environments.md) per informazioni su come crearlo.

## <a name="create-certificates-and-secrets"></a>Creare certificati e segreti

Per creare e configurare certificati e segreti, segui questi passaggi.

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Ambiente**, seleziona il riquadro **Fatturazione elettronica**.
3. Nella pagina **Configurazione ambiente**, nel riquadro Azioni seleziona **Ambienti del servizio**.
4. Nella pagina **Ambienti del servizio**, nel riquadro azioni seleziona **Parametri Key Vault**.
5. Nella pagina **Parametri Key Vault** seleziona un riferimento Key Vault e quindi nella sezione **Certificati** seleziona **Aggiungi**.
6. Nel campo **Nome** immettere il nome del segreto o certificato Key Vault. Per ulteriori informazioni, vedi [Creare un account di archiviazione Azure nel portale di Azure](e-invoicing-create-azure-storage-account-azure-portal.md).
7. Nel campo **Descrizione** immettere una descrizione.
8. Nel campo **Tipo**, seleziona **Certificato** se si fa riferimento al certificato archiviato nel Key Vault. Seleziona **Segreto** se si fa riferimento al segreto archiviato nel Key Vault.
9. Seleziona **Salva**.

> [!NOTE]
> In alcuni scenari, è necessario utilizzare certificati pubblici con estensione del nome file .cer. Tuttavia, Key Vault non supporta l'importazione e l'archiviazione di certificati di questo tipo come certificati Key Vault. In questi scenari, è consigliabile salvare il file .cer come stringa X.509 (.CER) con codifica Base-64. Quindi, in un segreto Key Vault, archivia la stringa che appare tra la riga **INIZIA CERTIFICATO** e la riga **FINE CERTIFICATO** nel file. Nell'ambiente di servizio, è consigliabile comunque creare un riferimento al record Key Vault e impostare il campo **Tipo** su **Certificato**.

## <a name="create-a-chain-of-certificates"></a>Creare una catena di certificati

Se le fatture specifiche del tuo paese/area geografica richiedono una catena di certificati per l'applicazione di firme digitali o per stabilire una connessione protetta (Secure Sockets Layer \[ SSL\]) a servizi Web esterni, creare una catena di certificati in cui i certificati sono nel seguente ordine:

1. Certificati radice
2. Certificati intermedi
3. Certificati per utenti finali

Le autorità di certificazione radice (CA) sono una fonte affidabile di certificati. I certificati CA intermedi sono bridge che collegano i certificati dell'utente finale ai certificati CA radice.

Per creare e configurare una catena di certificati, segui questi passaggi.

1. Nella pagina **Parametri Key Vault**, nel riquadro azioni seleziona **Catena di certificati**.
2. Seleziona **Nuovo** per creare una catena di certificati.
3. Nel campo **Nome** immettere il nome della catena di certificati.
4. Nel campo **Descrizione** immettere una descrizione.
5. Nella sezione **Certificati** seleziona **Aggiungi** per aggiungere un certificato alla catena.
6. Usa il pulsante **Su** o **Giù** per modificare la posizione del certificato nella catena. Mantieni il certificato radice CA in cima all'elenco e il certificato dell'utente finale in fondo.
7. Seleziona **Salva**.

È possibile creare un numero illimitato riferimenti Key Vault in RCS. Tieni presente che il segreto per il token SAS (Storage Shared Access Signature) viene utilizzato per collegare un determinato ambiente di servizio al riferimento Key Vault. È possibile fare riferimento ai certificati e ai segreti Key Vault archiviati in un Key Vault che contiene anche il segreto per il token SAS di archiviazione utilizzato durante la configurazione dell'ambiente di servizio.
