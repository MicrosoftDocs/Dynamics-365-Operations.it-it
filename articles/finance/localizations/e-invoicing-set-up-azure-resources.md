---
title: Configurare le risorse di Azure per la fatturazione elettronica
description: In questo articolo viene fornita una panoramica del processo di configurazione delle risorse di Microsoft Azure della fatturazione elettronica.
author: dkalyuzh
ms.date: 01/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: c5b7b2ca4d7733fb1c75ded8798655699284fe1a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907731"
---
# <a name="set-up-azure-resources-for-electronic-invoicing"></a>Configurare le risorse di Azure per la fatturazione elettronica

[!include [banner](../includes/banner.md)]

Il processo per la configurazione delle risorse di Microsoft Azure per la fatturazione elettronica prevede tre fasi. I primi due passaggi, "Creare un Azure Key Vaulti nel portale di Azure" e "Creare un account di archiviazione di Azure nel portale di Azure", sono obbligatori. Il terzo passaggio, "Configurare una connessione di SharePoint", è facoltativo.

## <a name="create-an-azure-key-vault-in-the-azure-portal"></a>Creare un Azure Key Vault nel portale di Azure

Crea un Key Vault nell'abbonamento di Azure. È consigliabile creare un Key Vault separato per la fatturazione elettronica e di non combinare i segreti con altre applicazioni. Crea tutti i segreti e i certificati necessari per i tuoi scenari in documenti elettronici. È necessario creare almeno un segreto per archiviare il token di firma di accesso condiviso (SAS) dell'account di archiviazione di Azure che verrà creato nel passaggio successivo.

Per informazioni su come completare questo passaggio, vedi [Creare un Azure Key Vault nel portale di Azure](e-invoicing-create-azure-key-vault-azure-portal.md).

## <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Creare un account di archiviazione di Azure nel portale di Azure

Sei proprietario di tutti i documenti e file elettronici generati dal servizio di fatturazione elettronica o che accedono al servizio. Tali documenti e file vengono archiviati in un account di archiviazione di Azure creato nella sottoscrizione di Azure. Il servizio accederà al tuo account di archiviazione utilizzando il token SAS importato dal tuo segreto Key Vault.

Per informazioni su come completare questo passaggio, vedi [Creare un account di archiviazione di Azure nel portale di Azure](e-invoicing-create-azure-storage-account-azure-portal.md).

## <a name="configure-a-sharepoint-connection"></a>Configurare una connessione SharePoint

In alcuni scenari, potrebbe essere necessario salvare file elettronici in SharePoint e recuperarli da SharePoint. Per fare in modo che il servizio di fatturazione elettronica possa accedere alle tue cartelle SharePoint, configura l'accesso a SharePoint.

Per informazioni su come completare questo passaggio, vedi [Configurare una connessione di SharePoint](e-invoicing-create-sharepoint-connection.md).
