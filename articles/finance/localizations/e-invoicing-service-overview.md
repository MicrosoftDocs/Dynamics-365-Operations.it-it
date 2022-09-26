---
title: Panoramica della fatturazione elettronica
description: Questo articolo fornisce informazioni generali sulla fatturazione elettronica in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 01/21/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 9d73b2dd7bf83c169aa776b41f962cc6addf5f19
ms.sourcegitcommit: a5a4c45bb265758c6e5c3483c8552503b1799a89
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2022
ms.locfileid: "9524718"
---
# <a name="electronic-invoicing-overview"></a>Panoramica della fatturazione elettronica

[!include [banner](../includes/banner.md)]

La fatturazione elettronica per Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management è un servizio multitenant iper-scalabile che consente l'elaborazione configurabile di fatture elettroniche e lo scambio di documenti configurabili. Le regole di elaborazione e integrazione sono completamente configurabili e la logica viene eseguita all'esterno di Finance and Supply Chain Management. Il servizio è mirato principalmente all'elaborazione di documenti di fatturazione elettronica in scenari business-to-government. Tuttavia, può essere configurato in modo personalizzato per altri scopi, ad esempio scenari business-to-business per diversi tipi di documenti.

La fatturazione elettronica può aiutarti a raggiungere i seguenti obiettivi:

- Adozione rapida e semplice di requisiti specifici per paese/area geografica
- Implementazioni standardizzate di una soluzione di fatturazione elettronica
- Tracciabilità avanzata della cronologia dei documenti
- Ciclo di implementazione più breve
- Costo totale di proprietà ridotto
- Configurazioni facilmente regolabili che non richiedono modifiche al codice
- Pacchetto di configurazione semplificato
- Esportazione, importazione e integrazione integrate e facile estendibilità nell'elaborazione di documenti di fatturazione elettronica
- Facile riutilizzo delle stesse configurazioni di esportazione, importazione e integrazione tra le aziende

## <a name="service-availability"></a>Disponibilità servizio

Attualmente, la funzionalità di fatturazione elettronica è disponibile per i clienti Finance e Supply Chain Management. Per ulteriori informazioni, consulta le condizioni della licenza per la tua applicazione.

Poiché la funzionalità che soddisfa i requisiti specifici del paese/area geografica potrebbe essere limitata in diverse fasi del rilascio, è necessario controllare sempre la documentazione più aggiornata che evidenzi la copertura e l'ambito delle soluzioni specifiche del paese/area geografica supportato.

La fatturazione elettronica viene distribuita nelle seguenti aree geografiche di Azure:

- Stati Uniti
- Europa
- Regno Unito
- Asia
- Giappone
- Svizzera
- Brasile
- Emirati Arabi Uniti
- Australia
- Canada
- Francia
- India

> [!NOTE]
> La fatturazione elettronica non supporta le distribuzioni locali.

## <a name="feature-highlights"></a>Caratteristiche principali

- Integrazione immediata con Finance e Supply Chain Management
- Esperienza utente coerente per la configurazione e il monitoraggio del processo di fatturazione elettronica per tutti i paesi e aree geografiche
- Adozione più rapida, semplice e meno costosa di soluzioni aggiuntive per la fatturazione elettronica in nuovi paesi o aree geografiche
- Configurazione del servizio tramite la configurazione delle funzionalità Regulatory Configuration Service (RCS) e globalizzazione
- Trasformazione dei dati aziendali in più formati di fattura elettronica (XML, JavaScript Object Notation \[JSON \], TXT e valori separati da virgole \[CSV\]) utilizzando le configurazioni definite in RCS:

    - Formati di report elettronici disponibili per paesi e aree geografiche in cui la configurabilità per la trasformazione della fattura elettronica non è disponibile

- Invio configurabile di fatture elettroniche a servizi Web esterni, inclusa la gestione della certificazione tramite firme digitali:

    - Integrazione incorporata, facilmente estendibile e configurabile con contenuti aggiuntivi per diversi paesi e aree geografiche

- Gestione delle risposte dai servizi Web, inclusa la gestione configurabile dei messaggi di eccezione
- Supporto per firme elettroniche (ad esempio, firme elettroniche che utilizzano l'algoritmo di firma XMLDSig)
- La possibilità di inviare documenti a e-mail e archiviarli in SharePoint
- Elaborazione batch di messaggi di fatturazione elettronica
- Trasformazione configurabile dei documenti in entrata ed elaborazione di tali documenti in Finance and Supply Chain Management
- La possibilità di ricevere documenti in arrivo da canali come e-mail e SharePoint

## <a name="privacy-notice"></a>Informativa sulla privacy

L'abilitazione e l'utilizzo funzionalità di fatturazione elettronica potrebbe richiedere l'invio di dati limitati. Questi dati includono l'ID di registrazione fiscale dell'organizzazione. Questi dati verranno trasmessi ad agenzie di terze parti autorizzate dalle autorità fiscali allo scopo di inviare fatture elettroniche nei formati predefiniti richiesti per l'integrazione con questi servizi Web del governo. I dati importati da questi sistemi esterni in questo servizio online Dynamics 365 sono soggetti alla nostra [informativa sulla Privacy](https://go.microsoft.com/fwlink/?LinkId=512132). Per ulteriori informazioni consulta la sezione "Informativa sulla privacy" nella documentazione delle funzionalità specifiche del paese/area geografica.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
