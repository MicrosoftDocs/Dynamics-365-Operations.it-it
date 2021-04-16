---
title: Servizio di calcolo delle imposte (anteprima)
description: In questo argomento vengono illustrati l'ambito e le funzionalità generali del servizio di calcolo delle imposte.
author: wangchen
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 518d3fda7b97e55d23beea6a1ba0e50b44a7aa0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818226"
---
# <a name="tax-calculation-service-preview"></a>Servizio di calcolo delle imposte (anteprima)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Il servizio di calcolo delle imposte è un servizio multitenant iperscalabile che consente al Global Tax Engine di automatizzare e semplificare il processo di determinazione e calcolo delle imposte. Il motore fiscale è completamente configurabile. Gli elementi che possono essere configurati includono, tra gli altri, il modello di dati imponibili, il codice imposta, la matrice di applicabilità fiscale e la formula di calcolo dell'imposta. Il motore fiscale funziona sulla piattaforma di servizi di base Microsoft Azure e offre una tecnologia moderna e la scalabilità esponenziale.

Il servizio di calcolo delle imposte si integra con Dynamics 365 Finance e Dynamics 365 Supply Chain Management. Alla fine, si integrerà anche con Dynamics 365 Project Operations, Dynamics 365 Commerce e altre applicazioni proprietarie e di terze parti.

Il servizio di calcolo delle imposte è un motore fiscale basato su Microsoft che offre scalabilità esponenziale. Ti consente di eseguire le attività descritte di seguito:

- Configura il servizio di calcolo delle imposte tramite Regulatory Configuration Service (RCS). RCS è una versione avanzata dello strumento di progettazione per la creazione di report elettronici (ER) ed è disponibile come servizio autonomo.
- Configura la matrice fiscale per determinare automaticamente i codici e le aliquote fiscali.
- Configura la matrice fiscale per determinare automaticamente il numero di registrazione fiscale.
- Configura lo strumento di progettazione del calcolo delle imposte per definire le formule e le condizioni.
- Condividi la determinazione delle imposte e la soluzione di calcolo tra le persone giuridiche.

Per utilizzare il servizio di calcolo delle imposte, installa il componente aggiuntivo del servizio di calcolo delle imposte dal progetto in Microsoft Dynamics Lifecycle Services (LCS). Quindi completa la configurazione in RCS e abilita il servizio di calcolo delle imposte in Finance and Supply Chain Management. Per altre informazioni, vedi [Introduzione al servizio per le imposte](https://go.microsoft.com/fwlink/?linkid=2138482).

## <a name="availability"></a>Disponibilità

Il servizio di calcolo delle imposte è disponibile solo in ambienti sandbox e per clienti selezionati, attraverso un programma di anteprima pubblica. Alla fine, diventerà generalmente disponibile per tutti i clienti e negli ambienti di produzione.

Nuove funzionalità continueranno a essere aggiunte nel servizio di calcolo delle imposte. Pertanto, assicurati di controllare spesso la documentazione più aggiornata per conoscere la copertura e l'ambito delle funzionalità supportate.

Il servizio di calcolo delle imposte viene distribuito nelle seguenti aree geografiche di Azure. Verrà inoltre distribuito in più aree geografiche di Azure, in base alle esigenze del cliente:

- Stati Uniti
- Europa
- Francia
- Regno Unito

> [!NOTE]
> Il servizio di calcolo delle imposte non supporta le distribuzioni locali di Dynamics 365. Inoltre non supporta le versioni precedenti, come Dynamics AX 2012.

## <a name="feature-highlights"></a>Caratteristiche principali

- Una matrice fiscale configurabile per determinare automaticamente e calcolare le imposte
- Supporto per più numeri di registrazione dell'IVA
- Supporto dell'ordine di trasferimento per la determinazione e il calcolo delle imposte
- Supporto per ordini di trasferimento per la determinazione di più numeri di registrazione dell'IVA

## <a name="supported-transactions"></a>Transazioni supportate

Il servizio di calcolo delle imposte può essere abilitato per persona giuridica e transazione. Sono supportate le transazioni che seguono:

- Processo di vendita

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

- Processo di acquisto

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

- Processo magazzino

    - Ordine di trasferimento - spedizione
    - Ordine di trasferimento - ricezione

## <a name="related-resources"></a>Risorse correlate

[Introduzione al servizio per le imposte](https://go.microsoft.com/fwlink/?linkid=2138482)

[Più numeri di registrazione IVA](https://go.microsoft.com/fwlink/?linkid=2153387)

[Supporto della funzione fiscale per l'ordine di trasferimento](https://go.microsoft.com/fwlink/?linkid=2153388)

[Come creare l'estensione nel servizio per le imposte](https://go.microsoft.com/fwlink/?linkid=2138483)
