---
title: Gruppi di test per la gestione della qualità
description: Questo articolo descrive come creare gruppi di test, in modo che più test possano essere utilizzati con gli ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7722bc92d8c2bf52d6a798a93f07af44037d4e0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857708"
---
# <a name="quality-management-test-groups"></a>Gruppi di test per la gestione della qualità

[!include [banner](../includes/banner.md)]

Questo articolo descrive come creare gruppi di test, in modo che più test possano essere utilizzati con gli ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.

Utilizzare la pagina **Gruppi di test** per impostare, modificare e visualizzare gruppi di test e i singoli test assegnati ai gruppi. Nella parte superiore della pagina sono visualizzati i gruppi di test, mentre nella parte inferiore sono visualizzati i test assegnati a un gruppo di test selezionato.

A un gruppo di test è possibile assegnare più criteri, tra cui un piano di campionamento, un livello di qualità accettabile e la richiesta di test distruttivo. Quindi, auando si assegna un singolo test a un gruppo di test, è necessario definire informazioni aggiuntive, come sequenza, documenti e date di validità. In un test quantitativo, le informazioni definite dall'utente includono anche i valori di misura accettabili e in un test qualitativo includono la variabile di test e il risultato predefinito.

Il gruppo di test assegnato a un ordine di controllo qualità definisce il set predefinito di test che devono essere eseguiti sull'articolo specificato. Tuttavia, è possibile aggiungere, eliminare o modificare i test per un ordine di controllo qualità. I risultati di ciascun test vengono riportati in un ordine di controllo qualità.

Quando si definisce un gruppo di test, è possibile facoltativamente specificare un campionamento articoli. I campionamenti degli articoli vengono utilizzati per definire la quantità di prodotto che deve essere testata. Per ulteriori informazioni, vedere [Campionamento degli articoli per la gestione della qualità](quality-item-sampling.md). È inoltre possibile indicare se i test in un gruppo di test sono distruttivi. In un test distruttivo, il campionamento degli articoli viene distrutto e la quantità viene rimossa dalle scorte disponibili.

## <a name="example-of-a-test-group"></a>Esempio di un gruppo di test

In una società di produzione è definito un gruppo di test per ogni variazione apportata alle linee guida per il controllo qualità. I vari gruppi di test riflettono le differenze nei piani di campionamento, nei set di test da eseguire congiuntamente, nel livello di qualità accettabile e in altri fattori. Per i test quantitativi sono inoltre presenti differenze nei valori di misura accettabili. Per applicare le proprie linee guida sulla qualità, l'azienda assegna un gruppo di test a ciascuna regola utilizzata per generare automaticamente gli ordini di controllo qualità nella pagina **Associazioni di controllo qualità**. Assegna inoltre un gruppo di test agli ordini di controllo qualità creati manualmente.

## <a name="create-a-test-group"></a>Creazione di un gruppo di test

Per creare un gruppo di test, eseguire i passaggi indicati di seguito:

1. Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Gruppi di test**.
1. Nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia nella parte superiore della pagina. Quindi imposta i seguenti campi per la nuova riga:

    - **Gruppi di test** – Immetti un ID o nome univoco per il gruppo di test.
    - **Descrizione** - Immettere una descrizione dettagliata del gruppo di test.
    - **Livello di qualità accettabile** - Immettere la percentuale totale di risultati del test che deve superare affinché il gruppo di test sia considerato superato.
    - **Campionamento articoli** - Seleziona un campionamento articoli. Per ulteriori informazioni, vedere [Campionamento degli articoli per la gestione della qualità](quality-item-sampling.md).
    - **Distruttivo** - Selezionare questa casella di controllo per indicare che il gruppo di test distruggerà gli articoli testati.

1. Mentre la nuova riga è ancora selezionata, seleziona la scheda **Generale** nella parte superiore della pagina. Alcune delle impostazioni per il gruppo di test selezionato nella scheda **Panoramica** vengono ripetute qui. Inoltre, puoi impostare i seguenti campi per il gruppo:

    - **Aggiorna attributo lotto di magazzino** - Quando imposti questa opzione su *Sì* qui, verrà automaticamente impostato su *Sì* per ogni nuovo test che viene aggiunto al gruppo di test nella parte inferiore della pagina.
    - **Aggiorna smaltimento batch** - Quando imposti questa opzione su *Sì*, se l'articolo che viene testato è controllato in batch, lo smaltimento batch verrà automaticamente aggiornato con il valore selezionato nel campo **Smaltimento batch ordine di controllo qualità non superato** o **Smaltimento batch ordine di controllo qualità superato**.
    - **Smaltimento batch ordine di controllo qualità non superato** - Selezionare il codice di smaltimento batch da assegnare quando un ordine di controllo qualità che include questo gruppo di test non riesce perché non soddisfa l'AQL.
    - **Smaltimento batch ordine di controllo qualità superato** - Selezionare il codice di smaltimento batch da assegnare quando un ordine di controllo qualità che include questo gruppo di test riesce perché soddisfa l'AQL.
    - **Aggiorna stato inventario** - Quando imposti questa opzione su *Sì*, Se **Stato inventario** è abilitato nel gruppo di dimensioni di immagazzinamento per l'articolo che viene testato, lo stato verrà automaticamente aggiornato con lo stato selezionato nel campo **Stato ordine di controllo qualità non superato** o **Stato ordine di controllo qualità superato**.
    - **Stato ordine di controllo qualità non superato** - Selezionare lo stato inventario da assegnare all'articolo quando un ordine di controllo qualità che include questo gruppo di test non riesce perché non soddisfa l'AQL.
    - **Stato ordine di controllo qualità superato** - Selezionare lo stato inventario da assegnare all'articolo quando un ordine di controllo qualità che include questo gruppo di test riesce perché soddisfa l'AQL.

## <a name="add-a-qualitative-test-to-a-test-group"></a>Aggiungere un test qualitativo a un gruppo di test

Per aggiungere un test qualitativo a un gruppo di test, segui questi passaggi.

1. Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Gruppi di test**.
1. Nella scheda **Panoramica** nella parte superiore della pagina, selezionare il gruppo di test a cui si desidera aggiungere un test.
1. Nella parte inferiore della pagina, nella scheda **Panoramica**, selezionare **Aggiungi** sulla barra degli strumenti per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Numero progressivo** - Immettere un numero intero per specificare l'ordine in cui devono essere eseguiti i test. I test che hanno numeri progressivi più piccoli verranno eseguiti prima dei test che hanno numeri progressivi più grandi.

        > [!NOTE]
        > Ti consigliamo di lasciare uno spazio tra i numeri progressivi. Ad esempio, imposta il campo **Numero progressivo** su *10* per il primo test, quindi incrementa il valore di 10 per ogni test aggiuntivo. In questo modo è possibile aggiungere nuovi test in un secondo momento senza dover eliminare e ricreare le righe per inserirle nell'ordine desiderato.

    - **Test** – Selezionare il test che si desidera eseguire. Per un test qualitativo, seleziona un test in cui il campo **Tipo** è impostato su *Opzione*.
    - **Validità** - Seleziona la prima data in cui il test è valido. Se lasci il campo vuoto, non c'è limite.
    - **Scadenza** - Seleziona l'ultima data in cui il test è valido. Se lasci vuoto questo campo o lo imposti su *Mai*, non c'è limite.
    - **Determinazione valori test** - Selezionare come determinare un AQL quando vengono registrati più risultati per lo stesso test. Per un test qualitativo solo *Manuale* può essere selezionato. Se selezioni uno degli altri valori (*Media*, *Minimo*, o *Massimo*), riceverai un messaggio di errore quando salverai il gruppo di test.
    - **Attributo** - Se desideri registrare i risultati del test su un attributo batch, seleziona l'attributo qui e seleziona la casella di controllo **Aggiorna attributo lotto di magazzino**.
    - **Aggiorna attributo lotto di magazzino** - seleziona questa casella di controllo per registrare i risultati del test per l'attributo batch selezionato nel campo **Attributo**.

1. Nella parte inferiore della pagina, seleziona la scheda **Generale**. Alcune delle impostazioni per il test selezionato nella scheda **Panoramica** vengono ripetute qui. Inoltre, puoi impostare i seguenti campi per il test:

    - **Report certificato di analisi** - Imposta questa opzione su *Sì* per indicare che i risultati del test devono essere stampati sul certificato di analisi (CoA). Questo report può essere generato dall'ordine di controllo qualità.
    - **Azione in caso di errore** - Seleziona *Accetta* o *Errore* per indicare se il test deve essere superato o meno se l'AQL non viene soddisfatto.
    - **Livello di qualità accettabile** - Immettere la percentuale totale di risultati del test che deve superare affinché il test sia considerato superato.

1. Nella parte inferiore della pagina, nella scheda **Test**, impostare i seguenti campi:

    - **Variabile** – Selezionare la variabile di test per cui registrare i risultati del test qualitativo.
    - **Risultato predefinito** - Selezionare il risultato predefinito da registrare per i risultati del test.
    - **Strumento di test** - Selezionare il dispositivo da utilizzare per il test. Se è definito uno strumento di test, viene automaticamente inserito per il test nel gruppo di test.

1. Chiudere la pagina.

## <a name="add-a-quantitative-test-to-a-test-group"></a>Aggiungere un test quantitativo a un gruppo di test

Per aggiungere un test quantitativo a un gruppo di test, segui questi passaggi.

1. Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Gruppi di test**.
1. Nella scheda **Panoramica** nella parte superiore della pagina, selezionare il gruppo di test a cui si desidera aggiungere un test.
1. Nella parte inferiore della pagina, nella scheda **Panoramica**, selezionare **Aggiungi** sulla barra degli strumenti per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Numero progressivo** - Immettere un numero intero per specificare l'ordine in cui devono essere eseguiti i test. I test che hanno numeri progressivi più piccoli verranno eseguiti prima dei test che hanno numeri progressivi più grandi.

        > [!NOTE]
        > Ti consigliamo di lasciare uno spazio tra i numeri progressivi. Ad esempio, imposta il campo **Numero progressivo** su *10* per il primo test, quindi incrementa il valore di 10 per ogni test aggiuntivo. In questo modo è possibile aggiungere nuovi test in un secondo momento senza dover eliminare e ricreare le righe per inserirle nell'ordine desiderato.

    - **Test** – Selezionare il test che si desidera eseguire. Per un test quantitativo, seleziona un test in cui il campo **Tipo** è impostato su *Frazione* o *Intero*.
    - **Validità** - Seleziona la prima data in cui il test è valido. Se lasci il campo vuoto, non c'è limite.
    - **Scadenza** - Seleziona l'ultima data in cui il test è valido. Se lasci vuoto questo campo o lo imposti su *Mai*, non c'è limite.
    - **Determinazione valori test** - Selezionare come determinare un AQL quando vengono registrati più risultati per lo stesso test. I metodi disponibili sono *Media*, *Minimo*, *Massimo* e *Manuale*.
    - **Attributo** - Se desideri registrare i risultati del test su un attributo batch, seleziona l'attributo qui e seleziona la casella di controllo **Aggiorna attributo lotto di magazzino**.
    - **Aggiorna attributo lotto di magazzino** - seleziona questa casella di controllo per registrare i risultati del test per l'attributo batch selezionato nel campo **Attributo**.

1. Nella parte inferiore della pagina, seleziona la scheda **Generale**. Alcune delle impostazioni per il test selezionato nella scheda **Panoramica** vengono ripetute qui. Inoltre, puoi impostare i seguenti campi per il test:

    - **Report certificato di analisi** - Imposta questa opzione su *Sì* per indicare che i risultati del test devono essere stampati sul certificato di analisi (CoA). Questo report può essere generato dall'ordine di controllo qualità.
    - **Azione in caso di errore** - Seleziona *Accetta* o *Errore* per indicare se il test deve essere superato o meno se l'AQL non viene soddisfatto.
    - **Livello di qualità accettabile** - Immettere la percentuale totale di risultati del test che deve superare affinché il test sia considerato superato.

1. Nella parte inferiore della pagina, nella scheda **Test**, impostare i seguenti campi:

    - **Standard** - Immettere la quantità (intero o frazione) previsto per i risultati del test. Il valore immesso verrà inserito per impostazione predefinita nei risultati del test. Inoltre, verrà inserito automaticamente come valore predefinito nei campi **Min** e **Max**.
    - **Min** - Immettere il valore minimo consentito per i risultati del test. Il valore immesso deve essere inferiore alla quantità impostata nel campo **Standard**. Quando aggiorni il campo **Min**, il campo **Tolleranza minima (%)** viene aggiornato automaticamente. Similmente, quando aggiorni il campo **Tolleranza minima (%)**, il campo **Min** viene aggiornato automaticamente.
    - **Max** - Immettere il valore massimo consentito per i risultati del test. Il valore immesso deve essere superiore alla quantità impostata nel campo **Standard**. Quando aggiorni il campo **Max**, il campo **Tolleranza massima (%)** viene aggiornato automaticamente. Similmente, quando aggiorni il campo **Tolleranza massima (%)**, il campo **Max** viene aggiornato automaticamente.
    - **Strumento di test** - Selezionare il dispositivo da utilizzare per il test. Se è definito uno strumento di test, viene automaticamente inserito per il test nel gruppo di test.

1. Chiudere la pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Strumenti di test di gestione qualità](quality-management-processes.md)
- [Test di gestione qualità](quality-management-processes.md)
- [Variabili di test di gestione qualità](quality-management-processes.md)
- [Associazioni di controllo qualità](quality-management-processes.md)
- [Attributi batch](../production-control/batch-attributes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
