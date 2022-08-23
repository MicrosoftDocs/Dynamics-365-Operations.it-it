---
title: Configurazione della fatturazione elettronica
description: In questo articolo viene fornita una panoramica del processo di impostazione e configurazione della fatturazione elettronica.
author: gionoder
ms.date: 02/28/2022
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
ms.openlocfilehash: de94843c1e98a8788375bd41def587a64baea07d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272181"
---
# <a name="electronic-invoicing-setup"></a>Configurazione della fatturazione elettronica

[!include [banner](../includes/banner.md)]

In questo articolo viene fornita una panoramica del processo di impostazione e configurazione della fatturazione elettronica. È necessario completare i passaggi di configurazione nell'ordine specificato qui. Se un passaggio è obbligatorio, ma lo salti, la funzionalità non funzionerà correttamente e si verificheranno più errori durante i passaggi successivi o quando utilizzi la funzionalità. 

Prima di iniziare, assicurati che tutti i componenti principali siano configurati correttamente, di esserti registrato a Regulatory Configuration Service (RCS) e di disporre di un'istanza di RCS e che il componente aggiuntivo di fatturazione elettronica sia installato per il tuo ambiente Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management. Per altre informazioni, vedi [Registrarsi e installare la fatturazione elettronica](e-invoicing-install-add-in-microservices-lcs.md).

Quindi, configura le risorse di Azure necessarie per la fatturazione elettronica per svolgere il proprio lavoro. Per ulteriori informazioni, vedi [Impostare le risorse di Azure per la fatturazione elettronica](e-invoicing-set-up-azure-resources.md).

Dopo aver configurato i componenti principali, lavora con RCS per configurare i principali componenti logici della fatturazione elettronica. Innanzitutto, definisci il numero di ambienti di servizio che manterrai. In questo modo si definiscono i dati logici e il partizionamento della configurazione per assicurarsi di avere un confine tra un ambiente di sviluppo o test e gli ambienti di produzione. Per configurare il processo di sviluppo in modo flessibile, potrebbero essere necessari diversi ambienti di sviluppo e test separati. Oltre a definire gli ambienti di servizio, imposta un collegamento alle tue applicazioni aziendali, come Finance o Supply Chain Management, direttamente da RCS per configurare i parametri necessari per il corretto funzionamento con la fatturazione elettronica. Per ulteriori informazioni sugli ambienti, vedi [Ambienti di servizio](e-invoicing-service-environments.md).

Dopo aver configurato tutto, puoi creare le tue funzionalità di globalizzazione che definiscono diversi scenari per l'elaborazione di documenti elettronici e la trasformazione dei dati, o per l'importazione dei documenti dal repository globale. Per ulteriori informazioni su come lavorare con le funzionalità di globalizzazione, vedi [Lavorare con le funzionalità di globalizzazione](e-invoicing-working-globalization-features.md).

Se i tuoi scenari richiedono l'integrazione con e-mail o SharePoint per elaborare i documenti elettronici in entrata, vedi [Elaborazione dei documenti elettronici in entrata](e-invoicing-process-incoming-electronic-documents.md) per informazioni su come impostare e utilizzare tali canali.
