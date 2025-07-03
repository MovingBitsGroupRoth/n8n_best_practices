# n8n Best Practices

## Test

### Testdaten

- Lokal als JSON-Array in JSON-File
- Einlesen mit Read/Write Files Node
- - Wenn Docker, dann aus Volume, das auf /files zeigt
- Extract from File Node (JSON)

### Code in Code Node testen

Code Node verwende ich sehr ungern. Business-Logik hat die unangenehme Eigenschaft schnell umfangreich zu werden

## Business Logik

Ablauf-Diagramm:

Code Node (Array Kunden-IDs)
         |
Split In Batches (Batch size: 1)
         |
HTTP Request Node (API Call mit {{$json.kundenId}})
         |
   (optional) Merge


