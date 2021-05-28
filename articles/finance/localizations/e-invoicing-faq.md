---
title: Domande frequenti sulla fatturazione elettronica
description: In questo argomento vengono fornite informazioni sulle domande frequenti sulla fatturazione elettronica.
author: gionoder
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 0b3bd48cbc1ce5f236f51b79b8235d6b7c3890c0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022350"
---
# <a name="electronic-invoicing-faq"></a>Domande frequenti sulla fatturazione elettronica

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite le risposte alle domande frequenti sul servizio di fatturazione elettronica. La fatturazione elettronica estende le funzionalità di fatturazione elettronica esistenti in Dynamics 365 Finance, Dynamics 365 Supply Chain Management, e Dynamics 365 Project Operations. 

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

## <a name="does-electronic-invoicing-service-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>Il servizio di fatturazione elettronica supporta le installazioni locali di Finance, Supply Chain Management e Project Operations? 

La piattaforma attuale non consente l'utilizzo della versione locale e non ci sono piani per supportarla in futuro.

## <a name="does-electronic-invoicing-service-interface-with-the-vendor-import-automation-feature"></a>Il servizio di fatturazione elettronica si interfaccia con la funzione di automazione di importazione del fornitore?

N. Ci sono piani per questa interfaccia, ma non c'è una tempistica pianificata. Quando saranno pianificate, le date verranno annunciate nei [Piani di rilascio](/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-service-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>In che modo il servizio di fatturazione elettronica gestisce gli allegati di file nella fattura elettronica? È necessario un server SharePoint per incorporare file PDF nel file XML?

I file allegati alla fattura elettronica vengono gestiti come dati binari incorporati in un elemento XML. Il server SharePoint non è necessario per incorporare file PDF, ma l'allegato deve essere archiviato nel sistema di gestione dei documenti Finance, Supply Chain Management e Project Operations.

## <a name="is-electronic-invoicing-service-available-according-to-the-regulations-of-my-countryregion"></a>Il servizio di fatturazione elettronica è disponibile in base alle normative del mio paese/area geografica?

Il servizio di fatturazione elettronica è una piattaforma di microservizi che sarà disponibile a livello globale.

Microsoft prevede di pubblicare i formati e le integrazioni delle fatture elettroniche per i paesi funzionalmente localizzati da Microsoft. Per ulteriori informazioni, vedi [Disponibilità delle funzionalità di fatturazione elettronica](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Se il formato di fatturazione elettronica per il tuo paese/area geografica non è elencato, la piattaforma mira a supportare questo scenario in futuro. È comunque possibile trarre vantaggio dalle funzionalità di configurazione di cui dispone la fatturazione elettronica e configurare autonomamente il formato della fatturazione elettronica oppure collaborare con un partner/ISV per configurarli per la propria organizzazione.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>Dynamics 365 for Regulatory Services è un nuovo modulo come Human Resources o Project Operations collegato a Finance o Supply Chain Management? Ci sono costi aggiuntivi per questo?

Dynamics 365 for Regulatory Services (RCS) è un servizio cloud per la configurazione delle risorse di globalizzazione. RCS è gratuito per tutti i titolari di licenza di Finance, Supply Chain Management e Project Operations.

Per l'iscrizione a RCS, vai a <https://marketing.configure.global.dynamics.com/>.

Per altre informazioni, vedi [Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing-service-or-just-turn-it-on-in-feature-management"></a>Devo registrarmi per ottenere il servizio di fatturazione elettronica o semplicemente attivarlo in Gestione funzionalità?

Se hai una licenza per Finance, Supply Chain Management e Project Operations, vedi [Introduzione all'amministrazione dei servizi del componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started-service-administration.md) per iscriverti alla fatturazione elettronica.

## <a name="does-electronic-invoicing-service-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>Il servizio di fatturazione elettronica funziona con le macchine virtuali di livello 1? Qual è l'ambiente minimo richiesto?

L'integrazione con il servizio di fatturazione elettronica richiede almeno una macchina virtuale di livello 2 per ospitare Finance o Supply Chain Management. Per ulteriori informazioni sulla pianificazione dell'ambiente, vedere [Pianificazione ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-service-have-a-test-mode-for-testing-invoice-submission"></a>Il servizio di fatturazione elettronica dispone di una modalità di test per testare l'invio delle fatture?

Ciò può essere ottenuto mediante la configurazione. Per testare l'invio della fattura, è possibile connettersi a Finance o Supply Chain Management da un ambiente UAT (User Acceptance Test) e inviare le fatture di prova. La fatturazione elettronica supporta la configurazione dei certificati digitali di prova e, nel caso di fatture elettroniche che richiedono l'approvazione digitale, l'impostazione di un URL dai servizi Web di prova pubblicati dalle autorità fiscali.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Esiste la documentazione delle funzionalità di fatturazione elettronica specifiche per paese predefinite?

Sì. Per informazioni sulla disponibilità delle funzioni di fatturazione elettronica e sui formati che supportano, vedi [Disponibilità delle funzionalità di fatturazione elettronica](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

## <a name="does-the-electronic-invoicing-service-allow-a-legal-entity-in-finance-or-supply-chain-management-that-is-configured-for-a-specific-country-to-consume-electronic-invoicing-features-from-different-countryregions"></a>Il servizio di fatturazione elettronica consente a una persona giuridica in Finance o Supply Chain Management configurata per un paese/area geografica specifico di utilizzare le funzionalità di fatturazione elettronica da paesi/aree geografiche diversi?

Sì. Le funzionalità di fatturazione elettronica possono essere utilizzate per elaborare gli invii di documenti aziendali indipendentemente dal paese/area geografica della persona giuridica, se si verifica quanto segue:

   - Il documento aziendale generato utilizza la mappatura del modello di documento appropriato.
   - Esiste una corrispondenza tra il documento aziendale e le regole di applicabilità configurate nella funzione di fatturazione elettronica.

## <a name="does-the-electronic-invoicing-service-use-the-same-configuration-and-design-experience-provided-by-the-electronic-reporting-module-in-finance-and-supply-chain-management"></a>Il servizio di fatturazione elettronica utilizza la stessa esperienza di configurazione e progettazione fornita dal modulo Creazione di report elettronici in Finance and Supply Chain Management? 

Sì. Gli stessi strumenti di progettazione utilizzati nel modulo Creazione di report elettronici (ER) in Finance and Supply Chain Management vengono utilizzati per creare e configurare la mappatura del modello di dati e le configurazioni del formato file. Questi strumenti di progettazione vengono utilizzati anche in Regulatory Configuration Services (RCS) per creare e configurare la mappatura del modello di dati e le configurazioni del formato di file utilizzate nella configurazione delle funzionalità di fatturazione elettronica.

## <a name="can-the-applicability-rules-be-extended-and-configured-so-that-they-arent-tied-to-any-specific-parameter-such-as-a-legal-entity"></a>Le regole di applicabilità possono essere estese e configurate in modo che non siano legate a parametri specifici, come una persona giuridica?

Sì. Le regole di applicabilità sono completamente configurabili. È possibile aggiungere o rimuovere clausole, creare operazioni logiche e raggruppare e separare clausole. Per ulteriori informazioni, vedi [Regole di applicabilità](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#applicability-rules).

## <a name="does-the-electronic-invoicing-service-support-adding-other-er-format-configurations-to-generate-other-types-of-documents-does-it-support-sending-the-documents-electronically-to-customers-such-as-a-delivery-note"></a>Il servizio di fatturazione elettronica supporta l'aggiunta di altre configurazioni di formato ER per generare altri tipi di documenti? Supporta l'invio elettronico dei documenti ai clienti, come una bolla di consegna?

È possibile utilizzare altre configurazioni di formato ER per produrre i file di output desiderati. Tuttavia, la configurazione del formato ER deve essere derivata dalla stessa mappatura del modello di fattura ER configurata in Finance o Supply Chain Management per generare documenti aziendali. L'invio del file di output direttamente al cliente come transazione EDI non è supportato immediatamente dalla fatturazione elettronica.

## <a name="does-the-electronic-invoicing-service-support-exchanging-electronic-invoices-with-customers-does-it-support-configuring-different-invoice-formats-for-the-same-invoice"></a>Il servizio di fatturazione elettronica supporta lo scambio di fatture elettroniche con i clienti? Supporta la configurazione di formati di fattura diversi per la stessa fattura?

La capacità di ricevere e importare fatture elettroniche del fornitore fa parte della roadmap, ma l'invio automatico delle fatture elettroniche ai clienti non è attualmente supportato.

## <a name="does-the-electronic-invoicing-service-extend-to-support-exchanging-edi-messages-with-other-companies"></a>Il servizio di fatturazione elettronica si estende per supportare lo scambio di messaggi EDI con altre società?

L'obiettivo del servizio di fatturazione elettronica è lo scambio di tipi di messaggi di fatturazione elettronica basati su requisiti di conformità normativa. La ricezione e l'importazione di fatture elettroniche del fornitore è nella roadmap, ma l'invio di file di fatture elettroniche ai clienti non è attualmente supportato immediatamente, tranne negli scenari in cui l'invio della fattura elettronica al cliente è un requisito normativo.

## <a name="does-the-electronic-invoicing-service-support-importing-or-merging-customizations-made-in-the-er-format-configurations-from-the-legacy-electronic-invoicing-feature"></a>Il servizio di fatturazione elettronica supporta l'importazione o l'unione di personalizzazioni effettuate nelle configurazioni del formato ER dalla funzione di fatturazione elettronica legacy?

È possibile riutilizzare le configurazioni del formato ER nel servizio di fatturazione elettronica. Tuttavia, la configurazione del formato ER deve essere derivata dalla stessa mappatura del modello di fattura ER che la funzione di fatturazione elettronica è stata progettata per usare e che è configurata in Finance o Supply Chain Management per generare documenti aziendali.

## <a name="does-the-electronic-invoicing-service-support-issuing-electronic-invoices-from-custom-made-tables-if-so-how-do-you-create-the-er-data-model-configurations-for-these-new-tables-and-entities"></a>Il servizio di fatturazione elettronica supporta l'emissione di fatture elettroniche da tabelle personalizzate? In tal caso, come si creano le configurazioni del modello di dati ER per queste nuove tabelle ed entità?

Sì. Tuttavia, richiede la personalizzazione della mappatura del modello di fattura e l'aggiunta dei riferimenti necessari alle tabelle personalizzate o, a seconda della complessità, la creazione di una nuova mappatura del modello di fattura.

## <a name="does-the-electronic-invoicing-service-support-different-web-service-endpoints"></a>Il servizio di fatturazione elettronica supporta diversi endpoint di servizi Web?

La fatturazione elettronica supporta diversi endpoint di servizi Web. È possibile utilizzare l'integrazione configurabile con i servizi Web REST o una serie di integrazioni di servizi Web parametrizzate specifiche per paese/area geografica. È possibile configurare endpoint diversi per gli stessi servizi Web e API utilizzando diverse versioni di configurazioni. Per ulteriori informazioni, vedi [Elenco dei parametri per azione](e-invoicing-setup.md#list-of-parameters-by-action).

## <a name="is-electronic-invoicing-integrated-with-the-various-invoice-operators-apis-from-the-nordic-countries-or-should-that-be-handled-on-a-case-by-case-basis"></a>La fatturazione elettronica è integrata con le API dei vari operatori di fatturazione dei paesi nordici o dovrebbe essere gestita caso per caso?

Microsoft estende continuamente la copertura funzionale per fornire integrazioni predefinite utilizzando le funzionalità di fatturazione elettronica. Per ulteriori informazioni sui formati e le integrazioni supportati, vedere [Disponibilità di funzionalità di fatturazione elettronica](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Se non hai trovato la risposta che stai cercando, invia la tua domanda tramite e-mail al team di sviluppo del prodotto all'indirizzo <D365EInvoicePreview@microsoft.com>. Ti contatteremo o miglioreremo la copertura di queste domande frequenti.
