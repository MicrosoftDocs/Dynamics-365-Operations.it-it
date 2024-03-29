---
title: Panoramica calcolo delle imposte
description: In questo articolo vengono illustrati l'ambito e le funzionalità generali di Calcolo imposte.
author: EricWangChen
ms.date: 09/08/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.search.form: TaxIntegrationTaxServiceParameters
ms.openlocfilehash: cafc4c7089e0c042fc65c1e3fd21f8f1e930b785
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689886"
---
# <a name="tax-calculation-overview"></a>Panoramica calcolo delle imposte

[!include [banner](../includes/banner.md)]

Calcolo imposte è un servizio multitenant iperscalabile che consente al Global Tax Engine di automatizzare e semplificare il processo di determinazione e calcolo delle imposte. Il motore fiscale è completamente configurabile. Gli elementi che possono essere configurati includono, tra gli altri, il modello di dati imponibili, il codice imposta, la matrice di applicabilità fiscale e la formula di calcolo dell'imposta. Il motore fiscale funziona sulla piattaforma di servizi di base Microsoft Azure e offre una tecnologia moderna e la scalabilità esponenziale.

Il calcolo delle imposte si integra con Dynamics 365 Finance e Dynamics 365 Supply Chain Management. Alla fine, si integrerà anche con Dynamics 365 Project Operations, Dynamics 365 Commerce e altre applicazioni proprietarie e di terze parti.

> [!IMPORTANT]
> Quando abiliti il calcolo delle tasse, alcune operazioni sui dati correlati potrebbero essere eseguite in un centro dati diverso dal centro dati che mantiene i tuoi dati di servizio. Rivedere i [termini e le condizioni](https://go.microsoft.com/fwlink/?linkid=2156043) prima di abilitare il calcolo delle tasse. La privacy è molto importante. Per ulteriori informazioni, leggere l'[Informativa sulla privacy](https://go.microsoft.com/fwlink/?LinkId=521839) di Microsoft.

Calcolo imposta è un motore fiscale basato su microservizi che offre una scalabilità esponenziale e può aiutarvi a eseguire i seguenti compiti:

- Determina automaticamente il corretto gruppo d'imposta sulle vendite, il gruppo d'imposta sulle vendite degli articoli e i codici fiscali attraverso un meccanismo di determinazione migliorato.
- Supporta più numeri di registrazione fiscale in un'entità legale, e determina automaticamente il corretto numero di registrazione fiscale sulle transazioni imponibili.
- Supporta la determinazione delle tasse, il calcolo, la registrazione e la liquidazione degli ordini di trasferimento.
- Definite formule e condizioni di calcolo delle tasse configurabili per le vostre specifiche esigenze aziendali.
- Condividere la soluzione di determinazione e calcolo delle imposte tra entità legali per risparmiare sforzi di manutenzione ed evitare errori.
- Sostenere la determinazione del numero di registrazione fiscale del cliente e del venditore.
- Determinazione del codice della lista di supporto.
- Supporta i parametri di calcolo delle tasse a livello di giurisdizione fiscale.

Per usare Calcolo imposta, installate l'add-in Calcolo imposta dal vostro progetto in Microsoft Dynamics Lifecycle Services. Poi completate la configurazione in [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/), e abilitate il calcolo delle tasse in Finance and Supply Chain Management. Per altre informazioni, vedi [Introduzione al servizio per le imposte](global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Disponibilità

Calcolo imposta è generalmente disponibile in ambienti di produzione per tutti i clienti a partire dalla versione 10.0.21.

Nuove funzionalità continueranno ad essere fornite. Controllate spesso il piano di rilascio più aggiornato per conoscere la copertura e la portata delle funzionalità supportate.

Calcolo imposte viene distribuito nelle seguenti aree geografiche di Azure. Altre aree geografiche di Azure saranno aggiunte in base alle esigenze dei clienti.

- Asia Pacifico
- Australia
- Brasile
- Canada
- Europa
- Francia
- India
- Giappone
- Sudafrica
- Svizzera
- Emirati Arabi Uniti
- Regno Unito
- Stati Uniti

> [!NOTE]
> Calcolo imposta non supporta le versioni precedenti di Dynamics 365, come Dynamics AX 2012, o le implementazioni on-premises di Dynamics 365.

## <a name="versions"></a>Versioni
Ti consigliamo di importare e impostare la configurazione del calcolo delle imposte con la versione che corrisponde alla tua versione di Finance o Supply Chain Management.

| Versione di Finance o Supply Chain Management | Versione di configurazione delle imposte               |
| --------------- | --------------------------------------- |
| 10.0.31         | Configurazione del calcolo dell'imposta 40.56.240 |
| 10.0.30         | Configurazione del calcolo dell'imposta 40.55.239 |
| 10.0.29         | Configurazione del calcolo dell'imposta 40.55.236 |
| 10.0.28         | Configurazione del calcolo dell'imposta 40.54.234 |
| 10.0.27         | Configurazione del calcolo dell'imposta 40.54.234 |


## <a name="data-flow"></a>Flusso di dati

Ecco uno schema del processo di flusso dei dati per Calcolo imposta. 

1. In RCS, visualizzare e importare configurazioni di modelli di documenti imponibili e configurazioni di mappatura dei modelli. Se devi estendere le configurazioni per uno scenario avanzato, vedi [Aggiungere campi di dati nelle configurazioni fiscali](tax-service-add-data-fields-tax-configurations.md).
2. In RCS, creare o mantenere caratteristiche fiscali. È possibile utilizzare le funzioni fiscali per mantenere le aliquote d'imposta e le regole di applicabilità dell'imposta.
3. Dopo che la configurazione delle caratteristiche fiscali è stata completata, pubblica le configurazioni fiscali e le caratteristiche fiscali da RCS al repository globale.
4. In Finanza, seleziona quale versione di impostazione delle funzioni fiscali utilizzare per una specifica entità legale.
5. In Finance e Supply Chain Management, operare le transazioni come al solito. Quando il calcolo delle tasse è necessario, il cliente raccoglierà le informazioni dalla transazione, come l'ordine cliente o fornitore, e impacchetterà le informazioni come payload. Verrà quindi inviata una richiesta per calcolare la tassa.
6. La richiesta di calcolo dell'imposta viene ricevuta dal cliente e il calcolo viene completato. Il risultato fiscale viene poi restituito al cliente.
7. Il client Dynamics 365 riceve il risultato dell'imposta e presenta il risultato del calcolo dell'imposta su una pagina dell'imposta sulle vendite.

## <a name="supported-transactions"></a>Transazioni supportate

Il calcolo delle tasse può essere abilitato dalle transazioni. 

La tabella seguente elenca le transazioni supportate nella versione corrispondente.

| Versione | Transazioni |
|---------|--------------|
| 10.0.29 | Giornali di registrazione periodici |
| 10.0.28 | Giornale di registrazione pagamenti fornitore<br> Giornale di registrazione pagamenti cliente | 
| 10.0.26 | Giornali di registrazione generali<br> Giornale di registrazione fatture fornitore |
| 10.0.23 | Fattura a testo libero |
| 10.0.21| Vendite<br><ul><li>Offerta di vendita</li><li>Ordine cliente</li><li>Conferma</li><li>Distinta di prelievo</li><li>Documento di trasporto</li><li>Fattura di vendita</li><li>Nota di accredito</li><li>Ordine di reso</li><li>Spese varie intestazione</li><li>Spese varie riga</li></ul>Acquisti<br><ul><li>Ordine fornitore</li><li>Conferma</li><li>Elenco entrate</li><li>Entrata prodotti</li><li>Fattura acquisto</li><li>Spese varie intestazione</li><li>Spese varie riga</li><li>Nota di accredito</li><li>Ordine di reso</li><li>Richiesta di acquisto</li><li>Spese varie riga di richiesta di acquisto</li><li>Richiesta di offerta</li><li>Spese varie intestazione richiesta di offerta</li><li>Spese varie riga richiesta di offerta</li></ul>Scorte<ul><li>Ordine di trasferimento - spedizione</li><li>Ordine di trasferimento - ricezione</li></ul>|

## <a name="supported-countriesregions"></a>Paesi/regioni supportati

Il calcolo delle imposte può essere eseguito con le funzionalità di localizzazione supportate. La tabella seguente elenca i paesi/aree geografiche per l'indirizzo principale di una persona giuridica.

| Versione | Paese |
|---------|----------------|
| 10.0.26 | - Cina <br>- Repubblica Ceca<br>- Spagna |
| 10.0.24 | Messico |
| 10.0.23 | - Thailandia <br>- Giappone <br>- Malaysia <br>- Singapore |
| 10.0.22 | - Australia<br>- Bahrein <br>- Canada<br>- Egitto <br>- RAS di Hong Kong <br>- Kuwait <br>- Nuova Zelanda <br>- Oman <br>- Qatar <br>- Arabia Saudita <br>- Sudafrica <br>- Emirati Arabi Uniti |
| 10.0.21 | - Austria <br>- Belgio <br>- Danimarca <br>- Estonia <br>- Finlandia <br>- Francia <br>- Germania <br>- Ungheria <br>- Islanda <br>- Irlanda <br>- Italia <br>- Lettonia <br>- Lituania <br>- Paesi Bassi <br>- Regno di Norvegia <br>- Polonia <br>- Svezia <br>- Svizzera <br>- Regno Unito <br>- Stati Uniti |

Per qualsiasi paese/area geografica non localizzata da Microsoft, Calcolo imposte può anche essere abilitato ed eseguito con altre funzionalità globali.

## <a name="related-resources"></a>Risorse correlate

[Introduzione al servizio per le imposte](./global-get-started-with-tax-calculation-service.md)

[Più numeri di registrazione IVA](./emea-multiple-vat-registration-numbers.md)

[Supporto della funzione fiscale per l'ordine di trasferimento](./tasks/tax-feature-support-for-transfer-order.md)

[Come creare l'estensione nel servizio per le imposte](./tax-service-add-data-fields-tax-integration-by-extension.md)
