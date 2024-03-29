---
title: Risoluzione dei problemi relativi all'ottimizzazione della pianificazione
description: Questo articolo descrive come risolvere i problemi che potresti riscontrare mentre lavori all'ottimizzazione della pianificazione.
author: t-benebo
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
ms.author: benebotg
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 37c38ab9cec8ae3c9d4decf8043b43ea2251083e
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739731"
---
# <a name="troubleshoot-planning-optimization"></a>Risoluzione dei problemi relativi all'ottimizzazione della pianificazione 

[!include [banner](../../includes/banner.md)]

Questo articolo descrive come risolvere i problemi comuni che potresti riscontrare mentre lavori all'ottimizzazione della pianificazione.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>L'installazione del componente aggiuntivo Ottimizzazione pianificazione non viene completata

Ottimizzazione pianificazione richiede un LCS (Lifecycle Services) abilitato, ambiente ad alta disponibilità di livello 2 o superiore (non un ambiente OneBox), con Dynamics 365 Supply Chain Management versione 10.0.7 o successiva. Se tenti di installare il componente aggiuntivo in un ambiente OneBox, l'installazione non verrà completata.

**Soluzione**: annulla l'installazione e utilizza un ambiente ad alta disponibilità, livello 2 o superiore (non un ambiente OneBox).

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>La pianificazione di processi batch non riesce quando è abilitata l'ottimizzazione della pianificazione

Quando abiliti l'ottimizzazione della pianificazione, il motore di pianificazione principale deprecato viene disabilitato automaticamente. I processi batch di pianificazione generale creati per il motore di pianificazione generale deprecato in Supply Chain Management falliranno se vengono attivati mentre Ottimizzazione pianificazione è abilitata. Puoi ricevere un messaggio di errore come *Questa operazione ha attivato la pianificazione generale che non è supportata quando il servizio Ottimizzazione pianificazione è abilitato*.

**Soluzione**: annulla tutti i processi batch di pianificazione generale creati per il motore di pianificazione generale deprecato.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>I risultati dell'ottimizzazione della pianificazione sono diversi dai risultati precedenti

L'ottimizzazione della pianificazione differisce dalla progettazione del motore di pianificazione generale deprecato in alcune aree. Ciò può anche essere causato da funzionalità in sospeso.

**Soluzione**: esegui l'analisi dell'adattamento dell'ottimizzazione della pianificazione, quindi analizza i risultati facendo riferimento alla documentazione correlata per comprenderne l'impatto. Per ulteriori informazioni, vedere [Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md).

## <a name="cant-enable-planning-optimization"></a>Impossibile abilitare l'ottimizzazione della pianificazione

**Stato connessione** deve essere **Connesso** prima di poter configurare **Usa ottimizzazione di pianificazione** su **Sì**. Per ulteriori informazioni, vedere [Introduzione all'ottimizzazione di pianificazione](get-started.md).

**Soluzione**: assicurati che il componente aggiuntivo Ottimizzazione pianificazione sia stato installato correttamente.

## <a name="error-message-is-shown-during-ctp"></a>Il messaggio di errore viene visualizzato durante CTP

Se tenti di eseguire CTP (capable to promise) da un ordine cliente quando Ottimizzazione pianificazione è abilitato, riceverai il seguente messaggio di errore: *Questa operazione ha attivato la pianificazione generale che non è supportata quando il servizio Ottimizzazione pianificazione è abilitato*.

Ciò è correlato a una funzionalità in sospeso pianificata come parte del supporto per gli ordini di produzione.

**Soluzione:** evita i calcoli CTP quando Ottimizzazione pianificazione è abilitata fino a quando è disponibile il supporto CTP.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Introduzione alla pianificazione generale](get-started.md)
- [Analisi corrispondenza Ottimizzazione pianificazione](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]