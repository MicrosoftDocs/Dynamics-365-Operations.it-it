---
title: Creare varianti prodotto predefinite
description: Questa procedura guida nella creazione di varianti prodotto per una rappresentazione generale prodotto mediante le combinazioni di dimensioni prodotto.
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a90e0eb469b823368c1140421fc9c92ccfe69a3b7bac73f762170c0da43e3eee
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747891"
---
# <a name="predefined-product-variants"></a>Varianti prodotto predefinite

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a>Scenario di esempio: Creare varianti prodotto predefinite

Questa scenario di esempio mostra come creare varianti prodotto per una rappresentazione generale prodotto mediante combinazioni di dimensioni prodotto.

### <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Per eseguire questo scenario usando i valori soggeriti qui, i dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica *USMF*.

### <a name="step-1-create-a-product-master"></a>Passaggio 1: Creare una rappresentazione generale prodotto

Per creare una rappresentazione generale prodotto:

1. Andare a **Gestione informazioni sul prodotto > Prodotti > Rappresentazioni generali prodotto**.
1. Selezionare **Nuovo**.
1. Se il campo **Numero prodotto** non mostra già un numero, inserisci un valore. Questo è obbligatorio solo se nessuna sequenza numerica è stata impostata per il campo.
1. Immettere un nome nel campo **Nome prodotto**.
1. Nel campo **Gruppo di dimensioni prodotto** selezionare il gruppo di dimensioni prodotto *SizeCol* (dimensione e colore).
1. Selezionare **OK** per creare e aprire la nuova rappresentazione generale del prodotto.

### <a name="step-2-add-product-dimensions"></a>Passaggio 2: Aggiungere dimensioni prodotto

In questo esempio viene illustrato come immettere manualmente le dimensioni prodotto. È inoltre possibile scegliere di selezionare un gruppo di dimensioni, colore o stile che include i valori della dimensione prodotto si desidera utilizzare.

Per aggiungere dimensioni prodotto:

1. Con la nuova rappresentazione generale prodotto ancora aperta, selezionare **Dimensioni prodotto** nel riquadro azioni.
1. Apri la scheda **Dimensione** e seleziona **Nuovo** sulla barra degli strumenti per aggiungere una riga alla griglia. Per ogni nuova riga, effettua le seguenti impostazioni:
    - **Dimensione:** seleziona un valore di dimensione.
    - **Nome**: immetti un nome per la dimensione.
1. Selezionare **Nuovo** sulla barra degli strumenti e aggiungi una seconda dimensione alla griglia con nuovi **Dimensione** e **Nome**.
1. Apri la scheda **Colori** e seleziona **Nuovo** sulla barra degli strumenti per aggiungere una riga alla griglia. Per ogni nuova riga, effettua le seguenti impostazioni:
    - **Colore:** Seleziona un valore di colore.
    - **Nome**: immetti un nome per il colore.
1. Selezionare **Nuovo** sulla barra degli strumenti e aggiungi un secondo colore alla griglia con nuovi **Colore** e **Nome**.
1. Selezionare **Salva**.
1. Chiudi la pagina per tornare alla tua nuova rappresentazione generale prodotto.

### <a name="step-3-generate-product-variants"></a>Passaggio 3: Generare varianti prodotto

> [!NOTE]
> Questa sezione descrive come generare varianti prodotto quando la funzionalità *Miglioramenti della pagina Suggerimenti variante* non è abilitata. Consulta la sezione successiva per i dettagli su come generare varianti prodotto quando tale funzionalità è disponibile.

Per generare varianti prodotto:

1. Con la nuova rappresentazione generale prodotto ancora aperta, selezionare **Varianti prodotto** nel riquadro azioni.
1. Nel riquadro azioni seleziona **Suggerimenti variante**.
1. Il sistema genera un elenco con tutte le possibili combinazioni delle dimensioni e dei colori definiti per il prodotto. Selezionare **Seleziona tutto** sulla barra degli strumenti.
    - In questo esempio selezionare tutte le possibili varianti. Se si desidera utilizzare solo un sottoinsieme delle possibili combinazioni di dimensioni prodotto, selezionare solo le caselle di controllo richieste in base alle esigenze.  
1. Selezionare **Crea**.
1. Selezionare **Salva**.

## <a name="improved-variant-suggestions"></a>Miglioramenti ai suggerimenti variante

La funzionalità *Miglioramenti della pagina Suggerimenti variante* migliora la pagina **Suggerimenti variante** per affrontare i problemi di prestazioni e usabilità per le aziende che hanno un numero elevato di combinazioni di dimensioni prodotto. Il processo migliorato per la selezione dei valori delle dimensioni prodotto per cui generare suggerimenti di varianti rende più veloce e più facile identificare e rilasciare la serie pertinente di varianti del prodotto.

I seguenti miglioramenti vengono aggiunti da questa funzione:

- **Generazione posticipata di suggerimenti su varianti:** la pagina **Suggerimenti variante** non mostra più i suggerimenti quando viene aperta per la prima volta. Invece, è necessario scegliere esplicitamente i valori necessari e quindi selezionare il pulsante **Suggerisci** per generare le combinazioni. Ciò rende il processo più visibile e interattivo.
- **Selezione di valori di dimensioni:** Quando si dispone di molti valori di dimensione, in genere si è interessati a generare suggerimenti di varianti che ne includano solo alcuni (ad esempio quando si introduce un nuovo set di colori o stili). Con il design migliorato, è possibile selezionare i valori di dimensione per i quali si desidera generare suggerimenti di varianti di prodotto. Ciò aumenta notevolmente la rilevanza delle varianti suggerite e migliora sia le prestazioni del sistema sia la produttività dell'utente.

### <a name="turn-on-the-variant-suggestions-page-improvements-feature"></a>Attivare la funzionalità Miglioramenti della pagina Suggerimenti variante

Prima di poter utilizzare la funzionalità *Miglioramenti della pagina Suggerimenti variante*, tale funzionalità deve essere attivata nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione informazioni sul prodotto*
- **Nome funzionalità:** *Miglioramenti della pagina Suggerimenti variante*

### <a name="work-with-the-improved-variant-suggestions"></a>Lavorare con i suggerimenti di varianti migliorati

Per generare suggerimenti di varianti prodotto quando la funzionalità *Miglioramenti della pagina Suggerimenti variante* è abilitata:

1. Aprire o creare una rappresentazione generale del prodotto e aggiungervi le dimensioni del prodotto richieste, come descritto nella sezione precedente.
1. Con la rappresentazione generale prodotto aperta, selezionare **Varianti prodotto** nel riquadro azioni.
1. Nel riquadro azioni seleziona **Suggerimenti variante**.
1. Selezionare i valori da usare per ognuna delle dimensioni.
1. Nella barra degli strumenti in alto, seleziona **Suggerisci**.
1. Il sistema genera un elenco con tutte le possibili combinazioni delle dimensioni e dei colori selezionati. Nella scheda dettaglio **Varianti suggerite**, selezionare la casella di controllo per ciascuna combinazione di dimensioni prodotto che si desidera utilizzare oppure selezionare **Seleziona tutto** sulla barra degli strumenti per selezionarle tutte.  
1. Selezionare **Crea** per aggiungere le varianti alla rappresentazione generale prodotto corrente.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
