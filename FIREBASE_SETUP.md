# Firebase Admin Panel Setup

## ⚠️ IMPORTANTE - Non esporre API key pubbliche!

**NON METTERE MAI API key Firebase in repository pubblici.** Google rileva e notifica chiavi esposte.

## Setup sicuro

### 1. Configurazione Firebase Web
Vai su Firebase Console → Project Settings → General → Your apps → Web app

Copia questi valori nel file `admin-panel-spot.html`:

```javascript
const firebaseConfig = {
  apiKey: "LA_TUA_API_KEY", 
  authDomain: "TUO_PROGETTO.firebaseapp.com",
  projectId: "TUO_PROGETTO_ID",
  storageBucket: "TUO_PROGETTO.appspot.com",
  messagingSenderId: "IL TUO SENDER_ID",
  appId: "IL TUO APP_ID"
};
```

### 2. Sicurezza API key
In Firebase Console → Project Settings → API Keys:
- **Limita la API key** solo ai domini autorizzati (pkour.it, *.github.io, localhost)
- **Limita le API** solo a "Identity Toolkit API" e "Firebase Authentication API"

### 3. Utenti Admin
Nel tuo progetto Firebase, assicurati che gli utenti admin abbiano:
- Ruolo admin nel tuo backend
- Email/password abilitati in Firebase Authentication

### 4. Deploy
- Il file è pronto per GitHub Pages
- Non contiene più API key hardcoded
- Usa Firebase SDK per login sicuro

## Flusso di login
1. Utente inserisce email/password admin
2. Firebase Auth SDK autentica
3. Token ID recuperato automaticamente
4. Backend verifica ruolo admin
5. Pannello mostrato solo se autorizzato

## Backup
Tieni una copia sicura della configurazione Firebase locale, non nel repository.
