# Consegna - Lezione 01

## Obiettivo

Trasformare un prompt vago in un prompt piu' utilizzabile, controllabile e verificabile.

Non devi risolvere il task. Devi migliorare la richiesta.

## Repository Di Lavoro

Lavora nel tuo fork della repo:

```txt
aicu-l01-prompt-refinement
```

Ogni prompt vive in una cartella dedicata:

```txt
prompts/
  <caso>/
    prompt-originale.md
    diagnosi.md
    prompt-migliorato.md
```

Leggi `prompt-originale.md`, compila `diagnosi.md` e salva la nuova versione in `prompt-migliorato.md`.

## Scenario

Stiamo lavorando su una piccola app didattica di gestione ticket.

Il tema e' lo stato in cui la lista dei ticket aperti e' vuota. Questo caso si chiama `empty state`: l'interfaccia deve comunicare chiaramente che non ci sono elementi da mostrare.

## Prompt Di Partenza

Scegli una cartella in `prompts/`. I prompt di partenza saranno simili a questi:

```txt
Sistema la pagina dei ticket.
```

```txt
Aggiungi un messaggio carino quando non ci sono ticket aperti.
```

```txt
Crea una PR per migliorare tutta la gestione dei ticket aperti con UX migliore e test.
```

## Fase 1 - Diagnosi Senza AI

Per 5 minuti non usare AI.

Compila `diagnosi.md`:

- informazioni mancanti;
- ambiguita';
- rischio di scope troppo largo;
- output non verificabile.
- se bastano istruzioni zero-shot o se servono esempi few-shot.

## Fase 2 - Refinement Con AI

Usa il tuo tool AI per migliorare il prompt.

Prompt consigliato:

```txt
Aiutami a migliorare questo prompt.
Non risolvere il task.
Dimmi prima quali informazioni mancano.
Poi proponi una versione migliore.
```

## Strategia Del Prompt

Nel prompt migliorato devi indicare quale strategia stai usando:

- `zero-shot`: dai istruzioni, contesto, confini, output e verifica senza esempi;
- `few-shot`: aggiungi 1-2 esempi brevi di input/output per mostrare formato o criterio atteso.

Usa few-shot solo se l'esempio chiarisce una sfumatura che a parole resta ambigua. Non usare esempi che risolvono gia' il task o anticipano codice.

Non chiedere all'AI di mostrare tutta la chain-of-thought. Se ti serve capire il perche' della proposta, chiedi invece:

```txt
Elenca le assunzioni principali, il criterio usato e la verifica proposta.
Poi proponi il prompt migliorato.
```

## Output Obbligatorio

Nel caso scelto devono essere compilati:

```txt
diagnosi.md
prompt-migliorato.md
```

Se riesci, compila anche:

```txt
setup-check.md
llm-observation.md
```

## Vincoli

- Non chiedere codice.
- Non chiedere una patch.
- Non aprire una PR.
- Non aggiungere `AGENTS.md` o `prompt-kit/`: arriveranno in L03.
- Non allargare il task a redesign, filtri, routing o nuove feature.
- Non incollare dati personali, credenziali, token, file `.env`, codice aziendale o log sensibili.

## Scala Di Qualita'

Classifica il prompt finale:

- `Vago`: l'AI deve inventarsi troppo.
- `Utilizzabile`: l'AI puo' iniziare senza indovinare tutto.
- `Controllabile`: puoi limitare scope, file, permessi e verifica.
- `Consegnabile`: puoi mostrare richiesta, vincoli e controllo a un'altra persona.

## Rubrica Di Controllo

Prima di classificare il prompt, controlla se risponde a queste domande:

| Criterio | Domanda |
| --- | --- |
| Contesto | L'AI sa in quale scenario sta lavorando? |
| Confini | E' chiaro cosa non deve fare? |
| Output | E' chiara la forma della risposta attesa? |
| Verifica | Esiste una prova di controllo? |
| Non-azione | E' chiaro che oggi non deve produrre codice, patch o PR? |
| Esempi | E' chiaro se il prompt resta zero-shot o usa esempi few-shot? |
| Evidenze | Chiede assunzioni, criterio e verifica invece di chain-of-thought estesa? |

## Pronto Quando

- Hai scelto un prompt di partenza.
- Hai scritto una diagnosi operativa.
- Hai prodotto un prompt migliorato.
- Hai indicato se il prompt finale e' zero-shot o few-shot e perche'.
- Hai compilato la rubrica di controllo.
- Hai classificato il risultato.
- Sai spiegare in 60 secondi perche' e' piu' controllabile.
- Hai committato e pushato il lavoro nel tuo fork.

> **Team Mode**
> Una chat AI privata e' difficile da revisionare. Una traccia breve nel repo permette a un collega o docente di capire richiesta, vincoli e output atteso.
