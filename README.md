# mistral-large-workflow

Ein Mistral-Workflow, der eine Eingabe an **Mistral Large 4** (`mistral-large-latest`) schickt und die Antwort zurückgibt. Er wird von einem Vibe-Skill genutzt, der bei Bedarf automatisch eine zweite Meinung von Mistral Large 4 einholt.

## Workflow

Name: `ml4-chat`

Eingabe:

```json
{
  "prompt": "Frage an Mistral Large 4",
  "system_prompt": "Optionale Vorgabe für Rolle und Stil"
}
```

Ausgabe:

```json
{
  "answer": "Antwort des Modells",
  "model": "mistral-large-latest"
}
```

## Struktur

- `apps/worker/src/worker/workflows/ml4_chat.py` – der Workflow
- `deploy/docker/Dockerfile.worker` – Container-Bau für die verwaltete Bereitstellung
- Erzeugt mit der Mistral CLI (`mistral workflows init`)

## Bereitstellung

Der Worker läuft als verwaltete Bereitstellung auf der Mistral-Plattform. Der Aufruf erfolgt über die Workflows-API oder aus Vibe heraus.
