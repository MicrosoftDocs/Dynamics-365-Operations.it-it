---
title: Esegui script X++ personalizzati senza tempi di inattività
description: Questo articolo descrive come caricare ed eseguire pacchetti distribuibili che contengono script X++ personalizzati senza dover sospendere il sistema.
author: AndersGirke
ms.date: 12/16/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-12-16
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 3d00f842da69f889738fbcb293c7489bb018e810
ms.sourcegitcommit: f62c9b24c2205d03e2fd6e7c67f7b5c316233b12
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2022
ms.locfileid: "9598084"
---
# <a name="run-custom-x-scripts-with-zero-downtime"></a>Esegui script X++ personalizzati senza tempi di inattività

[!include [banner](../includes/banner.md)]

Questa funzionalità consente di caricare ed eseguire pacchetti distribuibili che contengono script X++ personalizzati senza dover passare a Microsoft Dynamics Lifecycle Services (LCS) o sospendere il sistema. Pertanto, è possibile correggere piccole incoerenze dei dati senza causare tempi di inattività.

Il vantaggio dell'utilizzo di uno script X++ per correggere piccole incongruenze di dati è che il sistema regolerà automaticamente tutte le tabelle correlate come richiesto quando esegue lo script. Questo approccio aiuta a garantire l'integrità della correzione e aiuta a ridurre al minimo il rischio di introdurre nuove incoerenze.

> [!IMPORTANT]
> Questa funzionalità è intesa solo per la correzione di piccole incongruenze di dati. Non deve essere utilizzata per i seguenti scopi o per qualsiasi altro scopo:
>
> - Raccolta dati
> - Modifiche agli schemi
> - Migrazione dei dati o altri processi di lunga durata
> - Correzione dei dati che possono essere corretti con altri mezzi, come processi aziendali regolari, strumenti di coerenza dei dati o altri strumenti self-service
>
> La funzionalità consente agli utenti autorizzati di modificare direttamente le entità e i loro record, senza dover eseguire la logica aziendale associata a tali entità. Queste modifiche possono causare problemi di integrità dei dati. Pertanto, l'organizzazione potrebbe richiedere l'approvazione e la conferma da parte di revisori interni ed esterni (o altre parti interessate equivalenti) prima e/o dopo l'esecuzione di uno script. Per motivi di conformità, le modifiche che influiscono su alcune caratteristiche potrebbero dover essere divulgate anche in report esterni (come i rendiconti finanziari) o segnalate alle autorità governative. L'organizzazione è l'unica responsabile di eventuali modifiche apportate ai propri dati tramite questa funzionalità, di qualsiasi approvazione e conferma o divulgazione di tali modifiche e della conformità alle leggi applicabili. Tutti i rischi dell'utilizzo di questa funzionalità sono a tuo carico.

Tutti i pacchetti distribuibili caricati nel sistema passano attraverso un flusso di lavoro obbligatorio. Come precauzione di sicurezza e per garantire la separazione dei compiti, l'utente che carica un pacchetto distribuibile non può approvarlo per i passaggi successivi del flusso di lavoro. Un altro utente deve approvarlo. Tuttavia, dopo l'approvazione del pacchetto, l'utente che lo ha caricato potrà completare i passaggi rimanenti.

Il sistema richiede che tutti i pacchetti distribuibili siano sottoposti a un'esecuzione di prova. Prima che lo script possa essere eseguito sui dati di produzione, un utente deve convalidare che l'output sia corretto selezionando **Accetta registro di test**. Se l'output non è corretto, l'utente deve contrassegnare il pacchetto come non riuscito selezionando **Abbandona**. In questo caso, lo script non potrà essere eseguito sui dati di produzione.

Ogni pacchetto caricato viene salvato nel sistema e passa attraverso un flusso di lavoro definito di eventi. Per ogni evento, il sistema conserva un registro che include un timestamp e l'identità della persona che ha eseguito l'evento. In questo modo, il sistema garantisce la presenza di un audit trail.

Come mostra l'illustrazione seguente, il sistema fornisce dettagli su come ogni pacchetto distribuibile è stato eseguito in X++ e quali entità sono state toccate.

![Pagina dei dettagli dello script.](media/script-details.png "Pagina dei dettagli dello script")

## <a name="assign-duties-to-users-to-control-access"></a>Assegnare compiti agli utenti per controllare l'accesso

Questa funzionalità offre i seguenti compiti: Gli amministratori possono utilizzare questi compiti per controllare l'accesso alla funzionalità.

- **Mantieni script personalizzati** – Questo compito garantisce la possibilità di caricare, testare, verificare ed eseguire script X++ personalizzati in ambienti (test di accettazione dell'utente \[ UAT\] e produzione).
- **Approva script personalizzati** – Questo compito garantisce la possibilità di approvare uno script X++ personalizzato caricato. L'approvazione è un passaggio obbligatorio prima che qualsiasi script possa essere testato, verificato ed eseguito.

Per ridurre al minimo il rischio di azioni dannose, ogni script deve essere esplicitamente approvato da un utente diverso dall'utente che lo ha caricato. Prima di poter utilizzare questa funzionalità nella tua organizzazione, un amministratore deve assegnare i compiti precedenti ad almeno due utenti pertinenti e altamente affidabili. Sebbene un singolo utente possa avere entrambi i compiti, quell'utente non sarà comunque in grado di approvare i propri script.

## <a name="create-a-deployable-package"></a>Creare un pacchetto distribuibile

La funzionalità richiede un pacchetto distribuibile regolare che può essere creato in Visual Studio. Per istruzioni, vedi [Creare pacchetti distribuibili di modelli](../deployment/create-apply-deployable-package.md).

Il tuo pacchetto distribuibile deve contenere esattamente una classe X++ eseguibile. In altre parole, deve avere una classe che include un metodo con la seguente firma.

```xpp
public static void main(Args _args)
```

> [!NOTE]
> Il nome del metodo principale deve essere in minuscolo.

## <a name="code-example"></a>Esempio di codice

L'esempio di codice seguente mostra come è possibile strutturare un pacchetto distribuibile.

```xpp
class MyScriptClassForIssueXYZ
{
    public static void main(Args _args)
    {
        if (curExt() != 'DAT')
        {
            throw error("This script must run in the DAT company!");
        }

        ttsbegin;

        MyTable myTable;

        update_recordset myTable
            setting myField = 17
            where myTable.myReference == 'xyz';

        if (myTable.RowCount() != 1)
        {
            throw error("Not updating the expected row!");
        }

        info("Success");
  
        ttscommit;
    }

}
```

## <a name="best-practices"></a>Procedure consigliate

L'elenco seguente descrive alcune procedure consigliate per scrivere, implementare ed eseguire correttamente uno script. L'elenco non è esaustivo e dovrebbe essere considerato solo una guida.

- **Scrivi** un messaggio di completamento alla fine dello script. In questo modo, potrai vedere che lo script è stato eseguito senza eccezioni.
- **Aggiungi** la gestione esplicita dell'ambito della transazione.
- **Utilizza** la logica aziendale esistente, ad esempio i metodi `update()`, ma **non** ignorare la logica aziendale utilizzando i metodi `doUpdate()`, `doInsert()` e `doDelete()`. Questo approccio aiuterà a garantire che i dati dipendenti vengano gestiti correttamente. Ridurrà inoltre notevolmente il rischio di ulteriori incoerenze dei dati.
- **Afferma** il contesto aziendale. Questo approccio presentare gli errori comuni durante l'esecuzione di uno script. Ad esempio, rivelerà se lo script viene eseguito nell'azienda sbagliata.
- **Afferma** che il numero di record interessati corrisponde alle tue aspettative. Questo approccio rivelerà se i dati sono stati spostati in modo imprevisto nel sistema durante la preparazione dello script.
- **Utilizza** nomi di classe univoci per ogni script (ad esempio, includendo un riferimento a un elemento di lavoro nel nome). Questo approccio eviterà problemi di conflitto di nomi quando carichi lo script. Se è necessaria una nuova iterazione di uno script, assicurati di assegnargli un nuovo nome.
- **Testa** prima ogni script in un ambiente non di produzione. Testa l'impatto previsto e gli effetti collaterali non intenzionali sui dati correlati. Verifica che tutti i processi aziendali che potrebbero essere interessati possano essere completati interamente in seguito.

## <a name="upload-and-run-a-deployable-package"></a>Caricare ed eseguire un pacchetto distribuibile

Utilizza la procedura seguente per caricare ed eseguire uno script.

1. Nell'app per la finanza e le operazioni, vai a **Amministrazione di sistema \> Attività periodiche \> Database \> Script personalizzati**.
1. Selezionare **Carica**.
1. Seleziona il pacchetto distribuibile che hai creato come descritto in precedenza in questo articolo. Ti verrà chiesto di specificare lo scopo dello script.
1. Lo script ora deve essere approvato da un utente diverso dall'utente che lo ha caricato. Il responsabile dell'approvazione deve seguire questi passaggi:

    1. Vai a **Amministrazione di sistema \> Periodico \> Database \> Script personalizzati**.
    1. Seleziona lo script da approvare, quindi seleziona **Dettagli**.
    1. Nel riquadro azioni, scheda **Flusso di lavoro processo**, nel gruppo **Avvia**, seleziona **Approva** o **Rifiuta**. Se selezioni **Approva**, lo script viene contrassegnato come approvato e sbloccato per il test. Se selezioni **Rifiuta**, lo script è bloccato. In entrambi i casi, l'evento viene registrato e una copia dello script viene conservata nel sistema.

1. Lo script deve essere testato per assicurarsi che esegua ciò per cui è destinato. Il responsabile del test può essere lo stesso dell'autore del caricamento o del responsabile dell'approvazione, oppure può essere un terzo utente che dispone delle autorizzazioni richieste. Il responsabile del test deve seguire questi passaggi:

    1. Vai a **Amministrazione di sistema \> Periodico \> Database \> Script personalizzati**.
    1. Seleziona lo script da testare, quindi seleziona **Dettagli**.
    1. Nel riquadro Azioni, scheda **Flusso di lavoro processo**, gruppo **Test**, seleziona **Esegui test**. Lo script viene eseguito all'interno di una transazione temporanea che il sistema interromperà automaticamente mentre raccoglie vari registri e istruzioni SQL.
    1. Al termine dell'esecuzione dello script, rivedi i log e verifica che i risultati soddisfino le aspettative. Eseguire uno dei passaggi riportati di seguito.

        - Se sei soddisfatto del risultato del test, seleziona **Accetta registro di test** nel gruppo **Test** della scheda **Flusso di lavoro del processo** del riquadro azioni per consentire l'esecuzione dello script. Il registro eventi rifletterà il fatto che lo script è stato testato e indicherà chi lo ha testato e quando.
        - Se non sei soddisfatto del risultato del test, seleziona **Abbandona** nel gruppo **Fine** della scheda **Flusso di lavoro del processo** del riquadro azioni per impedire l'esecuzione dello script. Il sistema conserverà una copia dello script insieme a un registro della sua cronologia.

1. Quando sei sicuro che lo script soddisfa le tue aspettative, seleziona **Esegui** nel gruppo **Esegui** nella scheda **Flusso di lavoro del processo** del riquadro azioni per eseguirlo. Questo comando fa la stessa cosa del test precedente, ma la transazione verrà confermata alla fine.
1. Al termine dell'esecuzione dello script, controlla il risultato e conferma che lo script ha funzionato come previsto. Eseguire uno dei passaggi riportati di seguito.

    - Se sei soddisfatto del risultato, seleziona **Scopo risolto** nel gruppo **Fine** della scheda **Flusso di lavoro del processo** del riquadro azioni. Il registro eventi rifletterà il fatto che lo script è stato eseguito e indicherà chi ha verificato lo script e quando. Lo script è stato salvato, ma ora è bloccato e non può essere eseguito nuovamente.
    - Se non sei soddisfatto del risultato, seleziona **Scopo non risolto** nel gruppo **Fine** della scheda **Flusso di lavoro del processo** del riquadro azioni. Il registro eventi rifletterà il fatto che lo script non ha soddisfatto lo scopo per cui era inteso e indicherà chi ha eseguito lo script e quando. Lo script è stato salvato, ma ora è bloccato e non può essere eseguito nuovamente. Tuttavia, il sistema non annulla automaticamente l'azione dello script. Potrebbe essere necessario scrivere, importare ed eseguire un nuovo script per annullare l'effetto che lo script non riuscito ha avuto sul sistema.

La tua selezione nell'ultimo passaggio definisce lo stato finale dello script. Puoi ripetere il processo secondo le tue esigenze.

## <a name="upload-and-run-a-deployable-package-through-lcs"></a>Caricare ed eseguire un pacchetto distribuibile tramite LCS

Invece di distribuire il pacchetto distribuibile tramite l'interfaccia utente per l'app per la finanza e le operazioni, come descritto nella sezione precedente, puoi caricarlo in LCS e utilizzare la normale procedura per distribuirlo. Per altre informazioni, vedi [Installare pacchetti distribuibili dalla riga di comando](../deployment/install-deployable-package.md).

Sebbene questo approccio abbia meno restrizioni, fornisce una minore protezione dagli errori. Inoltre, poiché richiede il riavvio di tutti i server, causerà alcuni tempi di inattività.

