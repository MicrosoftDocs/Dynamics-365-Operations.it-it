---
title: Risoluzione dei problemi relativi all'ottimizzazione della pianificazione
description: Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori all'ottimizzazione della pianificazione.
author: ChristianRytt
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: bbf21abae60d4adee5a23a8405d14907b91724fa2cbf31c901bb46c589b2ea49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768097"
---
# <a name="troubleshoot-planning-optimization"></a>Risoluzione dei problemi relativi all'ottimizzazione della pianificazione 

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che potresti riscontrare mentre lavori all'ottimizzazione della pianificazione.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>L'installazione del componente aggiuntivo Ottimizzazione pianificazione non viene completata

Ottimizzazione pianificazione richiede un LCS (Lifecycle Services) abilitato, ambiente ad alta disponibilità di livello 2 o superiore (non un ambiente OneBox), con Dynamics 365 Supply Chain Management versione 10.0.7 o successiva. Se tenti di installare il componente aggiuntivo in un ambiente OneBox, l'installazione non verrà completata.

**Soluzione**: annulla l'installazione e utilizza un ambiente ad alta disponibilità, livello 2 o superiore (non un ambiente OneBox).

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>La pianificazione di processi batch non riesce quando è abilitata l'ottimizzazione della pianificazione

Quando abiliti l'ottimizzazione della pianificazione, il motore di pianificazione principale incorporato viene disabilitato automaticamente. I processi batch di pianificazione generale creati per il motore di pianificazione integrato in Supply Chain Management falliranno se vengono attivati mentre Ottimizzazione pianificazione è abilitata. Puoi ricevere un messaggio di errore come *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.

**Soluzione**: annulla tutti i processi batch di pianificazione generale creati per il motore di pianificazione integrato in Supply Chain Management.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>I risultati dell'ottimizzazione della pianificazione sono diversi dai risultati precedenti

L'ottimizzazione della pianificazione differisce dalla progettazione della pianificazione generale integrata in alcune aree. Ciò può anche essere causato da funzionalità in sospeso.

**Soluzione**: esegui l'analisi dell'adattamento dell'ottimizzazione della pianificazione, quindi analizza i risultati facendo riferimento alla documentazione correlata per comprenderne l'impatto. Per ulteriori informazioni, vedere [Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md).

## <a name="cant-enable-planning-optimization"></a>Impossibile abilitare l'ottimizzazione della pianificazione

**Stato connessione** deve essere **Connesso** prima di poter configurare **Usa ottimizzazione di pianificazione** su **Sì**. Per ulteriori informazioni, vedere [Introduzione all'ottimizzazione di pianificazione](get-started.md).

**Soluzione**: assicurati che il componente aggiuntivo Ottimizzazione pianificazione sia stato installato correttamente.

## <a name="error-message-is-shown-during-ctp"></a>Il messaggio di errore viene visualizzato durante CTP

Se tenti di eseguire CTP (capable to promise) da un ordine cliente quando Ottimizzazione pianificazione è abilitato, riceverai il seguente messaggio di errore: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.

Ciò è correlato a una funzionalità in sospeso pianificata come parte del supporto per gli ordini di produzione.

**Soluzione:** evita i calcoli CTP quando Ottimizzazione pianificazione è abilitata fino a quando è disponibile il supporto CTP.

## <a name="additional-resources"></a>Risorse aggiuntive

[Introduzione all'ottimizzazione della pianificazione](get-started.md)

[Analisi corrispondenza Ottimizzazione pianificazione](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]