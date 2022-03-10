---
title: Unione del modello di valore cespite e registro beni ammortizzabili
description: 'Nelle versioni precedenti, erano presenti due concetti di valutazione per i cespiti: modelli di valore e registri beni ammortizzabili. In Microsoft Dynamics 365 for Operations (1611), le funzionalità dei modelli di valore e le funzionalità dei registri beni ammortizzabili sono state unite in un unico concetto noto come libro.'
author: moaamer
ms.date: 10/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9b11edcbf03b0917e35d9cef03834629b7b67fad
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2021
ms.locfileid: "7674928"
---
# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Unione del modello di valore cespite e del registro beni ammortizzabili

[!include [banner](../includes/banner.md)]

Questo argomento descrive la funzionalità contabile corrente in Cespiti. Questa funzionalità dei libri si basa sulla funzionalità dei modelli di valore disponibile nelle versioni precedenti, ma include anche tutte le funzionalità prima fornite solo nei registri beni ammortizzabili.

La funzionalità contabile consente di utilizzare un unico set di pagine, richieste e report per tutti i processi relativi ai cespiti dell'organizzazione. Le tabelle in questo argomento descrivono la precedente funzionalità dei modelli di valore e dei registri dei beni ammortizzabili, insieme alle nuove funzionalità contabili correnti.

## <a name="setup"></a>Impostazione
Per impostazione predefinita, i libri registrano sia nella contabilità generale che nel giornale di registrazione cespiti secondario. I libri hanno una nuova opzione **Registra nella contabilità generale** che consente di disabilitare la registrazione nella contabilità generale e registrare solo nel giornale di registrazione cespiti secondario. Questa funzionalità somiglia al precedente comportamento di registrazione per i registri beni ammortizzabili. L'impostazione dei nomi di giornale di registrazione ha un nuovo livello di registrazione denominato Nessuno. Tale livello di registrazione è stato aggiunto specificamente per le transazioni cespiti. Per registrare transazioni per libri che non registrano nella contabilità generale è necessario usare un nome di giornale di registrazione il cui livello di registrazione è impostato su **Nessuno**.


| &nbsp;                                           | Registro beni ammortizzabili               | Modello di valore                     | Libro (Nuovo)                                              |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
| Registrare nella contabilità generale                                   | Mai                           | Sempre                          | Opzione per la registrazione nella contabilità generale                                |
| Livelli di registrazione                                   | Non applicabile                  | 3: Corrente, Operazioni e Imposta | 11: Corrente, Operazioni, Imposta, 7 livelli personalizzati e Nessuno |
| Nomi giornale di registrazione                                    | Nomi giornale di registrazione per registri beni ammortizzabili | Contabilità generale - nomi dei giornali              | Contabilità generale - nomi dei giornali                                      |
| Libri derivati                                    | Non consentito                     | Autorizzata                         | Autorizzata                                                 |
| Sostituzione profilo di ammortamento a livello cespite | Consentito                         | Non consentito                     | Consentito                                                 |

## <a name="processes"></a>Processi
I processi ora utilizzano una pagina comune. Alcuni processi sono consentiti solo se l'opzione **Registra nella contabilità generale** l'è impostata su **No** nell'impostazione del libro.

| &nbsp;                                           | Registro beni ammortizzabili               | Modello di valore                     | Libro (Nuovo)                                              |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
| Immissione transazione              | Giornale di registrazione per registri beni ammortizzabili | Giornale di registrazione cespiti | Giornale di registrazione cespiti                      |
| ammortamento straordinario             | Consentito                   | Non consentito         | Consentito                                  |
| Elimina le transazioni storiche | Consentito                   | Non consentito         | Consentito, a meno che si sta registrando nella contabilità generale |
| Aggiornamento di massa                    | Consentito                   | Non consentito         | Consentito, a meno che si sta registrando nella contabilità generale |

## <a name="inquiries-and-reports"></a>Richieste di informazioni e report
Le richieste di informazioni e i report supportano tutti i libri. I report non inclusi nella seguente tabella prima supportavano sia i registri beni ammortizzabili che i modelli di valore e ora continueranno a supportare tutti i tipi di libri. Il campo **Livello di registrazione** è stato aggiunto anche ai report, in modo da poter identificare più facilmente le registrazioni delle transazioni.

| &nbsp;                                           | Registro beni ammortizzabili               | Modello di valore                     | Libro (Nuovo)                                              |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
| Informazioni                             | Transazioni registro beni ammortizzabili | Transazioni cespiti | Transazioni cespiti |
| Rendiconto cespiti                 | Non consentito                    | Consentito                  | Consentito                  |
| Base ammortamento cespiti                     | Consentito                        | Non consentito              | Consentito                  |
| Applicabilità ammortamento cespiti a metà trimestre | Consentito                        | Non consentito              | Consentito                  |

## <a name="upgrade"></a>Aggiorna
Il processo di aggiornamento sposterà l'impostazione esistente e tutte le transazioni esistenti nella nuova struttura dei libri. I modelli di valore rimarranno come sono attualmente, come libro che registra nella contabilità generale. Tuttavia, i registri beni ammortizzabili vengono spostati in un libro con l'opzione **Registra nella contabilità generale** impostata su **No**. I nomi di giornale di registrazione per registri beni ammortizzabili vengono spostati in un nome di giornale di registrazione di contabilità generale con livello di registrazione impostato su **Nessuno**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
