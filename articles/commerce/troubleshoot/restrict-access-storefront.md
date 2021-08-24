---
title: Limitare l'accesso a una vetrina durante il processo di test o sviluppo
description: In questo argomento viene descritto come limitare l'accesso a una vetrina di Microsoft Dynamics 365 Commerce durante il processo di test o sviluppo.
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
ms.openlocfilehash: db3317c01cab2e123f3c2927c359f9e00b98bd8a2d5e851c2c20cb4763db1c49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716785"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a>Limitare l'accesso a una vetrina durante il processo di test o sviluppo

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come limitare l'accesso a una vetrina di Microsoft Dynamics 365 Commerce durante il processo di test o sviluppo.

## <a name="description"></a>Descrizione

Durante il processo di test o sviluppo attivo interno, è possibile che si intenda limitare l'accesso al sito per impedire agli utenti esterni di accedere alle pagine della vetrina pubblicate.

## <a name="resolution"></a>Risoluzione

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a>Impostare Azure AD B2C utilizzando flussi utente standard

Per informazioni su come configurare Azure Active Directory B2C (Azure AD B2C) per il sito di e-commerce, vedere [Impostare un tenant B2C in Commerce](../set-up-b2c-tenant.md).

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a>Limitare l'accesso degli utenti alle pagine della vetrina e bloccare la creazione di nuovi utenti

Per limitare l'accesso degli utenti alle pagine della vetrina in Creazione di siti di Commerce, procedere come segue.

1. Accedere al sito.
1. Selezionare **Pagine**, quindi selezionare la pagina per la quale limitare l'accesso utente.
1. Selezionare lo slot del modulo o del frammento, quindi selezionare **Modifica**.
1. Nel riquadro delle proprietà selezionare **È necessario l'accesso?**, quindi selezionare **Fine la modifica**.
1. Selezionare **Pubblica**

Per bloccare la creazione di nuovi utenti in Azure AD, procedere come segue.

1. Accedi al [portale di Azure](https://portal.azure.com/).
1. Selezionare l'applicazione Azure AD B2C creata per l'accesso al sito.
1. Nel pannello di navigazione a sinistra, selezionare **Flussi utente**.
1. Nella parte superiore della pagina **Flussi utente**, selezionare **Nuovo flusso utente**.
1. Nella pagina **Seleziona un tipo di flusso utente**, selezionare **Anteprima**.
1. Al centro della pagina, selezionare **Accedi v2**. Quindi seguire i passaggi in [Impostare un tenant B2C in Commerce](../set-up-b2c-tenant.md) per configurare il flusso come flusso utente standard del sito per Azure AD B2C durante il processo di test o sviluppo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un tenant B2C in Commerce](../set-up-b2c-tenant.md)

[Impostare pagine personalizzate per l'accesso degli utenti](../custom-pages-user-logins.md)
