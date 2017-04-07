---
title: ID registrazione
description: In questo argomento vengono fornite informazioni sull&quot;impostazione e l&quot;utilizzo gli identificativi.
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264824
ms.assetid: e86f0a35-be58-4ef5-b5ab-bcfc495eaa13
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 32cd09975861083b8940368ed53ae16e89bcd748
ms.lasthandoff: 03/31/2017


---

# <a name="registration-ids"></a>ID registrazione

In questo argomento vengono fornite informazioni sull'impostazione e l'utilizzo gli identificativi.

Molti Paesi e stati/regioni con i regolamenti e diversi requisiti di registrazione o i numeri di ID di registrazione. In questo argomento viene fornita una panoramica delle impostazioni e dell'elaborazione dei relativi tipi di supporto di registrazione per le parti in paesi europei diversi paesi. Tutti i paesi sono relativi requisiti del titolare delle funzionalità specifiche del paese varie correlate ai numeri di registrazione fornito dagli uffici diversi di stato. Esempi di numeri di registrazione includono, il Social Security Number (SSN), numero identificativo delle imposte (TIN) e l'ID europea VAT (ID VAT UE). Questa funzionalità consente il framework consolidata per tutti i paesi in tutte le aree che vengono presi in considerazione i requisiti specifici del paese di alcuni paesi europei. Nelle sezioni seguenti viene descritto il flusso di informazioni globale utilizzato per l'impostazione e l'elaborazione degli ID di registrazione.

## <a name="registration-type-creation"></a>Tipo creazione di registrazione
Prima di immettere l'ID di registrazione, è necessario impostare i tipi di registrazione per i diversi tipi di numeri di registrazione che ogni parte è conforme. Va ** Amministrazione organizzazione ** &gt; ** la rubrica globale ** &gt; ** tipi di registrazione ** &gt; ** tipi di registrazione ** pagina per creare e gestire i tipi di registrazione per fornitori, clienti, i lavoratori e persone giuridiche situate in paesi diversi paesi.

|Campo                 |descrizione      |
|------------------------------|----------------------------|                                                                           
| Nome                | Nome del tipo di registrazione. |                                                                           
| descrizione         | Descrizione del tipo di registrazione. |
| Paese      | Identificatore univoco del paese.|
| Ufficio tributario       | L'amministrazione fiscale associato al tipo di registrazione.|
| Limitato a       | Tipo di restrizioni applicabile al tipo di registrazione dell'VAT: Nessuno, persona, organizzazione.|
| Formatta              | Il formato di convalida del tipo di registrazione.|
| Aggiornamento possibile      | Determina se il numero di registrazione per il tipo di registrazione può essere aggiornato dopo immesso.|
| Univoco              | Determina se il numero di registrazione per il tipo di registrazione è univoco. |
| Principale per paese | Se una parte associata al paese di uno o più indirizzi in particolare e l'ID di registrazione è valida per tutti gli indirizzi, è necessario definire un indirizzo come primario per il paese. È possibile registrare solo un ID come primaria. Determina se il numero di registrazione può essere specificato solo per primario per l'indirizzo del paese. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Assegnare un tipo di registrazione a una categoria di registrazione
Categoria di registrazione è identificatore di registrazione paese approvato per l'utilizzo in particolare il paese dell'imposta, dipartimento HM e altri scopi. Questa categoria definisce le regole di convalida di identificazione specifico di registrazione (cifre di controllo vengono e così via.) e di identificazione di registrazione importazioni nei report. Utilizzare la pagina ** Amministrazione organizzazione ** &gt; ** rubrica globale ** &gt; ** tipi di registrazione ** &gt; ** categorie di registrazione ** assegnare il tipo di registrazione determinato paese alla categoria di supporto di registrazione.

| Campo            | descrizione|
|-----------------------|----------------|
| Tipo di registrazione     | Tipo in particolare paese di registrazione.|
| Limitato a         | Tipo di restrizioni applicabile al tipo di registrazione dell'VAT: Nessuno, persona, organizzazione.|
| Categoria di registrazione | Identificatore univoco di registrazione approvato da utilizzare nel paese. Elenco completo del supporto delle categorie di AX7.1 è seguito. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Immettere l'ID di registrazione per i record della Rubrica globale
La Rubrica globale (GAB) in Microsoft Dynamics 365 per le operazioni sono contenute informazioni sull'indirizzo unificate per clienti, fornitori, contatti, relazioni commerciali e le persone giuridiche. Per ulteriori informazioni, vedere [] panoramica della Rubrica globale (/dynamics365/operations/organization-administration/overview-global-address-book). I record di parti che vengono archiviati nella Rubrica globale possono contenere uno o più record di indirizzo. Gli indirizzi vengono utilizzati per scopi diversi, ad esempio la fatturazione o la consegna. È possibile impostare ID di registrazione per informazioni sull'indirizzo per clienti, fornitori, dipendenti e le persone giuridiche. Individuare la parte (persona giuridica, il fornitore, cliente, lavoratore) che il record per il quale si desidera immettere l'ID di registro e fare clic su ** identificativi ** nei moduli correlati per parti, persona giuridica, il fornitore, il cliente, lavoratore per aprire ** gestire gli indirizzi ** la pagina. ** Registrazione VAT ** nella scheda, quindi aggiungere ** ** quindi immettere le seguenti informazioni sull'identificazione di registrazione.

|Campo                |descrizione                                                |
|---------------------|-----------------------------------------------------------|
| Tipo di registrazione   | La registrazione nel paese selezionato.     |
| Numero di registrazione | Identificazione di registrazione della parte.                                |
| descrizione         | Descrizione del numero di registrazione.               |
| Sezione             | Ulteriori informazioni sul numero di registrazione. |
| Agenzia emittente      | Ufficio che ha emesso il numero di registrazione.        |
| Data di emissione         | Data emessa per il numero di registrazione.              |
| Valido           | Data di validità del numero di registrazione.           |
| Scadenza          | Data di fine del numero di registrazione.          |

> [!NOTE]
> Partita VAT della persona giuridica, il fornitore, a un gruppo l'ID di registrazione relativo all'ID VAT e immesso per la parte.

## <a name="search-for-records-by-registration-id"></a>Ricerca dei record in base all'ID di registrazione
La ricerca dei record di parti in base a un ID di registrazione è disponibile nei moduli correlati per parti, la persona giuridica, il fornitore, al cliente e sul lavoratore. Fare clic su ** ricerca di identificazione di registrazione ** per aprire ** criteri di ricerca di identificazione di registrazione ** la pagina. Consente di specificare i criteri di ricerca e fare clic su ** Trova **. Nel sistema vengono visualizzati i record selezionati dalla rubrica globale e i tipi corrispondenti di record parte.

## <a name="supported-registration-categories"></a>Categorie di supporto di registrazione
Nella seguente tabella sono elencati la registrazione supportati in Dynamics 365 per le operazioni. Se si ha dimestichezza con Microsoft Dynamics AX 2012 emesse per gli identificativi questa tabella, anche mappare i campi a Dynamics 365 per le categorie di registrazione delle operazioni.

| Dynamics 365 per la categoria di registrazione di operazioni         |Paese  | Termine/Campo di Dynamics AX 2012|
|---------------------------------------------------------------|---------------------|---------------------------------|
| ID IVA                                                        | Tutti i paesi dell'Unione Europea (EU)|  Partita VAT (tipo legislativo identificazione dell'IMPOSTA in AX2012 R3)|
| ID azienda (COID)                                          | La repubblica Ceca Estonia Ungheria Lettonia Lituania Polonia Svizzera Belgio | Numero di registrazione di numero impresa (EnterpriseNumber) (numero di registrazione di RegNum\_W) (numero di registrazione di RegNum\_W) (numero di registrazione di RegNum\_W) (numero di registrazione del codice Enterprise di RegNum\_W) (EnterpriseCode) (n di RegNum\_W) (tipo legislativo n in AX2012 R3) |
| ID filiale                                                     | Belgio            | Numero della filiale (BranchNumber)|
| Značka di Spisová (numero di registrazione, pubblicante agenzia, Sezione) | Repubblica Ceca     | Numero di inserimento (CommercialRegisterInsetNumber) ha ricoperto la sezione di registro commerciale (CommercialRegister) del registro commerciale (CommercialRegisterSection)|
| ID cliente per dogana                                           | Finlandia | Numero cliente della dogana (CustomsCustomerNumber\_FI)|
| INN                                                           | Federazione russa| INN (tipo legislativo in INN AX2012 R3)|
| RRC                                                           | Federazione russa| RRC (tipo legislativo in RRC AX2012 R3)|
| OKDP                                                          | Federazione russa| OKDP (tipo legislativo in OKDP AX2012 R3)|
| OKPO                                                          | Federazione russa| OKPO (tipo legislativo in OKPO AX2012 R3)|
| RCOAD                                                         | Federazione russa| RCOAD (tipo legislativo in RCOAD AX2012 R3)|
| OGRN                                                          | Federazione russa| OGRN (tipo legislativo in OGRN AX2012 R3) |
| SNILS                                                         | Federazione russa| SNILS (tipo legislativo in SNILS AX2012 R3)|
| CIFTS                                                         | Federazione russa| CIFTS (tipo legislativo in CIFTS AX2012 R3)|

Per ulteriori informazioni sull'ID di registrazione per l'elaborazione, inclusi i prerequisiti necessari, vedere le seguenti registrazioni di attività per l'identificazione dell'VAT per servizi (LCS) del ciclo di vita:

-   Impostare l'ID IVA
-   Registrazione di identificazione dell'VAT del fornitore
-    Ricerca della parte utilizzando l'ID IVA



