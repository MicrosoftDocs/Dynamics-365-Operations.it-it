---
title: Unione del modello di valore cespite e registro beni ammortizzabili
description: "Nelle versioni precedenti, presenza di due concetti dei prezzi per i cespiti ridotto - modelli di valore e registri beni ammortizzabili. In Microsoft Dynamics 365 per le operazioni di 1611, la funzionalità modello di valore e funzionalità del registro beni ammortizzabili è stata fusa in un unico concetto noti come registro beni ammortizzabili."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 6c8c005c7f5ede54ce0b6c8114cac69e2551d467
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Unione del modello di valore cespite e registro beni ammortizzabili

Nelle versioni precedenti, presenza di due concetti dei prezzi per i cespiti ridotto - modelli di valore e registri beni ammortizzabili. In Microsoft Dynamics 365 per le operazioni di 1611, la funzionalità modello di valore e funzionalità del registro beni ammortizzabili è stata fusa in un unico concetto noti come registro beni ammortizzabili.

La nuova funzionalità dei libri si basa sulla precedente funzionalità dei modelli di valore ma include anche tutte le funzionalità prima fornite solo nei registri beni ammortizzabili. [libro![come una fusione la funzionalità del registro beni ammortizzabili e modello di valore di ammortamento (]. /media/fixed-assets.png)](. /media/fixed-assets.png) A causa della stampa unione, sarà possibile utilizzare un singolo insieme di pagine, delle richieste di informazioni e nei report per tutti i processi del cespite. Le tabelle in questo argomento descrivono la precedente funzionalità dei modelli di valore e dei registri dei beni ammortizzabili, insieme alle nuove funzionalità per i libri.

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

