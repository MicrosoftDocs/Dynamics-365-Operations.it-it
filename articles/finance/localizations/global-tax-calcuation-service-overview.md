---
title: Panoramica calcolo delle imposte
description: In questo argomento vengono illustrati l'ambito e le funzionalità generali di Calcolo imposte.
author: wangchen
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: caa7e458763b6ba6b2b85ab016a1aa2e53cee89a
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647059"
---
# <a name="tax-calculation-overview"></a>Panoramica calcolo delle imposte

[!include [banner](../includes/banner.md)]

Calcolo imposte è un servizio multitenant iperscalabile che consente al Global Tax Engine di automatizzare e semplificare il processo di determinazione e calcolo delle imposte. Il motore fiscale è completamente configurabile. Gli elementi che possono essere configurati includono, tra gli altri, il modello di dati imponibili, il codice imposta, la matrice di applicabilità fiscale e la formula di calcolo dell'imposta. Il motore fiscale funziona sulla piattaforma di servizi di base Microsoft Azure e offre una tecnologia moderna e la scalabilità esponenziale.

Calcolo imposte si integra con Dynamics 365 Finance e Dynamics 365 Supply Chain Management. Alla fine, si integrerà anche con Dynamics 365 Project Operations, Dynamics 365 Commerce e altre applicazioni proprietarie e di terze parti.

> [!IMPORTANT]
> Quando abiliti il calcolo delle tasse, alcune operazioni sui dati correlati potrebbero essere eseguite in un centro dati diverso dal centro dati che mantiene i tuoi dati di servizio. Rivedere i [termini e le condizioni](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) prima di abilitare il calcolo delle tasse. La privacy è molto importante. Per ulteriori informazioni, leggere l'[Informativa sulla privacy](https://go.microsoft.com/fwlink/?LinkId=521839) di Microsoft.

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
- Canada
- Europa
- Giappone
- Regno Unito
- Stati Uniti

> [!NOTE]
> Calcolo imposta non supporta le versioni precedenti di Dynamics 365, come Dynamics AX 2012, o le implementazioni on-premises di Dynamics 365.

## <a name="data-flow"></a>Flusso di dati

Ecco uno schema del processo di flusso dei dati per tCalcolo imposta. 

1. In RCS, visualizzare e importare configurazioni di modelli di documenti imponibili e configurazioni di mappatura dei modelli. Se devi estendere le configurazioni per uno scenario avanzato, vedi [Aggiungere campi di dati nelle configurazioni fiscali](tax-service-add-data-fields-tax-configurations.md).
2. In RCS, creare o mantenere caratteristiche fiscali. È possibile utilizzare le funzioni fiscali per mantenere le aliquote d'imposta e le regole di applicabilità dell'imposta.
3. Dopo che la configurazione delle caratteristiche fiscali è stata completata, pubblica le configurazioni fiscali e le caratteristiche fiscali da RCS al repository globale.
4. In Finanza, seleziona quale versione di impostazione delle funzioni fiscali utilizzare per una specifica entità legale.
5. In Finance e Supply Chain Management, operare le transazioni come al solito. Quando il calcolo delle tasse è necessario, il cliente raccoglierà le informazioni dalla transazione, come l'ordine di vendita o di acquisto, e impacchetterà le informazioni come payload. Verrà quindi inviata una richiesta per calcolare la tassa.
6. La richiesta di calcolo dell'imposta viene ricevuta dal cliente e il calcolo viene completato. Il risultato fiscale viene poi restituito al cliente.
7. Il client Dynamics 365 riceve il risultato dell'imposta e presenta il risultato del calcolo dell'imposta su una pagina dell'imposta sulle vendite.

## <a name="supported-transactions"></a>Transazioni supportate

Il calcolo delle tasse può essere abilitato dalle transazioni. 

Le seguenti transazioni sono supportate nella versione 10.0.21: 

- Vendite

    - Offerta di vendita
    - Ordine cliente
    - Conferma
    - Distinta di prelievo
    - Documento di trasporto
    - Fattura di vendita
    - Nota di accredito
    - Ordine di reso
    - Spese varie intestazione
    - Spese varie riga

- Acquisti

    - Ordine fornitore
    - Conferma
    - Elenco entrate
    - Entrata prodotti
    - Fattura acquisto
    - Spese varie intestazione
    - Spese varie riga
    - Nota di accredito
    - Ordine di reso
    - Richiesta di acquisto
    - Spese varie riga di richiesta di acquisto
    - Richiesta di offerta
    - Spese varie intestazione richiesta di offerta
    - Spese varie riga richiesta di offerta

- Inventario

    - Ordine di trasferimento - spedizione
    - Ordine di trasferimento - ricezione

Le seguenti transazioni sono supportate nella versione 10.0.23: 

- Fattura a testo libero

## <a name="supported-countriesregions"></a>Paesi/regioni supportati

Il calcolo delle tasse può essere abilitato per entità giuridica. 

I seguenti paesi/regioni per l'indirizzo primario di una persona giuridica sono supportati nella versione 10.0.21:

- Austria
- Belgio
- Danimarca
- Estonia
- Finlandia
- Francia
- Germania
- Ungheria
- Islanda
- Italia
- Lettonia
- Lituania
- Paesi Bassi
- Norvegia
- Polonia
- Svezia
- Svizzera
- Regno Unito
- Stati Uniti

I seguenti paesi/regioni per l'indirizzo primario di una persona giuridica sono supportati nella versione 10.0.22:

- Australia
- Bahrein
- Canada
- Egitto
- RAS di Hong Kong
- Kuwait
- Nuova Zelanda
- Oman
- Qatar
- Arabo Saudita
- Sudafrica
- Emirati Arabi Uniti

I seguenti paesi/regioni per l'indirizzo primario di una persona giuridica sono supportati nella versione 10.0.23:

- Thailandia
- Giappone
- Malaysia
- Singapore

## <a name="related-resources"></a>Risorse correlate

[Introduzione al servizio per le imposte](./global-get-started-with-tax-calculation-service.md)

[Più numeri di registrazione IVA](./emea-multiple-vat-registration-numbers.md)

[Supporto della funzione fiscale per l'ordine di trasferimento](./tasks/tax-feature-support-for-transfer-order.md)

[Come creare l'estensione nel servizio per le imposte](./tax-service-add-data-fields-tax-integration-by-extension.md)
