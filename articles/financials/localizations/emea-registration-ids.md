---
title: ID registrazione
description: Questo argomento fornisce informazioni sull'impostazione e l'uso degli ID registrazione.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264824
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e85e1ef9bb27e3644264c898feb3a484c5b3ec3f
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="registration-ids"></a>ID registrazione

[!include[banner](../includes/banner.md)]


Questo argomento fornisce informazioni sull'impostazione e l'uso degli ID registrazione.

Molti paesi e regioni prevedono normative e requisiti diversi per la registrazione delle partite IVA o ID registrazione. In questo argomento viene fornita una panoramica delle impostazioni e dell'elaborazione dei tipi di registrazione supportati per le parti in diversi paesi europei. Tutti i paesi hanno propri requisiti per supportare varie funzionalità specifiche di paese correlati ai numeri di registrazione forniti dai diversi uffici di stato. Esempi di numeri di registrazione includono il Social Security Number (SSN), numero identificativo delle imposte (TIN) e la partita IVA europea (ID IVA UE). Questa funzionalità offre un framework unificato per tutti i paesi in tutte le regioni prendendo in considerazione i requisiti specifici di paese di alcuni paesi europei. Nelle sezioni seguenti viene descritto il flusso generale di informazioni utilizzato per impostare ed elaborare gli ID registrazione.

## <a name="registration-type-creation"></a>Creazioen del tipo di registrazione
Prima di immettere l'ID registrazione, è necessario impostare i tipi di registrazione per i diversi tipi di numeri di registrazione a cui ogni parte è soggetta. Andare a **Amministrazione organizzazione** &gt; **Rubrica globale** &gt; **Tipi di registrazione** &gt; pagina **Tipi di registrazione** per creare e gestire i tipi di registrazione per fornitori, clienti, lavoratori e persone giuridiche situate in paesi diversi.

|Campo                 |descrizione      |
|------------------------------|----------------------------|                                                                           
| Nome                | Il nome del tipo di registrazione. |                                                                           
| descrizione         | Descrizione del tipo di registrazione. |
| Paese      | Identificatore univoco per il paese.|
| Ufficio tributario       | Ufficio tributario associato al tipo di registrazione.|
| Limitato a       | Tipo di restrizione applicabile al tipo di registrazione fiscale: Nessuno, Persona, Organizzazione.|
| Formatta              | Formato di convalida per tipo di registrazione.|
| Aggiornamento possibile      | Definisce se il numero di registrazione per il tipo di registrazione può essere aggiornato dopo l'immissione.|
| Univoco              | Definisce se il numero di registrazione per il tipo di registrazione è univoco. |
| Principale per paese | Se una parte è associata a uno o più indirizzi in un particolare paese e l'ID di registrazione è valido per tutti gli indirizzi, è necessario definire un indirizzo come primario per il paese. È possibile registrare solo un ID come primario. Determina se il numero di registrazione può essere specificato solo per l'indirizzo del paese primario. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Assegnare un tipo di registrazione a una categoria di registrazione
La categoria di registrazione è l'identificatore di registrazione del paese/regione approvato per l'utilizzo in un particolare paese/regione a fini di imposte doganali e di altro tipo. Questa categoria definisce le regole di convalida di un ID di registrazione specifico (incluse cifre di controllo e così via) e l'ID di registrazione di inclusione in diversi report. Utilizzare la pagina **Amministrazione organizzazione** &gt; **Rubrica globale** &gt; **Tipi di registrazione** &gt; **Categorie di registrazione** per assegnare il tipo di registrazione di un determinato paese alla categoria di registrazione supportata.

| Campo            | descrizione|
|-----------------------|----------------|
| Tipo di registrazione     | IL tipo di registrazione in un particolare paese/regione.|
| Limitato a         | Tipo di restrizione applicabile al tipo di registrazione fiscale: Nessuno, Persona, Organizzazione.|
| Categoria di registrazione | Identificatore univoco di registrazione approvato per l'uso nel paese. Di seguito l'elenco completo delle categorie supportate in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Immettere gli ID di registrazione per i record della Rubrica globale

La Rubrica globale in Microsoft Finance and Operations contiene informazioni consolidate sugli indirizzi di clienti, fornitori, contatti, relazioni commerciali e le persone giuridiche. Per ulteriori informazioni, vedere  [Panoramica della rubrica globale](../../fin-and-ops/organization-administration/overview-global-address-book.md). I record delle parti che vengono archiviati nella rubrica globale possono contenere uno o più record di indirizzo. Gli indirizzi vengono utilizzati per scopi diversi, ad esempio la fatturazione o la consegna. È possibile impostare gli ID di registrazione per informazioni sull'indirizzo per clienti, fornitori, lavoratori e persone giuridiche. Individuare la parte (persona giuridica, fornitore, cliente, lavoratore) per cui si desidera immettere l'ID di registro e fare clic su **D registrazione** nei moduli correlati per la parte, la persona giuridica, il fornitore, il cliente, il lavoratore per aprire la pagina **Gestisci indirizzi** . Nella scheda **Registrazione fiscale** fare clic su  **Aggiungi** quindi immettere le seguenti informazioni sull'ID registrazione.


|Campo                |descrizione                                                |
|---------------------|-----------------------------------------------------------|
| Tipo di registrazione   | IL tipo di registrazione nel paese/regione selezionato.     |
| Numero di registrazione | ID registrazione della parte.                                |
| descrizione         | Descrizione del numero di registrazione.               |
| Sezione             | Informazioni aggiuntive sul numero di registrazione. |
| Agenzia emittente      | Ufficio tributario che emette il numero di registrazione.        |
| Data di emissione         | Data di emissione del numero di registrazione.              |
| Valido           | Data di validità del numero di registrazione.           |
| Scadenza          | Data di scadenza del numero di registrazione.          |

> [!NOTE]
> Il numero di partita IVA della persona giuridica, fornitore, cliente può essere selezionato dagli ID registrazione correlati all'ID IVA e immesso per la parte.

## <a name="search-for-records-by-registration-id"></a>Cercare record in base all'ID registrazione
La ricerca di record di parti in base a un ID registrazione è disponibile nei moduli correlati alla parte, persona giuridica, il fornitore, cliente e lavoratore. Fare clic su **Ricerca ID registrazione**  per aprire la pagina **Criteri di ricerca ID registrazione**. Specificare i criteri di ricerca e fare clic su **Trova**. Nel sistema vengono visualizzati i record selezionati dalla rubrica globale e i tipi associati del record della parte.

## <a name="supported-registration-categories"></a>Categorie di registrazione supportate
Nella seguente tabella sono elencati i tipi di registrazione supportati in Finance and Operations. Se si ha dimestichezza con i campi di Microsoft Dynamics AX 2012 per gli ID registrazione, questa tabella mappa anche quei campi alle categorie di registrazione di Finance and Operations.

| Categoria di registrazione di Finance and Operations         |Paese  | Termine/campo di Dynamics AX 2012|
|---------------------------------------------------------------|---------------------|---------------------------------|
| ID IVA                                                        | Tutti i paesi dell'Unione Europea (EU)|  Partita IVA (Tipo legislativo ID imposta in AX 2012 R3)|
| ID azienda (COID)                                          | Belgio, Repubblica Ceca, Estonia, Ungheria, Lettonia, Lituania, Polonia, Svizzera | Numero impresa (EnterpriseNumber) Numero di registrazione (RegNum\_W) Numero di registrazione (RegNum\_W) Numero di registrazione (RegNum\_W) Numero di registrazione (RegNum\_W) Codice impresa (EnterpriseCode) Numero di registrazione(RegNum\_W) UID (Tipo legislativo UID in AX 2012 R3) |
| ID filiale                                                     | Belgio            | Codice della filiale (BranchNumber)|
| Spisová značka (Numero di registrazione, Agenzia emittente, Sezione) | Repubblica Ceca     | Numero paragrafo (CommercialRegisterInsetNumber) Mantenuto nel registro commerciale (CommercialRegister) Sezione del registro commerciale (CommercialRegisterSection)|
| ID cliente per dogana                                           | Finlandia | Numero cliente per dogana (CustomsCustomerNumber\_FI)|
| INN                                                           | Federazione russa| INN (Tipo legislativo INN in AX 2012 R3)|
| RRC                                                           | Federazione russa| RRC (Tipo legislativo RRC in AX 2012 R3)|
| OKDP                                                          | Federazione russa| OKDP (Tipo legislativo OKDP in AX 2012 R3)|
| OKPO                                                          | Federazione russa| OKPO (Tipo legislativo OKPO in AX 2012 R3)|
| RCOAD                                                         | Federazione russa| RCOAD (Tipo legislativo RCOAD in AX 2012 R3)|
| OGRN                                                          | Federazione russa| OGRN (Tipo legislativo OGRN in AX 2012 R3) |
| SNILS                                                         | Federazione russa| SNILS (tipo legislativo SNILS in AX 2012 R3)|
| CIFTS                                                         | Federazione russa| CIFTS (tipo legislativo CIFTS in AX 2012 R3)|

Per ulteriori informazioni sull'elaborazione degli ID registrazione, inclusi i prerequisiti necessari, vedere le seguenti registrazioni attività per l'ID IVA in Lifecycle Services (LCS):

-   Impostare l'ID IVA
-   Registrazione dell'ID IVA fornitore
-    Ricerca della parte utilizzando l'ID IVA





