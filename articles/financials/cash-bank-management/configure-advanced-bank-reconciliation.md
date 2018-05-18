---
title: Processo di impostazione per la riconciliazione bancaria avanzata
description: "La funzionalità di riconciliazione bancaria avanzata consente di importare rendiconti bancari elettronici e riconciliarli automaticamente con le transazioni bancarie in Microsoft Dynamics 365 for Finance and Operations.  In questo articolo verrà spiegata l'impostazione dei processi per la riconciliazione."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: f77a9c927232c95558ba78037f6a6e9f77e202c2
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="advanced-bank-reconciliation-setup-process"></a>Processo di impostazione per la riconciliazione bancaria avanzata

[!include [banner](../includes/banner.md)]

La funzionalità di riconciliazione bancaria avanzata consente di importare rendiconti bancari elettronici e riconciliarli automaticamente con le transazioni bancarie in Microsoft Dynamics 365 for Finance and Operations.  In questo articolo verrà spiegata l'impostazione dei processi per la riconciliazione.  

È necessario impostare una serie di componenti prima di utilizzare la funzionalità di riconciliazione bancaria avanzata. Per ulteriori informazioni sull'impostazione dell'importazione dei rendiconti bancari, vedere [Impostare il processo di importazione dei rendiconti bancari](set-up-advanced-bank-reconciliation-import-process.md).  Di seguito sono descritti i requisiti per l'impostazione del processo di riconciliazione.

## <a name="transaction-codes"></a>Codici transazioni
I codici di transazione possono essere utilizzati come parte delle regole di abbinamento di riconciliazione bancaria.  I codici di transazione consentono di abbinare solo gli stessi tipi di transazioni tra Finance and Operations e il rendiconto bancario.  Per effettuare questo tipo di abbinamento, è innanzitutto necessario definire i tipi di transazione utilizzati per le transazioni bancarie da Finance and Operations, quindi mappare tali tipi ai codici di transazione di rendiconto utilizzati dalla banca.  I tipi di transazione per le transazioni bancarie di Finance and Operations sono definiti nella pagina **Tipo di transazione bancaria**.  In questa pagina è anche possibile definire il conto principale da utilizzare per le registrazioni associate a tale tipo di transazione. 

Una volta definiti i codici di transazione bancaria di Finance and Operations, è possibile mapparli ai codici di transazione utilizzati nei propri rendiconti bancari elettronici.  Questo processo di mapping verrà effettuato utilizzando la pagina **Mapping dei codici transazione**.  Il mapping dei codici di transazione viene completato separatamente per ciascun conto bancario.

## <a name="matching-rules-and-matching-rule-sets"></a>Regole di abbinamento e set di regole di abbinamento
Le regole di abbinamento consentono di definire i criteri per la riconciliazione automatica tra le transazioni bancarie di Finance and Operations e le transazioni del rendiconto bancario.  L'impostazione delle regole di abbinamento viene eseguita nella pagina **Regole di abbinamento della riconciliazione**.  Per ulteriori informazioni, vedere [Impostare le regole di abbinamento della riconciliazione bancaria](set-up-bank-reconciliation-matching-rules.md). 

I set di regole di abbinamento vengono utilizzati per definire un gruppo di regole di abbinamento che vengono eseguite in sequenza durante il processo di riconciliazione bancaria.  I set di regole di abbinamento sono configurati nella pagina **Set di regole di abbinamento della riconciliazione**.

## <a name="cash-and-bank-management-parameters"></a>Parametri di gestione cassa e banche
Esistono una serie di parametri specifici per il processo di riconciliazione bancaria avanzata nella pagina **Parametri di gestione cassa e banche**.  L'opzione **Mostra importo della riga di rendiconto nelle colonne Dare/Avere** modifica la visualizzazione degli importi nella pagina **Rendiconto bancario**.  Se questa opzione è selezionata, gli importi delle transazioni del rendiconto bancario vengono visualizzati in colonne di Dare e Avere separate.  Se non è selezionata, gli importi delle transazioni del rendiconto bancario appaiono in una colonna singola di importo con il segno appropriato. 

Le opzioni di convalida impostate nella pagina parametri sostituiscono le selezioni impostate nelle regole di abbinamento.  Ad esempio, non è possibile manualmente o automaticamente abbinare documenti oltre la differenza di date impostata nella scheda dei parametri.  Inoltre, se l'opzione **Convalida mapping tipo di transazione** è selezionata, i tipi di transazione devono essere mappati tra la transazione bancaria di Finance and Operations e la transazione del rendiconto bancario perché le transazioni vengano abbinate manualmente o automaticamente. 

È inoltre necessario configurare le sequenze numeriche necessarie nella pagina **Parametri di gestione cassa e banche**.  Nella scheda **Sequenze numeriche** impostare i codici di sequenza numerica per i riferimenti **ID download, ID rendiconto, ID riconciliazione e Riconciliazione bancaria**.

## <a name="bank-account-reconciliation-options"></a>Opzioni di riconciliazione dei conti bancari
È innanzitutto necessario abilitare la riconciliazione bancaria avanzata per il conto bancario.  Un numero di opzioni aggiuntive è disponibile nella pagina **Conto bancario** una volta attivata la funzionalità di riconciliazione bancaria avanzata. 

La funzionalità **Utilizza rendiconti bancari come conferma di pagamenti elettronici** integra le funzionalità di riconciliazione bancaria con gli stati di pagamento elettronico.  Quando è abilitata, un documento bancario verrà creato automaticamente per lo stato di pagamento elettronico impostato su **Inviato**.  Inoltre, verrà aggiornato lo stato di un pagamento elettronico da **Inviato** a **Ricevuto** dopo che il pagamento è abbinato, riconciliato e registrato. 

Il campo **Nome conto bancario nei rendiconti** è il nome utilizzato per il conto bancario nei rendiconti bancari elettronici.  Questo nome viene utilizzato per determinare le transazioni da importare per un conto bancario da un rendiconto che potrebbe contenere informazioni per più conti bancari. 

L'opzione **Riconcilia dopo l'importazione** automaticamente convalida il rendiconto bancario, crea una nuova riconciliazione bancaria e un foglio di lavoro ed esegue il set di regole di abbinamento predefinite.  Questa funzionalità rende automatico il processo fino al punto in cui le transazioni devono essere abbinate manualmente.  L'impostazione del conto bancario verrà automaticamente definita durante l'importazione.




