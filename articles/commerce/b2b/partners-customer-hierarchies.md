---
title: Gestire partner commerciali B2B utilizzando gerarchie di clienti
description: Questo argomento descrive come utilizzare le gerarchie di clienti per gestire partner commerciali per i siti Web di e-commerce business-to-business (B2B) di Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d6e594cbb824a8b823912118e99b819585adc45e
ms.sourcegitcommit: 8bcb9c13eccb14e61c39ca6578d135b64090fad2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2022
ms.locfileid: "8313832"
---
# <a name="manage-b2b-business-partners-using-customer-hierarchies"></a>Gestire partner commerciali B2B utilizzando gerarchie di clienti

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come utilizzare le gerarchie di clienti per gestire partner commerciali per i siti Web di e-commerce business-to-business (B2B) di Microsoft Dynamics 365 Commerce.

In Commerce Headquarters, un'entità *gerarchie clienti* è utilizzata per rappresentare le organizzazioni partner commerciali che utilizzeranno il tuo sito di e-commerce B2B. Prima di poter iniziare a utilizzare le gerarchie dei clienti per gestire i partner commerciali, è necessario abilitare le funzionalità di e-commerce B2B in Commerce headquarters e quindi definire una sequenza numerica per la gerarchia clienti.

## <a name="enable-the-b2b-e-commerce-feature-in-commerce-headquarters"></a>Abilitare la funzionalità di e-commerce B2B in Commerce headquarters

Per utilizzare le funzionalità di e-commerce B2B, devi prima abilitare la funzionalità **Abilita l'uso delle funzionalità di eCommerce B2B** in Commerce headquarters.

1. Vai a **Aree di lavoro \> Gestione funzionalità**.
1. Nella scheda **Tutti**, utilizza la casella di filtro per cercare **Modulo: Vendita al dettaglio e commercio**.
1. Trova la funzionalità **Abilita l'uso delle funzionalità di e-commerce B2B**, selezionala e quindi seleziona **Abilita adesso** nell'angolo in basso a destra.

## <a name="define-a-number-sequence-for-the-customer-hierarchy"></a>Definire una sequenza numerica per la gerarchia clienti

Le sequenze numeriche vengono utilizzate per generare identificatori univoci leggibili per record transazioni e dati master che richiedono identificatori. È necessario definire una sequenza numerica che verrà utilizzata per generare l'ID della gerarchia clienti. Per ulteriori informazioni sulle sequenze numeriche, vedere [Panoramica delle sequenze numeriche](/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview).

Per definire una sequenza numerica per la gerarchia clienti in Commerce headquarters, procedi come segue.

1. Vai a **Retail e Commerce \> Impostazione sedi centrali \> Sequenze numeriche \> Sequenze numeriche**.
1. Crea una nuova sequenza numerica o seleziona una sequenza numerica esistente per riutilizzarla.
1. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri condivisi di commercio**.
1. Nella scheda **Sequenze numeriche**, aggiungi la sequenza numerica che hai creato o selezionato in precedenza al riferimento **ID gerarchia clienti**.

![Sequenza numerica aggiunta al riferimento ID gerarchia clienti.](../media/NumberSequenceCustHierarchy.png)

## <a name="how-the-approval-process-works"></a>Processo di approvazione

Quando un business partner richiede l'iscrizione a un sito di e-commerce B2B, il sistema salva la richiesta come *prospect*. Un utente tipo di Commerce headquarters come un responsabile operativo vendita al dettaglio può approvare o rifiutare le richieste dei partner. Per ulteriori informazioni su come gestire le richieste dei partner commerciali e le approvazioni dei prospect, vedi [Gestire utenti partner commerciali nei siti Web di e-commerce B2B](manage-b2b-users.md).

Quando un prospect viene approvato, il sistema crea due nuovi record cliente:

- Un record cliente di tipo **Organizzazione** rappresenta l'organizzazione che richiede di diventare un partner commerciale.
- Un record cliente di tipo **Persona** rappresenta la persona che ha presentato la richiesta.

Inoltre, viene creato un nuovo record gerarchia clienti in **Vendita al dettaglio e commercio \> Clienti \> Gerarchie clienti**. Questo record gerarchia clienti include le seguenti proprietà:

- **ID gerarchia clienti**: un ID univoco per la gerarchia clienti. Questo ID utilizza la sequenza numerica definita nei parametri condivisi di Commerce.
- **Nome**: il nome dell'organizzazione del partner commerciale, come specificato nella richiesta di onboarding. Questo campo è modificabile.
- **Scopo**: questa proprietà è impostata sul valore predefinito **Organizzazione B2B**.
- **Organizzazione**: l'ID cliente dell'organizzazione partner commerciale.

La persona che ha presentato la richiesta di onboarding viene aggiunta alla Scheda dettaglio **Gerarchia** e le viene assegnato il ruolo **Amministratore**. Quando l'amministratore aggiunge più utenti all'organizzazione partner commerciale in un sito B2B, viene creato un nuovo record cliente per ogni utente. Questo record cliente viene inoltre aggiunto anche al record gerarchia clienti pertinente per il partner commerciale e gli viene assegnato il ruolo **Utente**.

### <a name="examples"></a>Esempi

Una persona di nome Sam J. invia una richiesta di onboarding per conto dell'organizzazione Microsoft. Dopo l'approvazione della richiesta, vengono creati due nuovi account cliente: uno di tipo **Persona** per Sam J. e uno di tipo **Organizzazione** per Microsoft.

Come mostra l'esempio nella figura seguente, viene creato anche un nuovo record gerarchia clienti. Questo record ha lo stesso nome dell'organizzazione (**Microsoft**) e il ruolo **Amministratore** è assegnato a Sam J. In qualità di amministratore, Sam J. aggiunge tutti gli altri utenti Microsoft del sito B2B a tale gerarchia e gli assegna il ruolo **Utente**. In questo esempio, Sush R. è stato aggiunto come utente.

![Esempio di un record gerarchia clienti.](../media/CustomerHierarchy2.png)

Per determinare se un cliente è associato a una gerarchia clienti, aprire il record cliente. Come mostra l'esempio nella figura seguente, il campo **ID gerarchia clienti** nella sezione **B2B** della Scheda dettaglio **Vendita al dettaglio** mostra se il cliente fa parte di una gerarchia clienti e l'opzione **Amministratore B2B** indica se il cliente è un amministratore di tale gerarchia.

![Esempio della sezione B2B nella Scheda dettaglio Vendita al dettaglio di un record cliente, in cui il cliente è associato a una gerarchia e specificato come amministratore.](../media/CustomerHierarchyMapping2.png)

Nella maggior parte dei casi, i valori delle proprietà corrispondenti di tutti i record cliente in una gerarchia devono corrispondere. Ad esempio, poiché tutti gli utenti partner commerciali dovrebbero ottenere prezzi simili per i prodotti, il loro gruppo di prezzi e le configurazioni associate dovrebbero corrispondere. Tuttavia, il sistema non applica questa coerenza. Pertanto, gli utenti di Commerce Headquarters pertinenti sono responsabili di garantire che i valori e le configurazioni delle proprietà corrispondano per tutti i clienti in una data gerarchia.

Gli utenti di Commerce Headquarters possono esaminare i valori delle proprietà per tutti i record di una gerarchia in una vista affiancata. Come mostra l'esempio nell'illustrazione seguente, è possibile utilizzare l'opzione **Generale** nell'elenco a discesa della Scheda dettaglio **Gerarchia** e quindi selezionare una qualsiasi sezione del record cliente per visualizzare le relative proprietà. Gli utenti possono modificare direttamente i valori delle proprietà in questa vista. Per copiare tutti i valori da un record cliente amministratore in tutti gli utenti, seleziona **Sostituisci** nella Scheda dettaglio **Gerarchia**.

![Esempio di record gerarchia clienti, che mostra il pulsante Sostituisci e l'opzione nell'elenco a discesa.](../media/HierarchyDetails2.png)

[!include [footer-include](../../includes/footer-banner.md)]
