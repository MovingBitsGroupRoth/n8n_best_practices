# n8n Best Practices

## Test

### Testdaten

- Lokal als JSON-Array in JSON-Datei
- Einlesen mit Read/Write Files Node
-- Wenn Docker, dann JSON-Datei aus Volume holen, das auf /files zeigt
- Extract from File Node (JSON)

### Code in Code Node testen

Code Node verwende ich sehr ungern. Business-Logik hat die unangenehme Eigenschaft schnell umfangreich zu werden

## Business Logik

### Webservice-Aufrufe für jede Kunden-Id 

```matematica
Code Node (Array Kunden-IDs)
         |
Split In Batches Node (Batch size: 1)
         |
HTTP Request Node (API Call mit {{$json.kundenId}})
         |
   (optional) Merge Node
```
Ablauf-Diagramm
