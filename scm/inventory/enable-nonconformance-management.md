---
title: "Gestione di non conformità"
description: "Questo articolo descrive l&quot;impostazione di base necessaria per l&quot;utilizzo della non conformità. Un&quot;impostazione aggiuntiva è richiesta se si desidera utilizzare la non conformità negli ordini di controllo qualità."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 28951
ms.assetid: a62d4ba8-eebc-4b14-b587-630be7298522
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 6f25e2930ff265df1f938cdf56e8a0f4993617af
ms.lasthandoff: 03/31/2017


---

# <a name="nonconformance-management"></a>Gestione di non conformità

Questo articolo descrive l'impostazione di base necessaria per l'utilizzo della non conformità. Un'impostazione aggiuntiva è richiesta se si desidera utilizzare la non conformità negli ordini di controllo qualità. 

Per attivare la gestione di non conformità, effettuare le operazioni seguenti:

1.  Definire i parametri di Gestione articoli e magazzino correlati alle non conformità:
    -   Impostare l'opzione **Usa Gestione qualità** su **Sì**.
    -   Nel campo **Tariffa oraria**, immettere una tariffa oraria per la manodopera nella valuta locale. La tariffa oraria viene utilizzata per calcolare i costi delle operazioni correlate a una non conformità. La tariffa oraria e i costi calcolati forniscono informazioni di riferimento per una non conformità. Non interagiscono con altre funzionalità.
    -   ** La gestione della qualità ** la scheda ** impostazione report ** nella pagina per definire il tipo di documento da stampare. È possibile stampare un report di non conformità, un tag di non conformità, un report di correzione. È possibile definire più di un record per la stampa di tipi di documento diversi in un report o per la stampa di note interne ed esterne. Può essere utile utilizzare la pagina **Tipo di documento** per definire un tipo di documento univoco per non conformità e un tipo di documento univoco per le correzioni. Ad esempio, si desidera immettere note su una non conformità utilizzando il tipo di documento univoco per non conformità. In questo caso, identificare il tipo di documento univoco nelle opzioni di report.
    -   Attivare le sequenze numeriche per non conformità e i riferimenti di correzione.

2.  Attivare l'approvazione dell'utente di non conformità. Utilizzare il campo **Nome** nella pagina **Utenti** per assegnare un dipendente a ciascun utente che deve approvare una non conformità. Il sistema utilizza i dipendenti che modificano lo stato di una non conformità per tenere traccia dello storico non conformità. Gli utenti possono approvare una non conformità solo se è stato loro assegnato un ID dipendente.
3.  Definire i tipi di problemi che verranno assegnati a non conformità. Utilizzare la pagina **Tipi di problemi** per definire una classificazione dei problemi relativi alla qualità riscontarti per i vari tipi di non conformità. È possibile impostare i seguenti tipi di non conformità: **Interno**, **Cliente**, **Fornitore**, **Richiesta di assistenza**, **Produzione** e **Produzione co-prodotti**. Utilizzare la pagina **Tipi di non conformità** per autorizzare l'utilizzo di un tipo di problema in uno o più tipi di non conformità. Ad esempio, un tipo di problema relativo a un codice errato può essere applicato a tutti i tipi di non conformità, mentre un tipo di problema relativo a reclami dei clienti può essere utilizzato solo per i tipi di non conformità **Cliente** e **Richiesta di assistenza**.
4.  Definire le aree di quarantena per fornire istruzioni sulla modalità di gestione di materiale difettoso. Utilizzare la pagina **Aree quarantena** per definire le aree che possono essere assegnate a una non conformità. Il tag di non conformità stampato indicherà l'area di quarantena assegnata e le informazioni sull'utilizzo per fornire istruzioni sulla modalità di gestione del materiale difettoso. Le aree possono corrispondere alle ubicazioni di magazzino o alle risorse operative.
5.  Definire i tipi di diagnostica che verranno assegnati alle correzioni. Utilizzare la pagina **Tipi di diagnostica** per definire una classificazione delle azioni di diagnostica. Una correzione specifica il tipo di azione di diagnostica da eseguire per una non conformità approvata e l'utente che deve eseguire l'azione. Specifica inoltre la data di completamento richiesta e la data di completamento pianificata.
6.  Definire le operazioni correlate che verranno assegnate a non conformità. Utilizzare la pagina **Operazioni** per definire una classificazione delle operazioni che è possibile eseguire per una non conformità approvata. Quando si assegna un'operazione correlata a una non conformità, è possibile fornire informazioni dettagliate, ad esempio sul materiale associato, sulle ore di manodopera e sulle spese varie, necessarie per l'esecuzione dell'operazione. Queste informazioni vengono utilizzate per calcolare un costo stimato per l'operazione. Le informazioni dettagliate e i costi stimati vengono forniti a scopo di riferimento. Le operazioni correlate del controllo qualità sono diverse da quelle che è possibile definire per un ciclo di lavorazione produzione.


<a name="see-also"></a>Vedere anche
--------

[Creare ed elaborare una non conformità (Guida di attività)](https://ax.help.dynamics.com/en/wiki/create-and-process-a-nonconformance/)

[Quality management processes](quality-management-processes.md)

[Prerequisiti per l'impostazione della gestione di non conformità (Guida di attività)](https://ax.help.dynamics.com/en/wiki/set-up-prequisites-for-nonconformance-management/)


