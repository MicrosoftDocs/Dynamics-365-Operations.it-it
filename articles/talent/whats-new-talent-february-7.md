---
title: Novità o modifiche in Dynamics 365 Talent (7 febbraio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c4005a8745e46a23fe16b94cab7b7aeb20f84035
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009764"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-7-2019"></a>Novità o modifiche in Dynamics 365 Talent (7 febbraio 2019)

[!include [banner](includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate di Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

### <a name="interview-scheduling-enhancements"></a>Miglioramenti alla programmazione dei colloqui
Dei miglioramenti sono stati apportati all'esperienza completa di programmazione dei colloqui. Ora è possibile visualizzare la disponibilità nel calendario di un candidato interno e utilizzare il calendario del candidato interno per suggerimenti di programmazione. Per ulteriori informazioni, vedere [Programmazione e riscontro del colloquio](interview-scheduling-feedback.md).

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a>Annunci di lavoro in LinkedIn - Problema di società non corrispondente risolto
Un'uscita è stata fissa dei processi registrati LinkedIn Attract stavano comparendo nel nome della società errato. Per ulteriori informazioni, vedere [Creazione, approvazione e pubblicazione di annunci di mansioni in Attract](creating-jobs-attract.md).

### <a name="career-site-url-displayed-in-admin-settings"></a>URL del sito di avanzamento professionale visualizzato nelle impostazioni di amministrazione
L'URL della home page del sito di avanzamento professionale è ora visualizzato in **Impostazioni di amministrazione** in **Gestione del sito per le possibilità di carriera**.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

**Build 8.1.2134**

### <a name="multiple-compensation-levels-supported-on-jobs"></a>Molteplici livelli retributivi più supportati nelle mansioni
Questa modifica consente la definizione di più livelli retributivi in una mansione, abilitando intervalli di retribuzione fissa dei dipendenti che possono differire tra i piani quando si utilizza la stessa mansione. 

Ad esempio:    
*Mansione* - *Livelli retributivi associati* account manager: B1 and B2 - Ogni livello ha un intervallo di valori definito. B1 = Min. 50.000, Interm. 60.000, Mass. 75.000 e B2= Min. 65.000, Interm. 74.000, Mass. 85.000. Durante la creazione della retribuzione fissa per i dipendenti, in base alle regole di idoneità definite, ciascun piano fisso può ora puntare alla stessa mansione e a livelli diversi nella mansione. Ciò consente la definizione di piani in aree geografiche/società definite, che puntano alla stessa mansione ma a intervalli diversi senza duplicare le mansioni nell'account per tali differenze.

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a>Il campo Livello retributivo è stato aggiunto all'entità Retribuzione fissa dipendente 
Con questo aggiornamento, l'entità Retribuzione fissa dipendente è stata aggiornata per includere il campo **Livello retributivo**. Questa aggiunta facilita l'aggiornamento i piani di retribuzione fissa dei dipendenti. 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a>Aggiornamento della famiglia di mansioni durante l'aggiornamento e la creazione di nuove posizioni
Quando si modifica una mansione in una posizione, verrà utilizzato il valore predefinito di **Famiglia di processi** in base alla mansione selezionata.

### <a name="performance-improvements-when-rendering-workspaces"></a>Miglioramento delle prestazioni durante il rendering delle aree di lavoro
La scheda Analisi nelle aree di lavoro verrà ora caricata quando si accede a tali pagine. Un indicatore verrà visualizzato durante il rendering iniziale della pagina nell'angolo in alto a sinistra della pagina.
