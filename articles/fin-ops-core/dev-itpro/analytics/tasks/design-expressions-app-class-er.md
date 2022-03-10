---
title: Progettare espressioni di ER per chiamare i metodi delle classi dell'applicazione
description: Questo argomento descrive come riutilizzare la logica dell'applicazione esistente nelle configurazioni dei report elettronici chiamando i metodi richiesti delle classi dell'applicazione.
author: NickSelin
ms.date: 11/02/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 81fae8d3603677afd7dd4b09b9073805f73582b4
ms.sourcegitcommit: e6b4844a71fbb9faa826852196197c65c5a0396f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "7751708"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>Progettare espressioni di ER per chiamare i metodi delle classi dell'applicazione

[!include [banner](../../includes/banner.md)]

Questo argomento illustra come riutilizzare la logica dell'applicazione esistente nelle configurazioni di [Creazione di report elettronici](../general-electronic-reporting.md) chiamando i metodi richiesti delle classi dell'applicazione nelle espressioni ER. I valori degli argomenti per le classi chiamanti possono essere definiti dinamicamente in fase di esecuzione. Ad esempio, i valori possono essere basati sulle informazioni nel documento di analisi, per assicurarne la correttezza.

Ad esempio, in questo argomento dovrai progettare un processo per l'analisi dei rendiconti bancari in entrata per un aggiornamento dei dati dell'applicazione. Riceverai gli estratti conto in entrata come file di testo (.txt) che contengono i codici IBAN (International Bank Account Number). Durante il processo di importazione dei rendiconti bancari, è necessario convalidare la correttezza del codice IBAN utilizzando la logica già disponibile.

## <a name="prerequisites"></a>Prerequisiti

Le procedure in questo argomento sono intese per utenti a cui è stato assegnato il ruolo di **amministratore di sistema** o di **sviluppatore per la creazione di report elettronici**.

Le procedure possono essere completate utilizzando qualsiasi set di dati.

Per completare, devi scaricare e salvare il file seguente: [SampleIncomingMessage.txt](https://download.microsoft.com/download/8/0/a/80adbc89-f23c-46d9-9241-e0f19125c04b/SampleIncomingMessage.txt).

In questo argomento verranno create le configurazioni ER necessarie per la società di esempio Litware, Inc. Pertanto, prima di completare le procedure in questo argomento, è necessario seguire i seguenti passaggi.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, verifica che il provider di configurazione per la società di esempio **Litware, Inc.** sia disponibile e contrassegnato come Attivo. Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi in [Creare provider di configurazione e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-a-new-er-model-configuration"></a>Importare una nuova configurazione del modello ER

1. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, selezionare il riquadro per il provider di configurazione **Microsoft**.
2. Selezionare **Archivi**.
3. Nella pagina **Repository di localizzazione**, seleziona **Mostra filtri**.
4. Per selezionare il record del repository globale, aggiungi un campo di filtro **Nome**.
5. Nel campo **Nome** immetti **Globale**. Quindi seleziona l'operatore di filtro **contiene**.
6. Selezionare **Applica**.
7. Seleziona **[Apri](../er-download-configurations-global-repo.md#open-configurations-repository)** per rivedere l'elenco delle configurazioni ER per l'archivio selezionato.
8. Nella pagina **Archivio di configurazione**, nella struttura delle configurazioni, seleziona **Modello di pagamento**.
9. Nella Scheda dettaglio **Versioni** se il pulsante **Importa** è disponibile selezionalo, quindi seleziona **Sì**.

    Se il pulsante **Importa** non è disponibile, hai già importato la versione selezionata della configurazione ER **Modello di pagamento**.

10. Chiudi la pagina **Archivio di configurazione** pagina, quindi chiudi la pagina **Repository di localizzazione**.

## <a name="add-a-new-er-format-configuration"></a>Aggiungere una nuova configurazione di formato ER

Aggiungere un nuovo formato ER per analizzare i rendiconti bancari in entrata nel formato TXT.

1. Nella pagina **Configurazioni localizzazione**, seleziona il riquadro **Configurazioni report**.
2. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, seleziona **Modello di pagamento**.
3. Selezionare **Crea configurazione**. 
4. Nella finestra di dialogo a discesa, effettuare le seguenti operazioni:

    1. Nel campo **Nuovo** immettere **Formato in base al modello dati PaymentModel**.
    2. Nel campo **Nome**, immetti **Formato di importazione per rendiconto bancario (esempio)**.
    3. Seleziona **Sì** nel campo **Supporta importazione dati**.
    4. Seleziona **Crea configurazione** per terminare la creazione della configurazione.

## <a name="design-the-er-format-configuration--format"></a>Progettare la configurazione di formato ER - Formato

Progetta un formato ER che rappresenta la struttura prevista del file esterno nel formato TXT.

1. Per la configurazione del formato **Formato di importazione per rendiconto bancario (esempio)** che hai aggiunto, seleziona **Progettazione**.
2. Nella pagina **Progettazione formato** nell'albero della struttura formati nel riquadro di sinistra, seleziona **Aggiungi radice**.
3. Nella finestra di dialogo che viene visualizzata, effettuare le seguenti operazioni:

    1. Nell'albero, seleziona **Testo\\Sequenza** per aggiungere un componente formato **Sequenza**.
    2. Nel campo **Nome**, immetti **Radice**.
    3. Nel campo **Caratteri speciali**, seleziona **Nuova riga - Windows (CR LF)**. In base a questa impostazione, ogni riga del file di analisi verrà considerata come record separato.
    4. Seleziona **OK**.

4. Seleziona **Aggiungi**.
5. Nella finestra di dialogo che viene visualizzata, effettuare le seguenti operazioni:

    1. Nell'albero, seleziona **Testo\\Sequenza**.
    2. Nel campo **Nome** immetti **Righe**.
    3. Nel campo **Molteplicità** selezionare **Uno molti**. In base a questa impostazione, si prevede che almeno una riga verrà presentata nel file di analisi.
    4. Seleziona **OK**.

6. Nell'albero, seleziona **Radice\\Righe**, quindi seleziona **Aggiungi sequenza**.
7. Nella finestra di dialogo che viene visualizzata, effettuare le seguenti operazioni:

    1. Nel campo **Nome**, immetti **Campi**.
    2. Nel campo **Molteplicità** seleziona **Uno e solo uno**.
    3. Seleziona **OK**.

8. Nell'albero, seleziona **Radice\\Righe\\Campi**, quindi seleziona **Aggiungi**.
9. Nella finestra di dialogo che viene visualizzata, effettuare le seguenti operazioni:

    1. Nella struttura seleziona **Testo\\Stringa**.
    2. Nel campo **Nome** immetti **IBAN**.
    3.. Seleziona **OK**.

10. Seleziona **Salva**.

La configurazione è ora completata in modo che ogni riga del file di analisi contiene solo il numero IBAN.

![Configurazione del formato Formato di importazione per rendiconto bancario (esempio) nella pagina Progettazione formati.](../media/design-expressions-app-class-er-01.png)

## <a name="design-the-er-format-configuration--mapping-to-a-data-model"></a>Progettare la configurazione di formato ER - Mapping a un modello dati

Progetta un mapping del formato ER che utilizza le informazioni del file di analisi per compilare un modello di dati.

1. Nella pagina **Progettazione formati**, nel riquadro azioni, seleziona **Mapping formato a modello**.
2. Seleziona **Nuovo** nel riquadro azioni della pagina **Modello per mapping origine dati**.
3. Nel campo **Definizione**, seleziona **BankToCustomerDebitCreditNotificationInitiation**.
4. Nel campo **Nome** immetti **Mapping a modello di dati**.
5. Seleziona **Salva**.
6. Selezionare **Progettazione**.
7. Nella pagina **Progettazione mapping modello**, nell'albero **Tipi di origine dati**, seleziona **Dynamics 365 for Operations\\Classe**.
8. Nella sezione **Origini dati**, seleziona **Aggiungi radice** per aggiungere un'origine dati che richiami la logica applicativa esistente per la convalida dei codici IBAN.
9. Nella finestra di dialogo che viene visualizzata, effettuare le seguenti operazioni:

    1. Nel campo **Nome** immetti **Verifica\_codici**.
    2. Nel campo **Classe**, immetti o seleziona **ISO7064**.
    3. Seleziona **OK**.

10. Nell'albero **Tipi di origini dati**, effettuare le operazioni seguenti:

    1. Espandi l'origine dati **formato**.
    2. Espandi **format\\Root: Sequence(Root)**.
    3. Espandi **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Righe)**.
    4. Espandi **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Righe)\\Fields: Sequence 1..1 (Campi)**.

11. Nell'albero **Modello di dati**, effettua le operazioni seguenti:

    1. Espandi il campo **Pagamenti** del modello dati.
    2. Espandi **Pagamenti\\Conto creditore(CreditorAccount)**.
    3. Espandi **Pagamenti\\Conto creditore(CreditorAccount)\\Identificazione**.
    4. Espandi **Pagamenti\\Conto creditore(CreditorAccount)\\Identificazzione\\IBAN**.

12. Segui questi passaggi per associare i componenti del formato configurato ai campi del modello dati:

    1. Seleziona **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Righe)**.
    2. Seleziona **Pagamenti**.
    3. Selezionare **Associa**. In base a questa impostazione, ogni riga del file di analisi verrà considerata come un singolo pagamento.
    4. Seleziona **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Righe)\\Campi: Sequence 1..1 (Campi)\\IBAN: String(IBAN)**.
    5. Seleziona **Pagamenti\\Conto creditore(CreditorAccount)\\Identificazzione\\IBAN**.
    6. Selezionare **Associa**. In base a questa impostazione, il campo **IBAN** del modello di dati verrà riempito con il valore del file di analisi.

    ![Associazione dei componenti del formato ai campi del modello dati nella pagina Progettazione mapping modello.](../media/design-expressions-app-class-er-02.png)

13. Nella scheda **Convalide**, segui questi passaggi per aggiungere una regola di [convalida](../general-electronic-reporting-formula-designer.md#Validation) che mostra un messaggio di errore per qualsiasi riga nel file di analisi che contiene un codice IBAN non valido:

    1. Seleziona **Nuovo** e quindi **Modifica condizione**.
    2. Nella pagina **Designer formula**, nell'albero **Origine dati**, espandi l'origine dati **Verifica\_codici** che rappresenta la classe di applicazione **ISO7064** per visualizzare i metodi disponibili di questa classe.
    3. Seleziona **Verifica\_ codici\\verifyMOD1271\_36**.
    4. Selezionare **Aggiungi origine dati**.
    5. Nel campo **Formula**, immetti la seguente [espressione](../general-electronic-reporting-formula-designer.md#Binding): **Check\_codes.verifyMOD1271\_36(format.Root.Rows.Fields.IBAN)**.
    6. Selezionare **Salva**, quindi chiudere la pagina.
    7. Seleziona **Modifica messaggio**.
    8. Nella pagina **Designer formula**, nel campo **Formula**, immetti **CONCATENATE("Invalid IBAN code has been found:&nbsp;", format.Root.Rows.Fields.IBAN)**.
    9. Selezionare **Salva**, quindi chiudere la pagina.

    In base a queste impostazioni, la condizione di convalida restituirà *[FALSE](../er-formula-supported-data-types-primitive.md#boolean)* per qualsiasi codice IBAN non valido chiamando il metodo **verifyMOD1271\_36** esistente della classe di applicazione **ISO7064**. Si noti che il valore del codice IBAN è definito in modo dinamico in fase di esecuzione come argomento del metodo di chiamata in base al contenuto del file di testo di analisi.

    ![Regola di convalida nella pagina di progettazione del mapping del modello.](../media/design-expressions-app-class-er-03.png)

14. Seleziona **Salva**.
15. Chiudi la pagina **Progettazione mapping modello**, quindi chiudi la pagina **Modello per mapping origine dati**.

## <a name="run-the-format-mapping"></a>Eseguire il mapping di formato

Per scopi di verifica, esegui il mapping di formato utilizzando il file SampleIncomingMessage.txt scaricato in precedenza. L'output generato includerà i dati che verranno importati dal file di testo e popolati nel modello dati personalizzati al momento dell'importazione effettiva.

1. Seleziona **Esegui** nella pagina **Modello per mapping origine dati**.
2. Nella pagina **Parametri per la creazione di report elettronici**, seleziona **Esplora**, vai al file **SampleIncomingMessage.txt** che hai scaricato e selezionalo.
3. Seleziona **OK**.
4. Nota che la pagina **Modello per mapping origine dati** mostra un messaggio di errore relativo a un codice IBAN non valido.

    ![Risultato dell'esecuzione del mapping di formato nella pagina Modello per mapping origine dati.](../media/design-expressions-app-class-er-04.png)

5. Esaminare l'output in formato XML, che rappresenta i dati che sono stati importati dal file selezionato e trasferiti nel modello dati. Notare che solo tre righe del file di testo importato sono state elaborate senza errori. Il codice IBAN online 4 non è valido ed è stato saltato.

    ![Output XML.](../media/design-expressions-app-class-er-05.png)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
