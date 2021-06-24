---
title: Introduzione a Calcolo imposte
description: In questo argomento viene illustrato come configurare Calcolo imposte.
author: wangchen
ms.date: 05/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e72b81d4a109db2dd8b4c6ca2ca0b030220e25f3
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216721"
---
# <a name="get-started-with-the-tax-calculation-preview"></a>Introduzione a Calcolo imposte

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Questo argomento fornisce informazioni su come iniziare a usare Calcolo imposte. Innanzitutto, ti guida attraverso i passaggi di configurazione in Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS), e Dynamics 365 Finance e Dynamics 365 Supply Chain Management. Esamina quindi il processo comune per l'utilizzo della funzionalità Calcolo imposte nelle transazioni di Finance e Supply Chain Management.

La configurazione consiste in quattro passaggi principali:

1. In LCS, installazione di Calcolo imposte.
2. In RCS, configurazione della funzionalità Calcolo imposte. Questa configurazione non è specifica di una persona giuridica. Può essere condivisa tra le persone giuridiche in Finance and Supply Chain Management.
3. In Finance and Supply Chain Management, configurazione dei parametri di Calcolo imposte in base alla persona giuridica.
4. In Finance and Supply Chain Management, creazione delle transazioni come ordini di vendita e utilizzo di Calcolo imposte per determinare e calcolare le imposte.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter completare le procedure in questo argomento, è necessario soddisfare i seguenti prerequisiti:

- Hai l'accesso al tuo account LCS e hai distribuito un progetto LCS con un ambiente di livello 2 (o successivo) che esegue Dynamics 365 versione 10.0.18 con [KB4616360](https://fix.lcs.dynamics.com/Issue/Details?kb=4616360&bugId=568738&dbType=3&qc=1f1c04ff39adad74ef871f539e8d73e14c1893ef7cc4b6e3f7d5c5864ec2781a) o successiva.
- Hai l'accesso al tuo account RCS.
- Hai contattato Microsoft per abilitare la versione di anteprima nel tuo ambiente Finance o Supply Chain Management distribuito.

## <a name="set-up-tax-calculation-in-lcs"></a>Configurare Calcolo imposte in LCS

1. Accedi a [LCS](https://lcs.dynamics.com)
2. Completa la configurazione per l'integrazione di Microsoft Power Platform. Per ulteriori informazioni, vedi [Panoramica dei componenti aggiuntivi](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Seleziona uno degli ambienti non di produzione distribuiti, quindi seleziona **Installa un nuovo componente aggiuntivo**.
4. Seleziona **Calcolo imposte (anteprima)**.
5. Leggi e accetta le condizioni, quindi seleziona **Installa**.

## <a name="set-up-tax-calculation-in-rcs"></a>Configurare Calcolo imposte in RCS

I passaggi in questa sezione non sono correlati a una persona giuridica specifica. Devi completare questa procedura solo una volta e poi puoi completarla in qualsiasi persona giuridica in RCS.

1. Accedere a [RCS](https://marketing.configure.global.dynamics.com/).
2. Nell'area di lavoro **Creazione di report elettronici**, aggiungi un nuovo provider di configurazioni. Usa il nome della tua azienda come nome del provider. Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Seleziona il provider di configurazione appena creato, quindi seleziona **Imposta attivo**.
4. Seleziona il provider di configurazioni **Microsoft** e seleziona **Repository**.
5. Nel campo **Tipo** seleziona **Globale**.
6. Selezionare **Apri**.
7. Vai a **Modello dati fiscali**, espandi la struttura ad albero dei file e quindi seleziona **Configurazione fiscale**.
8. Seleziona la versione più recente, quindi seleziona **Importa**.
9. Torna all'area di lavoro **Funzionalità di globalizzazione (anteprima)** seleziona **Funzionalità**, seleziona il riquadro **Calcolo imposte**, quindi seleziona **Aggiungi**.
10. Consente di selezionare uno dei seguenti tipi di funzionalità:

    - **Nuova funzionalità** - Crea una configurazione della funzionalità con contenuto vuoto.
    - **Basata su funzionalità esistente** - Crea una funzionalità da una funzionalità esistente e copia il contenuto dalla configurazione della funzionalità esistente.

11. Immetti un nome e una descrizione per la funzionalità e seleziona **Crea funzionalità**.

    Dopo la creazione della funzionalità, ne viene creata automaticamente una versione bozza.

12. Seleziona la versione bozza della funzionalità, quindi seleziona **Modifica**. La pagina **Configurazione di Calcolo imposte** è compilata.
13. Seleziona **Versione configurazione**. Dovresti vedere la versione della configurazione che hai importato nel passaggio 8.

    Microsoft fornisce una configurazione fiscale predefinita per il componente aggiuntivo Calcolo imposte. Questa configurazione copre la maggior parte dei requisiti per i comportamenti di Calcolo imposte. Sarà aggiornata in base ai feedback del mercato. Se è necessario estendere la configurazione per soddisfare requisiti specifici, vedi [Come creare l'estensione nel servizio per le imposte](./tax-service-add-data-fields-tax-integration-by-extension.md) per informazioni su come generare e selezionare la propria configurazione fiscale.

    Dopo aver selezionato **Versione configurazione**, vengono visualizzate diverse schede aggiuntive:

    - **Codici fiscali** - Questa scheda è obbligatoria. Viene utilizzato per mantenere i dati mater per i codici imposta. Tutti i codici imposta creati in questa scheda vengono sincronizzati automaticamente con Finance quando si abilita la versione corrente dell'impostazione della funzione fiscale nella persona giuridica.
    - **Applicabilità codici imposta** - Questa scheda è obbligatoria. Viene utilizzata per definire una matrice che determina il codice imposta, il gruppo di imposte e il gruppo di imposte degli articoli. Il codice imposta determinato viene utilizzato per calcolare l'importo dell'imposta. I valori dei campi **Codice imposta**, **Gruppo di imposte**, e **Gruppo di imposte articolo** vengono restituiti a Finance.
    - **Applicabilità numero partita IVA cliente** - Questa scheda è facoltativa. Se hai più partite IVA per un cliente, Calcolo imposte può determinare automaticamente la partita IVA corretta. Nella matrice di questa scheda si definiscono le regole che il componente aggiuntivo utilizza per effettuare la determinazione. In caso contrario, Finance e Supply Chain Management continueranno a utilizzare la partita IVA predefinita nei documenti tassabili per le transazioni di vendita.
    - **Applicabilità numero partita IVA fornitore** - Questa scheda è facoltativa. Se hai più partite IVA per un fornitore, Calcolo imposte può determinare automaticamente la partita IVA corretta. Nella matrice di questa scheda si definiscono le regole che il componente aggiuntivo utilizza per effettuare la determinazione. In caso contrario, Finance e Supply Chain Management continueranno a utilizzare la partita IVA predefinita nei documenti tassabili per le transazioni di acquisto.
    - **Applicabilità codici elenco** - Questa scheda è facoltativa. Può aiutare a determinare automaticamente il valore del campo **Codice elenco** attraverso regole più flessibili e configurabili. Nella matrice di questa scheda puoi definire le regole che il componente aggiuntivo utilizza per effettuare la determinazione. In caso contrario, Finance e Supply Chain Management continueranno a utilizzare il codice sui documenti tassabili.

14. Nella scheda **Codici imposta** seleziona **Aggiungi** e inserisci il codice imposta e una descrizione.
15. Seleziona **Componente fiscale**. Il componente fiscale è un gruppo di metodi definiti nella versione precedente della configurazione fiscale selezionata. Sono disponibili i seguenti componenti fiscali:

    - Per importo netto
    - Per importo lordo
    - Per quantità
    - Per margine
    - Imposta sull'imposta

16. Selezionare **Salva**. Diventano disponibili più campi, in base al componente fiscale selezionato.
17. Utilizza le seguenti opzioni per identificare la natura del codice imposta:

    - Esente
    - IVA intracomunitaria
    - Reverse charge
    - Escludi da calcolo importo di base

    Per uno scenario di IVA intracomunitaria, configura un codice imposta unico con un'aliquota fiscale positiva e contrassegnalo come **IVA intracomunitaria**.

    Per uno scenario di reverse charge, configura due codici imposta, uno dei quali ha un'aliquota fiscale positiva e l'altro ha un'aliquota fiscale negativa ma lo stesso valore dell'aliquota. Contrassegna il codice imposta negativo come **Reverse charge**. Per ulteriori informazioni sulla soluzione di reverse charge in Finance, vedi [Meccanismo di reverse charge per lo schema IVA/GST](emea-reverse-charge.md).
    
    Per alcuni tipi di imposta che devono essere esclusi nel calcolo dell'importo della base imponibile per le transazioni che includono il prezzo, come i dazi doganali in alcuni paesi, selezionare la casella di controllo **Escludi da calcolo importo di base**.

    Mantieni le aliquote fiscali e i limiti di importo delle imposte per questo codice imposta.

18. Ripeti i passaggi dal 14 al 17 per aggiungere tutti gli altri codici imposta necessari.
19. Nella scheda **Applicabilità codici imposta**, seleziona le colonne necessarie per determinare il codice imposta corretto, quindi seleziona **Aggiungi**.
20. Immetti o seleziona i valori per ciascuna colonna. I campi **Codice imposta**, **Gruppo di imposte**, e **Gruppo di imposte articolo** saranno l'output di questa matrice.
21. Ripeti i passaggi da 19 a 20 per configurare l'applicabilità delle partite IVA del cliente, delle partite IVA del fornitore e dei codici di elenco.
22. Selezionare **Salva**, quindi chiudere la pagina.
23. Selezionare **Cambia stato** \> **Completato**. Dopo che lo stato è cambiato in **Completato**, la versione non può più essere modificata.
24. Seleziona **Cambia stato** \> **Pubblica**. Questa versione della configurazione della funzione fiscale verrà inviata al repository globale e sarà visibile a ogni persona giuridica in Finance.

## <a name="dynamics-365-setup"></a>Configurazione di Dynamics 365

Dopo aver completato la configurazione in RCS, come descritto nella sezione precedente, avrai una versione pubblicata della funzionalità fiscale. Segui questi passaggi per configurare Calcolo imposte in Finance.

La configurazione in questa sezione viene eseguita dalla persona giuridica. Devi configurarla per ogni persona giuridica per cui vuoi abilitare Calcolo imposte in Finance.

1. In Finance, vai a **Imposta** \> **Impostazioni** \> **Configurazione fiscale** \> **Configurazione del calcolo delle imposte (anteprima)**.
2. Nella scheda **Generale**, impostare i seguenti campi:

    - **Abilita Calcolo imposte** - Seleziona questa casella di controllo per abilitare il componente aggiuntivo Calcolo imposte per la persona giuridica. Se non è abilitato per la persona giuridica corrente, la persona giuridica continuerà a utilizzare il motore fiscale esistente per determinare e calcolare le imposte.
    - **Configurazione funzionalità** - Seleziona una configurazione e una versione della funzione fiscale pubblicata per la persona giuridica. Per ulteriori informazioni su come configurare e completare una funzione fiscale pubblicata, vedi la sezione precedente di questo argomento.
    - **Processo aziendale** - Seleziona i processi aziendali da abilitare.
    - **Abilita rettifica codice imposta** - Imposta questa opzione su **Sì** per abilitare le rettifiche del codice imposta nella pagina IVA.

3. Nella scheda **Calcolo** definisci la regola di arrotondamento prevista per la persona giuridica.
4. Nella scheda **Gestione degli errori** definisci il metodo di gestione degli errori previsti per la persona giuridica. Sono disponibili tre opzioni per ogni codice di risultato:

    - Nessuno
    - Avviso
    - Errore

5. Salva la configurazione.
6. Ripeti i passaggi da 1 a 5 per ciascuna persona giuridica aggiuntiva.

## <a name="transaction-processing"></a>Elaborazione delle transazioni

Dopo aver completato tutte le procedure di configurazione, puoi utilizzare Calcolo imposte per determinare e calcolare le imposte in Finance. I passaggi per elaborare le transazioni rimangono gli stessi. Le seguenti transazioni sono supportate nella versione Finance 10.0.18:

- Processo di vendita

    - Offerta di vendita
    - Ordine cliente
    - Conferma
    - Distinta di prelievo
    - Documento di trasporto
    - Fattura di vendita
    - Nota di accredito
    - Ordine di reso
    - Spesa intestazione
    - Spesa riga

- Processo di acquisto

    - Ordine fornitore
    - Conferma
    - Elenco entrate
    - Entrata prodotti
    - Fattura acquisto
    - Spesa intestazione
    - Spesa riga
    - Nota di accredito
    - Ordine di reso
    - Richiesta di acquisto
    - Spese riga di richiesta di acquisto
    - Richiesta di offerta
    - Spese intestazione richiesta di offerta
    - Spese riga richiesta di offerta

- Processo magazzino

    - Ordine di trasferimento - spedizione
    - Ordine di trasferimento - ricezione
