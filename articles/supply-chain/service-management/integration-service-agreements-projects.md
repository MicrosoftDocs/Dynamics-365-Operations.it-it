---
title: Integrazione per contratti e progetti di servizio
description: Quando si gestiscono contratti di assistenza e righe dei contratti di assistenza, vengono utilizzati i dati impostati nelle aree di Gestione progetti e contabilità.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 578e4b9fe5ef487e999fd0de28d7566bad21fd89
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431367"
---
# <a name="integration-for-service-agreements-and-projects"></a>Integrazione per contratti e progetti di servizio 

[!include [banner](../includes/banner.md)]


Quando si gestiscono contratti di assistenza e righe dei contratti di assistenza, vengono utilizzati i dati impostati nelle aree di **Gestione progetti e contabilità** riportate di seguito.

## <a name="project-prices"></a>Prezzi progetto

Il prezzo di costo e di vendita per una transazione di contratto di assistenza derivano dall'impostazione del prezzo di costo applicata al progetto collegato al contratto di assistenza. I prezzi di costo e di vendita possono essere impostati per progetto, per dipendente e per categoria. 

## <a name="project-validation"></a>Convalida progetto

I progetti, i dipendenti e le categorie disponibili per la selezione in una riga del contratto di assistenza possono essere limitati dall'impostazione di convalida in **Gestione progetti e contabilità**. Utilizzando l'impostazione di convalida è possibile combinare dipendenti, progetti e categorie per l'accesso del controllo. 

## <a name="project-line-properties"></a>Proprietà di riga del progetto

Per una riga del contratto di assistenza viene immessa automaticamente una proprietà di riga.

Le proprietà di riga vengono create nel modulo **Proprietà riga** in **Gestione progetti e contabilità**. La proprietà di riga immessa in un contratto di assistenza è collegata al progetto selezionato per il contratto di assistenza e successivamente ereditata dalla riga del contratto di assistenza. 

## <a name="default-offset-accounts"></a>Conti di contropartita predefiniti

Se si immette una transazione di spesa, per la transazione viene selezionato automaticamente un conto spese di contropartita predefinito. Il conto spese di contropartita predefinito viene impostato per il progetto collegato al contratto di assistenza corrente.

## <a name="project-categories"></a>Categorie di progetti

Le categorie disponibili per le righe del contratto di assistenza vengono impostate nel modulo **Categorie di progetto** in **Gestione progetti e contabilità**. 

> [!NOTE]
> <P>Sono disponibili per la selezione le categorie con la casella di controllo <STRONG>Attivo nei giornali di registrazione</STRONG> selezionata nella scheda <STRONG>Progetto</STRONG> del modulo <STRONG>Categorie di progetto</STRONG>. Se la casella di controllo <STRONG>Categorie inattive</STRONG> nella scheda <STRONG>Giornali di registrazione</STRONG> del modulo <STRONG>Parametri Gestione progetti e contabilità</STRONG> è selezionata, tuttavia, tutte le categorie sono disponibili per la selezione.</P>

## <a name="project-parameters"></a>Parametri progetto

Se il campo **Lavoratori con rapporto chiuso** della scheda **Giornali di registrazione** del modulo **Parametri Gestione progetti e contabilità** è selezionata, è possibile selezionare i dipendenti inattivi e quelli attivi nei moduli **Ordini di assistenza** e **Contratti di assistenza**.

È inoltre possibile attivare i campi **Ora di inizio** e **Ora di fine** della scheda **Progetto** nel modulo **Ordini di assistenza** per immettere le ore di inizio e di fine nelle righe dell'ordine di assistenza.

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a>Attivare la funzionalità delle ore di inizio e di fine per gli ordini di assistenza

1.  Fare clic su **Gestione progetti e contabilità** \> **Impostazione** \> **Parametri Gestione progetti e contabilità**.

2.  Fare clic sulla scheda **Giornali di registrazione** e selezionare la casella di controllo **Mostra ora di inizio/fine**.

3.  Fare clic su **Gestione progetti e contabilità** \> **Impostazione** \> **Giornali di registrazione** \> **Nomi giornale di registrazione**.

4.  Selezionare il nome di giornale di registrazione collegato all'ordine di assistenza.

5.  Fare clic sulla scheda **Generale** e selezionare la casella di controllo **Mostra ora di inizio/fine**.


> [!NOTE]
> <P>Selezionare il nome di giornale di registrazione per l'ordine di assistenza nel campo <STRONG>Ora</STRONG> della scheda <STRONG>Giornali di registrazione</STRONG> nel modulo <STRONG>Parametri di gestione assistenza</STRONG>.</P>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]