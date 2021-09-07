---
title: Introduzione a Calcolo imposte
description: In questo argomento viene illustrato come configurare Calcolo imposte.
author: wangchen
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1ddbb22d4f7c6108ca93b415276c53794b5450dd
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2021
ms.locfileid: "7394514"
---
# <a name="get-started-with-tax-calculation"></a>Introduzione al calcolo delle imposte

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Questo argomento fornisce informazioni su come iniziare a usare Calcolo imposte. Ti guida attraverso i passi di configurazione in Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS), Dynamics 365 Finance, e Dynamics 365 Supply Chain Management. Esamina quindi il processo comune per l'utilizzo della funzionalità Calcolo imposte nelle transazioni di Finance e Supply Chain Management.

La configurazione consiste in quattro passaggi principali:

1. In LCS, installate l'add-in Calcolo imposta.
2. In RCS, configurazione della funzionalità Calcolo imposte. Questa configurazione non è specifica di una persona giuridica. Può essere condivisa tra le persone giuridiche in Finance and Supply Chain Management.
3. In Finance and Supply Chain Management, configurazione dei parametri di Calcolo imposte in base alla persona giuridica.
4. In Finance and Supply Chain Management, creazione delle transazioni come ordini di vendita e utilizzo di Calcolo imposte per determinare e calcolare le imposte.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter completare le procedure in questo argomento, i prerequisiti devono essere presenti per ogni tipo di ambiente.

### <a name="for-a-production-environment"></a>Per un ambiente di produzione

Per un ambiente di produzione, devono essere soddisfatti i seguenti prerequisiti:

- Devi avere accesso al tuo account LCS e devi avere un progetto LCS distribuito che ha un ambiente Tier 2 o superiore che esegue Dynamics 365 versione 10.0.21 o successiva.
- Devi creare un ambiente RCS per la tua organizzazione e devi avere accesso al tuo account. Per maggiori informazioni su come creare un ambiente RCS, vedere [Panoramica di Regulatory Configuration Service](rcs-overview.md).
- Le seguenti funzioni devono essere attivate nell'area di lavoro di **gestione delle funzioni** del tuo ambiente di Finance o Supply Chain Management distribuito, in base alle tue esigenze aziendali:

    - Calcolo imposte
    - Supporta più numeri di partita IVA
    - Imposta in ordine di trasferimento
    - Trasferimento elenco vendite UE solo in base alle transazioni di imposta
    - Segnalazione Intrastat per codice fiscale multiplo
    - Segnalazione dell'elenco delle vendite UE per ID fiscale multiplo
    - Dichiarazione dell'imposta sulle vendite per codice fiscale multiplo

- Le seguenti caratteristiche devono essere attivate nell'area di lavoro di **gestione delle caratteristiche** del tuo ambiente RCS distribuito.

    - Funzionalità di globalizzazione

### <a name="for-a-test-environment-public-preview"></a>Per un ambiente di prova (Anteprima pubblica)

Per un ambiente di prova, devono essere soddisfatti i seguenti prerequisiti:

- Devi avere accesso al tuo account LCS e devi avere un progetto LCS distribuito che ha un ambiente Tier 2 o superiore che esegue Dynamics 365 versione 10.0.18 con KB4616360, o una versione successiva.
- Devi creare un ambiente RCS per la tua organizzazione e devi avere accesso al tuo account. Per maggiori informazioni su come creare un ambiente RCS, vedere [Panoramica di Regulatory Configuration Service](rcs-overview.md).
- Dovete contattare Microsoft, inviando un'e-mail a <taxcalc@microsoft.com>, per abilitare il flighting nel vostro ambiente Finance o Supply Chain Management distribuito.
- Le seguenti funzioni devono essere attivate nell'area di lavoro di **gestione delle funzioni** del tuo ambiente di Finance o Supply Chain Management distribuito, in base alle tue esigenze aziendali:

    - Calcolo imposte
    - Supporta più numeri di partita IVA
    - Imposta in ordine di trasferimento
    - Trasferimento elenco vendite UE solo in base alle transazioni di imposta
    - Segnalazione Intrastat per codice fiscale multiplo
    - Segnalazione dell'elenco delle vendite UE per ID fiscale multiplo
    - Dichiarazione dell'imposta sulle vendite per codice fiscale multiplo

- Le seguenti caratteristiche devono essere attivate nell'area di lavoro di **gestione delle caratteristiche** del tuo ambiente RCS distribuito.

    - Funzionalità di globalizzazione

## <a name="set-up-tax-calculation-in-lcs"></a>Configurare Calcolo imposte in LCS

1. Accedi a [LCS](https://lcs.dynamics.com)
2. Completa la configurazione per l'integrazione di Microsoft Power Platform. Per ulteriori informazioni, vedi [Panoramica dei componenti aggiuntivi](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Seleziona uno dei tuoi ambienti distribuiti e poi seleziona **Installa un nuovo componente aggiuntivo**.
4. Selezionare **Calcolo delle tasse**.
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
8. Seleziona la versione di configurazione fiscale corretta, in base alla tua versione Finance, e poi seleziona **Importa**.

    | Versione di rilascio | Configurazione fiscale                       | Mapping modello                   |
    | --------------- | --------------------------------------- | ------------------------------- |
    | 10.0.18         | Configurazione fiscale - Europa 30.12.82     |                                 |
    | 10.0.19         | Configurazione del calcolo delle tasse 36.38.193 |                                 |
    | 10.0.20         | Configurazione del calcolo dell'imposta 40.43.208 |                                 |
    | 10.0.21         | Configurazione del calcolo dell'imposta 40.46.212 | Dataverse Mappatura del modello 40.46.9 |

9. Nell'area di lavoro delle **funzioni di globalizzazione** , selezionare **Funzioni**, selezionare il riquadro **Calcolo delle tasse** e poi selezionare **Aggiungi**.
10. Consente di selezionare uno dei seguenti tipi di funzionalità:

    - **Nuova funzionalità** - Crea una configurazione della funzionalità con contenuto vuoto.
    - **Basata su funzionalità esistente** - Crea una funzionalità da una funzionalità esistente e copia il contenuto dalla configurazione della funzionalità esistente.

11. Immetti un nome e una descrizione per la funzionalità e seleziona **Crea funzionalità**.

    Dopo la creazione della funzionalità, ne viene creata automaticamente una versione bozza. Puoi selezionare **Ottieni questa versione** per ribasare la versione di bozza su qualsiasi versione completata.

12. Seleziona la versione bozza della funzionalità, quindi seleziona **Modifica**. La pagina **Configurazione di Calcolo imposte** è compilata.
13. Seleziona **Versione configurazione**. Dovresti vedere la versione della configurazione che hai importato nel passaggio 8.

    Microsoft fornisce una configurazione fiscale predefinita per il calcolo delle tasse. Questa configurazione copre la maggior parte dei requisiti per i comportamenti di Calcolo imposte. Sarà aggiornata in base ai feedback del mercato. Se è necessario estendere la configurazione per soddisfare requisiti specifici, vedi [Come creare l'estensione nel servizio per le imposte](./tax-service-add-data-fields-tax-integration-by-extension.md) per informazioni su come generare e selezionare la propria configurazione fiscale.

14. Dopo aver selezionato **Versione configurazione**, appaiono diverse schede aggiuntive. Segui l'ordine che è mostrato qui per completare la configurazione della scheda obbligatoria.

    **Impostazione obbligatoria**

    - **Codici fiscali** - Mantenere i dati principali per i codici fiscali. Tutti i codici fiscali creati in questa scheda sono automaticamente sincronizzati con Finance quando si attiva la versione corrente.
    - **Gruppo fiscale** - Definisci i dati anagrafici del gruppo fiscale e i codici fiscali sotto il gruppo.
    - **Gruppo d'imposta** dell'articolo - Definisci i dati anagrafici del gruppo d'imposta dell'articolo e i codici d'imposta sotto il gruppo.

    **Impostazione facoltativa**

    - **Applicabilità del gruppo** fiscale - Definire una matrice che determina il gruppo fiscale. Se nessuna regola di applicabilità in questa matrice corrisponde al documento imponibile da Dynamics 365, Calcolo imposta usa il valore predefinito sulla riga del documento imponibile.
    - **Applicabilità del gruppo** d'imposta dell'articolo - Definisci una matrice che determina il gruppo d'imposta dell'articolo. Se nessuna regola di applicabilità in questa matrice corrisponde al documento imponibile da Dynamics 365, Calcolo imposta usa il valore predefinito sulla riga del documento imponibile.
    - **Applicabilità del numero di registrazione fiscale del cliente** - Se hai più numeri di registrazione fiscale per un cliente, Calcolo delle imposte può determinare automaticamente il numero di registrazione fiscale corretto. Nella matrice di questa scheda, definisci le regole che dovrebbero essere usate per fare la determinazione. In caso contrario, Finance e Supply Chain Management continueranno a utilizzare la partita IVA predefinita nei documenti tassabili per le transazioni di vendita.
    - **Applicabilità del numero di registrazione fiscale del venditore** - Se hai più numeri di registrazione fiscale per un venditore, Calcolo imposta può determinare automaticamente il corretto numero di registrazione fiscale. Nella matrice di questa scheda, definisci le regole che dovrebbero essere usate per fare la determinazione. In caso contrario, Finance e Supply Chain Management continueranno a utilizzare la partita IVA predefinita nei documenti tassabili per le transazioni di acquisto.
    - **Applicabilità del codice elenco** - Determina automaticamente il valore del campo **Codice elenco** attraverso regole più flessibili e configurabili. Nella matrice di questa scheda, definisci le regole che dovrebbero essere usate per fare la determinazione. In caso contrario, Finance e Supply Chain Management continueranno a utilizzare il codice sui documenti tassabili.

14. Nella scheda **Codici imposta** seleziona **Aggiungi** e inserisci il codice imposta e una descrizione.
15. Seleziona **Componente fiscale**. Il componente fiscale è un gruppo di metodi definiti nella versione precedente della configurazione fiscale selezionata. Sono disponibili i seguenti componenti fiscali:

    - Per importo netto
    - Per importo lordo
    - Per quantità
    - Per margine
    - Imposta sull'imposta

16. Selezionare **Salva**. Diventano disponibili più campi, in base al componente fiscale selezionato.
17. Utilizza le seguenti opzioni per identificare la natura del codice imposta:

    - È esente
    - È la tassa sull'uso
    - Reverse charge
    - Escludere dal calcolo dell'importo di base

    Per uno scenario di imposta sull'uso, imposta un singolo codice fiscale che abbia un'aliquota positiva e contrassegnalo come **Imposta sull'uso**.

    Per uno scenario di reverse charge, configura due codici imposta, uno dei quali ha un'aliquota fiscale positiva e l'altro ha un'aliquota fiscale negativa ma lo stesso valore dell'aliquota. Contrassegna il codice imposta negativo come **Reverse charge**. Per ulteriori informazioni sulla soluzione di reverse charge in Finance, vedi [Meccanismo di reverse charge per lo schema IVA/GST](emea-reverse-charge.md).

    Per alcuni tipi di imposta che dovrebbero essere esclusi dal calcolo dell'importo di base dell'imposta per le transazioni con prezzo incluso (per esempio, il dazio doganale in alcuni paesi o regioni), seleziona la casella **Escludi dal calcolo dell'importo di base** . Per maggiori informazioni su questo parametro, vedi [Calcolo delle tasse in aggiunta al prezzo quando i prezzi includono le tasse è abilitato](global-exclude-from-tax-base-amount-calculation.md).

    Mantieni le aliquote fiscali e i limiti di importo delle imposte per questo codice imposta.

18. Ripeti i passaggi dal 14 al 17 per aggiungere tutti gli altri codici imposta necessari.
19. Nella scheda **Gruppo d'imposta** , seleziona la colonna **Gruppo d'imposta** , aggiungila alla matrice come condizione d'ingresso e poi aggiungi delle righe per mantenere i dati anagrafici del gruppo d'imposta.

    Ecco un esempio.

    | Gruppo di imposte    | Codici imposta           |
    | ------------ | ------------------- |
    | DEU_Domestic | DEU_VAT19; DEU_VAT7 |
    | DEU_EU       | DEU_Esente          |
    | BEL_Domestic | BEL_VAT21; BEL_VAT6 |
    | BEL_EU       | BEL_Exempt          |

20. Nella scheda **Gruppo d'imposta** degli articoli, seleziona la colonna **Gruppo d'imposta degli articoli** , aggiungila alla matrice come condizione d'ingresso e poi aggiungi delle righe per mantenere i dati anagrafici del gruppo d'imposta degli articoli.

    Ecco un esempio.

    | Gruppo d'imposta dell'articolo | Codici imposta                                    |
    | -------------- | -------------------------------------------- |
    | Completo           | DEU_VAT19; BEL_VAT21; DEU_Exempt; BEL_Exempt |
    | Ridotta        | DEU_VAT7; BEL_VAT6; DEU_Exempt; BEL_Exempt   |

21. Nella scheda **Applicabilità del gruppo fiscale** , seleziona le colonne che sono necessarie per determinare il gruppo fiscale corretto e poi seleziona **Aggiungi**. Immetti o seleziona i valori per ciascuna colonna. Il campo del **gruppo fiscale** sarà l'output di questa matrice. Se questa scheda non è configurata, verrà utilizzato il gruppo di imposte sulle vendite sulla linea della transazione.

    Ecco un esempio.

    | Processo aziendale | Spedisci da | Spedisci a | Gruppo di imposte    |
    | ---------------- | --------- | ------- | ------------ |
    | Vendite            | DEU       | DEU     | DEU_Domestic |
    | Vendite            | DEU       | FRA     | DEU_EU       |
    | Vendite            | BEL       | BEL     | BEL_Domestic |
    | Vendite            | BEL       | FRA     | BEL_EU       |

22. Nella scheda **Applicabilità del gruppo d'imposta dell'articolo** , seleziona le colonne che sono necessarie per determinare il codice d'imposta corretto e poi seleziona **Aggiungi**. Immetti o seleziona i valori per ciascuna colonna. Il campo del **gruppo fiscale dell'articolo** sarà l'output di questa matrice. Se questa scheda non è configurata, verrà utilizzato il gruppo di imposte sulle vendite dell'articolo sulla linea della transazione.

    Ecco un esempio.

    | Codice articolo | Gruppo d'imposta dell'articolo |
    | --------- | -------------- |
    | D0001     | Completo           |
    | D0003     | Ridotta        |

    Per maggiori informazioni su come i codici fiscali sono determinati in Calcolo imposta, vedi [Logica di determinazione dei gruppi di imposte sulle vendite e dei gruppi di imposte sulle vendite degli articoli](global-sales-tax-group-determination.md).

23. Impostare l'applicabilità dei numeri di registrazione fiscale dei clienti, dei numeri di registrazione fiscale dei fornitori e dei codici elenco in base alle esigenze aziendali.
24. Selezionare **Salva**, quindi chiudere la pagina.
25. Selezionare **Cambia stato** \> **Completato**. Dopo che lo stato è cambiato in **Completato**, la versione non può più essere modificata.
26. Seleziona **Cambia stato** \> **Pubblica**. Questa versione della configurazione della funzione fiscale verrà inviata al repository globale e sarà visibile a ogni persona giuridica in Finance.

## <a name="set-up-tax-calculation-in-dynamics-365"></a>Impostare il calcolo delle tasse in Dynamics 365

Dopo aver completato la configurazione in RCS, avrete una versione pubblicata della funzione fiscale. Segui questi passaggi per configurare Calcolo imposte in Finance.

La configurazione in questa sezione viene eseguita dalla persona giuridica. Devi configurarla per ogni persona giuridica per cui vuoi abilitare Calcolo imposte in Finance.

1. In Finance, vai a **Imposta** \> **Impostazione** \> **Configurazione imposta** \> **Parametri calcolo imposta**.
2. Nella scheda **Generale**, impostare i seguenti campi:

    - **Abilita il servizio di calcolo delle tasse** - Seleziona questa casella di controllo per abilitare il calcolo delle tasse per la persona giuridica. Se non è abilitato per la persona giuridica corrente, la persona giuridica continuerà a utilizzare il motore fiscale esistente per determinare e calcolare le imposte.
    - **Configurazione funzionalità** - Seleziona una configurazione e una versione della funzione fiscale pubblicata per la persona giuridica. Per ulteriori informazioni su come configurare e completare una funzione fiscale pubblicata, vedi la sezione precedente di questo argomento.
    - **Processo aziendale** - Seleziona i processi aziendali da abilitare.

3. Nella scheda **Calcolo** definisci la regola di arrotondamento prevista per la persona giuridica. Per maggiori informazioni sulla logica di arrotondamento, vedere [Regole di arrotondamento del calcolo delle tasse](https://go.microsoft.com/fwlink/?linkid=2166988).
4. Nella scheda **Gestione degli errori** definisci il metodo di gestione degli errori previsti per la persona giuridica. Sono disponibili tre opzioni:

    - Nessuno
    - Avviso
    - Errore

    Puoi impostare un metodo di gestione degli errori per ogni codice di risultato nella sezione **Dettagli** . In alternativa, se alcuni codici di risultato non sono sincronizzati dal servizio di calcolo delle tasse, puoi impostare un metodo predefinito nella sezione **Generale** .

5. Nella scheda **Registrazione IVA multipla** , puoi attivare separatamente la dichiarazione IVA, l'elenco vendite UE e Intrastat per lavorare in uno scenario di registrazioni IVA multiple. Per maggiori informazioni sulle dichiarazioni fiscali per registrazioni multiple dell'IVA, vedi [Dichiarazione per registrazioni multiple dell'IVA](emea-reporting-for-multiple-vat-registrations.md).
6. Salvare la configurazione e ripetere i passi precedenti per ogni entità legale aggiuntiva. Quando una nuova versione è pubblicata, e vuoi che sia applicata, imposta il campo **Impostazione funzionalità** nella scheda **Generale** della pagina **Parametri calcolo imposta** (vedi passo 2).

## <a name="transaction-processing"></a>Elaborazione delle transazioni

Dopo aver completato tutte le procedure di configurazione, puoi usare Calcolo imposta per determinare e calcolare le tasse in Finance. I passaggi per elaborare le transazioni rimangono gli stessi. Le seguenti transazioni sono supportate nella versione Finance 10.0.21:

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
