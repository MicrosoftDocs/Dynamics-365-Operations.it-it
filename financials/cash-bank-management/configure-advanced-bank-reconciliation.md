---
title: Panoramica sulla riconciliazione bancaria avanzata
description: "La riconciliazione estratti conto avanzata consente di importare i rendiconti bancari elettronici e riconciliate automaticamente con transazioni bancarie in Microsoft Dynamics 365 per le operazioni.  In questo articolo verrà spiegata l&quot;impostazione dei processi per la riconciliazione."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: c2fc9e858f61d7d0122393bbf306ba64ac3659b8
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Panoramica sulla riconciliazione bancaria avanzata

La riconciliazione estratti conto avanzata consente di importare i rendiconti bancari elettronici e riconciliate automaticamente con transazioni bancarie in Microsoft Dynamics 365 per le operazioni.  In questo articolo verrà spiegata l'impostazione dei processi per la riconciliazione.  

Sono presenti una serie di pezzi che devono essere impostati prima di utilizzare la funzionalità avanzata di riconciliazione estratti conto. Per ulteriori informazioni sull'inclusione di rendiconto bancario dell'impostazione, vedere [impostare il processo di importazione] di rendiconto bancario (setup-advanced-bank-reconciliation-import-process.md).  I requisiti di impostazione del processo di riconciliazione vengono dettagliati di seguito.

## <a name="transaction-codes"></a>Codici transazioni
I codici delle transazioni possono essere utilizzati come parte delle regole di abbinamento di riconciliazione estratti conto.  I codici transazione consentano di abbinare solo gli stessi tipi di transazioni tra Dynamics 365 per le operazioni e il rendiconto bancario.  Per effettuare questo tipo di abbinamento, è necessario definire i tipi di transazione utilizzati per le transazioni bancarie da Dynamics 365 per le operazioni, quindi mapparli tali tipi ai codici transazioni utilizzati di rendiconto dalla banca.  I tipi di transazioni per Dynamics 365 per le transazioni bancarie delle operazioni vengono definiti ** tipo di transazione bancaria ** nella pagina.  Corrisponde anche possibile definire il conto principale da utilizzare per le registrazioni correlate al tipo di transazione. 

Dopo che il proprio Dynamics 365 per i codici transazione bancaria delle operazioni è definito, quindi mapparli quelli ai codici transazioni utilizzati nei rendiconti bancari elettronici.  Questo processo di mapping verrà effettuata utilizzando ** mapping di codice transazione ** della pagina.  Il mapping di codice transazione vengono impostate separatamente per ciascun conto bancario.

## <a name="matching-rules-and-matching-rule-sets"></a>Regole di abbinamento e set di regole di abbinamento
Le regole di abbinamento consentono di definire i criteri per la riconciliazione automatica tra Dynamics 365 per le transazioni bancarie le operazioni e le transazioni di rendiconto bancario.  Le impostazioni delle regole di abbinamento è ** regole di corrispondenza di riconciliazione ** pagina sopra effettuata.  Per ulteriori informazioni, vedere [impostare le regole di abbinamento] di riconciliazione estratti conto (setup-bank-reconciliation-matching-rules.md). 

I set di regole di abbinamento vengono utilizzati per definire un gruppo di regole di corrispondenza che vengono eseguite nell'intervallo durante il processo di riconciliazione estratti conto.  I set di regole di abbinamento vengono configurati ** set di regole di abbinamento di riconciliazione ** nella pagina.

## <a name="cash-and-bank-management-parameters"></a>Parametri di gestione cassa e banche
Sono presenti una serie di parametri specifici al processo di riconciliazione estratti conto avanzato ** incasso e i parametri di gestione ** nella pagina.  ** Visualizza l'importo della riga rendiconto in Dare/Avere ** le modifiche la visualizzazione degli importi ** rendiconto bancario ** nella pagina.  Se questa opzione è selezionata, gli importi delle transazioni di rendiconto bancario vengono visualizzati nelle colonne distinte in Dare e in Avere.  Se l'opzione non è selezionata, gli importi delle transazioni di rendiconto bancario verranno visualizzati in un unico importo della colonna con il segno appropriato. 

Le opzioni di convalida impostate nella pagina dei parametri prevalgono su quelle selezionare impostate nelle regole di abbinamento.  Ad esempio, si potrebbe non corrispondere manualmente o automaticamente i documenti oltre a quelle della differenza di date nella pagina dei parametri.  Inoltre, se l'opzione ** convalidare il tipo di transazione mappare ** è selezionata, tipi di transazioni devono essere mappati tra Dynamics 365 per le operazioni transazione bancaria e la transazione di rendiconto bancario in modo che le transazioni associare manualmente o automaticamente. 

È inoltre necessario configurare le sequenze numeriche necessarie ** incasso e i parametri di gestione ** nella pagina.  ** Sequenze numeriche ** nella scheda, impostare i codici di sequenza numerica per il download ** l'identificazione, l'ID del rendiconto, riconciliare l'identificazione e la riconciliazione degli estratti conto ** riferimenti.

## <a name="bank-account-reconciliation-options"></a>Opzioni di riconciliazione dei conti bancari
È innanzitutto necessario attivare la riconciliazione degli estratti conto avanzata per il conto bancario.  Serie di opzioni aggiuntive sono disponibili ** conto bancario ** nella pagina dopo che la funzionalità avanzata di riconciliazione estratti conto è attivata. 

** Utilizzare i rendiconti bancari come conferma di pagamento elettronico ** la funzionalità integra la funzionalità di riconciliazione estratti conto con le condizioni di pagamento elettronico.  Se questa opzione è attivata, un documento bancario verrà creato automaticamente per lo stato di pagamento elettronico è impostato su ** ** inviato.  Inoltre, lo stato di un pagamento elettronico verrà aggiornato a ** ** inviato a ** ** ricevuto dopo che il pagamento è associato, riconciliato e registrata. 

** Nome del conto bancario nei rendiconti ** il campo è il nome utilizzato per il conto bancario sui rendiconti bancari elettronici.  Viene utilizzato determina quando le transazioni da includere per un conto bancario da un rendiconto contenente le informazioni relative a più conti bancari. 

L'opzione a ** riconciliare dopo l'importazione ** convalidati automaticamente il rendiconto bancario, verrà creata una nuova riconciliazione estratti conto e foglio di lavoro ed esegue il set di regole di abbinamento predefinito.  Questa funzionalità viene automatizzato il processo fino al passaggio alle transazioni che devono essere associati manualmente.  L'impostazione per il conto bancario impostazione predefinita durante l'importazione.


