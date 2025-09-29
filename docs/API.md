# API Documentation - Voice Biometric System

## Desarrollador: Luisana Ceballos Ceballos
## Empresa: Redessip Perú

### Base URL
```
https://api.redessip.pe/biometric
```
### Endpoints

#### 1. Iniciar Verificación Biométrica
```http
POST /biometric/initiate
```

**Request Body:**
```json
{
  "phoneNumber": "+51999888777",
  "transactionType": "TRANSFER",
  "amount": 5000
}
```

**Response:**
```json
{
  "success": true,
  "sessionId": "uuid-here",
  "message": "Verificación biométrica iniciada",
  "riskLevel": "MEDIUM"
}
```

#### 2. Estado de Verificación
```http
GET /biometric/status/:sessionId
```

**Response:**
```json
{
  "sessionId": "uuid-here",
  "status": "IN_PROGRESS",
  "timestamp": "2024-01-15T10:30:00Z"
}
```

#### 3. Estadísticas del Sistema
```http
GET /biometric/stats
```

**Response:**
```json
{
  "company": "Redessip Perú",
  "developer": "Luisana Ceballos Ceballos",
  "stats": {
    "totalProfiles": 5000,
    "todayVerifications": 250,
    "successRate": "94.7%",
    "avgResponseTime": "1.8s"
  }
}
```

### Webhooks de Twilio

- `/biometric/enrollment/:sessionId` - Proceso de enrollment
- `/biometric/verify/:sessionId` - Proceso de verificación
- `/biometric/call-status` - Estado de llamadas
- `/biometric/recording-complete` - Grabación completada

---
Desarrollado por Luisana Ceballos Ceballos - ceballosluisana37@gmail.com
