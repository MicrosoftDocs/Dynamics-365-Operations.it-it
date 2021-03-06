---
title: Confronto tra funzionalità cloud e locali
description: Questo argomento fornisce informazioni sulla disponibilità delle funzionalità cloud e locali supportate.
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
ms.openlocfilehash: 497061500660e41c8f82c73e5dd6c085810c9209
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910451"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>Confronto tra funzionalità cloud e locali

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato un confronto delle funzionalità disponibili nel cloud rispetto a quelle locali per le seguenti applicazioni:

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

Sono incluse anche informazioni sulle [funzionalità di amministrazione e sviluppo](cloud-prem-comparison.md#development-and-administration-features).

Nelle tabelle seguenti sono elencate le aree di applicazione. Il supporto cloud e locale è elencato per la funzionalità nel suo insieme. Quando specifiche funzionalità differiscono dall'area, le funzionalità sono elencate in una riga distinta nella colonna Funzionalità.

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **Area**             | **Funzionalità**                | **Cloud** | **Locale** |
|---------------------|-----------------------------|-----------|-----------------|
| Conformità e certificazioni        |                                                                                           | Sì       | Sì             |
|                                      | Certificazione SOC 1 tipo 1                                                                | Sì       | Nessuno              |
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
|                                      | Report elettronici: integrazione con LCS                                                                  | Sì       | Nessuno              |
|                                      | Report elettronici: integrazione con SharePoint                                                           | Sì       | Nessuno              |
|                                      | Report elettronici: integrazione con Regulatory Configuration Service (RCS)                              | Sì       | Nessuno              |
|                                      | Report elettronici: utilizza il file system locale come archivio delle configurazioni di report elettronici accessibili via repository di report elettronici | Nessuno        | Sì             |
|                                      | Integrazione con PowerBI.com                                                              | Sì       | Nessuno              |
|                                      | Integrazione con PowerBI Desktop                                                          | Nessuno        | Sì             |
|                                      | Aree di lavoro analitiche                                                                     | Sì       | Nessuno              |
|                                      | Processo aziendale intelligente: suggerimenti                                             | Sì       | Nessuna              |
|                                      | Creazione di report Power BI con OData utilizzando il desktop Power BI o gli strumenti PowerQuery di Excel    | Sì       | Nessuna              |
|                                      | SQL Server Reporting Services (SSRS) supporta la scalabilità orizzontale                                 | Sì       | Sì             |
|                                      | La telemetria viene trasferita nel cloud                                                   | Sì       | Nessuno              |
| Lifecycle Services                   |                                                                                           | Sì       | Sì             |
|                                      | Processi aziendali configurabili                                                           | Sì       | Nessuno              |
| Localizzazioni                        |                                                                                           | Sì       | Sì             |
| App per dispositivi mobili, aree di lavoro e piattaforma |                                                                                           | Sì       | Sì             |
| Integrazione di Office                   |                                                                                           | Sì       | Sì             |
| Amministrazione organizzazione          |                                                                                           | Sì       | Sì             |
| Retribuzioni                              |                                                                                           | Sì       | Sì             |
|                                      | Deposito diretto                                                                            | Sì       | Nessuno              |
| Gestione progetti e contabilità    |                                                                                           | Sì       | Sì             |
| Sicurezza                             |                                                                                           | Sì       | Sì             |
| Gestione dei servizi                   |                                                                                           | Sì       | Sì             |
| Client Web                           |                                                                                           | Sì       | Sì             |
|                                      | Registrazione attività - Salvataggio o caricamento di registrazioni attività dalla libreria BPM                         | Sì       | No              |
| Supporto                              |                                                                                           | Sì       | Sì             |
|                                      | Accesso al supporto tramite il menu Guida e supporto                                             | Sì       | Nessuno              |
|                                      | Eventi aziendali                                                                           | Sì       | Sì (è necessaria la connessione Internet o è necessario implementare endpoint personalizzati per inviare/ricevere eventi aziendali nella rete Intranet)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **Area**                | **Funzionalità**             | **Cloud** | **Locale** |
|-------------------------|-------------------|-----------|-----------------|
| Gestione cespiti                     |                                                                                           | Sì       | Sì             |
| Conformità e certificazioni        |                                                                                           | Sì       | Sì             |
|                                      | Certificazione SOC 1 tipo 1                                                                | Sì       | Nessuna              |
| Contabilità industriale                      |                                                                                           | Sì       | Sì             |
|                                      | Pacchetto di contenuti per la contabilità industriale in Power BI                                                 | Sì       | Nessuna              |
|                                      | Area di lavoro di contabilità industriale per app per dispositivi mobili                                                  | Sì       | Nessuna              |
| Gestione costi                      |                                                                                           | Sì       | Sì             |
|                                      | Pacchetto di contenuti per la gestione dei costi in Power BI                                                 | Sì       | Nessuna              |
| Gestione dati e integrazione      |                                                                                           | Sì       | Sì             |
|                                      | Estensione basata sulla configurazione                                                            | Sì       | No              |
|                                      | Esportazione di dati nel proprio magazzino dati                                                    | Sì       | Sì             |
|                                      | Attivazione dell'esportazione di aggiornamenti incrementali in un'entità di dati                                 | Sì       | Sì             |
|                                      | Integrazioni di dati                                                                         | Sì       | Sì             |
| Gestione documenti                  |                                                                                           | Sì       | Sì             |
| ?                                 |                                                                                           | Sì       | Nessuno              |
| Intelligence                         |                                                                                           | Sì       | Sì             |
|                                      | Creazione di report elettronici (ER)                                                                 | Sì       | Sì             |
|                                      | Report elettronici: integrazione con LCS                                                                  | Sì       | Nessuno              |
|                                      | Report elettronici: integrazione con SharePoint                                                           | Sì       | Nessuno              |
|                                      | Report elettronici: integrazione con Regulatory Configuration Service (RCS)                              | Sì       | Nessuno              |
|                                      | Report elettronici: utilizza il file system locale come archivio delle configurazioni di report elettronici accessibili via repository di report elettronici | Nessuno        | Sì             |
|                                      | Integrazione con PowerBI.com                                                              | Sì       | Nessuno              |
|                                      | Integrazione con PowerBI Desktop                                                          | Nessuno        | Sì             |
|                                      | Aree di lavoro analitiche                                                                     | Sì       | Nessuno              |
|                                      | Processo aziendale intelligente: suggerimenti                                             | Sì       | Nessuna              |
|                                      | Creazione di report Power BI con OData utilizzando il desktop Power BI o gli strumenti PowerQuery di Excel    | Sì       | Nessuna              |
|                                      | SQL Server Reporting Services (SSRS) supporta la scalabilità orizzontale                                 | Sì       | Sì             |
|                                      | La telemetria viene trasferita nel cloud                                                   | Sì       | Nessuno              |
| Gestione inventario                 |                                                                                           | Sì       | Sì             |
| Lifecycle Services                   |                                                                                           | Sì       | Sì             |
|                                      | Processi aziendali configurabili                                                           | Sì       | No              |
| Localizzazioni                        |                                                                                           | Sì       | Sì             |
| Produzione                        |                                                                                           | Sì       | Sì             |
| Offerta e pianificazione generale      |                                                                                           | Sì       | Sì             |
| Ottimizzazione pianificazione                |                                                                                           | Sì       | Nessuno              |
| App per dispositivi mobili, aree di lavoro e piattaforma |                                                                                           | Sì       | Sì             |
| Integrazione Office                   |                                                                                           | Sì       | Sì             |
| Amministrazione organizzazione          |                                                                                           | Sì       | Sì             |
| Approvvigionamento             |                                                                                           | Sì       | Sì             |
|                                      | Collegamento al catalogo esterno dalla richiesta di acquisto                                   | Sì       | Nessuna              |
|                                      | Report Power BI sull'analisi delle spese di acquisto                                                  | Sì       | Nessuna              |
| Gestione informazioni sul prodotto       |                                                                                           | Sì       | Sì             |
| Dati di rappresentazione generale prodotto                  |                                                                                           | Sì       | Sì             |
| Produzione                           |                                                                                           | Sì       | Sì             |
|                                      | Report Power BI su prestazioni di produttività                                                   | Sì       | Nessuna              |
| Gestione progetti e contabilità    |                                                                                           | Sì       | Sì             |
| Vendite                                |                                                                                           | Sì       | Sì             |
|                                      | Report Power BI su prestazioni di vendita e profitto                                      | Sì       | Nessuna              |
| Sicurezza                             |                                                                                           | Sì       | Sì             |
| Gestione assistenza                   |                                                                                           | Sì       | Sì             |
| Gestione della supply chain              |                                                                                           | Sì       | Sì             |
| Gestione trasporto            |                                                                                           | Sì       | Sì             |
| Collaborazione fornitore                 |                                                                                           | Sì       | No              |
| Gestione magazzino                 |                                                                                           | Sì       | Sì             |
|                                      | App magazzino per dispositivi mobili                                                                      | Sì       | Sì             |
|                                      | Report Power BI su magazzino                                                              | Sì       | Nessuna              |
| Client Web                           |                                                                                           | Sì       | Sì             |
|                                      | Registrazione attività - Salvataggio o caricamento di registrazioni attività dalla libreria BPM                         | Sì       | No              |
| Supporto                              |                                                                                           | Sì       | Sì             |
|                                      | Accesso al supporto tramite il menu Guida e supporto                                             | Sì       | Nessuno              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

Per visualizzare un elenco delle capacità disponibili nelle distribuzioni locali, vedere [Funzionalità di commercio disponibili in distribuzioni locali](../../../commerce/retail-onprem.md).

## <a name="dynamics-365-human-resources"></a>Dynamics 365 Human Resources 

| **Area**         | **Funzionalità**         | **Cloud** | **On-premises** |
|------------------|---------------------|-----------|-----------------|
| Tutte le aree di Human Resources | Tutte le funzionalità di Human Resources | Sì       | Nessuno              |

## <a name="development-and-administration-features"></a>Funzionalità di amministrazione e sviluppo

| **Area**                   | **Funzionalità**                               | **Cloud** | **On-premises** |
|----------------------------|-------------------------------------------|-----------|-----------------|
| Compilazione e test             |                                           | Sì       | Sì             |
| Estendibilità              |                                           | Sì       | Sì             |
| Monitoraggio e telemetria   |                                           | Sì       | Sì             |
| Compatibilità della piattaforma     |                                           | Sì       | Sì             |
| Manutenzione                  |                                           | Sì       | Sì             |
|                            | Ambienti di manutenzione                    | Sì       | Nessuno              |
| Parser di traccia               |                                           | Sì       | Sì             |
| PerfTimer                  |                                           | Sì       | Sì\*           |
| Aggiorna                    |                                           | Sì       | Sì             |
|                            | Aggiorna                                   | Sì       | Nessuno              |
|                            | Aggiornamento e supporto per le versioni precedenti | Sì       | Nessuno              |
| Sviluppo di Visual Studio  |                                           | Sì       | Sì             |

\* Negli ambienti locali, PerfTimer mostra solo i risultati per il client.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
