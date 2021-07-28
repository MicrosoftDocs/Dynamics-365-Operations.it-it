---
title: Configurare un ambiente di sviluppo di e-commerce per eseguire il debug su una macchina virtuale Retail Server di livello 1
description: Questo argomento descrive come configurare un ambiente di sviluppo di e-commerce per eseguire il debug su una macchina virtuale (VM) Retail Server di livello 1
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 892f8001c52cd40d748c81f27c2f83618b84e5c2
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350404"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a>Configurare un ambiente di sviluppo di e-commerce per eseguire il debug su una macchina virtuale Retail Server di livello 1

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come configurare un ambiente di sviluppo di e-commerce per eseguire il debug su una macchina virtuale (VM) Retail Server di livello 1

## <a name="description"></a>Descrizione

Gli ambienti Microsoft Dynamics 365 Commerce di livello 1 sono in genere distribuiti per lo sviluppo di Commerce Runtime (CRT) e dell'estensione POS. Si tratta di ambienti autonomi. A seguito della natura SaaS (Software as a Service) dell'architettura, non includono componenti di e-commerce.

In alcuni scenari, è possibile che si intenda testare le chiamate alle estensioni in un ambiente di livello 1, in modo da poter eseguire il debug delle estensioni dai componenti di e-commerce. Per istruzioni generali, vedere [Debug di un ambiente di sviluppo di Commerce di livello 1](../e-commerce-extensibility/debug-tier-1.md).

Quando si esegue il debug in un ambiente di livello 1, poiché il sito ora chiama un Retail Server diverso, le chiamate tra server potrebbero causare vari errori correlati ai criteri di protezione del contenuto.

La seguente illustrazione mostra un esempio di errore che potrebbe verificarsi quando una variante viene selezionata in una pagina dei dettagli del prodotto.

![Errore durante la selezione di una variante in una pagina dei dettagli del prodotto.](media/unhandled-rejection-error.jpg)

L'illustrazione seguente mostra un esempio di errore simile negli strumenti di debug di un browser (Strumenti di sviluppo F12). Il messaggio di errore menziona la violazione della direttiva sui criteri di sicurezza del contenuto.

![Errore degli strumenti di debug.](media/debugger-tools-error.JPG)

## <a name="resolution"></a>Risoluzione

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a>Disabilitare i criteri di sicurezza del contenuto per il sito in Creazione di siti di Commerce

1. Selezionare il sito sul quale si sta lavorando.
1. Selezionare **Impostazioni**, quindi selezionare **Estensioni**.
1. Nella scheda **Criteri di sicurezza dei contenuti**, selezionare **Disabilita criteri di sicurezza del contenuto**.
1. Seleziona **Salva e pubblica**.

> [!NOTE]
> L'accesso business-to-consumer (B2C) non funzionerà in un ambiente di sviluppo locale. Tuttavia, è possibile utilizzare checkout guest o creare simulazioni di pagine per simulare l'accesso utente come richiesto.

## <a name="additional-resources"></a>Risorse aggiuntive

[Introduzione allo sviluppo dell'estensibilità online dell'e-commerce](../e-commerce-extensibility/sdk-getting-started.md)

[Gestire criteri di sicurezza dei contenuti nel sito di e-commerce](../manage-csp.md)
