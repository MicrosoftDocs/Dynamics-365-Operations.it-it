---
title: Domande frequenti sulla fatturazione elettronica
description: In questo argomento vengono fornite informazioni sulle domande frequenti sulla fatturazione elettronica.
author: gionoder
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1ba1a6c5542c10306d4b7494d33e7ff04504fa95
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893780"
---
# <a name="electronic-invoicing-faq"></a>Domande frequenti sulla fatturazione elettronica

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite le risposte alle domande frequenti sulla fatturazione elettronica. La fatturazione elettronica estende le funzionalità di fatturazione elettronica esistenti in Dynamics 365 Finance, Dynamics 365 Supply Chain Management, e Dynamics 365 Project Operations. 

## <a name="what-is-important-about-electronic-invoicing-and-why-should-it-matter-to-my-organization"></a>Che cosa è importante per la fatturazione elettronica e perché dovrebbe essere importante per la mia organizzazione?

La complessità operativa e il rischio continuano a intensificarsi man mano che le organizzazioni crescono a livello globale ed espandono la propria presenza nelle aree geografiche. Il mantenimento della conformità e l'adattamento alle normative che cambiano frequentemente è una sfida crescente ed è di particolare importanza quando si tratta di fatturazione. La fatturazione è stata tradizionalmente costosa e soggetta a errori poiché le aziende si affidano a documenti cartacei e processi manuali intensivi.  

Le organizzazioni hanno iniziato ad abbandonare le fatture cartacee per ridurre i costi e accelerare il processo end-to-end. I governi si rivolgono sempre più alla fatturazione elettronica come componente chiave della digitalizzazione fiscale. Richiedendo alle organizzazioni di inviare digitalmente informazioni fiscali in tempo reale alle autorità fiscali, i governi possono ridurre al minimo l'evasione e la manipolazione fiscale e le frodi. 

Il mondo sta passando all'elaborazione di documenti senza carta e senza implementare la fatturazione elettronica, i clienti potrebbero rischiare problemi di conformità, costi inutili e rimanere indietro rispetto ai concorrenti. 

## <a name="doesnt-finance-supply-chain-management-and-project-operations-already-include-electronic-invoicing-functionality-what-value-does-this-provide-to-me-as-a-customer"></a>Finance, Supply Chain Management e Project Operations non includono già la funzionalità di fatturazione elettronica? Che valore mi offre come cliente? 

La fatturazione elettronica estende le funzionalità di fatturazione elettronica esistenti in Finance, Supply Chain Management e Project Operations. La funzionalità semplifica inoltre l'adesione ai più recenti standard di fatturazione elettronica e fornisce esperienze coerenti per diverse aree geografiche nell'elaborazione e nello scambio di fatture elettroniche. Le capacità della fatturazione elettronica sbloccano una serie di vantaggi, tra cui: 

   - Adozione rapida e semplice di requisiti specifici per paese/area geografica.
   - Implementazioni standardizzate della soluzione di fatturazione elettronica. 
   - Tracciabilità avanzata dell'elaborazione delle fatture elettroniche.  
   - Manutenzione più semplice per soddisfare i requisiti legali in evoluzione e le procedure aziendali locali. 
   - Packaging della soluzione semplificato.
   - Funzionalità di ridimensionamento per un grande volume di documenti inviati che si traduce in tempi di consegna più rapidi.
   - Capacità di condividere le tue soluzioni con altre aziende.

## <a name="does-electronic-invoicing-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>La fatturazione elettronica supporta le installazioni locali di Finance, Supply Chain Management e Project Operations? 

La piattaforma attuale non consente l'utilizzo della versione locale e non ci sono piani per supportarla in futuro.

## <a name="does-electronic-invoicing-interface-with-the-vendor-import-automation-feature"></a>La fatturazione elettronica si interfaccia con la funzione di automazione di importazione del fornitore?

N. Ci sono piani per questa interfaccia, ma non c'è una tempistica pianificata. Quando saranno pianificate, le date verranno annunciate nei [Piani di rilascio](/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>In che modo la fatturazione elettronica gestisce gli allegati di file nella fattura elettronica? È necessario un server SharePoint per incorporare file PDF nel file XML?

I file allegati alla fattura elettronica vengono gestiti come dati binari incorporati in un elemento XML. Il server SharePoint non è necessario per incorporare file PDF, ma l'allegato deve essere archiviato nel sistema di gestione dei documenti Finance, Supply Chain Management e Project Operations.

## <a name="is-electronic-invoicing-available-according-to-the-regulations-of-my-countryregion"></a>La fatturazione elettronica è disponibile in base alle normative del mio paese/area geografica?

La fatturazione elettronica è una piattaforma di microservizi che sarà disponibile a livello globale.

Microsoft prevede di pubblicare i formati e le integrazioni delle fatture elettroniche per i paesi funzionalmente localizzati da Microsoft. Per ulteriori informazioni, vedi [Disponibilità delle funzionalità di fatturazione elettronica](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Se il formato di fatturazione elettronica per il tuo paese/area geografica non è elencato, la piattaforma mira a supportare questo scenario in futuro. È comunque possibile trarre vantaggio dalle funzionalità di configurazione di cui dispone la fatturazione elettronica e configurare autonomamente il formato della fatturazione elettronica oppure collaborare con un partner/ISV per configurarli per la propria organizzazione.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>Dynamics 365 for Regulatory Services è un nuovo modulo come Human Resources o Project Operations collegato a Finance o Supply Chain Management? Ci sono costi aggiuntivi per questo?

Dynamics 365 for Regulatory Services (RCS) è un servizio cloud per la configurazione delle risorse di globalizzazione. RCS è gratuito per tutti i titolari di licenza di Finance, Supply Chain Management e Project Operations.

Per l'iscrizione a RCS, vai a <https://marketing.configure.global.dynamics.com/>.

Per altre informazioni, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing--or-just-turn-it-on-in-feature-management"></a>Devo registrarmi per ottenere la fatturazione elettronica o semplicemente attivarla in Gestione funzionalità?

Se hai una licenza per Finance, Supply Chain Management e Project Operations, vedi [Introduzione all'amministrazione dei servizi del componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started-service-administration.md) per iscriverti alla fatturazione elettronica.

## <a name="does-electronic-invoicing-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>La fatturazione elettronica funziona con le macchine virtuali di livello 1? Qual è l'ambiente minimo richiesto?

L'integrazione con la fatturazione elettronica richiede almeno una macchina virtuale di livello 2 per ospitare Finance o Supply Chain Management. Per ulteriori informazioni sulla pianificazione dell'ambiente, vedere [Pianificazione ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-have-a-test-mode-for-testing-invoice-submission"></a>La fatturazione elettronica dispone di una modalità di test per testare l'invio delle fatture?

Ciò può essere ottenuto mediante la configurazione. Per testare l'invio della fattura, è possibile connettersi a Finance o Supply Chain Management da un ambiente UAT (User Acceptance Test) e inviare le fatture di prova. La fatturazione elettronica supporta la configurazione dei certificati digitali di prova e, nel caso di fatture elettroniche che richiedono l'approvazione digitale, l'impostazione di un URL dai servizi Web di prova pubblicati dalle autorità fiscali.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Esiste la documentazione delle funzionalità di fatturazione elettronica specifiche per paese predefinite?

Sì. Per informazioni sulla disponibilità delle funzioni di fatturazione elettronica e sui formati che supportano, vedi [Disponibilità delle funzionalità di fatturazione elettronica](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Se non hai trovato la risposta che stai cercando, invia la tua domanda tramite e-mail al team di sviluppo del prodotto all'indirizzo <D365EInvoicePreview@microsoft.com>. Ti contatteremo o miglioreremo la copertura di queste domande frequenti.