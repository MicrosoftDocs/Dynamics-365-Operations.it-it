---
title: Modificare la valuta di contabilizzazione o di dichiarazione
description: In questo argomento viene illustrato come modificare la valuta di contabilizzazione o di dichiarazione o come aggiungere una valuta di dichiarazione all'impostazione della contabilità generale.
author: kweekley
ms.date: 05/05/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ff5c38193e8469cb806c525b77809844847d6c92
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710892"
---
# <a name="change-the-accounting-or-reporting-currency"></a>Modificare la valuta di contabilizzazione o di dichiarazione

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come modificare la valuta di contabilizzazione o di dichiarazione o come aggiungere una valuta di dichiarazione all'impostazione della contabilità generale.

## <a name="symptom"></a>Sintomo

Si desidera modificare la valuta di contabilizzazione o di dichiarazione o aggiungere una valuta di dichiarazione all'impostazione della contabilità generale. Questo problema si verifica in genere nei seguenti scenari:

- Quando per una persona giuridica impostata viene specificata una valuta di contabilizzazione o di dichiarazione errata ed è necessario modificare quella valuta.
- Una valuta di dichiarazione è stata specificata per una persona giuridica impostata, ma ora l'organizzazione desidera rimuoverla.
- L'organizzazione sta eseguendo l'aggiornamento o la migrazione a Microsoft Dynamics 365 Finance e desidera modificare la valuta di contabilizzazione o di dichiarazione.

Un'organizzazione che in precedenza non utilizzava la funzionalità della doppia valuta desidera iniziare a utilizzarla. Questo problema si verifica in genere nei seguenti scenari.

- Quando per una persona giuridica impostata non è stata specificata alcuna valuta di dichiarazione. La valuta di dichiarazione è facoltativa, ma ora è necessario aggiungerla.

## <a name="resolution"></a>Risoluzione

La considerazione più importante è se le transazioni (effettive o di budget) sono state registrate nella persona giuridica per l'impostazione della contabilità generale. **Non è possibile modificare la valuta di contabilizzazione o di dichiarazione o aggiungere una valuta di dichiarazione se nella persona giuridica sono state registrate transazioni (effettive o di budget).** Seguire i passaggi di una delle seguenti sezioni, a seconda se le transazioni sono state registrate o meno.

### <a name="no-transactions-have-been-posted"></a>Non sono state registrate transazioni

1. Nella persona giuridica per cui si aggiornano le valute, andare a **Contabilità generale \> Impostazione contabilità generale \> Contabilità generale**.
2. Nella pagina **Contabilità generale** selezionare **Modifica**.
3. Nella Scheda dettaglio **Valuta** selezionare la valuta di contabilizzazione e la valuta di dichiarazione da utilizzare per la persona giuridica.
4. Selezionare **Salva**.

Se i campi per la valuta di contabilizzazione e la valuta di dichiarazione non sono disponibili nella pagina **Contabilità generale**, una o più transazioni (effettive o di budget) sono state registrate nella persona giuridica. Pertanto, le valute non possono essere modificate. In questo caso, seguire i passaggi della sezione successiva.

### <a name="transactions-have-been-posted"></a>Sono state registrate transazioni

**Se le transazioni sono state registrate nella persona giuridica, l'unico modo per modificare o aggiungere valute di contabilizzazione e di dichiarazione è creare una nuova persona giuridica con le valute corrette.** Per semplificare questo processo, la gestione dei dati nel sistema consente di copiare i record di impostazione e i record di dati master dall'attuale persona giuridica in una nuova persona giuridica.

Le modifiche alle valute di contabilizzazione e di dichiarazione sono pervasive. Influiscono non solo sulla contabilità generale, ma anche su tutti i registri secondari (contabilità clienti, contabilità fornitori, inventario, progetto e così via), su tutte le soluzioni di fornitori di software indipendenti (ISV) e su qualsiasi estensione creata per archiviare gli importi.

Il processo di ricerca e conversione di ogni importo in una valuta diversa è soggetto a errori. Pertanto, il team di progettazione non approva uno script che modifica o aggiunge valute di contabilizzazione e di dichiarazione. Inoltre, lo strumento disponibile per Microsoft Dynamics AX 2012 che consentiva di modificare o aggiungere valute di contabilizzazione e di dichiarazione è stato ritirato per AX 2012 R3 e Finance.

Attenersi alla seguente procedura per copiare l'impostazione e i dati master dalla persona giuridica corrente in una nuova persona giuridica.

1. Passare a **Aree di lavoro \> Gestione dati**.
2. Selezionare **Modelli** nel gruppo **Importa/esporta**.
3. Assicurarsi che i modelli siano disponibili. Se i modelli non sono disponibili, selezionare **Carica modelli predefiniti** e attendere che i modelli vengano generati.
4. Tornare all'area di lavoro **Gestione dati**.
5. Selezionare **Copia in persona giuridica**.
6. Immettere un nome e una descrizione per il gruppo.
7. Nel campo **Persona giuridica di origine** selezionare la persona giuridica da cui copiare i dati.
8. Nella Scheda dettaglio **Persone giuridiche di destinazione**, selezionare **Crea persone giuridiche** per creare una nuova persona giuridica in cui copiare i dati della persona giuridica di origine. Selezionare **Seleziona esistente** per copiare i dati in una persona giuridica esistente.
9. Facoltativo: impostare il campo **Copia sequenze numeriche** su **Sì**. Questo passaggio è consigliato quando si copiano i dati.
10. Nell'area **Entità selezionate** selezionare **Aggiungi modello**.
11. Selezionare i modelli da utilizzare. I modelli suggeriti per una nuova persona giuridica includono **025 - Contabilità generale** e **dati Finance**. Consigliamo di esaminare tutti gli altri modelli disponibili per determinare se si applicano ai propri requisiti.
12. Selezionare **Copia in persona giuridica** per avviare un processo batch che crea le entità selezionate e le copia nella persona giuridica di destinazione.
13. Dopo che il processo è stato completato, ma prima che venga registrata qualsiasi transazione, andare alla contabilità generale e aggiornare le valute di contabilizzazione e di dichiarazione come descritto in precedenza in questo argomento.

Se è stata creata una nuova persona giuridica in modo da poter modificare la valuta di contabilizzazione o di dichiarazione, verificare che i saldi iniziali siano convertiti dalle valute della persona giuridica precedente alle nuove valute.

Per un video che mostra i passaggi precedenti, vedere [Copia in persona giuridica](https://community.dynamics.com/365/b/techtalks/posts/copy-into-legal-entity-october-24-2017).
