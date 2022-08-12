---
title: Confronto tra funzionalità cloud e locali
description: Questo articolo fornisce informazioni sulla disponibilità delle funzionalità cloud e locali supportate.
author: sericks007
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: 5ef6a1574f55ad8a4222658887249db4a5490042
ms.sourcegitcommit: 9cfccb5c260ce56a3457f9ea12e80f54ea55a3b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183839"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>Confronto tra funzionalità cloud e locali

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato un confronto delle funzionalità disponibili nel cloud rispetto a quelle locali per le seguenti applicazioni:

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

Sono incluse anche informazioni sulle [funzionalità di amministrazione e sviluppo](cloud-prem-comparison.md#development-and-administration-features).

Nelle tabelle seguenti sono elencate le aree di applicazione. Il supporto cloud e locale è elencato per la funzionalità nel suo insieme. Quando specifiche funzionalità differiscono dall'area, le funzionalità sono elencate in una riga distinta nella colonna Funzionalità.

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **Area**             | **Funzionalità**                | **Cloud** | **On-premises** |
|---------------------|-----------------------------|-----------|-----------------|
| Conformità e certificazioni        |                                                                                           | Sì       | Sì             |
|                                      | Certificazione SOC 1 tipo 1                                                                | Sì       | No              |
| Gestione dati e integrazione      |                                                                                           | Sì       | Sì             |
|                                      | Esportazione di dati nel proprio magazzino dati                                                    | Sì       | Sì             |
|                                      | Attivazione dell'esportazione di aggiornamenti incrementali in un'entità di dati                                 | Sì       | Sì             |
|                                      | Integrazioni di dati                                                                         | Sì       | Sì             |
| Gestione documenti                  |                                                                                           | Sì       | Sì             |
| Gestione finanziaria                 |                                                                                           | Sì       | Sì             |
| ?                                 |                                                                                           | Sì       | No              |
| Risorse umane                      |                                                                                           | Sì       | Sì             |
| Intelligence                         |                                                                                           | Sì       | Sì             |
|                                      | Creazione di report elettronici (ER)                                                                 | Sì       | Sì             |
|                                      | Report elettronici: integrazione con LCS                                                                  | Sì       | No              |
|                                      | Report elettronici: integrazione con SharePoint                                                           | Sì       | No              |
|                                      | Report elettronici: integrazione con Regulatory Configuration Service (RCS)                              | Sì       | No              |
|                                      | Report elettronici: utilizza il file system locale come archivio delle configurazioni di report elettronici accessibili via repository di report elettronici | No        | Sì             |
|                                      | Integrazione con PowerBI.com                                                              | Sì       | No              |
|                                      | Integrazione con PowerBI Desktop                                                          | No        | Sì             |
|                                      | Aree di lavoro analitiche                                                                     | Sì       | No              |
|                                      | Processo aziendale intelligente: suggerimenti                                             | Sì       | No              |
|                                      | Creazione di report Power BI con OData utilizzando il desktop Power BI o gli strumenti PowerQuery di Excel    | Sì       | No              |
|                                      | SQL Server Reporting Services (SSRS) supporta la scalabilità orizzontale                                 | Sì       | Sì             |
|                                      | La telemetria viene trasferita nel cloud                                                   | Sì       | No              |
| Lifecycle Services                   |                                                                                           | Sì       | Sì             |
|                                      | Processi aziendali configurabili                                                           | Sì       | No              |
| Localizzazioni                        |                                                                                           | Sì       | Sì             |
| App per dispositivi mobili, aree di lavoro e piattaforma |                                                                                           | Sì       | Sì             |
| Integrazione di Office                   |                                                                                           | Sì       | Sì             |
| Amministrazione organizzazione          |                                                                                           | Sì       | Sì             |
| Retribuzioni                              |                                                                                           | Sì       | Sì             |
|                                      | Deposito diretto                                                                            | Sì       | No              |
| Gestione progetti e contabilità    |                                                                                           | Sì       | Sì             |
| Sicurezza                             |                                                                                           | Sì       | Sì             |
| Gestione dei servizi                   |                                                                                           | Sì       | Sì             |
| Client Web                           |                                                                                           | Sì       | Sì             |
|                                      | Registrazione attività - Salvataggio o caricamento di registrazioni attività dalla libreria BPM                         | Sì       | No              |
| Supporto                              |                                                                                           | Sì       | Sì             |
|                                      | Accesso al supporto tramite il menu Guida e supporto                                             | Sì       | No              |
|                                      | Eventi aziendali                                                                           | Sì       | Sì (è necessaria la connessione Internet o è necessario implementare endpoint personalizzati per inviare/ricevere eventi aziendali nella rete Intranet)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **Area**                | **Funzionalità**             | **Cloud** | **Locale** |
|-------------------------|-------------------|-----------|-----------------|
| Gestione cespiti                     |                                                                                           | Sì       | Sì             |
| Conformità e certificazioni        |                                                                                           | Sì       | Sì             |
|                                      | Certificazione SOC 1 tipo 1                                                                | Sì       | No              |
| Contabilità industriale                      |                                                                                           | Sì       | Sì             |
|                                      | Pacchetto di contenuti per la contabilità industriale in Power BI                                                 | Sì       | No              |
|                                      | Area di lavoro di contabilità industriale per app per dispositivi mobili                                                  | Sì       | No              |
| Gestione costi                      |                                                                                           | Sì       | Sì             |
|                                      | Pacchetto di contenuti per la gestione dei costi in Power BI                                                 | Sì       | No              |
| Gestione dati e integrazione      |                                                                                           | Sì       | Sì             |
|                                      | Estensione basata sulla configurazione                                                            | Sì       | No              |
|                                      | Esportazione di dati nel proprio magazzino dati                                                    | Sì       | Sì             |
|                                      | Attivazione dell'esportazione di aggiornamenti incrementali in un'entità di dati                                 | Sì       | Sì             |
|                                      | Integrazioni di dati                                                                         | Sì       | Sì             |
| Gestione documenti                  |                                                                                           | Sì       | Sì             |
| ?                                 |                                                                                           | Sì       | No              |
| Intelligence                         |                                                                                           | Sì       | Sì             |
|                                      | Creazione di report elettronici (ER)                                                                 | Sì       | Sì             |
|                                      | Report elettronici: integrazione con LCS                                                                  | Sì       | No              |
|                                      | Report elettronici: integrazione con SharePoint                                                           | Sì       | No              |
|                                      | Report elettronici: integrazione con Regulatory Configuration Service (RCS)                              | Sì       | No              |
|                                      | Report elettronici: utilizza il file system locale come archivio delle configurazioni di report elettronici accessibili via repository di report elettronici | No        | Sì             |
|                                      | Integrazione con PowerBI.com                                                              | Sì       | No              |
|                                      | Integrazione con PowerBI Desktop                                                          | No        | Sì             |
|                                      | Aree di lavoro analitiche                                                                     | Sì       | No              |
|                                      | Processo aziendale intelligente: suggerimenti                                             | Sì       | No              |
|                                      | Creazione di report Power BI con OData utilizzando il desktop Power BI o gli strumenti PowerQuery di Excel    | Sì       | No              |
|                                      | SQL Server Reporting Services (SSRS) supporta la scalabilità orizzontale                                 | Sì       | Sì             |
|                                      | La telemetria viene trasferita nel cloud                                                   | Sì       | No              |
| Gestione inventario                 |                                                                                           | Sì       | Sì             |
| Lifecycle Services                   |                                                                                           | Sì       | Sì             |
|                                      | Processi aziendali configurabili                                                           | Sì       | No              |
| Localizzazioni                        |                                                                                           | Sì       | Sì             |
| Produzione                        |                                                                                           | Sì       | Sì             |
| Offerta e pianificazione generale      |                                                                                           | Sì       | Sì             |
|                                      | Ottimizzazione pianificazione                                                                     | Sì       | No              |
| App per dispositivi mobili, aree di lavoro e piattaforma |                                                                                           | Sì       | Sì             |
| Integrazione Office                   |                                                                                           | Sì       | Sì             |
| Amministrazione organizzazione          |                                                                                           | Sì       | Sì             |
| Approvvigionamento             |                                                                                           | Sì       | Sì             |
|                                      | Collegamento al catalogo esterno dalla richiesta di acquisto                                   | Sì       | No              |
|                                      | Report Power BI sull'analisi delle spese di acquisto                                                  | Sì       | No              |
| Gestione informazioni sul prodotto       |                                                                                           | Sì       | Sì             |
| Dati di rappresentazione generale prodotto                  |                                                                                           | Sì       | Sì             |
| Produzione                           |                                                                                           | Sì       | Sì             |
|                                      | Report Power BI su prestazioni di produttività                                                   | Sì       | No              |
| Gestione progetti e contabilità    |                                                                                           | Sì       | Sì             |
| Vendite                                |                                                                                           | Sì       | Sì             |
|                                      | Report Power BI su prestazioni di vendita e profitto                                      | Sì       | No              |
| Sicurezza                             |                                                                                           | Sì       | Sì             |
| Gestione assistenza                   |                                                                                           | Sì       | Sì             |
| Gestione della supply chain              |                                                                                           | Sì       | Sì             |
| Gestione trasporto            |                                                                                           | Sì       | Sì             |
| Collaborazione fornitore                 |                                                                                           | Sì       | No              |
| Gestione magazzino                 |                                                                                           | Sì       | Sì             |
|                                      | App magazzino per dispositivi mobili                                                                      | Sì       | Sì             |
|                                      | Report Power BI su magazzino                                                              | Sì       | No              |
| Client Web                           |                                                                                           | Sì       | Sì             |
|                                      | Registrazione attività - Salvataggio o caricamento di registrazioni attività dalla libreria BPM                         | Sì       | No              |
| Supporto                              |                                                                                           | Sì       | Sì             |
|                                      | Accesso al supporto tramite il menu Guida e supporto                                             | Sì       | No              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

Per visualizzare un elenco delle capacità disponibili nelle distribuzioni locali, vedere [Funzionalità di commercio disponibili in distribuzioni locali](../../../commerce/retail-onprem.md).

## <a name="dynamics-365-human-resources"></a>Dynamics 365 Human Resources 

| **Area**         | **Funzionalità**         | **Cloud** | **On-premises** |
|------------------|---------------------|-----------|-----------------|
| Tutte le aree di Human Resources | Tutte le funzionalità di Human Resources | Sì       | No              |

## <a name="development-and-administration-features"></a>Funzionalità di amministrazione e sviluppo

| **Area**                   | **Funzionalità**                               | **Cloud** | **On-premises** |
|----------------------------|-------------------------------------------|-----------|-----------------|
| Compilazione e test             |                                           | Sì       | Sì             |
| Estendibilità              |                                           | Sì       | Sì             |
| Monitoraggio e telemetria   |                                           | Sì       | Sì             |
| Compatibilità della piattaforma     |                                           | Sì       | Sì             |
| Manutenzione                  |                                           | Sì       | Sì             |
|                            | Ambienti di manutenzione                    | Sì       | No              |
| Parser di traccia               |                                           | Sì       | Sì             |
| PerfTimer                  |                                           | Sì       | Sì\*           |
| Aggiorna                    |                                           | Sì       | Sì             |
|                            | Aggiorna                                   | Sì       | No              |
|                            | Aggiornamento e supporto per le versioni precedenti | Sì       | No              |
| Sviluppo di Visual Studio  |                                           | Sì       | Sì             |

\* Negli ambienti locali, PerfTimer mostra solo i risultati per il client.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
