---
title: Impostare i parametri per la gestione
description: "Utilizzare questa procedura per attivare i processi di gestione delle non conformità."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 4bb4af7cb7aff101a8b9e6162823515f63b12886
ms.openlocfilehash: 9b5b05a3c00f093066a2714964bb99146427c3bc
ms.contentlocale: it-it
ms.lasthandoff: 11/02/2017

---
# <a name="set-up-prerequisites-for-management"></a>Impostare i parametri per la gestione

[!include [task guide banner](../../includes/task-guide-banner.md)]

Utilizzare questa procedura per attivare i processi di gestione delle non conformità. Con non conformità si intende una procedura o un elemento con un problema di qualità, il cui tipo e la cui origine vengono specificati nelle informazioni descrittive. Questa procedura utilizza la società di dati dimostrativi USMF. In genere, questa procedura viene eseguita da un responsabile della qualità.


## <a name="enable-quality-management-processes-within-the-company"></a>Abilitare i processi di gestione della qualità all'interno della società
1. Fare clic su Gestione magazzino > Impostazioni > Parametri di gestione articoli e magazzino.
2. Fare clic sulla scheda Gestione qualità.
3. Selezionare Sì nel campo Usa Gestione qualità.
    * Selezionare questo parametro per attivare i processi di gestione della qualità per la società.  
4. Immettere un numero nel campo Tariffa oraria.
    * Utilizzare il campo Tariffa oraria per immettere una tariffa oraria per la manodopera nella valuta locale. La tariffa oraria viene utilizzata per calcolare i costi delle operazioni correlate a una non conformità. La tariffa oraria e i costi calcolati forniscono informazioni di riferimento per una non conformità e non interagiscono con altre funzionalità.  
5. Fare clic su Impostazione report.
    * Questa pagina consente di definire i tipi di note del report della qualità che verranno utilizzati in diversi tipi di report per la gestione della qualità.  
6. Chiudere la pagina.
7. Chiudere la pagina.

## <a name="enable-user-for-nonconformance-processing"></a>Abilitare l'utente per l'elaborazione di non conformità
1. Andare a Amministrazione sistema > Utenti > Utenti.
    * Per elaborare l'approvazione di una non conformità, l'utente che approva o rifiuta le non conformità deve avere un valore "Nome" assegnato alla pagina Utenti. Per utilizzare le note del documento, l'utente deve inoltre avere Gestione documenti attivata nelle opzioni utente.  
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare il campo Nome con il valore "Ricardo".
    * Utilizzare il filtro per trovare l'utente che approverà o rifiuterà i record di non conformità.  
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Per elaborare l'approvazione di una non conformità, verificare che l'utente che approva o rifiuta le non conformità abbia un valore "Nome" assegnato alla pagina Utenti.  
4. Fare clic su Opzioni utente.
5. Fare clic sulla scheda Preferenze.
6. Selezionare Sì nel campo Attiva gestione documenti.
    * Per utilizzare le note del documento, l'utente deve inoltre avere Gestione documenti attivata nelle opzioni utente.  
7. Chiudere la pagina.
8. Chiudere la pagina.
9. Chiudere la pagina.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Definire i tipi di diagnostica per l'elaborazione di non conformità
1. Andare a Gestione articoli > Impostazioni > Gestione qualità > Tipi di diagnostica.
    * Utilizzare la pagina Tipi di diagnostica per definire una classificazione delle azioni di diagnostica. Una correzione identifica il tipo di azione di diagnostica che è consigliabile eseguire per una non conformità approvata, l'autore e la data di completamento richiesta e pianificata.  
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Diagnostica.
4. Nel campo Descrizione digitare un valore.
5. Chiudere la pagina.

## <a name="define-quality-charges-for-nonconformance-processing"></a>Definire le spese di gestione qualità per l'elaborazione di non conformità
1. Andare a Gestione articoli > Impostazioni > Gestione qualità > Spese gestione qualità.
    * Utilizzare la pagina Spese gestione qualità per definire una classificazione delle spese che verranno utilizzate nelle operazioni correlate alle non conformità.  
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Codice spese.
4. Nel campo Descrizione digitare un valore.
5. Chiudere la pagina.

## <a name="define-the-operations-for-nonconformance-processing"></a>Definire le operazioni per l'elaborazione di non conformità
1. Andare a Gestione articoli > Impostazioni > Gestione qualità > Operazioni.
    * Utilizzare la pagina Operazioni per definire una classificazione delle operazioni che è possibile eseguire per una non conformità approvata. Quando si correla un'operazione a una non conformità, è possibile definire anche informazioni dettagliate sul materiale, le ore di manodopera e le spese varie che sono necessari per l'esecuzione dell'operazione. Tali informazioni costituiscono la base per il calcolo di un costo stimato per l'esecuzione dell'operazione.  
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Operazione.
4. Nel campo Descrizione digitare un valore.
5. Chiudere la pagina.

## <a name="define-problem-types-for-nonconformance-processing"></a>Definire i tipi di problema per l'elaborazione di non conformità
1. Andare a Gestione articoli > Impostazioni > Gestione qualità > Tipi di problema.
    * Utilizzare la pagina Tipi di problemi per definire una classificazione dei problemi relativi alla qualità riscontarti nei vari tipi di non conformità. I tipi di non conformità includono Interno, Cliente, Fornitore, Richiesta di assistenza, Produzione e Produzione co-prodotti. Un tipo di problema singolo può essere associato a più tipi di non conformità.  
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Tipo di problema.
4. Nel campo Descrizione digitare un valore.
5. Fare clic su Tipi di non conformità.
    * Utilizzare la pagina Tipi di non conformità per autorizzare l'utilizzo di un tipo di problema per uno o più tipi di non conformità. Un tipo di problema relativo a un codice errato, ad esempio, può essere applicato a tutti i tipi di non conformità, mentre un tipo di problema relativo a reclami dei clienti può essere utilizzato solo per i tipi di non conformità cliente e richiesta di assistenza.  
6. Fare clic su Nuovo.
7. Nell'elenco contrassegnare la riga selezionata.
8. Selezionare un'opzione nel campo Tipo di non conformità.
9. Chiudere la pagina.
10. Chiudere la pagina.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Definire le aree quarantena per l'elaborazione di non conformità
1. Andare a Gestione articoli > Impostazioni > Gestione qualità > Aree quarantena.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Aree quarantena.
4. Nel campo Descrizione digitare un valore.
5. Chiudere la pagina.

