---
title: Errore del percorso di certificazione durante la configurazione della connessione dell'app
description: Se l'app Warehouse Management mostra l'errore "L'ancoraggio di trust per il percorso di certificazione non è stato trovato", utilizzare questa pagina per risolvere o aggirare il problema.
author: ivanv-microsoft
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: WMA
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e4a36874ac4982c9c92a7dcc17c13c7c7c02bf8c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476771"
---
# <a name="trust-anchor-for-certification-path-not-found-when-setting-up-app-connection"></a>Ancoraggio di trust per il percorso di certificazione non trovato durante la configurazione della connessione dell'app

## <a name="symptoms"></a>Sintomi

Quando si tenta di connettersi a Supply Chain Management, l'app Warehouse Management potrebbe mostrare il seguente messaggio di errore:

> java.security.cert.certPathValidatorException: l'ancoraggio attendibile per il percorso di certificazione non è stato trovato.

Questo problema può interessare i dispositivi con le seguenti proprietà:

- **Versione del sistema operativo**: Android 4.4.x (come Zebra TC55). Questo problema non si verifica sulle versioni Android recenti.
- **Ubicazione di Supply Chain Management**: cloud
- **Modalità di connessione**: segreto client o certificato

## <a name="possible-cause"></a>Possibile causa

Microsoft potrebbe aver aggiornato i certificati SSL del server utilizzati da Supply Chain Management. Di conseguenza, il certificato radice e/o uno dei certificati intermedi potrebbe essere cambiato, quindi il nuovo certificato non è nell'elenco dei certificati di sistema attendibili per il dispositivo mobile. Le versioni più recenti di Android aggiornano automaticamente gli elenchi dei certificati attendibili, a differenza di Android 4.4.x.

## <a name="resolution"></a>Risoluzione

Per risolvere questo problema, effettuare una delle seguenti operazioni.

- Utilizzare la soluzione alternativa descritta nella sezione successiva per aggiornare ogni dispositivo pertinente.
- *Potrebbe* essere possibile contattare Zebra o Google per ottenere un aggiornamento dei certificati dell'autorità di certificazione attendibile (CA) del sistema. Tuttavia, ciò non è confermato.
- Se possibile, valutare la possibilità di sostituire i dispositivi meno recenti con dispositivi che eseguono una versione più recente di Android (in cui i certificati CA attendibili vengono aggiornati automaticamente).

### <a name="workaround"></a>Soluzione alternativa

#### <a name="step-1-export-the-new-root-certificate-from-supply-chain-management"></a>Passaggio 1: esportare il nuovo certificato radice da Supply Chain Management

Scaricare manualmente il nuovo certificato radice utilizzando il browser Internet procedendo come segue:

1. Accedere a Dynamics Supply Chain Management e aprire la prima pagina.

1. Nella barra degli indirizzi del browser, selezionare l'icona del lucchetto per aprire la finestra di dialogo **La posizione è sicura**.
1. Nella finestra di dialogo, selezionare **Certificato (valido)** per aprire la finestra **Certificato** per tale certificato.
1. Aprire la scheda **Percorso di certificazione** della finestra **Certificato**.
1. Selezionare il primo certificato mostrato nella gerarchia. (Questo è il certificato radice).
1. Aprire la scheda **Dettagli** della finestra **Certificato**.
1. Selezionare il pulsante **Copia su file** nella parte inferiore della scheda **Dettagli**.
1. Si apre **Esportazione guidata certificati**. Selezionare **Avanti** per continuare.
1. Si apre la pagina **Formato file di esportazione**. Selezionare **X.509 binario codificato DER (.CER)**. Quindi, selezionare **Avanti** per continuare.
1. Si apre la pagina **File da esportare**; specificare un nome file e una posizione. Quindi, selezionare **Avanti** per continuare.
1. Si apre la pagina **Completamento esportazione guidata certificati** che mostra il risultato dell'esportazione. Selezionare **Fine**.

#### <a name="step-2-install-the-downloaded-certificate-onto-the-affected-devices"></a>Passaggio 2: installare il certificato scaricato sui dispositivi interessati

Installare il certificato scaricato effettuando le seguenti operazioni:

1. Trasferire il certificato scaricato nel passaggio precedente nel dispositivo che si desidera aggiornare. Ad esempio, è possibile utilizzare una scheda SD o una connessione di rete per rendere disponibile il file sul dispositivo.
1. Aprire le impostazioni di sicurezza per il dispositivo e scegliere l'opzione di menu per installare un certificato da un file. (I passaggi esatti per questa procedura variano in base al dispositivo e alla versione del sistema operativo).
1. Il nuovo certificato viene ora mostrato sulla scheda **Utente** per i certificati attendibili.
1. Ripetere questa procedura per ogni dispositivo interessato.
