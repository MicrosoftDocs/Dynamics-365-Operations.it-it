---
title: Registrazione per Esecuzione produzione
description: "In questo argomento vengono descritti i concetti e termini importanti con cui sarà necessario acquisire familiarità per configurare e utilizzare la funzionalità di esecuzione produzione."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgRegistration
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 70103
ms.assetid: 52ba1cdd-767f-4edd-896f-61adce8479d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 939cb219a63a27ee9cb05036041d2722df3b0abc
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="registration-for-manufacturing-execution"></a>Registrazione per Esecuzione produzione

[!include[banner](../includes/banner.md)]


In questo argomento vengono descritti i concetti e termini importanti con cui sarà necessario acquisire familiarità per configurare e utilizzare la funzionalità di esecuzione produzione. 

Esecuzione produzione è destinato principalmente all'utilizzo da parte di società di produzione. I lavoratori possono registrare il consumo per ore e per articoli nei processi di produzione per cui viene utilizzando il modulo **Registrazione processi**. Tutte le registrazioni vengono approvate e successivamente trasferite ai moduli appropriati. L'approvazione e il trasferimento continuativi delle registrazioni consentono ai responsabili di tenere facilmente traccia dei costi effettivi degli ordini di produzione.

## <a name="manufacturing-execution-and-registration-terminology"></a>Terminologia di esecuzione e registrazione produzione
Nella tabella riportata di seguito sono illustrati i termini relativi all'esecuzione produzione e alle attività di registrazione correlate.

| Termine                          | descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Esecuzione produzione       | Funzione usata per la registrazione di tempo, consumo di materiali, costi relativi ai processi di produzione, progetti e attività indirette. La registrazione viene effettuata tramite un client di registrazione di esecuzione produzione.                                                                                                                                                                                                                                                                                                                                                                                                   |
| Elenco processi                      | Nella pagina **Registrazione processi** viene visualizzato l'elenco di processi che i lavoratori devono eseguire su una specifica risorsa, ad esempio una macchina. I lavoratori possono registrare il consumo per ore e per articoli per ciascun processo o attività presente nell'elenco processi.                                                                                                                                                                                                                                                                                                                                                                           |
| Aggregazione processi                  | Se un lavoratore avvia simultaneamente più di un processo nella pagina **Registrazione processi** l'attività viene definita aggregazione processi. Il tempo impiegato nei processi aggregati può essere allocato ai singoli processi in diversi modi utilizzando delle chiavi di allocazione.                                                                                                                                                                                                                                                                                                                                                         |
| Registrazioni pilota/assistente | Un lavoratore può registrarsi come assistente per una risorsa e creare un piccolo team nel quale vari lavoratori operano sugli stessi processi di produzione. Le risorse a cui sono collegati i lavoratori come assistenti sono dette piloti. Solo la risorsa pilota deve effettuare le registrazioni. Tutti gli assistenti ottengono automaticamente le stesse registrazioni. Se, ad esempio, una macchina funge da pilota, i lavoratori registrati come assistenti per quella macchina possono effettuare registrazioni nella pagina **Registrazione processi** e sia la macchina che i lavoratori connessi come assistenti riceveranno le stesse registrazioni. |
| Attività indiretta             | Attività non direttamente correlata a un processo di produzione o a un progetto, ad esempio riunioni di reparto, attività di manutenzione o di pulizia nello shop floor. I lavoratori possono effettuare registrazioni per attività indirette nel modo in cui le effettuano per processi e progetti di produzione.                                                                                                                                                                                                                                                                                                |

## <a name="registrations-in-manufacturing-execution"></a>Registrazioni in esecuzione produzione
I lavoratori possono effettuare diversi tipi di registrazioni in esecuzione produzione per il lavoro completato nei processi di produzione. A seconda dell'impostazione del sistema, i lavoratori possono anche effettuare registrazioni per attività di progetto e non produttive, quali pause, assenze e altre attività indirette. Sono disponibili i tipi di registrazione seguenti:

-   **Entrata/uscita** (disponibile nel modulo Orario e presenze) - I lavoratori registrano l'ora di entrata quando arrivano al lavoro e l'ora di uscita quando lasciano il luogo di lavoro.
-   **Registrazioni nei processi di produzione** - I lavoratori possono effettuare registrazioni, ad esempio l'avvio di un processo e la dichiarazione di un riscontro su un processo nei processi di produzione visualizzati nel proprio elenco processi. È possibile avviare più processi contemporaneamente. Questo tipo di attività viene definita aggregazione processi.
-   **Registrazioni di magazzino** - I lavoratori possono effettuare registrazioni relative ai materiali utilizzati nello shop floor e non direttamente correlati ai processi di produzione. Esempi di questi materiali sono grasso, lubrificanti o altri materiali utilizzati per mantenere i macchinari in funzione. Le registrazioni vengono effettuate in un giornale di registrazione magazzino.
-   **Registrazioni nei progetti** (disponibile nel modulo Orario e presenze) - I lavoratori possono effettuare registrazioni, ad esempio avviare e completare il lavoro nei progetti o nelle attività di progetto visualizzate nel proprio elenco processi.
-   **Registrazione di commissioni e articoli per i progetti** (disponibile nel modulo Orario e presenze) - I lavoratori possono registrare le commissioni (spese) associate a un progetto in un giornale di registrazione commissioni progetto, ad esempio carburante e pedaggi autostradali. I lavoratori possono inoltre registrare il consumo per articolo nei progetti. In tal caso viene utilizzato un giornale di registrazione articoli progetto.
-   **Registrazione di un assistente di un altro lavoratore** - Se due o più lavoratori lavoreranno insieme su un processo o progetto di produzione, uno dei lavoratori può essere registrato come assistente a una macchina oppure a un altro lavoratore, che in questo caso rappresenterà il pilota. Il pilota può selezionare un altro lavoratore come pilota, in base alle esigenze.
-   **Registrazione delle assenze** (disponibile nel modulo Orario e presenze) - Un lavoratore può registrare le ore in base a diversi codici assenza impostati. È possibile indicare l'assenza se un lavoratore arriva tardi al lavoro, se chiede di allontanarsi durante la giornata lavorativa o se lascia il luogo di lavoro in anticipo rispetto all'ora prevista dal profilo standard dell'orario di lavoro.
-   **Registrazione delle pause** (disponibile nel modulo Orario e presenze) - Nel corso della giornata lavorativa, un lavoratore può registrare eventuali allontanamenti dalla propria postazione di lavoro per prendere delle pause. È possibile impostare diversi tipi di pausa. Quando il lavoratore torna ed esegue di nuovo l'accesso, nel sistema viene registrato il ritorno del lavoratore e viene interrotta la registrazione della pausa.
-   **Registrazione di attività indirette** (disponibile nel modulo Orario e presenze) - Con il termine attività indirette si fa riferimento alle attività non produttive in cui potrebbe essere impegnato un lavoratore durante la giornata lavorativa, ad esempio riunioni di reparto o del team oppure attività di manutenzione svolte nello shop floor. I lavoratori possono effettuare registrazioni per le attività indirette preimpostate.
-   **Registrazione degli straordinari** (disponibile nel modulo Orario e presenze) - Se a un lavoratore è stato chiesto di continuare il lavoro oltre l'orario standard, sarà possibile registrare le ore aggiuntive come orario flessibile o straordinario.





