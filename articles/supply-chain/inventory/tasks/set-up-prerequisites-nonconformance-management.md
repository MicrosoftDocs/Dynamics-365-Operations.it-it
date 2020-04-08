---
title: Impostare prerequisiti per la gestione di non conformità
description: Utilizzare questo argomento per attivare i processi di gestione delle non conformità.
author: perlynne
manager: AnnBe
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, SysUserManagement, SysUserSetup, InventTestDiagnosticType, InventTestMiscCharges, InventTestOperation, InventProblemType, InventProblemTypeSetup, InventQuarantineZone
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dfd0bc7edb3236d016e64bd08b1858fd7b12417f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145734"
---
# <a name="set-up-prerequisites-for-nonconformance-management"></a>Impostare prerequisiti per la gestione di non conformità

[!include [banner](../../includes/banner.md)]

Utilizzare questo argomento per attivare i processi di gestione delle non conformità. Con non conformità si intende una procedura o un elemento con un problema di qualità, il cui tipo e la cui origine vengono specificati nelle informazioni descrittive. Questa procedura utilizza la società di dati dimostrativi USMF. In genere, questa procedura viene eseguita da un responsabile della qualità.


## <a name="enable-quality-management-processes-within-the-company"></a>Abilitare i processi di gestione della qualità all'interno della società
1. Nel pannello di navigazione, andare a **Moduli > Gestione magazzino > Impostazione > Parametri di gestione articoli e magazzino**.
2. Selezionare la scheda **Gestione qualità**.
3. Selezionare **Sì** nel campo **Usa Gestione qualità** per abilitare i processi di gestione della qualità per la società.
4. Nel campo **Tariffa oraria**, immettere un numero nella valuta locale. La tariffa oraria viene utilizzata per calcolare i costi delle operazioni correlate a una non conformità. La tariffa oraria e i costi calcolati forniscono informazioni di riferimento per una non conformità e non interagiscono con altre funzionalità.  
5. Selezionare **Impostazione report** per definire i tipi di note del report della qualità che verranno utilizzati in diversi tipi di report per la gestione della qualità.

## <a name="enable-user-for-nonconformance-processing"></a>Abilitare l'utente per l'elaborazione di non conformità
1. Nel pannello di navigazione, andare a **Moduli > Amministrazione sistema > Utenti > Utenti**. 
2. Utilizzare il filtro rapido per trovare l'utente che approverà o rifiuterà i record di non conformità. Ad esempio, applicare un filtro nel campo **Nome** con un valore `Ricardo`. Per elaborare l'approvazione di una non conformità, l'utente che approva o rifiuta le non conformità deve avere un valore "Nome" assegnato alla pagina **Utenti**. Per utilizzare le note del documento, l'utente deve inoltre avere Gestione documenti attivata nelle opzioni utente.  
3. Contrassegnare la riga del record desiderato.
4. Selezionare **Opzioni utente**.
5. Selezionare la scheda **Preferenze**.
6. Selezionare **Sì** nel campo **Attiva gestione documenti**.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Definire i tipi di diagnostica per l'elaborazione di non conformità
1. Nel pannello di navigazione andare a **Moduli > Gestione articoli > Impostazioni > Gestione qualità > Tipi di diagnostica**. Utilizzare la pagina **Tipi di diagnostica** per definire una classificazione delle azioni di diagnostica. Una correzione identifica il tipo di azione di diagnostica che è consigliabile eseguire per una non conformità approvata, l'autore e la data di completamento richiesta e pianificata.  
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Diagnostica**.
4. Digitare un valore nel campo **Descrizione**

## <a name="define-quality-charges-for-nonconformance-processing"></a>Definire le spese di gestione qualità per l'elaborazione di non conformità
1. Nel pannello di navigazione andare a **Moduli > Gestione articoli > Impostazioni > Gestione qualità > Spese gestione qualità**. Utilizzare la pagina **Spese gestione qualità** per definire una classificazione delle spese che verranno utilizzate nelle operazioni correlate alle non conformità.  
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Codice spese**.
4. Digitare un valore nel campo **Descrizione**

## <a name="define-the-operations-for-nonconformance-processing"></a>Definire le operazioni per l'elaborazione di non conformità
1. Nel pannello di navigazione andare a **Moduli > Gestione articoli > Impostazioni > Gestione qualità > Operazioni**. Utilizzare la pagina **Operazioni** per definire una classificazione delle operazioni che è possibile eseguire per una non conformità approvata. Quando si correla un'operazione a una non conformità, è possibile definire anche informazioni dettagliate sul materiale, le ore di manodopera e le spese varie che sono necessari per l'esecuzione dell'operazione. Tali informazioni costituiscono la base per il calcolo di un costo stimato per l'esecuzione dell'operazione.  
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Operazione**.
4. Digitare un valore nel campo **Descrizione**

## <a name="define-problem-types-for-nonconformance-processing"></a>Definire i tipi di problema per l'elaborazione di non conformità
1. Nel pannello di navigazione andare a **Moduli > Gestione articoli > Impostazioni > Gestione qualità > Tipi di problema**. Utilizzare la pagina **Tipi di problemi** per definire una classificazione dei problemi relativi alla qualità riscontarti nei vari tipi di non conformità. I tipi di non conformità includono **Interno**, **Cliente**, **Fornitore**, **Richiesta di assistenza**, **Produzione** e **Produzione co-prodotti**. Un tipo di problema singolo può essere associato a più tipi di non conformità.  
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Tipo di problema**.
4. Digitare un valore nel campo **Descrizione**
5. Selezionare **Tipi di non conformità**. Utilizzare la pagina **Tipi di non conformità** per autorizzare l'utilizzo di un tipo di problema per uno o più tipi di non conformità. Un tipo di problema relativo a un codice errato, ad esempio, può essere applicato a tutti i tipi di non conformità, mentre un tipo di problema relativo a reclami dei clienti può essere utilizzato solo per i tipi di non conformità cliente e richiesta di assistenza.  
6. Selezionare **Nuovo**.
7. Selezionare un'opzione nel campo **Tipo di non conformità** della nuova riga.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Definire le aree quarantena per l'elaborazione di non conformità
1. Nel pannello di navigazione andare a **Moduli > Gestione articoli > Impostazioni > Gestione qualità > Aree quarantena**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Aree quarantena**.
4. Digitare un valore nel campo **Descrizione**
5. Chiudere la pagina.

