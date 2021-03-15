---
title: Unione del modello di valore cespite e registro beni ammortizzabili
description: 'Nelle versioni precedenti, erano presenti due concetti di valutazione per i cespiti: modelli di valore e registri beni ammortizzabili. In Microsoft Dynamics 365 for Operations (1611), le funzionalità dei modelli di valore e le funzionalità dei registri beni ammortizzabili sono state unite in un unico concetto noto come libro.'
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0528c378ffbb24ac8cb19af25290a1002ece2327
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969057"
---
# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Unione del modello di valore cespite e registro beni ammortizzabili

[!include [banner](../includes/banner.md)]

Nelle versioni precedenti, erano presenti due concetti di valutazione per i cespiti: modelli di valore e registri beni ammortizzabili. In Microsoft Dynamics 365 for Operations (1611), le funzionalità dei modelli di valore e le funzionalità dei registri beni ammortizzabili sono state unite in un unico concetto noto come libro.

La nuova funzionalità dei libri si basa sulla precedente funzionalità dei modelli di valore ma include anche tutte le funzionalità prima fornite solo nei registri beni ammortizzabili. [![Libro come unione di funzionalità dei modelli di valore e dei registri beni ammortizzabili](./media/fixed-assets.png)](./media/fixed-assets.png) A causa di questa unione, è ora possibile usare un singolo insieme di pagine, richieste di informazioni e report per tutti i processi cespiti. Le tabelle in questo argomento descrivono la precedente funzionalità dei modelli di valore e dei registri dei beni ammortizzabili, insieme alle nuove funzionalità per i libri.

## <a name="setup"></a>Imposta
Per impostazione predefinita, i libri registrano sia nella contabilità generale che nel giornale di registrazione cespiti secondario. I libri hanno una nuova opzione **Registra nella contabilità generale** che consente di disabilitare la registrazione nella contabilità generale e registrare solo nel giornale di registrazione cespiti secondario. Questa funzionalità somiglia al precedente comportamento di registrazione per i registri beni ammortizzabili. L'impostazione dei nomi di giornale di registrazione ha un nuovo livello di registrazione denominato Nessuno. Tale livello di registrazione è stato aggiunto specificamente per le transazioni cespiti. Per registrare transazioni per libri che non registrano nella contabilità generale è necessario usare un nome di giornale di registrazione il cui livello di registrazione è impostato su **Nessuno**.

|                                                  |                                 |                                 |                                                         |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
|                                                  | Registro beni ammortizzabili               | Modello di valore                     | Libro (Nuovo)                                              |
| Registra nella contabilità generale                                   | Mai                           | Sempre                          | Opzione per effettuare registrazioni nella contabilità generale                                |
| Livelli di registrazione                                   | Non applicabile                  | 3: Corrente, Operazioni e Imposta | 11: Corrente, Operazioni, Imposta, 7 livelli personalizzati e Nessuno |
| Nomi giornale di registrazione                                    | Nomi giornale di registrazione per registri beni ammortizzabili | Contabilità generale - Nomi giornale di registrazione              | Contabilità generale - Nomi giornale di registrazione                                      |
| Libri derivati                                    | Non consentito                     | Consentito                         | Consentito                                                 |
| Sostituzione profilo di ammortamento a livello cespite | Consentito                         | Non consentito                     | Consentito                                                 |

## <a name="processes"></a>Processi
I processi ora utilizzano una pagina comune. Alcuni processi sono consentiti solo se l'opzione **Registra nella contabilità generale** l'è impostata su **No** nell'impostazione del libro.

|                                |                           |                     |                                          |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
|                                | Registro beni ammortizzabili         | Modello di valore         | Libro (Nuovo)                               |
| Immissione transazione              | Giornale di registrazione per registri beni ammortizzabili | Giornale di registrazione cespiti | Giornale di registrazione cespiti                      |
| ammortamento straordinario             | Consentito                   | Non consentito         | Consentito                                  |
| Elimina le transazioni storiche | Consentito                   | Non consentito         | Consentito, a meno che si sta registrando nella contabilità generale |
| Aggiornamento di massa                    | Consentito                   | Non consentito         | Consentito, a meno che si sta registrando nella contabilità generale |

## <a name="inquiries-and-reports"></a>Richieste di informazioni e report
Le richieste di informazioni e i report supportano tutti i libri. I report non inclusi nella seguente tabella prima supportavano sia i registri beni ammortizzabili che i modelli di valore e ora continueranno a supportare tutti i tipi di libri. Il campo **Livello di registrazione** è stato aggiunto anche ai report, in modo da poter identificare più facilmente le registrazioni delle transazioni.

|                                       |                                |                          |                          |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
|                                       | Registro beni ammortizzabili              | Modello di valore              | Libro (Nuovo)               |
| Informazioni                             | Transazioni registro beni ammortizzabili | Transazioni cespiti | Transazioni cespiti |
| Rendiconto cespiti                 | Non consentito                    | Consentito                  | Consentito                  |
| Base ammortamento cespiti                     | Consentito                        | Non consentito              | Consentito                  |
| Applicabilità ammortamento cespiti a metà trimestre | Consentito                        | Non consentito              | Consentito                  |

## <a name="upgrade"></a>Aggiorna
Il processo di aggiornamento sposterà l'impostazione esistente e tutte le transazioni esistenti nella nuova struttura dei libri. I modelli di valore rimarranno come sono attualmente, come libro che registra nella contabilità generale. Tuttavia, i registri beni ammortizzabili vengono spostati in un libro con l'opzione **Registra nella contabilità generale** impostata su **No**. I nomi di giornale di registrazione per registri beni ammortizzabili vengono spostati in un nome di giornale di registrazione di contabilità generale con livello di registrazione impostato su **Nessuno**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]