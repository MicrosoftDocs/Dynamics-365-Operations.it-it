---
title: Risolvere i problemi relativi alle informazioni sul prodotto
description: Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizzano le informazioni sul prodotto.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4c505ccfd1998acd40dbae715c7fa572e315af2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007518"
---
# <a name="troubleshoot-product-information"></a>Risolvere i problemi relativi alle informazioni sul prodotto

Questo argomento descrive come risolvere i problemi che si potrebbero riscontrare mentre si utilizzano le informazioni sul prodotto.

## <a name="i-cant-delete-a-released-product"></a>Impossibile eliminare un prodotto rilasciato.

### <a name="issue-description"></a>Descrizione del problema

È possibile eliminare un prodotto rilasciato e tutte le sue varianti solo se il prodotto rilasciato non ha transazioni correlate.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Seguire questi passaggi per eliminare un prodotto rilasciato o una rappresentazione generale del prodotto.

1. Chiudere tutte le transazioni aperte per gli articoli.
1. Ridurre l'inventario a 0 (zero).
1. Eseguire la chiusura dell'inventario.
1. Eliminare tutte le varianti prodotto per la rappresentazione generale prodotto che si desidera eliminare.

## <a name="can-i-change-the-item-number-of-a-released-product"></a>È possibile modificare il numero di articolo di un prodotto rilasciato?

Nella maggior parte dei casi, non è possibile modificare i numeri di articolo per i prodotti rilasciati, poiché tale modifica provocherà il danneggiamento dei dati. È possibile modificare il numero di articolo solo se è necessario riparare il danneggiamento dei dati causato da una precedente ridenominazione della chiave primaria di quel prodotto rilasciato, come indicato nell'elenco delle [funzionalità rimosse o deprecate per Finance and Operations 10.0.0 con aggiornamento della piattaforma 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).

Per poter modificare i numeri degli articoli per i prodotti rilasciati, [votare questa idea nel portale Ideas](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).

## <a name="the-default-flushing-principle-from-the-product-isnt-being-entered-on-the-bill-of-materials-line"></a>Il principio di registrazione predefinito dal prodotto non viene inserito nella riga della distinta base.

### <a name="issue-description"></a>Descrizione del problema

Quando si aggiunge un articolo a una riga della distinta base (BOM), il sistema non utilizza le informazioni sul principio di registrazione predefinito impostato per l'articolo. In altre parole, il principio di registrazione dell'articolo non appare nella pagina **Riga DBA**.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Se si specifica un principio di registrazione su una riga DBA, verrà applicato a quella riga DBA. Tuttavia, se il principio di registrazione è vuoto o se non è impostato su una riga della distinta base, il principio di registrazione impostato sull'articolo si applicherà comunque a quella riga della distinta base, anche se non viene visualizzato nella riga della distinta base.

La logica predefinita per altre funzionalità in Microsoft Dynamics 365 Supply Chain Management di solito non funziona in questo modo. Tuttavia, il comportamento corrente non può essere modificato. In caso contrario, alcune personalizzazioni esistenti che lo utilizzano potrebbero essere interrotte.

## <a name="the-system-lets-me-save-duplicate-bar-codes-for-different-items-or-for-the-same-item-that-has-different-dimensions"></a>Il sistema consente di salvare i codici a barre duplicati per articoli diversi o per lo stesso articolo con dimensioni diverse.

Il sistema attualmente non applica codici a barre univoci e l'aggiunta di questa restrizione rappresenterebbe un cambiamento radicale. In effetti, Microsoft ha le prove che alcune installazioni dei clienti esistenti verrebbero interrotte da questa modifica. Tuttavia, prenderemo in considerazione una modifica più ampia di progettazione per abilitare questa funzione in futuro.

## <a name="i-receive-the-following-error-message-when-i-edit-item-record-templates-the-warehouse-location-cannot-be-created-because-the-item-is-not-stocked-to-stock-items-the-stocked-product-option-on-the-associated-item-model-group-must-be-selected"></a>Quando modifico i modelli di record dell'articolo, viene visualizzato il seguente messaggio di errore: "Impossibile creare l'ubicazione del magazzino perché l'articolo non è stoccato. Per stoccare gli articoli, è necessario selezionare l'opzione Prodotto stoccato nel gruppo di modelli di articoli associato."

### <a name="issue-description"></a>Descrizione del problema

Questo problema si verifica se si seguono questi passaggi per provare a creare un modello per un articolo che non è stoccato.

1. Aprire un prodotto rilasciato che non è stoccato.
1. Nel riquadro azioni, sella scheda **Opzioni**, selezionare **Informazioni record**.
1. Nel finestra di dialogo **Informazioni record**, selezionare **Modello di account società**.

In questo caso, viene visualizzato il seguente messaggio di errore:

> Impossibile creare l'ubicazione del magazzino perché l'articolo non è stoccato. Per stoccare gli articoli, è necessario selezionare l'opzione Prodotto stoccato nel gruppo di modelli di articoli associato.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Il processo di creazione dei modelli di prodotto richiede una logica aggiuntiva specifica del prodotto. Pertanto, non è possibile utilizzare il generico pulsante **Modello di account società** per questo scopo. Invece, procedere come segue.

1. Aprire un prodotto rilasciato.
1. Nel riquadro azioni, nella scheda **Prodotto** nel gruppo **Nuovo** selezionare **Modello \> Crea modello condiviso**.

## <a name="default-help-text-that-is-added-in-product-attributes-isnt-entered-in-a-released-product"></a>Il testo della guida predefinito che viene aggiunto negli attributi del prodotto non viene immesso in un prodotto rilasciato.

Una descrizione e un testo della guida aggiunti negli attributi del prodotto non sono visibili o inseriti per impostazione predefinita nei prodotti rilasciati. Questo comportamento è predefinito.

## <a name="the-default-quantity-that-is-entered-differs-when-its-registered-from-a-bom-and-when-its-registered-from-a-bom-version"></a>La quantità predefinita immessa è diversa quando è registrata da una distinta materiali e quando è registrata da una versione distinta base.

### <a name="issue-description"></a>Descrizione del problema

Per impostazione predefinita, quando si aggiunge un articolo a una distinta base, la quantità viene impostata su 1 anziché sulla quantità definita nel campo **Quantità minima ordine** della pagina **Impostazioni ordine predefinite** per un prodotto selezionato. Tuttavia, quando si aggiunge un articolo da una versione DBA e l'articolo e la variante vengono selezionati, la quantità immessa per impostazione predefinita tiene conto della quantità minima impostata nelle impostazioni dell'ordine predefinite per le dimensioni specifiche.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è previsto. Tuttavia, il fatto che la logica differisca nella versione DBA e nella DBA è un problema noto. Tuttavia, questo comportamento non verrà modificato, poiché una modifica potrebbe influire su molti scenari di clienti diversi.

## <a name="in-the-released-product-details-i-cant-change-the-attached-images-that-were-uploaded-from-the-product-document-attachments-data-entity"></a>Nei dettagli del prodotto rilasciato, non è possibile modificare le immagini allegate che sono state caricate dall'entità di dati Allegati documento del prodotto.

### <a name="issue-description"></a>Descrizione del problema

Questo problema può verificarsi quando si allega un'immagine a un elemento utilizzando l'entità dati *Allegati documento prodotto*. In questo caso, viene visualizzata l'immagine dell'articolo. Tuttavia, se si seleziona **Cambia immagine**, non viene mostrato nulla nell'elenco delle immagini caricate. Inoltre, non vengono visualizzati allegati per l'articolo.

### <a name="issue-resolution"></a>Risoluzione dei problemi

L'entità *EcoResProductDocumentAttachmentEntity* (*Allegati documento prodotto*) importa gli allegati del documento per i *prodotti* ma non per i *prodotti rilasciati*. I prodotti rilasciati sono noti anche come *articoli*. Per visualizzare gli allegati per un articolo nella pagina **Dettagli prodotto rilasciato** è necessario utilizzare l'entità *EcoResReleasedProductDocumentAttachmentEntity* (*Allegati documento prodotto rilasciati*).

## <a name="the-microsoft-flow-connector-shows-the-following-error-message-update-not-allowed-for-field-productnumber"></a>Il connettore Microsoft Flow mostra il seguente messaggio di errore: "Aggiornamento non consentito per il campo "ProductNumber"."

### <a name="issue-description"></a>Descrizione del problema

Questo problema si verifica se si tenta di aggiornare il campo **Numero prodotto** utilizzando l'entità *Prodotti rilasciati* V2 e Microsoft Flow.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è previsto. La possibilità di modificare il numero di prodotto per un prodotto rilasciato è stata rimossa in Dynamics 365 Finance and Operations 10.0.0 con aggiornamento della piattaforma 24 per aiutare a prevenire il danneggiamento dei dati. In casi eccezionali, in cui è necessario riparare il danneggiamento dei dati causato da una precedente ridenominazione della chiave primaria di un prodotto rilasciato, è possibile chiedere al supporto Microsoft di rimuovere temporaneamente questa restrizione.

## <a name="i-cant-create-a-released-product-variant-in-another-legal-entity"></a>Impossibile creare una variante di prodotto rilasciata in un'altra persona giuridica.

### <a name="issue-description"></a>Descrizione del problema

Se si tenta di rilasciare una rappresentazione generale prodotto senza varianti e quindi si creano le varianti in ciascuna persona giuridica (società) come richiesto, non sarà possibile rilasciare le varianti utilizzando i suggerimenti di varianti. Inoltre, non sarà possibile creare manualmente le varianti.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo comportamento è predefinito. Le relazioni di una rappresentazione generale prodotto e le dimensioni che la rappresentazione può assumere sono mantenute a un livello condiviso. Pertanto, non è possibile creare le dimensioni disponibili per una rappresentazione generale prodotto condivisa nella persona giuridica specifica in cui vengono rilasciate tali dimensioni e quindi replicare il processo in ciascuna persona giuridica in cui le dimensioni sono richieste. Invece, è necessario modificare il processo di rilascio per adattarlo al processo progettato.

Ecco il processo per il rilascio dei prodotti.

1. Creare la rappresentazione generale prodotto condivisa e le dimensioni che possono essere rilasciate alle persone giuridiche.
1. Rilasciare i prodotti alle persone giuridiche utilizzando suggerimenti di varianti o aggiungendo manualmente le combinazioni che devono essere rilasciate.

In alternativa, è possibile creare direttamente il prodotto rilasciato.

## <a name="when-i-release-a-variant-in-another-company-i-receive-the-following-error-message-product-variant-with-specified-dimensions-has-already-been-created"></a>Quando viene rilasciata una variante in un'altra società, viene visualizzato il seguente messaggio di errore: "La variante del prodotto con le dimensioni specificate è già stata creata".

### <a name="issue-description"></a>Descrizione del problema

Se una variante di prodotto è già stata rilasciata in un'azienda A e si tenta di rilasciarla nell'azienda B utilizzando il pulsante **Nuovo** della pagina **Varianti prodotti rilasciati**, viene visualizzato il seguente messaggio di errore:

> Una variante prodotto con dimensioni specificate è già stata creata.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Il pulsante **Nuovo** della pagina **Varianti prodotti rilasciati** crea la variante e la rilascia nel contesto aziendale. Se la variante è già stata creata, non è possibile utilizzare il pulsante **Nuovo** per rilasciarla in un'altra azienda.

Per risolvere il problema, aprire la pagina **Rappresentazione generale prodotto** e selezionare **Rilascia prodotto** per rilasciare la variante esistente nella società desiderata.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]