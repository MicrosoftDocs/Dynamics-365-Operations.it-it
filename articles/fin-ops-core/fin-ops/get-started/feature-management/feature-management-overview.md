---
title: Panoramica della gestione funzionalità
description: In questo argomento viene descritta la caratteristica Gestione funzionalità e come è possibile utilizzarla.
author: ChrisGarty
manager: AnnBe
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 22e5333859d37ad33f5806d63fc874b1b5a52831
ms.sourcegitcommit: 165e082e59ab783995c16fd70943584bc3ba3455
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2020
ms.locfileid: "3967336"
---
# <a name="feature-management-overview"></a>Panoramica della gestione funzionalità

[!include [banner](../../includes/banner.md)]

Le funzionalità vengono aggiunte e aggiornate in ogni versione. L'esperienza di gestione delle funzionalità offre un'area di lavoro in cui è possibile visualizzare un elenco delle funzionalità incluse in ciascuna versione. Per impostazione predefinita, le nuove funzionalità sono disabilitate. È possibile utilizzare l'area di lavoro per accendere alle funzionalità e visualizzare la documentazione correlata.

## <a name="the-feature-management-workspace"></a>Area di lavoro Gestione funzionalità

È possibile aprire l'area di lavoro **Gestione funzionalità** selezionando i riquadri appropriati nel dashboard. Verrà visualizzata una pagina che mostra un elenco di funzionalità per tutte le versioni supportate dall'esperienza di gestione delle funzionalità. Nel corso del tempo, Microsoft migliorerà l'esperienza di gestione delle funzionalità in modo che includa caratteristiche aggiuntive per agevolare la gestione delle funzionalità.

L'elenco delle funzionalità include le seguenti informazioni:

- **Nome funzionalità** - Una descrizione della funzionalità che è stata aggiunta.
- **Stato abilitato** - Un simbolo indica se una funzionalità è stata abilitata (segno di spunta), non è abilitata (vuoto), se è stata programmata per essere abilitata (orologio) o se è obbligatorio abilitarla (blocco), richiede attenzione prima di essere abilitata (avviso) o non può essere abilitata (X). L'impostazione mostrata viene utilizzata per tutte le persone giuridiche. Tenere presente che anche quando una funzione è stata abilitata, è comunque controllata dalla sicurezza. Di conseguenza, la funzionalità sarà disponibile solo per gli utenti che hanno accesso ad essa, in base al ruolo di sicurezza. Inoltre è disponibile solo nelle persone giuridiche a cui l'utente può accedere.
- **Data abilitazione** - La data in cui la funzionalità è stata o verrà abilitata.
- **Funzionalità aggiunta** - La data in cui la funzionalità è stata aggiunta all'ambiente. Questa data viene immessa automaticamente quando si aggiorna l'ambiente durante i cicli mensili di rilascio.
- **Modulo** - Il modulo interessato dalla nuova funzionalità.

Quando si seleziona una funzionalità, ulteriori informazioni vengono visualizzate nel riquadro dei dettagli a destra dell'elenco delle funzionalità. Nella parte superiore del riquadro, verrà visualizzato il nome della funzionalità, la data in cui la funzionalità è stata aggiunta, il modulo interessato dalla funzionalità e un collegamento **Ulteriori informazioni**. Selezionare il collegamento per visualizzare la documentazione relativa alla funzionalità. Se la documentazione non è disponibile, si viene reindirizzati a una pagina temporanea. Nel riquadro Dettagli è presente anche un campo **Commenti** in cui è possibile aggiungere i propri commenti sulla funzionalità.

L'area lavoro **Gestione funzionalità** contiene anche più schede, ognuna con un elenco delle funzionalità.

- **Nuove** - Questa scheda visualizza tutte le funzionalità aggiunte dall'ultimo aggiornamento mensile. Se sono stati ignorati degli aggiornamenti mensili, la scheda visualizza tutte le nuove funzionalità aggiunte dall'ultimo aggiornamento. Le nuove funzionalità compaiono nella parte superiore dell'elenco. Il numero totale di nuove funzionalità è mostrato anche in un riquadro nella parte superiore della pagina.
- **Non abilitate** - Questa scheda visualizza tutte le funzionalità che non sono state abilitate. Le nuove funzionalità compaiono nella parte superiore dell'elenco. Il numero totale di nuove funzionalità che non sono state abilitate è visualizzato anche in un riquadro nella parte superiore della pagina.
- **Programmate** - Questa scheda visualizza tutte le funzionalità che sono state programmate per essere abilitate in futuro. Le funzionalità con la data programmata più prossima sono visualizzate nella parte superiore dell'elenco. Il numero totale di nuove funzionalità pianificate è visualizzato anche in un riquadro nella parte superiore della pagina.
- **Tutte** - Questa scheda mostra tutte le funzionalità. Le nuove funzionalità compaiono nella parte superiore dell'elenco.

## <a name="turn-on-a-feature"></a>Abilitare una funzionalità

Se una funzionalità non è stata abilitata, un pulsante **Abilita ora** viene visualizzato nel riquadro dei dettagli. È possibile utilizzare questo pulsante per abilitare la funzionalità.

- Selezionare la funzionalità che si desidera abilitare, quindi nel riquadro dei dettagli, selezionare **Abilita ora**. La funzionalità viene abilitata.

Alcune funzionalità non possono essere disabilitate dopo l'abilitazione. Se la funzionalità che si sta cercando di abilitare non può essere disabilitata, viene visualizzato un avviso. A quel punto, è possibile selezionare **Annulla** per annullare l'operazione e lasciare la funzionalità disabilitata. Tuttavia, se si seleziona **Abilita** per abilitare la funzionalità, non sarà possibile disabilitarla in un secondo momento.

Alcune funzionalità visualizzeranno un messaggio che fornisce ulteriori informazioni prima dell'abilitazione. Queste funzionalità sono contrassegnate da un simbolo giallo di avviso. È consigliabile leggere attentamente informazioni aggiuntive per capire meglio che cosa si verifica quando la funzionalità è abilitata. Tuttavia, è comunque possibile selezionare **Abilita** per abilitare la funzionalità.

Alcune funzionalità visualizzeranno un messaggio che la funzionalità non può essere abilitata finché non si intraprende un'azione. Queste funzionalità sono contrassegnate da un simbolo X rosso. È necessario intraprendere azioni descritti nella descrizione prima di abilitare la funzionalità. Ad esempio, se non è possibile utilizzare una funzionalità finché non si disabilita una chiave di configurazione, è necessario prima disabilitare la chiave di configurazione e successivamente tornare alla Gestione funzionalità per abilitare la funzionalità.

Dopo la disabilitazione di una funzionalità, sotto il collegamento **Ulteriori informazioni** viene visualizzato un messaggio nel riquadro dei dettagli. Questo messaggio informa che la funzionalità è stata abilitata o indica la data in cui la funzionalità verrà abilitata. Viene visualizzato ogni volta che si seleziona la funzionalità nell'elenco delle funzionalità.

Le funzionalità di cui è stata programmata l'abilitazione sono visualizzate nella scheda **Programmate**. Un processo batch le abiliterà alla mezzanotte di quella data in base al fuso orario rappresentato dalla data di sistema.

## <a name="reschedule-a-feature"></a>Ripianificare una funzionalità

Se l'abilitazione di una funzionalità è stata programmata, un pulsante **Programma** viene visualizzato nel riquadro dei dettagli. È possibile utilizzare questo pulsante per cambiare il valore **Data abilitazione** con una data diversa.

1. Selezionare la funzionalità programmata che si desidera riprogrammare, quindi nel riquadro dei dettagli, selezionare **Programma**.
2. Nella finestra di dialogo visualizzata, nel campo **Data abilitazione**, specificare la nuova data in cui la funzionalità deve essere abilitata.
3. Selezionare **Abilita** per riprogrammare la funzionalità o **Disabilita** per annullare la programmazione.

## <a name="turn-off-a-feature"></a>Disabilitare una funzionalità

Se una funzionalità è già stata abilitata, un pulsante **Disabilita** viene visualizzato nel riquadro dei dettagli. È possibile utilizzare questo pulsante per disabilitare la funzionalità. Il pulsante **Disabilita** non è disponibile se la funzionalità non può essere disabilitata dopo che è stata abilitata.

- Selezionare la funzionalità da disabilitare, quindi nel riquadro dei dettagli, selezionare **Disabilita**. La funzionalità è disabilitata e il campo **Data abilitazione** è vuoto.

Dopo la disabilitazione di una funzionalità, sotto il collegamento **Ulteriori informazioni** viene visualizzato un messaggio nel riquadro dei dettagli. Questo messaggio indica che la funzionalità non è stata ancora abilitata. Viene visualizzato ogni volta che si seleziona la funzionalità nell'elenco delle funzionalità. Le funzionalità che non sono state abilitate sono visualizzate nella scheda **Non abilitate**.

## <a name="features-that-must-be-turned-on"></a>Funzionalità che devono essere abilitate

A volte, viene fornita una funzionalità fondamentale che deve essere abilitata automaticamente quando si esegue un aggiornamento. Queste funzionalità saranno abilitate automaticamente alla data specificata nel campo **Data abilitazione**. Per queste funzionalità, sotto il collegamento **Ulteriori informazioni** viene visualizzato un messaggio nel riquadro dei dettagli. Questo messaggio informa che la funzionalità è stata abilitata o indica la data in cui la funzionalità verrà abilitata. Viene visualizzato ogni volta che si seleziona la funzionalità nell'elenco delle funzionalità.

## <a name="enable-all-features"></a>Abilita tutte le funzionalità

Per impostazione predefinita, tutte le funzionalità aggiunte all'ambiente sono disabilitate. È possibile abilitare tutte le funzionalità selezionando il pulsante **Abilita tutto**. 

Quando si seleziona **Abilita tutto**, verrà visualizzato un'opzione in cui necessario immettere le seguenti informazioni:
- Elenco di tutte le funzionalità che richiedono la conferma prima di poter essere abilitate. Se si desidera abilitare le funzionalità nell'elenco, scegliere **Sì** per il pulsante **Abilita le funzionalità che richiedono conferma**.
- Elenco di tutte le funzionalità che non possono essere abilitate verrà visualizzato. Quelle funzionalità non verranno abilitate.

Tutte le funzionalità che possono essere abilitate verranno abilitate. Se una funzionalità è già programmata per essere abilitata in futuro, la programmazione non verrà modificata. 

## <a name="turn-on-all-features-automatically"></a>Abilitare automaticamente tutte le funzionalità

Per impostazione predefinita, tutte le funzionalità aggiunte all'ambiente sono disabilitate, a meno che non siano funzionalità obbligatorie. Tuttavia, se si desidera abilitare automaticamente tutte le nuove funzionalità, è possibile utilizzare l'elenco a discesa sotto il titolo dell'area di lavoro per modificare ciò che avviene quando vengono aggiunte nuove funzionalità.

- Selezionare **Abilità nuove funzionalità automaticamente** per abilitare automaticamente tutte le nuove funzionalità quando vengono aggiunte all'ambiente.
- Selezionare **Non abilitare nuove funzionalità automaticamente** per disabilitare tutte le nuove funzionalità quando vengono aggiunte all'ambiente.


Quando si abilita automaticamente ogni funzionalità, saranno abilitate tutte le funzionalità che verrebbero abilitate quando si fa clic sul pulsante **Abilita tutto**. Non saranno abilitate le funzionalità che richiedono la conferma o le funzionalità che non possono essere abilitate finché non si intraprende un'azione.

## <a name="check-for-updates"></a>Controlla aggiornamenti

Le funzionalità vengono aggiunti all'ambiente dopo ogni aggiornamento. Tuttavia, è possibile controllare manualmente se esistono aggiornamenti facendo clic sul pulsante **Controlla aggiornamenti**. Qualsiasi funzionalità che è stata aggiunta al sistema dopo l'aggiornamento verrà aggiunta all'elenco delle funzionalità. Ad esempio, se una funzionalità in anteprima viene abilitata dopo un rilascio di versione, è possibile verificare la presenza di eventuali aggiornamenti e la funzionalità verrà aggiunta all'elenco.

## <a name="assigning-roles"></a>Assegnare i ruoli

L'area di lavoro **Gestione funzionalità** può essere aperta dagli amministratori di sistema nonché dagli utenti a cui è assegnato il ruoli di responsabile delle funzionalità o di visualizzatore delle funzionalità. Questi due ruoli sono stati creati per supportare l'esperienza di gestione delle funzionalità. Gli utenti con ruolo di responsabile delle funzionalità possono abilitare o disabilitare tutte le funzionalità. Possono anche aggiornare il campo **Commenti** relativo alla funzionalità. Gli utenti con ruolo di visualizzatore della funzionalità possono visualizzare solo l'area di lavoro **Gestione funzionalità**. Non possono abilitare o disabilitare le funzionalità.

I ruoli di responsabile delle funzionalità e visualizzatore delle funzionalità non sostituiscano la protezione esistente dell'utente. Questi controllano se un utente può abilitare e disabilitare le funzionalità. Non forniscono accesso alle funzionalità vere e proprie.

## <a name="features-that-use-configuration-keys"></a>Funzionalità che utilizzano chiavi di configurazione

Se una funzionalità utilizza una chiave di configurazione, ma questa chiave non è abilitata, la funzionalità non è visualizzata nell'elenco delle funzionalità disponibili nell'area di lavoro **Gestione funzionalità**. Dopo l'abilitazione della chiave di configurazione, è necessario aggiornare l'elenco delle funzionalità utilizzando la voce **Verifica disponibilità aggiornamento**. La funzionalità è quindi visualizzata nell'elenco delle funzionalità.

Se si disabilita la chiave di configurazione, la funzionalità non viene rimossa dall'elenco delle funzionalità.

## <a name="data-entities"></a>Entità di dati

Un'entità di dati denominata **Gestione funzionalità** consente di esportare le impostazioni di gestione delle funzionalità da un ambiente e quindi di importarle in un altro ambiente. Questa entità aggiorna solo le funzionalità esistenti. La logica di business nell'entità garantisce inoltre che le stesse regole utilizzate nell'area di lavoro **Gestione funzionalità** verranno applicate all'importazione. Ad esempio, non è possibile sostituire l'impostazione di una funzionalità obbligatoria rimuovendo la data durante l'importazione.

Gli esempi riportati di seguito descrivono cosa accade quando si utilizza l'entità **Gestione funzionalità** per importare dati.

- Se si modifica il valore del campo **Abilitato** su **Sì**, la funzionalità viene abilitata e il campo **Data abilitazione** è impostato sulla data corrente.
- Se si modifica il valore del campo **Abilitato** su **No** o si lascia vuoto il campo **EnableDate**, la funzionalità viene disabilitata e il campo **Data abilitazione** è vuoto. Non è possibile disabilitare una funzionalità obbligatoria o una funzionalità che non può essere disabilitata dopo l'abilitazione.
- Se si imposta il campo **EnableDate** su una data futura, la funzionalità viene programmata per tale data.
- Se si imposta il campo **Abilitato** su **Sì** e il campo **EnableDate** su una data futura, la funzionalità viene programmata per quella data. 
- Se si imposta il campo **Abilitato** su **No** nonché il campo **EnableDate** su una data futura, la funzionalità viene programmata per quella data.
- Se una funzionalità viene abilitata e si aggiunge un campo **EnableDate** impostato su una data futura, la funzionalità rimane abilitata. Per riprogrammare la funzionalità, è necessario impostare il campo **Abilitato** su **No**.

## <a name="feature-management-and-flighting"></a>Gestione delle funzionalità e versione di anteprima

La gestione delle funzionalità consente di controllare le funzionalità fornite in ogni versione. La versione di anteprima consente ai team Microsoft di rilasciare funzionalità per un numero limitato di clienti, in modo che tali funzionalità possano essere testate e convalidate senza influire su tutti i clienti. La gestione delle funzionalità non controlla la versione di anteprima di alcuna funzionalità.

## <a name="new-features-are-optional-for-12-months"></a>Le nuove funzionalità sono facoltative per 12 mesi

Quando viene installata una nuova funzionalità non critica, sarà facoltativa per un periodo di 12 mesi. Ciò consente a te e alla tua organizzazione di pianificare in anticipo quando utilizzare una funzionalità e verificarla rispetto alle operazioni quotidiane. Per ulteriori informazioni, vedi [Domande frequenti aggiornamenti del servizio versione uno](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/one-version#what-about-new-features).

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>Utilizzo della gestione delle funzionalità per abilitare funzionalità ISV o funzionalità personalizzate

La gestione della funzionalità non è attualmente disponibile per le funzionalità ISV (Independent Software Vendor) e personalizzate. Tuttavia, Microsoft aggiunge ulteriori funzionalità per migliorare la gestione della funzionalità. Dopo il completamento di tali miglioramenti, Microsoft renderà la gestione della funzionalità disponibile per tutte le funzionalità e fornirà istruzioni per l'aggiornamento delle funzionalità.

## <a name="frequently-asked-questions-faq"></a>Domande frequenti

### <a name="when-are-features-added-removed-or-changed"></a>Quando sono state aggiunte, rimosse o modificate le funzionalità? 
Le funzionalità vengono aggiunte, rimosse e modificate mediante modifiche al codice. Gli ambienti devono essere aggiornati per ricevere tali modifiche.

### <a name="does-a-feature-become-mandatory-automatically"></a>Una funzionalità diventa automaticamente obbligatoria? 
No, una funzione che diventa obbligatoria non è un'azione automatica. I team del prodotto devono apportare una modifica del codice.

### <a name="when-do-features-become-mandatory"></a>Quando le funzionalità diventano obbligatorie? 
I criteri prevedono che tutte le nuove funzionalità saranno attivate per un periodo di 12 mesi e non richiederanno alcuna gestione delle modifiche fino a quando non verrà abilitata la funzionalità. I team del prodotto possono scegliere se rendere obbligatoria una funzione dopo la fine di tale periodo. 

### <a name="why-isnt-there-a-specific-mandatory-enabled-date"></a>Perché non esiste una "data di abilitazione obbligatoria" specifica? 
I tempi di rilascio degli aggiornamenti sono variabili, i tempi di aggiornamento dell'ambiente sono variabili e i clienti possono scegliere di saltare alcuni aggiornamenti. Di conseguenza, le date specifiche sono difficili da determinare. 

### <a name="wheres-the-documentation-for-features-that-are-being-made-mandatory"></a>Dov'è la documentazione per le funzionalità rese obbligatorie? 
Questa documentazione proviene dai team delle applicazioni. Spesso, questi verranno menzionati in [Funzionalità rimosse o deprecate](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features). 

### <a name="is-there-an-in-product-notification-or-signal-that-a-feature-is-going-to-be-mandatory-enabled"></a>Esiste una notifica all'interno del prodotto o un segnale che indica che la funzionalità sta per essere abilitata obbligatoriamente? 
Oggi non esiste un meccanismo di notifica correlato a rendere obbligatoria una funzione.

### <a name="do-features-ever-get-enabled-without-the-customer-knowing-about-it"></a>Le funzionalità vengono sempre abilitate senza che il cliente lo sappia? 
Sì, se le funzionalità non hanno un impatto funzionale, possono essere abilitate per impostazione predefinita.

### <a name="what-is-feature-flighting-and-how-does-it-relate-to-feature-management"></a>Che cos'è la versione di anteprima delle funzionalità e in che modo è correlata alla gestione delle funzionalità? 
Le versioni di anteprima sono interruttori attivati/disabilitati in tempo reale controllate da Microsoft. Sono diverse dal controllo del cliente fornito da Gestione funzionalità. 
- Le funzionalità di anteprima private non verranno elencate in Gestione funzionalità fino a quando non vengono visualizzate in anteprima. Nella produzione, il cliente deve accettare di far parte di un programma speciale affinché ciò avvenga.
- Le funzionalità di anteprima pubblica e rilasciate (generalmente disponibili) verranno elencate in Gestione funzionalità a meno che non vengano disattivate. La versione di anteprima di una funzionalità è considerata l'ultima opzione di ultima istanza per i team del prodotto se viene riscontrato un problema critico e di solito potrebbe essere un'operazione per cliente.

### <a name="do-features-ever-get-flighted-off-without-the-customer-knowing-about-it"></a>Le funzionalità vengono sempre visualizzate in anteprima senza che il cliente lo sappia? 
Sì, se una funzionalità influisce sul funzionamento di un ambiente che non ha un impatto funzionale, puoi abilitarla per impostazione predefinita.

### <a name="how-can-feature-enablement-be-checked-in-code"></a>Come è possibile controllare l'abilitazione delle funzionalità nel codice?
Usa il metodo **isFeatureEnabled** nella classe **FeatureStateProvider**, passandogli un'istanza della classe di funzionalità. Esempio: 

    if (FeatureStateProvider::isFeatureEnabled(BatchContentionPreventionFeature::instance()))

### <a name="how-can-feature-enablement-be-checked-in-metadata"></a>Come è possibile controllare l'abilitazione delle funzionalità nei metadati?
La proprietà **FeatureClass** può essere utilizzata per indicare che alcuni metadati sono associati a una funzionalità. Deve essere utilizzato il nome della classe utilizzato per la funzionalità, ad esempio **BatchContentionPreventionFeature**. Questi metadati sono visibili solo in quella funzionalità. La proprietà **FeatureClass** è disponibile in menu, voci di menu, valori di enumerazione e campi di tabelle/visualizzazioni.

### <a name="what-is-a-feature-class"></a>Cos'è una classe di funzionalità?
Le funzionalità in Gestione funzionalità sono definite come *classi di funzionalità*. Una classe di funzionalità **implementa IFeatureMetadata** e utilizza l'attributo della classe di funzionalità per identificarsi nello spazio di lavoro Gestione funzionalità. Sono disponibili numerosi esempi di classi di funzionalità che è possibile verificare per l'abilitazione nel codice utilizzando l'API **FeatureStateProvider** e nei metadati utilizzando la proprietà **FeatureClass**. Esempio: 

    [ExportAttribute(identifierStr(Microsoft.Dynamics.ApplicationPlatform.FeatureExposure.IFeatureMetadata))]
    internal final class BankCurrencyRevalGlobalEnableFeature implements IFeatureMetadata
    
### <a name="what-is-the-ifeaturelifecycle-implemented-by-some-feature-classes"></a>Cos'è l'IFeatureLifecycle implementato da alcune classi di funzionalità?
IFeatureLifecycle è un meccanismo interno a Microsoft per indicare la fase del ciclo di vita delle funzionalità. Le funzionalità possono essere:
- PrivatePreview - Necessita una distribuzione in anteprima per essere visibile.
- PublicPreview: - Visualizzato per impostazione predefinita ma con un avviso indicante che la funzionalità è in anteprima.
- Released - Rilasciato completamente.

