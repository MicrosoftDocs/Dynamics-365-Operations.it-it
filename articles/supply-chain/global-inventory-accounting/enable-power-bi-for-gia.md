---
title: Abilitare Power BI per contabilità inventario globale
description: Questo articolo descrive come abilitare Microsoft Power BI per la contabilità dell'inventario globale.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 757d969cf9d1ebc12aeb34b0810fc291e47dffad
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906068"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a>Abilitare Power BI per contabilità inventario globale

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

Puoi aggiungere riquadri, dashboard e report dal tuo account [PowerBI.com](https://powerbi.com/) nella tua area di lavoro dell'applicazione Microsoft Dynamics 365.

## <a name="prerequisites"></a>Prerequisiti

I seguenti prerequisiti devono essere presenti prima di poter abilitare la creazione di report Power BI:

- Devi essere un amministratore di sistema nell'applicazione Dynamics 365.
- Devi avere un account [PowerBI.com](https://powerbi.com/).
- Devi avere almeno un dashboard e un report nel tuo account Power BI.
- Devi essere un amministratore per il tuo account Azure Active Directory (Azure AD).
- Il dominio Azure AD deve essere lo stesso che hai usato per il tuo account [PowerBI.com](https://powerbi.com/).

## <a name="setup"></a>Attrezzaggio

Seguire questi passaggi per configurare Power BI.

1. Accedi a [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Vai a **Raccolta di risorse condivise**, seleziona **Modello di report Power BI** come tipo di risorsa e scarica il pacchetto **Contabilità inventario globale**. 
1. Accedi a [PowerBI.com](https://app.powerbi.com/), e carica il file di report Power BI **Contabilità inventario globale** seguendo questi passaggi:

    1. Selezionare **Nuovo**.
    1. Seleziona **Carica un file**.
    1. Seleziona il file di report Power BI **Contabilità inventario globale**.

1. Configura il report Power BI **Contabilità inventario globale** seguendo questi passaggi:

    1. Vai a **Area di lavoro personale**, trova il set di dati per Contabilità inventario globale, quindi, sul menu **Opzioni** seleziona **Impostazioni**.
    1. In **Impostazioni per Contabilità inventario globale**, espandi **Parametri** e aggiorna tutti i parametri come richiesto. In particolare, assicurati di controllare le seguenti impostazioni:
        1. Sovrascrivi i valori predefiniti **URL Dataverse** usando i valori trovati in **Informazioni sull'ambiente Power Platform** in LCS (nella sezione **Integrazione di Power Platform**).
        1. Sovrascrivi i valori predefiniti **ID ambiente** utilizzando i valori trovati in **Dettagli ambiente** in LCS (nella sezione **Gestione ambiente**).
        1. Seleziona il collegamento **Modifica credenziali** accanto all'etichetta **CDS** nella sezione **Credenziali dell'origine dati**. Quindi accedi al tuo account Dataverse utilizzando il metodo di autenticazione **OAuth2**.
    1. Verificare che i report Power BI trovati in **Area di lavoro personale \> Report \> Contabilità inventario globale** ora funzionano correttamente e visualizzano il contenuto dal tuo sistema.

1. Registra l'applicazione come descritto in [Configurare l'integrazione di PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).
1. Integra il file di report Power BI **Contabilità inventario globale** in Dynamics 365 Supply Chain Management seguendo questi passaggi:

    1. Accedere a **Amministrazione sistema \> Impostazioni \> Configurazione PowerBI.com**.
    1. Seleziona **Modifica**.
    1. Seleziona **Abilita integrazione PowerBI.Com**.
    1. Nel campo **ID applicazione** immetti l'ID applicazione.
    1. Nel campo **Chiave applicazione** immetti la chiave dell'applicazione.
    1. Selezionare **Salva**.

1. Aggiorna la pagina in modo che viene visualizzata la finestra di dialogo di accesso Power BI.
1. Nella scheda **Opzioni** seleziona **Apri catalogo di report**, quindi seleziona il file di report Power BI **Contabilità inventario globale** che hai caricato in precedenza.
1. Aggiorna la pagina. Dovresti vedere che il tuo report è stato aggiunto.
1. In **Report Power BI**, seleziona il collegamento **Contabilità inventario globale**.

Per ulteriori informazioni, vedi [Configurare l'integrazione di PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).
