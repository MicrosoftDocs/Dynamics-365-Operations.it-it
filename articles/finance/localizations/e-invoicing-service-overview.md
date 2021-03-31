---
title: Panoramica del componente aggiuntivo per la fatturazione elettronica
description: Questo argomento fornisce informazioni sul componente aggiuntivo per la fatturazione elettronica in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 01/22/2021
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
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 381f5ecdb3d6fc909a8350ba28af9fd21152da7a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228791"
---
# <a name="electronic-invoicing-add-on-overview"></a>Panoramica del componente aggiuntivo per la fatturazione elettronica

[!include [banner](../includes/banner.md)]

Il componente aggiuntivo per la fatturazione elettronica per Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management è un servizio multitenant iper-scalabile che consente l'elaborazione configurabile di documenti di fatturazione elettronica e lo scambio di documenti configurabili. Le regole di elaborazione e integrazione sono completamente configurabili e la logica viene eseguita all'esterno di Finance and Supply Chain Management. Il servizio si rivolge principalmente all'elaborazione di fatture elettroniche in scenari business to government, ma può essere configurato in modo personalizzato per altri scopi.

Il componente aggiuntivo per la fatturazione elettronica può aiutarti a raggiungere i seguenti obiettivi:

- Adozione rapida e semplice di requisiti specifici per paese/area geografica
- Implementazioni standardizzate di una soluzione di componente aggiuntivo per la fatturazione elettronica
- Tracciabilità avanzata della cronologia dei documenti
- Ciclo di implementazione più breve
- Costo totale di proprietà ridotto
- Configurazioni facilmente regolabili che non richiedono modifiche al codice
- Pacchetto di configurazione semplificato
- Esportazione, importazione e integrazione integrate e facile estendibilità nell'elaborazione di documenti di fatturazione elettronica
- Facile riutilizzo delle stesse configurazioni di esportazione, importazione e integrazione tra le aziende

Per utilizzare il componente aggiuntivo per la fatturazione elettronica, è necessario installarlo dal progetto in formato Microsoft Dynamics Lifecycle Services (LCS). Successivamente, segui la procedura di configurazione per attivare l'integrazione con Finance o Supply Chain Management. Per altre informazioni, vedi [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

## <a name="service-availability"></a><a name="availability"></a>Disponibilità servizio

Attualmente il componente aggiuntivo per la fatturazione elettronica è disponibile per i clienti tramite il programma di anteprima e nella fase successiva il servizio diventerà generalmente disponibile. Poiché la funzionalità che soddisfa i requisiti specifici del paese/area geografica potrebbe essere limitata in diverse fasi del rilascio, è necessario controllare sempre la documentazione più aggiornata che evidenzi la copertura e l'ambito delle soluzioni specifiche del paese/area geografica supportato.

Il componente aggiuntivo per la fatturazione elettronica viene distribuito nelle seguenti aree geografiche di Azure:

- Stati Uniti
- Europa

> [!NOTE]
> Il componente aggiuntivo per la fatturazione elettronica non supporta le distribuzioni locali.

## <a name="extended-configurability"></a>Configurabilità estesa

Il componente aggiuntivo per la fatturazione elettronica può essere utilizzato in scenari in cui è necessario creare e inviare un documento elettronico alle parti designate. È progettato specificamente per eseguire un flusso configurabile di azioni di elaborazione, in base ai dati ricevuti. Le opzioni di configurabilità disponibili in Finance and Supply Chain Management sono limitate alla trasformazione dei documenti. Il servizio estende queste opzioni aggiungendo le integrazioni configurabili disponibili al suo interno. Inoltre, tutte le funzionalità di fatturazione elettronica precedentemente disponibili, come Nota fiscal eletrônica brasiliana (NF-e), Mexican Comprobante Fiscal Digital por Internet (CFDI) o altri Western European Universal Business Language (UBL)/Pan-European Public Procurement OnLine (PEPPOL) utilizzeranno le configurazioni per l'esportazione e l'importazione e per abilitare le integrazioni con servizi Web esterni.

## <a name="feature-highlights"></a>Caratteristiche principali

- Integrazione immediata con Finance e Supply Chain Management
- Esperienza utente coerente per la configurazione e il monitoraggio del processo di fatturazione elettronica per tutti i paesi o aree geografiche
- Adozione più rapida, semplice e meno costosa di soluzioni aggiuntive per la fatturazione elettronica in nuovi paesi o aree geografiche
- Configurazione del servizio tramite la funzionalità Regulatory Configuration Service (RCS) e globalizzazione
- Trasformazione dei dati aziendali in più formati di fattura elettronica (XML, JavaScript Object Notation \[JSON \], TXT e valori separati da virgole \[CSV\]) utilizzando le configurazioni definite in RCS:

    - Formati di report elettronici disponibili per paesi o aree geografiche in cui la configurabilità per la trasformazione della fattura elettronica non è disponibile

- Invio configurabile di fatture elettroniche a servizi Web esterni, inclusa la gestione della certificazione tramite firme digitali:

    - Integrazione incorporata, facilmente estendibile e configurabile con contenuti aggiuntivi per diversi paesi

    > [!NOTE]
    > Attualmente, è supportato un numero limitato di invii diretti. Per ulteriori informazioni, vedi la sezione [Disponibilità servizio](#availability) descritta precedentemente in questo argomento. Il supporto verrà esteso in futuro.

- Gestione delle risposte dai servizi Web, inclusa la gestione configurabile dei messaggi di eccezione
- Supporto per firme elettroniche (ad esempio, utilizzando l'algoritmo di firma XMLDSig)
- Elaborazione batch di messaggi di fatturazione elettronica

## <a name="architecture-and-data-flow"></a>Architettura e flusso di dati

Quando il componente aggiuntivo per la fatturazione elettronica viene installato da LCS e la configurazione obbligatoria è stata completata in tutte le applicazioni richieste, viene stabilita una connessione sicura. Il servizio si trova attualmente nei data center negli Stati Uniti e in Europa. Pertanto, l'ubicazione del servizio potrebbe differire dall'ubicazione dell'istanza di Finance o Supply Chain Management correlata. Dopo aver completato la configurazione del componente aggiuntivo per la fatturazione elettronica e attivato l'integrazione, ogni volta che viene inviata una fattura elettronica, i dati anagrafici e transazionali relativi a un documento specifico vengono inviati al componente aggiuntivo per la fatturazione elettronica.

> [!NOTE]
> Se la fattura elettronica o qualsiasi altro documento contiene dati personali, verifica che l'utilizzo di questa funzione soddisfi il Regolamento generale sulla protezione dei dati (GDPR) e altre normative relative al trasferimento dei dati personali.

### <a name="high-level-description-of-the-data-flow"></a>Descrizione generale del flusso di dati

1. Il cliente invia un documento aziendale canonico al servizio.
2. In base alle informazioni di contesto ricevute dal client, il servizio seleziona il flusso di elaborazione applicabile.
3. Il servizio esegue le azioni di elaborazione. Queste azioni potrebbero includere la trasformazione del documento aziendale in una fattura elettronica, l'applicazione di una firma elettronica e l'invio del documento a un servizio Web esterno.
4. Tutti i documenti ricevuti ed elaborati vengono archiviati in Archiviazione BLOB di Azure del cliente.
5. Tutti i segreti e i certificati del tenant usati per l'elaborazione vengono archiviati in Azure Key Vault del cliente.
6. Il servizio fornisce informazioni su richiesta al cliente sullo stato di elaborazione del documento aziendale inviato.
7. Il client riceve informazioni sull'esecuzione dell'elaborazione completata e rende disponibili tutte le informazioni di registro. Rende inoltre disponibile il documento creato o ricevuto durante l'elaborazione del flusso.

La figura seguente mostra i flussi di dati verso il e provenienti dal componente aggiuntivo per la fatturazione elettronica.

![Flusso di dati per il componente aggiuntivo per la fatturazione elettronica](media/e-invoicing-service-data-flow-diagram-overview.png)

## <a name="privacy-notice"></a>Informativa sulla privacy
L'abilitazione e l'utilizzo del componente aggiuntivo per la fatturazione elettronica potrebbe richiedere l'invio di dati limitati, che includono l'ID di registrazione fiscale dell'organizzazione. Questo verrà trasmesso ad agenzie di terze parti autorizzate dalle autorità fiscali allo scopo di inviare fatture elettroniche nei formati predefiniti richiesti per l'integrazione con questi servizi Web del governo. I dati importati da questi sistemi esterni in questo servizio online Dynamics 365 sono soggetti alla nostra [informativa sulla Privacy](https://go.microsoft.com/fwlink/?LinkId=512132). Consulta le sezioni dell'Informativa sulla privacy nella documentazione delle funzionalità specifiche del paese.

## <a name="additional-resources"></a>Risorse aggiuntive
- [Amministrazione del servizio](e-invoicing-service-administration.md)
- [Configurare le fattura elettroniche in RCS](e-invoicing-configuration-rcs.md)
- [Emissione di fatture elettroniche in Finance e Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]