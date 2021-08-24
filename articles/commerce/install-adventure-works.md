---
title: Installare il tema Adventure Works
description: Questo argomento descrive come installare il tema Adventure Works in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ad704c6c3b95abcfd52e449a0ffbb4b82b236498ae8d2775c4e65811de3ef503
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763838"
---
# <a name="install-the-adventure-works-theme"></a>Installare il tema Adventure Works

[!include [banner](includes/banner.md)]

Questo argomento descrive come installare il tema Adventure Works in Microsoft Dynamics 365 Commerce. 

> [!IMPORTANT]
> Il tema Adventure Works e i moduli sono disponibili a partire dalla versione 10.0.20 di Dynamics 365 Commerce. Sono disponibili da Microsoft AppSource.

## <a name="prerequisites"></a>Prerequisiti

Prima di installare il tema Adventure Works, devi avere un ambiente Dynamics 365 Commerce (versione Commerce 10.0.20 o successiva) che include Retail Cloud Scale Unit (RCSU), l'SDK di Commerce online e la libreria dei moduli Commerce. Per informazioni su come installare l'SDK di Commerce e la libreria dei moduli, vedi [Aggiornamenti dell'SDK e della libreria dei moduli](e-commerce-extensibility/sdk-updates.md). 

## <a name="installation-steps"></a>Passaggi di installazione

### <a name="install-the-adventure-works-theme-in-your-application"></a>Installare il tema Adventure Works nell'applicazione

Il pacchetto di temi Adventure Works è disponibile nel feed **dynamics365-commerce**, come **@msdyn365-commerce-theme/adventureworks-theme-kit**. Tuttavia, anche se il pacchetto del tema Adventure Works fa parte di quel feed, si trova in uno spazio dei nomi diverso. Pertanto, è necessario seguire questi passaggi per aggiungere le voci del Registro di sistema per lo spazio dei nomi.

1. Aggiorna il file **.npmrc** in modo che includa la seguente voce del Registro di sistema (se la voce non è già inclusa):

    `@msdyn365-commerce-theme:registry=https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/`

1. Aggiorna il file **.yarnrc** in modo che includa la seguente voce del Registro di sistema (se la voce non è già inclusa):

    `"@msdyn365-commerce-theme:registry" "https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/"`  
    
Per installare il pacchetto nel tuo ambiente locale, esegui il comando seguente dal prompt dei comandi. Questo comando aggiorna automaticamente il file package.json in modo che includa la dipendenza.

`yarn add @msdyn365-commerce-theme/adventureworks-theme-kit`

Nel file **package.json** devi aggiornare la versione del tema a una versione specifica.

> [!IMPORTANT]
> - La versione del tema deve corrispondere alla versione della libreria dei moduli per garantire che tutte le funzionalità funzionino come previsto. 
> - La versione minima per la libreria dei moduli Commerce e l'SDK è 10.0.20 (9.31). 

### <a name="add-the-font-files-for-the-adventure-works-theme"></a>Aggiungere i file dei caratteri per il tema Adventure Works

Dopo aver installato il tema Adventure Works nella tua app, devi aggiungere i file di caratteri necessari. Per completare questo passaggio, copia tutti i file dei caratteri da **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\public\webfonts** al percorso della directory pubblica dell'applicazione partner **\public\webfonts**.

### <a name="set-up-the-resources-for-the-adventure-works-theme"></a>Impostare le risorse per il tema Adventure Works

Il passaggio successivo consiste nell'aggiornare la risorsa predefinita richiesta per il tema. Per completare questo passaggio, copia il contenuto dal file global.json in **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\resources\modules** nel file global.json dell'applicazione partner in **\src\resources\modules**. Se la directory di destinazione **\src\resources** non esiste, può essere copiata nella sua interezza dalla directory di origine **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks** nella directory di destinazione **\src**.

### <a name="pull-updates-and-validate-the-theme"></a>Eseguire il pull degli aggiornamenti e convalidare il tema

Per informazioni su come eseguire il pull dell'SDK più recente, della libreria di moduli e di altri aggiornamenti delle dipendenze, vedi la sezione "Pull degli aggiornamenti" di [Aggiornamenti dell'SDK e della libreria dei moduli](e-commerce-extensibility/sdk-updates.md#pull-updates).

Dopo che le ultime dipendenze sono state sottoposte al pull, puoi eseguire il comando **yarn start** per avviare il server Nodo nel tuo ambiente di sviluppo e testare il nuovo tema Adventure Works. Sfoglia l'applicazione localmente utilizzando il parametro della stringa di query `?theme=adventureworks` (ad esempio, `https://localhost:4000/?theme=adventureworks`).

## <a name="additional-resources"></a>Risorse aggiuntive

[Tema Adventure Works](adventure-works-theme.md)

[Panoramica della libreria moduli](starter-kit-overview.md)

[SDK e aggiornamenti della libreria moduli](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
