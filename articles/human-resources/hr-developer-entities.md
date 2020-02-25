---
title: Entità di Common Data Service
description: Microsoft Dynamics 365 Human Resources utilizza Common Data Service per abilitare scenari di estendibilità e integrazione.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85dd95e8209fff28f214986f7960372db200351b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009591"
---
# <a name="common-data-service-entities"></a>Entità di Common Data Service

Microsoft Dynamics 365 Human Resources utilizza Common Data Service per abilitare scenari di estendibilità e integrazione.

Per ulteriori informazioni su Common Data Service, vedere [Che cos'è Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Le seguenti entità di Human Resources sono disponibili in Common Data Service.

## <a name="benefit-entities"></a>Entità Benefit

**Frequenza di calcolo benefit**

| **Campi**        | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-------------------|---------------|--------------|----------------|
| Descrizione       | Text          |              | X              |
| Controllo frequenza | Set di opzioni    | X            | X              |
| Immutabile      | Due opzioni   |              | X              |
| Nome              | Text          | X            | X              |


**Coefficiente di calcolo benefit**

| **Campi**  | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-------------|---------------|--------------|----------------|
| Descrizione | Text          |              | X              |
| Nome        | Text          | X            | X              |
| Tipo di livello    | Set di opzioni    | X            | X              |


**Dettagli dei coefficienti di calcolo benefit**

| **Campi**                             | **Tipo di dati**  | **Obbligatorio** | **Ricercabile** |
|----------------------------------------|----------------|--------------|----------------|
| Numero dettagli dei coefficienti di calcolo benefit | Text           | X            | X              |
| ID percentuale di calcolo                    | Ricerca         | X            | X              |
| Metodo di contribuzione                    | Set di opzioni     | X            | X              |
| Valido                              | Solo data      | X            | X              |
| Contributo del datore di lavoro                  | Numero decimale |              | X              |
| Scadenza                             | Solo data      | X            | X              |
| Detrazione lavoratore                        | Numero decimale |              | X              |


**Tipo di benefit**

| **Campi**           | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|----------------------|---------------|--------------|----------------|
| Iscrizione simultanea | Set di opzioni    |              | X              |
| Descrizione          | Text          |              | X              |
| Nome                 | Text          | X            | X              |
| Categoria retributiva      | Set di opzioni    |              | X              |


**Piano di benefit**

| **Campi**                               | **Tipo di dati**  | **Obbligatorio** | **Ricercabile** |
|------------------------------------------|----------------|--------------|----------------|
| Metodo di limite arretrato                      | Set di opzioni     |              | X              |
| Tipo di benefit                             | Ricerca         | X            | X              |
| Metodo limite di contribuzione                | Set di opzioni     |              | X              |
| Metodo di contribuzione                      | Set di opzioni     |              | X              |
| Valuta                                 | Ricerca         |              | X              |
| Priorità detrazione                       | Numero intero   |              | X              |
| Importo limiti di contribuzioni predefiniti        | Valuta       |              | X              |
| Importo limiti di contribuzione predefiniti (base) | Valuta       |              | X              |
| Periodo limiti di contribuzione predefiniti        | Set di opzioni     |              | X              |
| Importo limite di detrazione predefiniti           | Valuta       |              | X              |
| Importo limiti di detrazione predefiniti (base)    | Valuta       |              | X              |
| Periodo limiti di detrazione predefiniti           | Set di opzioni     |              | X              |
| Descrizione                              | Text           |              | X              |
| Tasso di cambio                            | Numero decimale |              | X              |
| Esecuzione aggiuntiva della retribuzione                | Due opzioni    |              | X              |
| Affordable Care Act dichiarabile        | Due opzioni    |              | X              |
| Generato da arretrati                      | Due opzioni    |              | X              |
| Calcolo lordo                              | Due opzioni    |              | X              |
| Primario                               | Due opzioni    |              | X              |
| Nome                                     | Text           | X            | X              |
| Impatto retribuzioni                           | Set di opzioni     |              | X              |
| Tipo di pensionamento                          | Set di opzioni     |              | X              |


**Entità Impiego**

| **Campi**                     | **Tipo di dati**  | **Obbligatorio** | **Ricercabile** |
|--------------------------------|----------------|--------------|----------------|
| Data di inizio rettificata del lavoratore     | Data e ora  |              | X              |
| Società                        | Ricerca         | X            | X              |
| Importo unità di preavviso datore di lavoro | Numero decimale |              | X              |
| Unità di preavviso datore di lavoratore        | Set di opzioni     |              | X              |
| Data di fine impiego            | Data e ora  |              | X              |
| Numero di impieghi              | Text           | X            | X              |
| Data di inizio impiego          | Data e ora  |              | X              |
| Ultimo giorno di lavoro              | Data e ora  |              | X              |
| Data transizione                | Data e ora  |              | X              |
| Data di inizio validità                     | Data e ora  | X            | X              |
| Data di fine validità                       | Data e ora  |              | X              |
| Lavoro                         | Ricerca         | X            | X              |
| Periodo di preavviso lavoratore           | Numero decimale |              | X              |
| Data di inizio del lavoratore             | Data e ora  |              | X              |
| Tipo di lavoratore                    | Set di opzioni     | X            | X              |
| Unità di preavviso lavoratore          | Set di opzioni     |              | X              |

## <a name="worker-entities"></a>Persone giuridiche - Lavoratore

**Origine etnica**

| **Campi**         | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|--------------------|---------------|--------------|----------------|
| Descrizione        | Text          |              | X              |
| Nome origine etnica | Text          | X            | X              |


**Lingua**

| **Campi**    | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|---------------|---------------|--------------|----------------|
| Descrizione   | Text          |              | X              |
| Nome lingua | Text          | X            | X              |


**Stato veterano**

| **Campi**           | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|----------------------|---------------|--------------|----------------|
| Descrizione          | Text          |              | X              |
| Veterano protetto | Due opzioni    |              | X              |
| Nome lingua        | Text          | X            | X              |


**Lavoro**

| **Campi**                | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|---------------------------|---------------|--------------|----------------|
| Data di nascita                 | Solo data     |              | X              |
| Descrizione               | Text          |              | X              |
| Indirizzo di posta elettronica 1           | Indirizzo di posta elettronica         |              | X              |
| Indirizzo di posta elettronica 2           | Indirizzo di posta elettronica         |              | X              |
| Identità Facebook         | Text          |              | X              |
| Nome                | Text          |              | X              |
| Nome completo                 | Text          |              | X              |
| Genere                    | Set di opzioni    |              | X              |
| Generazione                | Text          |              | X              |
| Contatto tramite posta elettronica consentito  | Due opzioni   |              | X              |
| Contatto tramite telefono consentito  | Due opzioni   |              | X              |
| Cognome                 | Text          |              | X              |
| Identità LinkedIn         | Text          |              | X              |
| Responsabile                   | Ricerca        |              | X              |
| Secondo nome               | Text          |              | X              |
| Cellulare              | Telefono         |              | X              |
| Identificatore di Office Graph   | Text          |              | X              |
| Indirizzo di posta elettronica principale     | Indirizzo di posta elettronica         |              | X              |
| Telefono principale         | Telefono         |              | X              |
| Professione                | Text          |              | X              |
| Social Network 1          | Set di opzioni    |              | X              |
| Social Network 2          | Set di opzioni    |              | X              |
| Identità di social network 1 | Text          |              | X              |
| Identità di social network 2 | Text          |              | X              |
| Origine                    | Set di opzioni    | X            | X              |
| Stato                    | Set di opzioni    | X            | X              |
| Telefono 1               | Telefono         |              | X              |
| Telefono 2               | Telefono         |              | X              |
| Telefono 3               | Telefono         |              | X              |
| Identità Twitter          | Text          |              | X              |
| Utente                      | Ricerca        |              | X              |
| URL sito Web               | URL           |              | X              |
| Numero lavoratore             | Text          | X            | X              |
| Tipo di lavoratore               | Set di opzioni    | X            | X              |
| Nome Yomi           | Text          |              | X              |
| Nome completo Yomi            | Text          |              | X              |
| Cognome Yomi            | Text          |              | X              |
| Secondo nome Yomi          | Text          |              | X              |


**Indirizzo lavoratore**

| **Campi**           | **Tipo di dati**  | **Obbligatorio** | **Ricercabile** |
|----------------------|----------------|--------------|----------------|
| Numero civico       | Text           | X            | X              |
| Tipo di indirizzo         | Set di opzioni     | X            | X              |
| Città                 | Text           |              | X              |
| Paese    | Text           |              | X              |
| Regione               | Text           |              | X              |
| Fax                  | Telefono          |              | X              |
| Preferito         | Due opzioni    |              | X              |
| Latitudine             | Numero decimale |              | X              |
| Riga 1               | Text           |              | X              |
| Riga 2               | Text           |              | X              |
| Riga 3               | Text           |              | X              |
| Longitudine            | Numero decimale |              | X              |
| CAP          | Text           |              | X              |
| Casella postale      | Text           |              | X              |
| Codice metodo di spedizione | Numero intero   |              | X              |
| Stato/regione o provincia    | Text           |              | X              |
| Telefono 1          | Telefono          |              | X              |
| Telefono 2          | Telefono          |              | X              |
| Telefono 3          | Telefono          |              | X              |
| Area UPS             | Text           |              | X              |
| Differenza UTC           | Numero intero   |              | X              |
| Lavoro               | Ricerca         | X            | X              |


**Dati personali lavoratore**

| Campi                             | Tipo di dati    | Obbligatorio | Ricercabile |
|------------------------------------|--------------|----------|------------|
| Città di nascita                         | Text         |          | X          |
| Paese di nascita            | Set di opzioni   |          | X          |
| Data di nascita                          | Solo data    |          | X          |
| Paese di cittadinanza      | Set di opzioni   |          | X          |
| Data di decesso                      | Solo data    |          | X          |
| Data di verifica veterano disabile | Solo data    |          | X          |
| Istruzione                          | Text         |          | X          |
| Origine etnica                     | Ricerca       |          | X          |
| Data di fine lavoratore straniero                  | Solo data    |          | X          |
| Data di inizio lavoratore straniero                | Solo data    |          | X          |
| Paese di nascita padre     | Set di opzioni   |          | X          |
| Genere                             | Set di opzioni   |          | X          |
| Disabile                        | Due opzioni  |          | X          |
| Veterano disabile                | Due opzioni  |          | X          |
| Indica se la normativa per lavoratori stranieri è applicabile    | Due opzioni  |          | X          |
| Studente a tempo pieno               | Due opzioni  |          | X          |
| Stato civile                     | Set di opzioni   |          | X          |
| Data di fine servizio militare          | Solo data    |          | X          |
| Data di inizio servizio militare        | Solo data    |          | X          |
| Paese di nascita madre     | Set di opzioni   |          | X          |
| Paese nazionalità      | Set di opzioni   |          | X          |
| Madrelingua                    | Ricerca       |          | X          |
| Numero persone a carico               | Numero intero |          |            |
| Stato di veterano                     | Ricerca       |          | X          |
| Lavoro                             | Ricerca       | X        | X          |
| Numero dati personali lavoratore      | Text         | X        | X          |


**Conto bancario del lavoratore**

| **Campi**                 | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|----------------------------|---------------|--------------|----------------|
| Titolare conto             | Text          |              | X              |
| Identificazione conto     | Text          |              | X              |
| Descrizione indirizzo        | Text          |              | X              |
| Tipo di conto bancario          | Set di opzioni    |              | X              |
| Codice ubicazione banca         | Text          |              | X              |
| Nome filiale                | Text          |              | X              |
| Codice della filiale              | Text          |              | X              |
| Città                       | Text          |              | X              |
| Paese          | Text          |              | X              |
| Regione                     | Text          |              | X              |
| Descrizione                | Text          |              | X              |
| Nome distretto              | Text          |              | X              |
| Indirizzo di posta elettronica                      | Text          |              | X              |
| Interno                  | Text          |              | X              |
| Fax                        | Text          |              | X              |
| IBAN                       | Text          |              | X              |
| Riga 1                     | Text          |              | X              |
| Riga 2                     | Text          |              | X              |
| Riga 3                     | Text          |              | X              |
| Cellulare               | Text          |              | X              |
| Nome della persona             | Text          |              | X              |
| CAP                | Text          |              | X              |
| Casella postale            | Text          |              |                |
| Numero di registrazione             | Text          |              | X              |
| Tipo di numero di registrazione        | Set di opzioni    |              | X              |
| Stato/regione o provincia          | Text          |              | X              |
| Codice SWIFT                 | Text          |              | X              |
| Telefono                  | Text          |              | X              |
| Numero di telex               | Text          |              | X              |
| URL sito Web                | Text          |              | X              |
| Lavoro                     | Ricerca        | X            | X              |
| Numero conto bancario lavoratore | Text          |              | X              |
| Numero conto bancario lavoratore | Text          | X            | X              |

**Retribuzione fissa lavoratore**

| Campi                                | Tipo di dati      | Obbligatorio | Ricercabile |
|---------------------------------------|----------------|----------|------------|
| Società                               | Ricerca         | X        | X          |
| Tipo di retribuzione                     | Set di opzioni     |          | X          |
| Valuta                              | Ricerca         |          | X          |
| Data di validità                        | Solo data      |          | X          |
| Evento                                 | Ricerca         | X        | X          |
| Tasso di cambio                         | Numero decimale |          | X          |
| Data di scadenza                       | Solo data      |          | X          |
| Numero riga                           | Numero decimale |          | X          |
| Frequenza retribuzione                         | Ricerca         | X        | X          |
| Retribuzione                              | Valuta       |          | X          |
| Retribuzione (base)                       | Valuta       |          | X          |
| Pianifica                                  | Ricerca         | X        | X          |
| Posizione                              | Ricerca         | X        | X          |
| Tipo di processo                          | Set di opzioni     | X        | X          |
| Riga impostazione punti di riferimento            | Ricerca         |          | X          |
| Lavoro                                | Ricerca         | X        | X          |
| Numero retribuzione fissa lavoratore      | Text           | X        | X          |

**Numero identificazione lavoratore**

| Campi                 | Tipo di dati   | Obbligatorio | Ricercabile |
|------------------------|-------------|----------|------------|
| Descrizione            | Text        |          | X          |
| Tipo di voce             | Text        |          | X          |
| Data di scadenza        | Solo data   |          | X          |
| Numero di identificazione  | Text        | X        | X          |
| Tipo di identificazione    | Ricerca      | X        | X          |
| Primario             | Due opzioni |          | X          |
| Data di emissione             | Solo data   |          | X          |
| Agenzia emittente         | Ricerca      | X        | X          |
| Lavoro                 | Ricerca      | X        | X          |


## <a name="position-entities"></a>Entità Posizione

**Posizione lavorativa**

| **Campi**               | **Tipo di dati**  | **Obbligatorio** | **Ricercabile** |
|--------------------------|----------------|--------------|----------------|
| Attivazione               | Data e ora  |              | X              |
| Disponibile per l'assegnazione | Data e ora  |              | X              |
| Reparto               | Ricerca         |              | X              |
| Descrizione              | Text           |              | X              |
| Equivalente a tempo pieno     | Numero decimale |              | X              |
| Posizione                      | Ricerca         | X            | X              |
| Numero posizione lavorativa      | Text           | X            | X              |
| Posizione lavorativa padre      | Ricerca         |              | X              |
| Tipo di posizione            | Ricerca         |              | X              |
| Pensione               | Data e ora  |              | X              |
| Funzione                    | Set di opzioni     |              | X              |
| Data di inizio validità               | Data e ora  | X            | X              |
| Data di fine validità                 | Data e ora  |              | X              |


**Tipo di posizione**

| **Campi**         | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|--------------------|---------------|--------------|----------------|
| Classificazione     | Set di opzioni    |              | X              |
| Descrizione        | Text          |              | X              |
| Nome tipo di posizione | Text          | X            | X              |


**Assegnazione lavoratore posizione**

| **Campi**                        | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-----------------------------------|---------------|--------------|----------------|
| Posizione lavorativa                      | Ricerca        | X            | X              |
| Numero assegnazione lavoratore posizione | Text          | X            | X              |
| Data di inizio validità                        | Text          | X            | X              |
| Data di fine validità                          |               |              | X              |
| Lavoro                            |               | X            | X              |

## <a name="job-entities"></a>Entità Lavoro

**Mansione**

| **Campi**                   | **Tipo di dati**  | **Obbligatorio** | **Ricercabile** |
|------------------------------|----------------|--------------|----------------|
| Consenti quantità illimitata    | Due opzioni    |              | X              |
| Equivalente a tempo pieno predefinito | Numero decimale |              | X              |
| Descrizione                  | Text           |              | X              |
| Descrizione posizione              | Text           |              | X              |
| Funzione lavorativa                 | Ricerca         |              | X              |
| Tipo di mansione                     | Ricerca         |              | X              |
| Numero massimo di posizioni  | Numero intero   |              | X              |
| Nome                         | Text           | X            | X              |
| Funzione                        | Set di opzioni     |              | X              |
| Data di inizio validità                   | Data e ora  | X            | X              |
| Data di fine validità                     | Data e ora  |              | X              |


**Funzione lavorativa**

| **Campi**        | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-------------------|---------------|--------------|----------------|
| Descrizione       | Text          | X            | X              |
| Nome funzione lavorativa | Text          | X            | X              |


**Tipo di mansione**

| **Campi**    | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|---------------|---------------|--------------|----------------|
| Descrizione   | Text          | X            | X              |
| Stato esenzione | Set di opzioni    | X            | X              |
| Nome tipo di mansione | Text          | X            | X              |

## <a name="leave-and-absence-entities"></a>Entità Congedo e assenza

**Iscrizione congedo**

| **Campi**            | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-----------------------|---------------|--------------|----------------|
| Base data di accumulo    | Solo data     | X            | X              |
| Data di inizio accumulo    | Solo data     | X            | X              |
| Data personalizzata           | Solo data     | X            | X              |
| Accumulo sospeso  | Due opzioni   |              | X              |
| Numero iscrizione congedo | Text          | X            | X              |
| Piano di congedo            | Ricerca        | X            | X              |
| Data di inizio            | Solo data     | X            | X              |
| Base livello            | Set di opzioni    | X            | X              |
| Lavoro                | Ricerca        | X            | X              |


**Transazione bancaria di congedo**

| **Campi**                    | **Tipo di dati**  | **Obbligatorio** | **Ricercabile** |
|-------------------------------|----------------|--------------|----------------|
| Periodo                        | Numero decimale | X            | X              |
| Società                       | Ricerca         | X            | X              |
| Numero transazione bancaria di congedo | Text           | X            | X              |
| Piano di congedo                    | Ricerca         |              | X              |
| Tipo di congedo                    | Ricerca         | X            | X              |
| Data transazione              | Solo data      | X            | X              |
| Numero transazione            | Numero decimale | X            | X              |
| Tipo di transazione              | Set di opzioni     | X            | X              |
| Lavoro                        | Ricerca         | X            | X              |


**Piano di congedo**

| **Campi**        | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-------------------|---------------|--------------|----------------|
| Frequenza di attribuzione per competenza | Set di opzioni    | X            | X              |
| Società           | Ricerca        | X            | X              |
| Descrizione       | Text          |              | X              |
| Tipo di congedo        | Ricerca        | X            | X              |
| Nome              | Text          | X            | X              |
| Data di inizio        | Solo data     | X            | X              |


**Richiesta di congedo**

| **Campi**           | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|----------------------|---------------|--------------|----------------|
| Commento              | Text          | X            | X              |
| Società              | Ricerca        | X            | X              |
| Numero richiesta di congedo | Text          |              | X              |
| Data richiesta         | Data e ora | X            | X              |
| Stato               | Set di opzioni    | X            | X              |
| Lavoro               | Ricerca        | X            | X              |


**Dettagli richiesta congedo**

| **Campi**                  | **Tipo di dati**  | **Obbligatorio** | **Ricercabile** |
|-----------------------------|----------------|--------------|----------------|
| Periodo                      | Numero decimale | X            | X              |
| Data congedo                  | Data e ora  | X            | X              |
| Richiesta di congedo               | Ricerca         | X            | X              |
| Numero dettagli richiesta congedo | Text           | X            | X              |
| Tipo di congedo                  | Ricerca         | X            | X              |


**Tipo di congedo**

| **Campi**      | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-----------------|---------------|--------------|----------------|
| Società         | Ricerca        | X            | X              |
| Descrizione     | Text          |              | X              |
| Codice di reddito    | Ricerca        |              | X              |
| Nome tipo di congedo | Text          | X            | X              |


**Calendario lavorativo**

| **Campi**  | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-------------|---------------|--------------|----------------|
| Società     | Ricerca        | X            | X              |
| Descrizione | Text          |              | X              |
| Nome        | Text          | X            | X              |


**Giorno calendario di lavoro**

| **Campi**               | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|--------------------------|---------------|--------------|----------------|
| Data calendario            | Solo data     | X            | X              |
| Società                  | Ricerca        |              | X              |
| Stato                   | Text          |              | X              |
| Calendario lavorativo            | Ricerca        | X            | X              |
| Numero giorno calendario di lavoro | Text          | X            | X              |


**Festività calendario lavorativo**

| **Campi**  | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-------------|---------------|--------------|----------------|
| Nome        | Text          |              | X              |
| Descrizione | Text          | X            | X              |


**Riga festività del calendario di lavoro**

| **Campi**                        | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-----------------------------------|---------------|--------------|----------------|
| Data festività                      | Solo data     | X            | X              |
| Nome                              | Text          |              | X              |
| Festività calendario lavorativo             | Ricerca        | X            | X              |
| Numero riga festività del calendario di lavoro | Text          | X            | X              |


**Intervallo orario calendario di lavoro**

| **Campi**                         | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|------------------------------------|---------------|--------------|----------------|
| Società                            | Ricerca        |              | X              |
| Ora di fine                           | Numero intero  |              | X              |
| Ora di inizio                         | Numero intero  |              | X              |
| Calendario lavorativo                      | Ricerca        | X            | X              |
| Giorno calendario di lavoro                  | Ricerca        | X            | X              |
| Numero intervallo orario calendario di lavoro | Text          | X            | X              |

## <a name="organization-entities"></a>Entità Organizzazione

**Società**

| **Campi**   | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|--------------|---------------|--------------|----------------|
| Codice società | Text          | X            | X              |
| Nome         | Text          | X            | X              |


**Reparto**

| **Campi**        | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-------------------|---------------|--------------|----------------|
| Numero reparto | Text          | X            | X              |
| Descrizione       | Text          |              | X              |
| Nome              | Text          | X            | X              |
| Reparto padre | Ricerca        |              | X              |


**Valuta**

| **Campi**         | **Tipo di dati**  | **Obbligatorio** | **Ricercabile** |
|--------------------|----------------|--------------|----------------|
| Codice valuta      | Text           | X            | X              |
| Nome valuta      | Text           | X            | X              |
| Precisione valuta | Numero intero   | X            | X              |
| Simbolo valuta    | Text           | X            | X              |
| Immagine entità       | Immagine          |              |                |
| Tasso di cambio      | Numero decimale | X            | X              |
| Organizzazione       | Ricerca         | X            | X              |
| Stato             | Set di opzioni     |              | X              |

## <a name="payroll-entities"></a>Entità Retribuzioni

**Ciclo retributivo**

| **Campi**  | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-------------|---------------|--------------|----------------|
| Descrizione | Text          | X            | X              |
| Frequenza   | Set di opzioni    | X            | X              |
| Nome        | Text          | X            | X              |


**Periodo retributivo**

| **Campi**           | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|----------------------|---------------|--------------|----------------|
| Data di pagamento predefinita | Solo data     |              | X              |
| Descrizione          | Text          |              | X              |
| Ciclo retributivo            | Ricerca          | X            | X              |
| Numero periodo retributivo    | Text          | X            | X              |
| Data di fine periodo      | Solo data     | X            | X              |
| Data di inizio periodo    | Solo data     | X            | X              |
| Stato               | Set di opzioni    |              | X              |


**Codice di reddito per retribuzione**

| **Campi**              | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-------------------------|---------------|--------------|----------------|
| Descrizione             | Text          | X            | X              |
| Includi in tipo di pagamento | Set di opzioni    | X            | X              |
| Produttivo           | Due opzioni   | X            | X              |
| Nome                    | Text          |              | X              |
| Unità di quantità           | Set di opzioni    |              | X              |
| Traccia ore FMLA        | Due opzioni   |              | X              |


**Regione fiscale**

| **Campi**        | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-------------------|---------------|--------------|----------------|
| Città              | Text          |              | X              |
| Paese | Text          |              | X              |
| Regione            | Text          |              | X              |
| Nome              | Text          | X            | X              |
| Stato/regione o provincia | Text          |              | X              |


**Periodo retributivo della frequenza di calcolo benefit**

| **Campi**                                      | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-------------------------------------------------|---------------|--------------|----------------|
| Frequenza di calcolo benefit                   | Ricerca        | X            | X              |
| Numero periodo retributivo della frequenza di calcolo benefit | Text          | X            | X              |
| Periodo retributivo                                      | Ricerca        | X            | X              |


**Esborso conto bancario**

| **Campi**                       | **Tipo di dati**  | **Obbligatorio** | **Ricercabile** |
|----------------------------------|----------------|--------------|----------------|
| Periodo                           | Valuta       |              | X              |
| Importo (base)                    | Valuta       |              | X              |
| Conto bancario                     | Ricerca         | X            | X              |
| Numero esborso conto bancario | Text           | X            | X              |
| Società                          | Ricerca         | X            | X              |
| Valuta                         | Ricerca         |              | X              |
| Tasso di cambio                    | Numero decimale |              | X              |
| Residuo                     | Due opzioni    |              | X              |
| Priorità                         | Numero intero   |              | X              |

**Agenzia di rilascio dell'identificazione della persona**

| **Campi**           | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|----------------------|---------------|--------------|----------------|
| Descrizione indirizzo  | Text          |              | X              |
| Riga indirizzo 1       | Text          |              | X              |
| Riga indirizzo 2       | Text          |              | X              |
| Riga indirizzo 3       | Text          |              | X              |
| Città                 | Text          |              | X              |
| Paese    | Set di opzioni    |              | X              |
| Regione               | Text          |              | X              |
| Descrizione          | Text          |              | X              |
| Indirizzo di posta elettronica                | Text          |              | X              |
| Interno            | Text          |              | X              |
| Fax                  | Text          |              | X              |
| Nome agenzia emittente  | Text          | X            | X              |
| Cellulare         | Text          |              | X              |
| Pagina                 | Text          |              | X              |
| CAP          | Text          |              | X              |
| Casella postale      | Text          |              | X              |
| SMS                  | Text          |              | X              |
| Stato/regione o provincia    | Text          |              | X              |
| Telefono            | Text          |              | X              |
| Telex                | Text          |              | X              |
| URL sito Web          | Text          |              | X              |

**Tipo di identificazione lavoratore**

| **Campi**                        | **Tipo di dati**  | **Obbligatorio** | **Ricercabile** |
|-----------------------------------|----------------|--------------|----------------|
| Valori consentiti                    | Set di opzioni     |              | X              |
| Paese                 | Text           |              | X              |
| Descrizione                       | Text           |              | X              |
| Lunghezza fissa                      | Numero intero   |              | X              |
| Formato numero di identificazione      | Text           |              | X              |
| Tipo                              | Set di opzioni     |              | X              |
| Tipo di identificazione lavoratore | Text           | X            | X              |

## <a name="fixed-compensation-entities"></a>Entità Retribuzione fissa

**Piano di retribuzione fissa**

| **Campi**                  | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-----------------------------|---------------|--------------|----------------|
| Società                     | Ricerca        | X            | X              |
| Griglia di retribuzione           | Ricerca        |              | X              |
| Valuta                    | Ricerca        | X            | X              |
| Descrizione                 | Text          | X            | X              |
| Data di validità              | Solo data     | X            | X              |
| Data di scadenza             | Solo data     | X            | X              |
| Regola di assunzione                   | Set di opzioni    | X            | X              |
| Nome                        | Text          | X            | X              |
| Tolleranza non compresa nell'intervallo      | Set di opzioni    | X            | X              |
| Frequenza retribuzione               | Ricerca        | X            | X              |
| Suggerimento consentito      | Due opzioni   | X            | X              |
| Impostazione riga punti di riferimento  | Ricerca        |              | X              |
| Tipo                        | Set di opzioni    | X            | X              |

**Griglia retributiva**

| **Campi**                  | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-----------------------------|---------------|--------------|----------------|
| Società                     | Ricerca        | X            | X              |
| Valuta                    | Ricerca        |              | X              |
| Descrizione                 | Text          | X            | X              |
| Data di validità              | Solo data     |              | X              |
| Data di scadenza             | Solo data     |              | X              |
| Nome                        | Text          | X            | X              |
| Impostazione punti di riferimento       | Ricerca        | X            | X              |
| Tipo                        | Set di opzioni    | X            | X              |

**Livello retributivo**

| **Campi**      | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-----------------|---------------|--------------|----------------|
| Descrizione     | Text          |              | X              |
| Nome            | Text          | X            | X              |
| Tipo            | Set di opzioni     | X            | X              |

**Frequenza della retribuzione**

| **Campi**                  | **Tipo di dati**   | **Obbligatorio** | **Ricercabile** |
|-----------------------------|-----------------|--------------|----------------|
| Fattore di conversione annuale    | Numero decimale  |              | X              |
| Società                     | Ricerca          | X            | X              |
| Descrizione                 | Text            |              | X              |
| Fattore di conversione oraria    | Numero decimale  |              | X              |
| Fattore di conversione mensile   | Numero decimale  |              | X              |
| Nome                        | Text            | X            | X              |
| Periodo                      | Set di opzioni      |              | X              |
| Fattore di conversione settimanale    | Set di opzioni      |              | X              |


**Impostazione punti di riferimento per le retribuzioni**

| **Campi**          | **Tipo di dati**   | **Obbligatorio** | **Ricercabile** |
|---------------------|-----------------|--------------|----------------|
| Società             | Ricerca          | X            | X              |
| Tipo di retribuzione   | Set di opzioni      | X            | X              |
| Descrizione         | Text            | X            | X              |
| Nome                | Text            | X            | X              |

**Riga impostazione punti di riferimento per le retribuzioni**

| **Campi**            | **Tipo di dati**   | **Obbligatorio** | **Ricercabile** |
|-----------------------|-----------------|--------------|----------------|
| Società               | Ricerca          | X            | X              |
| Descrizione           | Text            | X            | X              |
| Numero di riga           | Numero decimale  | X            | X              |
| Nome                  | Text            | X            | X              |
| Impostazione punti di riferimento | Ricerca          | X            | X              |

**Paese di retribuzione**

| **Campi**      | **Tipo di dati** | **Obbligatorio** | **Ricercabile** |
|-----------------|---------------|--------------|----------------|
| Descrizione     | Text          | X            | X              |
| Nome            | Text          | X            | X              |

**Struttura retributiva**

| **Campi**                    | **Tipo di dati**   | **Obbligatorio** | **Ricercabile** |
|-------------------------------|---------------  |--------------|----------------|
| Periodo                        | Valuta        |              | X              |
| Imponibile                   | Valuta        |              | X              |
| Società                       | Ricerca          | X            | X              |
| Numero struttura retributiva | Text            | X            | X              |
| Valuta                      | Ricerca          |              | X              |
| Tasso di cambio                 | Numero decimale  |              | X              |
| Griglia                          | Ricerca          | X            | X              |
| Livello                         | Ricerca          | X            | X              |
| Punto di riferimento               | Ricerca          | X            | X              |
| Impostazione riga punti di riferimento    | Ricerca          | X            | X              |

**Evento di retribuzione fissa**

| **Campi**            | **Tipo di dati**   | **Obbligatorio** | **Ricercabile** |
|-----------------------|-----------------|--------------|----------------|
| Società               | Ricerca          | X            | X              |
| Descrizione           | Text            | X            | X              |
| Tipo di evento            | Set di opzioni      | X            | X              |
| Attivo             | Due opzioni     | X            |                |
| Nome                  | Text            | X            | X              |

## <a name="entity-relationship-models"></a>Modelli di relazioni tra entità

### <a name="worker"></a>Lavoro
![Lavoro](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Lavoro e posizione lavorativa
![Lavoro e posizione lavorativa](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Benefit
![Benefit](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Retribuzione
![Retribuzione](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Uscire
![Uscire](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Calendario lavorativo
![Calendario lavorativo](./media/HCMCommon-work-calendar-entity-diagram.png)
