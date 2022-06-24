---
title: Impossibile accedere al servizio imposte
description: Questo articolo spiega come risolvere un problema di accesso al servizio Calcolo imposte.
author: hangwan
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 02/16/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 65d819b97be3d1238bc0ecfc201b4e24edac8616
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861224"
---
# <a name="failed-to-access-tax-service"></a>Impossibile accedere al servizio imposte

[!include [banner](../includes/banner.md)]


In questo articolo viene spiegato come correggere l'errore "Impossibile accedere al servizio imposte" del servizio Calcolo imposte.

## <a name="symptoms"></a>Sintomi

In Microsoft Dynamics 365 Finance, vai a **Imposta** \> **Configura** \> **Configurazione fiscale** \> **Parametri del servizio fiscale**. Nella scheda **Generale**, abilita l'opzione **Abilita calcolo imposte**. Se tenti di selezionare un valore nel campo **Nome della configurazione della funzione**, si verifica un errore. Il messaggio di errore indica "Impossibile accedere al servizio fiscale".

## <a name="cause"></a>Causa

Questo errore si verifica perché Finance non può accedere al servizio di calcolo delle imposte.

## <a name="resolution"></a>Risoluzione 

1. Accedere a Microsoft Dynamics Lifecycle Services (LCS).
2. Nella pagina **Ambiente**, nella scheda **Componenti aggiuntivi per l'ambiente**, trova l'elemento **Calcolo imposte** e verificarne lo stato. Lo stato dovrebbe essere **Installazione in corso** o **Installato**. Se il componente aggiuntivo del servizio di calcolo delle imposte non è installato, riceverai l'errore.

## <a name="mitigation"></a>Attenuazione

1. In LCS, nella pagina **Finanza** e nella sezione **Integrazione di Power Platform**, seleziona **Installa un nuovo componente aggiuntivo**.
2. Scorri fino in fondo alla pagina e seleziona il componente aggiuntivo **Calcolo imposte** per installarlo.
3. Torna al tuo ambiente Finance e prova ad accedere al servizio di Calcolo imposte.

> [!NOTE]
> Prima di installare il servizio di calcolo delle imposte, rivedi i [prerequisiti del servizio di calcolo delle imposte](global-get-started-with-tax-calculation-service.md#prerequisites).
> 
> Se non riesci a installare il componente aggiuntivo perché la sezione **Integrazione di Power Platform** non è disponibile, vedi [Panoramica del componente aggiuntivo](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Se si verifica ancora l'errore dopo aver installato il componente aggiuntivo, contattare l'amministratore di sistema.
