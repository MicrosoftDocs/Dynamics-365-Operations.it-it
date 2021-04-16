---
title: Configurare la fatturazione elettronica in Regulatory Configuration Services (RCS)
description: Questo argomento spiega come configurare la fatturazione elettronica in Dynamics 365 Regulatory Configuration Services (RCS).
author: gionoder
ms.date: 03/29/2021
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
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 9958091db4a3d7ce0b625e5adc8e2a6b37878618
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840246"
---
# <a name="configure-electronic-invoicing-in-regulatory-configuration-services-rcs"></a>Configurare la fatturazione elettronica in Regulatory Configuration Services (RCS)

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni sulle funzionalità di configurazione della fatturazione elettronica in Dynamics 365 Regulatory Configuration Services (RCS).

È grazie alle funzionalità di configurazione che Fatturazione elettronica consente di soddisfare i requisiti aziendali e normativi delle fatture elettroniche senza dover eseguire alcuna codifica. Negli scenari in cui le fatture elettroniche devono essere approvate elettronicamente da un servizio Web, le funzionalità di configurazione aiutano anche a soddisfare i requisiti per lo scambio di messaggi con un servizio Web, senza scrivere alcun codice.

## <a name="electronic-reporting"></a>Creazione di report elettronici

La creazione di report elettronici (ER) supporta la fatturazione elettronica.

Il mapping e i formati del modello di dati sono componenti configurabili che vengono creati e gestiti tramite ER e utilizzati nella Fatturazione elettronica. La progettazione formato ER è lo strumento per creare e mantenere i formati di file. Viene utilizzato per configurare le funzionalità di fatturazione elettronica.

Per ulteriori informazioni, vedi [Panoramica dello strumento di creazione di report elettronici](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

## <a name="electronic-invoicing-features"></a>Funzioni di fatturazione elettronica

Le funzioni di fatturazione elettronica sono responsabili della generazione di fatture elettroniche tramite la Fatturazione elettronica. Incapsulano le regole di configurazione e le usano per elaborare i dati che Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management inviano alla Fatturazione elettronica e alle fatture elettroniche.

Le funzionalità supportano anche scenari in cui è richiesta la conformità con le specifiche del formato di file e l'output è un file elettronico autonomo. Nella maggior parte dei casi, le specifiche del formato di file sono pubblicate dall'ufficio tributario.

Infine, le funzionalità supportano lo scambio di messaggi con servizi web esterni ospitati dall'ufficio tributario o da parte accreditata e le richieste di autorizzazione o un timbro di approvazione nella fattura elettronica.

### <a name="availability-of-electronic-invoicing-features"></a>Disponibilità di funzionalità di fatturazione elettronica

La disponibilità delle funzionalità di fatturazione elettronica dipende dal paese o dalla regione. Sebbene alcune funzionalità siano generalmente disponibili, altre sono in anteprima.

#### <a name="preview-features"></a>Funzionalità di anteprima

La tabella seguente mostra le funzionalità di fatturazione elettronica attualmente in anteprima.

| Paese/area geografica | Nome funzionalità                         | Documento aziendale |
|----------------|--------------------------------------|-------------------|
| Austria        | Fatture elettroniche austriache (AT)    | Fatture di vendita e fatture di progetto |
| Belgio        | Fattura elettronica belga (BE)      | Fatture di vendita e fatture di progetto |
| Brasile         | NF-e brasiliano (BR)                  | Documento fiscale modello 55, lettere di correzione, annullamenti e rifiuti |
| Brasile         | Brasiliano NFS-e ABRASF Curitiba (BR) | Documenti fiscali di servizio |
| Danimarca        | Fattura elettronica danese (DK)       | Fatture di vendita e fatture di progetto |
| Egitto          | Fattura elettronica egiziana (EG) | Fatture di vendita e fatture di progetto |
| Estonia        | Fattura elettronica estone (EE)     | Fatture di vendita e fatture di progetto |
| Finlandia        | Fattura elettronica finlandese (FI)      | Fatture di vendita e fatture di progetto |
| Francia         | Fattura elettronica francese (FR)       | Fatture di vendita e fatture di progetto |
| Germania        | Fattura elettronica tedesca (DE)       | Fatture di vendita e fatture di progetto |
| Italia          | FatturaPA (IT)                       | Fatture di vendita e fatture di progetto |
| Messico         | Messicano CFDI (MX)                    | Fatture di vendita, documenti di trasporto, trasferimenti di magazzino, complementi di pagamento e annullamenti |
| Paesi Bassi    | Fattura elettronica olandese (NL)        | Fatture di vendita e fatture di progetto |
| Norvegia         | Fattura elettronica norvegese (NO)    | Fatture di vendita e fatture di progetto |
| Spagna          | Fattura elettronica spagnola (ES)      | Fatture di vendita e fatture di progetto |
| Europa         | Fattura elettroniche PEPPOL            | Fatture di vendita e fatture di progetto PEPPOL |

### <a name="configurable-components-of-electronic-invoicing-features"></a>Componenti configurabili delle funzionalità di fatturazione elettronica

Le funzionalità di fatturazione elettronica sono costituite dai seguenti gruppi di componenti configurabili:

- **Formati** - I formati consentono di configurare ciò che Fatturazione elettronica deve generare quando un documento elettronico diventa una fattura elettronica. I formati includono la configurazione del formato per la fattura elettronica e per file e messaggi utilizzati per inviare richieste e ricevere risposte quando è richiesta la comunicazione con un servizio Web esterno.
- **Azioni** - Le azioni consentono di configurare il modo in cui Fatturazione elettronica genera la trasformazione di un documento elettronico inviato da Finance e Supply Chain Management in una fattura elettronica.
- **Regole di applicabilità** - Le regole di applicabilità consentono di configurare il contesto che Fatturazione elettronica deve considerare per elaborare una funzione di fatturazione elettronica.
- **Variabili** - Le variabili consentono di configurare il supporto per la costruzione della logica di configurazione. Le variabili possono funzionare come input di valori per eseguire un'azione specifica. In alternativa, possono funzionare come scambio di valori tra Finance e Supply Chain Management e i Fatturazione elettronica.
- **Mapping del modello di documento elettronico** - Il mapping del modello di documento elettronico consente di configurare il mapping del modello ER. Il mapping del modello definisce il mapping dei dati della fattura astratta che viene integrata in Fatturazione elettronica quando vengono inviati documenti elettronici.
- **Modello di contesto della fattura** - Il modello del contesto della fattura consente di configurare il modello del contesto della fattura ER e definire il contesto di una funzione di fatturazione elettronica.
- **Tipi di risposta** - I tipi di risposta consentono di configurare ciò che Fatturazione elettronica deve aggiornare in Finance e Supply Chain Management come risultato dell'elaborazione della fattura elettronica.

### <a name="formats"></a>Formati

Gli elenchi seguenti mostrano le configurazioni del formato ER disponibili per le funzioni di fatturazione elettronica.

#### <a name="austrian-at-electronic-invoices-sales-and-project-invoices-for-austria"></a>Fatture elettroniche austriache (AT): fatture di vendita e di progetto per l'Austria

- Fattura di vendita OIOUBL
- Fattura di progetto OIOUBL
- Nota di credito vendita OIOUBL
- Nota di credito progetto OIOUBL

#### <a name="belgian-be-electronic-invoice-sales-and-project-invoices-for-belgium"></a>Fattura elettronica belga (BE): fatture di vendita e di progetto per il Belgio

- Fattura di vendita UBL BE
- Fattura di progetto UBL BE
- Nota di credito di progetto UBL BE
- Nota di credito vendita UBL BE

#### <a name="brazilian-br-nf-e-nf-e-federal-brazil"></a>NF-e brasiliano (BR): NF-e federale (Brasile)

- Formato di esportazione per l'invio NF-e (BR)
- Formato di esportazione per la lettera di correzione NF-e (BR)
- Formato di esportazione per l'annullamento NF-e (BR)
- Formato di esportazione per l'eliminazione NF-e (BR)

#### <a name="brazilian-nfs-e-br-nfs-e-abrasf-curitiba-city"></a>Brasiliano NFS-e (BR): NFS-e ABRASF Curitiba city

- NFS-e ABRASF Curitiba (BR)
- NFS-e ABRASF Inquire Curitiba (BR)

#### <a name="danish-dk-electronic-invoice-sales-and-project-invoices-for-denmark"></a>Fattura elettronica danese (DK): fatture di vendita e di progetto per la Danimarca

- Fattura di vendita OIOUBL
- Fattura di progetto OIOUBL
- Nota di credito vendita OIOUBL
- Nota di credito progetto OIOUBL

#### <a name="dutch-nl-electronic-invoice-sales-and-project-invoices-for-netherlands"></a>Fattura elettronica olandese (NL): fatture di vendita e di progetto per i Paesi Bassi

- Fattura di vendita UBL NL
- Fattura di progetto UBL NL
- Nota di credito di progetto UBL NL
- Nota di credito vendita UBL NL

#### <a name="egyptian-eg-electronic-invoice-sales-and-project-invoices-for-egypt"></a>Fattura elettronica egiziana (EG): fatture di vendita e di progetto per l'Egitto

- Fattura di vendita (EG) (Fatturazione)
- Fattura di progetto (EG) (Fatturazione)

#### <a name="estonian-ee-electronic-invoice-sales-and-project-invoices-for-estonia"></a>Fattura elettronica estone (EG): fatture di vendita e di progetto per l'Estonia

- Fattura di vendita (EE)
- Fattura di progetto (EE)

#### <a name="finnish-fi-electronic-invoice-sales-and-project-invoices-for-finland"></a>Fattura elettronica finlandese (FI): fatture di vendita e di progetto per la Finlandia

- Fattura di vendita (FI)
- Fattura di progetto (FI)

#### <a name="french-fr-electronic-invoice-sales-and-project-invoices-for-france"></a>Fattura elettronica francese (FR): fatture di vendita e di progetto per la Francia

- Fattura di vendita UBL FR
- Fattura di progetto UBL FR
- Nota di credito di progetto UBL FR
- Nota di credito vendita UBL FR

#### <a name="german-de-electronic-invoice-sales-and-project-invoices-for-germany"></a>Fattura elettronica tedesca (DE): fatture di vendita e di progetto per la Germania

- Fattura di vendita (DE)
- Fattura di progetto (DE)

#### <a name="italian-it-electronic-invoice-sales-and-project-invoices-for-italy"></a>Fattura elettronica italiana (IT): fatture di vendita e di progetto per l'Italia

- Fattura di vendita (IT)
- Fattura di progetto (IT)

#### <a name="mexican-mx-cfdi-cfdi-for-mexico"></a>CFDI messicano (MX): CFDI per il Messico

- Formato fattura CFDI (MX)
- Documento di trasporto CFDI (MX)
- Trasferimento scorte CFDI (MX)
- Formato di pagamento CFDI (MX)
- Formato annullamento fattura CFDI (MX)

#### <a name="norwegian-no-electronic-invoice-sales-and-project-invoices-for-norway"></a>Fattura elettronica norvegese (BE): fatture di vendita e di progetto per la Norvegia

- Fattura di vendita OIOUBL
- Fattura di progetto OIOUBL
- Nota di credito vendita OIOUBL
- Nota di credito progetto OIOUBL

#### <a name="peppol-electronic-invoice-peppol-sales-and-project-invoices"></a>Fattura elettronica PEPPOL: fatture di vendita e di progetto PEPPOL

- Fattura di vendita PEPPOL
- Fattura di progetto PEPPOL
- Nota di credito vendita PEPPOL
- Nota di credito progetto PEPPOL

#### <a name="spanish-es-electronic-invoice-sales-and-project-invoices-for-spain"></a>Fattura elettronica spagnola (ES): fatture di vendita e di progetto per la Spagna

- Fattura di vendita (ES)
- Fattura di progetto (ES)

### <a name="actions"></a>Azioni

La tabella seguente elenca le azioni disponibili e se sono attualmente generalmente disponibili o ancora in anteprima.

| Azione                                        | Descrizione                                                                  | Disponibilità         |
|-----------------------------------------------|------------------------------------------------------------------------------|----------------------|
| Trasforma documento                            | Esegui il formato di Creazione di report elettronici per trasformare il documento.                   | Generalmente disponibile  |
| Firma documento xml                             | Firma documenti xml con firma digitale.                                   | In anteprima           |
| Firma documento JSON per ufficio tributario egiziano | Firma documenti JSON con firma digitale per l'ufficio tributario egiziano.       | Generalmente disponibile  |
| Integrazione con il servizio ETA egiziano           | Comunicazioni con l'ufficio tributario egiziano.                                     | Generalmente disponibile  |
| Chiama servizio SEFAZ brasiliano                  | Integrazione con il servizio SEFAZ brasiliano per l'invio di documenti fiscali.       | In anteprima           |
| Chiama servizio PAC messicano                      | Integrazione con il servizio PAC messicano per l'invio CFDI.                      | In anteprima           |
| Elabora risposta                              | Analizza la risposta ricevuta dalla chiamata al servizio Web.                     | Generalmente disponibile  |
| Usa MS Power Automate                         | Integrazione con il flusso integrato in Microsoft Power Automate.                       | In anteprima           |

## <a name="configuration-providers"></a>Provider di configurazione

I provider di configurazioni forniscono le funzionalità di fatturazione elettronica e i relativi componenti ER, come il mapping del modello, la configurazione del formato e il modello di contesto. Pubblicano le funzionalità di fatturazione elettronica e i componenti ER nel repository globale associato. Da lì, altre organizzazioni possono eseguire il download.

Prima di configurare le funzionalità di fatturazione elettronica tramite RCS, è necessario configurare la propria organizzazione come provider di configurazioni nel modulo **Creazione di report elettronici**. Per ulteriori informazioni su come impostare un provider di configurazioni su **Attivo**, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="viewing-electronic-invoicing-features-in-the-global-repository"></a>Visualizzazione delle funzionalità di fatturazione elettronica nel repository globale

Per esplorare le funzionalità di fatturazione elettronica disponibili nel repository globale per un provider di configurazione specifico, sincronizza l'istanza RCS della tua organizzazione. Al termine della sincronizzazione, l'elenco delle funzioni di fatturazione elettronica disponibili viene aggiornato.

## <a name="importing-electronic-invoicing-features"></a>Importazione delle funzionalità di fatturazione elettronica

Prima di utilizzare o configurare le funzionalità di fatturazione elettronica, è necessario importarle nell'istanza RCS della propria organizzazione. L'operazione di importazione crea una copia locale delle funzionalità e copia tutti gli artefatti ER che le funzionalità utilizzano (ad esempio, configurazioni di formato e configurazioni di modello) nell'istanza RCS dell'organizzazione.

Puoi importare le funzionalità di fatturazione elettronica da qualsiasi provider di configurazioni.

## <a name="creating-electronic-invoicing-features"></a>Creazione delle funzionalità di fatturazione elettronica

Puoi creare una funzionalità di fatturazione elettronica da zero o derivarla da un'altra funzionalità di fatturazione elettronica.

Quando crei una funzionalità di fatturazione elettronica da zero, è necessario aggiungere manualmente i componenti ER (ad esempio, configurazioni della versione della funzionalità e altre configurazioni, come l'impostazione della versione della funzionalità e l'impostazione dell'applicazione). Quando crei una funzione derivandola da un'altra, la nuova funzione eredita tutte le configurazioni dall'originale. 

## <a name="electronic-invoicing-feature-version"></a>Versione della funzione di fatturazione elettronica

Viene effettuato il controllo delle versioni delle funzioni di fatturazione elettronica. Quando viene creata una nuova versione, il numero di versione viene incrementato automaticamente. È possibile definire una data di "inizio validità" per la nuova versione.

Le versioni delle funzionalità di fatturazione elettronica seguono un ciclo di vita che ha fino a tre stati:

- **Bozza** - Se la versione di una funzione si trova in questo stato, è possibile modificare i suoi attributi di configurazione e tutti i suoi artefatti (ad esempio, configurazioni del formato di file).
- **Completata** - Se una versione della funzionalità si trova in questo stato, è stata pubblicata nel repository globale associato alla propria organizzazione. Non è più possibile modificare la versione della funzione o uno dei componenti ER.
- **Pubblicata** - Se una versione della funzione si trova in questo stato, è stata pubblicata in Fatturazione elettronica. Non è più possibile modificare la versione della funzione o uno dei componenti ER.

### <a name="feature-configurations"></a>Configurazioni delle funzioni

Le configurazioni delle funzionalità contengono tutte le configurazioni del formato ER utilizzate dalle funzionalità di fatturazione elettronica. Tutti i file elettronici utilizzati da una funzione di fatturazione elettronica durante l'elaborazione provengono dalle configurazioni di formato che sono state aggiunte alle configurazioni di quella funzione.

Dalle configurazioni delle funzionalità, è possibile accedere alla progettazione formato ER, che è lo strumento ER utilizzato per creare configurazioni del formato.

### <a name="feature-setup"></a>Impostazione funzionalità

Le impostazioni delle funzionalità vengono utilizzate in combinazione con le configurazioni delle funzionalità. Ciascuna configurazione di funzionalità incapsula una serie di azioni, regole di applicabilità e variabili che forniscono il comportamento previsto in modo che la funzionalità di fatturazione elettronica possa soddisfare il requisito specifico della fattura elettronica.

### <a name="application-setup"></a>Impostazione applicazioni

L'impostazione dell'applicazione deve essere associata a un'applicazione connessa creata in precedenza.

Attraverso l'impostazione dell'applicazione, è possibile configurare la parte di una funzione di fatturazione elettronica che deve essere eseguita in Finance e Supply Chain Management. Sono obbligatori almeno tre componenti configurabili, indipendentemente dalla funzione di fatturazione elettronica:

- **Nome tabella** - L'entità in Finance e Supply Chain Management che contiene le fatture registrate e su cui si basa la funzione di fatturazione elettronica.
- **Contesto** - Il nome del modello di contesto della fattura configurato tramite ER.
- **Mapping di documento aziendale** - Il nome del modello di mapping della fattura configurato tramite ER.

> [!IMPORTANT]
> La configurazione immessa nell'impostazione dell'applicazione può essere visualizzata in Finance e Supply Chain Management. Vai a **Amministrazione organizzazione \> Impostazione \> Parametro documento elettronico**. Nella scheda **Documento elettronico** seleziona **Distribuisci**, quindi seleziona l'opzione **Applicazione connessa**.

### <a name="deploying-feature-versions"></a>Distribuzione delle versioni delle funzionalità

In RCS, usi il comando **Distribuisci** per pubblicare come destinazione una versione della funzione di fatturazione elettronica. Seleziona **Distribuisci**, quindi seleziona una delle seguenti opzioni per definire la destinazione della distribuzione: 

- **Ambiente del servizio** - Quando l'obiettivo della distribuzione è l'ambiente del servizio, la versione della funzione di fatturazione elettronica viene pubblicata nell'ambiente del servizio. Fatturazione elettronica è quindi pronto per ricevere ed elaborare i documenti elettronici inviati da Finance e Supply Chain Management.
- **Applicazione connessa** - Quando la destinazione della distribuzione è l'applicazione connessa, la configurazione fornita dall'impostazione dell'applicazione viene scritta nell'istanza di Finance e Supply Chain Management precedentemente associata ad essa.

Solo le versioni delle funzionalità di fatturazione elettronica con stato **Completato** possono essere distribuite in un ambiente del servizio o in un'applicazione connessa.

### <a name="removing-feature-versions"></a>Rimozione delle versioni delle funzionalità

In RCS, usi il comando **Annulla distribuzione** per rimuovere una versione specifica della funzione di fatturazione elettronica da un ambiente del servizio in Fatturazione elettronica.

> [!IMPORTANT]
> Il comando **Annulla distribuzione** funziona solo negli ambienti del servizio. Non rimuove le versioni della funzione di fatturazione elettronica dalle applicazioni connesse.

### <a name="rebasing-electronic-invoicing-features"></a>Riassegnazione delle funzionalità di fatturazione elettronica

Quando una funzione di fatturazione elettronica deriva da un'altra, il comando **Riassegna** aggiorna la funzionalità derivata con le modifiche introdotte nella funzionalità originale.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Emissione di fatture elettroniche in Finance e Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
