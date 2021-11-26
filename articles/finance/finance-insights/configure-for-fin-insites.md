---
title: Configurazione per Finance Insights
description: In questo argomento vengono illustrati i passaggi di configurazione che consentiranno al sistema di utilizzare le funzionalità disponibili in Finance Insights.
author: ShivamPandey-msft
ms.date: 1/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 5668d3ddff777645b4f1c6608f025d0c5a63208a
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752980"
---
# <a name="configuration-for-finance-insights"></a>Configurazione per Finance Insights

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Finance Insights combina le funzionalità di Microsoft Dynamics 365 Finance con Dataverse, Azure e AI Builder per fornire potenti strumenti di previsione per la tua organizzazione. In questo argomento vengono illustrati i passaggi di configurazione che consentiranno al sistema di utilizzare le funzionalità disponibili in Finance Insights. Per completare correttamente le procedure in questo argomento, è necessario disporre dell'accesso come amministratore di sistema e addetto alla personalizzazione del sistema nell'[interfaccia di amministrazione di Power Portal](https://admin.powerplatform.microsoft.com/), dell'accesso come amministratore di sistema in Dynamics 365 Finance e dell'accesso per creare ambienti in Microsoft Dynamics Lifecycle Services (LCS).

> [!NOTE]
> Le seguenti procedure per l'impostazione di Finance Insights sono valide per Dynamics 365 Finance versione 10.0.21 e successive.

## <a name="deploy-dynamics-365-finance"></a>Distribuire Dynamics 365 Finance

Attieniti a questa procedura per distribuire gli ambienti.

1. In LCS, crea o aggiorna un ambiente Dynamics 365 Finance. L'ambiente richiede la versione dell'app 10.0.21 o successiva.

    > [!NOTE]
    > L'ambiente deve essere un ambiente ad alta disponibilità (HA). (Questo tipo di ambiente è noto anche come ambiente Tier-2). Per altre informazioni, vedi [Pianificazione ambientale](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

2. Se stai configurando Finance Insights in un ambiente sandbox, potresti dover copiare i dati di produzione in tale ambiente affinché le stime funzionino. Il modello di stima utilizza più anni di dati per creare previsioni. I dati della demo di Contoso non contengono dati storici sufficienti per addestrare adeguatamente il modello di stima. 

## <a name="configure-dataverse"></a>Configura Dataverse

Segui questa procedura per configurare Dataverse per Finance insights.

- In LCS, apri la pagina dell'ambiente e verifica che la sezione **Integrazione di Power Platform** sia già configurata.

    - Se è già configurata, il nome dell'ambiente Dataverse collegato all'ambiente Finance dovrebbe essere incluso nell'elenco.
    - In caso contrario, seleziona **Configura**. La configurazione dell'ambiente Dataverse potrebbe richiedere fino a un'ora. Quando la configurazione è completata, il nome dell'ambiente Dataverse collegato all'ambiente Finance dovrebbe essere incluso nell'elenco.

## <a name="configure-the-finance-insights-add-in"></a>Configurare il componente aggiuntivo Finance Insights

Se in precedenza hai installato il componente aggiuntivo Finance Insights, disinstallalo prima di completare la procedura seguente.

> [!NOTE]
> Se hai già installato il componente aggiuntivo data lake in LCS, Finance Insights lo utilizzerà per salvare i dati necessari per le previsioni. Se non hai ancora installato il componente aggiuntivo data lake in LCS, il componente aggiuntivo Finance Insights creerà per te un data lake gestito.

Segui questi passaggi per installare il componente aggiuntivo Finance Insights.

1. Accedi a LCS, quindi, sotto il nome dell'ambiente sul lato destro della pagina, seleziona **Dettagli completi**.
2. Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.
3. Seleziona il componente aggiuntivo **Finance Insights**.
4. Accetta le condizioni, quindi seleziona **Installa**.

L'installazione del componente aggiuntivo potrebbe richiedere diversi minuti.

## <a name="one-last-thing"></a>Un'ultima cosa...

Dopo che il componente aggiuntivo è stato installato correttamente, potrebbe essere necessaria fino a un'ora prima che tu possa abilitare le funzionalità di Finance insights nell'area **Gestione funzionalità** in Dynamics 365 Finance. Se non vuoi aspettare così a lungo, puoi eseguire manualmente il processo **Verifica stato provisioning di Insights**. 

1. In Dynamics 365 Finance, vai a **Amministratore di sistema \> Imposta \> Automazione del processo**.
2. Nella scheda **Processi in background**, trova **Verifica stato provisioning di Insights** e seleziona **Modifica**.
3. Imposta il campo **Esecuzione successiva** su 30 minuti prima dell'ora corrente.

   Questa modifica dovrebbe forzare l'esecuzione immediata del processo **Verifica stato provisioning di Insights**.

   Dopo l'esecuzione del processo **Verifica stato provisioning di Insights**, puoi abilitare le funzionalità di Finance Insights nell'area di lavoro **Gestione funzionalità**.

## <a name="feedback-and-support"></a>Feedback e supporto

Se vuoi fornire un feedback o hai bisogno di supporto, invia un'e-mail a [Finance Insights (anteprima)](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
