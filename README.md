# GPT Mini - AI Chat Mobile App

Mobile application yang menggabungkan **ChatGPT** dan **Google Gemini** dalam satu platform.

## 🚀 Fitur Utama

- ✅ **Dual AI Integration** - ChatGPT + Google Gemini dalam satu respon
- ✅ **Google OAuth Login** - Autentikasi aman dengan akun Google
- ✅ **Chat History** - Simpan dan akses riwayat chat
- ✅ **File Upload** - Kirim gambar dan dokumen
- ✅ **Rate Limiting** - Smart rate limiting untuk API calls
- ✅ **User Profiles** - Manajemen profil pengguna
- ✅ **Real-time Sync** - Sinkronisasi data real-time dengan Firebase

## 📱 Tech Stack

### Frontend
- **React Native** dengan Expo
- **Redux** untuk state management
- **Firebase** untuk real-time database
- **AsyncStorage** untuk local storage

### Backend
- **Node.js** + Express
- **Firebase Admin SDK**
- **OpenAI API** untuk ChatGPT
- **Google Generative AI API** untuk Gemini
- **Rate Limiter** untuk throttling

### Database & Auth
- **Firebase Firestore** untuk database
- **Firebase Authentication** untuk Google OAuth
- **Firebase Storage** untuk file uploads

## 🔧 Setup & Installation

### Prerequisites
- Node.js >= 16
- Expo CLI
- Firebase Account
- OpenAI API Key
- Google Gemini API Key

### 1. Clone Repository
```bash
git clone https://github.com/aliffadhil369-wq/gpt-mini.git
cd gpt-mini
```

### 2. Setup Backend
```bash
cd server
npm install
cp .env.example .env
# Edit .env dengan API keys Anda
npm start
```

### 3. Setup Mobile App
```bash
cd mobile
npm install
# atau
expo install
cp .env.example .env
# Edit .env dengan Firebase config
expo start
```

### 4. Setup Firebase
1. Buat project di [Firebase Console](https://console.firebase.google.com)
2. Enable Firestore Database
3. Enable Authentication (Google Sign-In)
4. Enable Storage
5. Copy credentials ke `.env` files

### 5. Dapatkan API Keys
- **OpenAI API**: https://platform.openai.com/api-keys
- **Google Gemini API**: https://makersuite.google.com/app/apikey

## 📋 Environment Variables

### Backend (.env)
```
PORT=5000
NODE_ENV=development

# Firebase
FIREBASE_API_KEY=xxx
FIREBASE_AUTH_DOMAIN=xxx
FIREBASE_PROJECT_ID=xxx
FIREBASE_STORAGE_BUCKET=xxx
FIREBASE_MESSAGING_SENDER_ID=xxx
FIREBASE_APP_ID=xxx

# APIs
OPENAI_API_KEY=xxx
GOOGLE_GEMINI_API_KEY=xxx

# Rate Limiting
RATE_LIMIT_WINDOW=15
RATE_LIMIT_MAX_REQUESTS=30
```

### Mobile (.env)
```
FIREBASE_API_KEY=xxx
FIREBASE_AUTH_DOMAIN=xxx
FIREBASE_PROJECT_ID=xxx
FIREBASE_STORAGE_BUCKET=xxx
FIREBASE_MESSAGING_SENDER_ID=xxx
FIREBASE_APP_ID=xxx

API_URL=http://localhost:5000
```

## 📚 Project Structure

```
gpt-mini/
├── mobile/
│   ├── app.json
│   ├── package.json
│   ├── .env.example
│   ├── app/
│   │   ├── index.tsx
│   │   └── (tabs)/
│   ├── screens/
│   │   ├── ChatScreen.tsx
│   │   ├── ProfileScreen.tsx
│   │   └── SettingsScreen.tsx
│   ├── components/
│   │   ├── ChatBubble.tsx
│   │   ├── InputBox.tsx
│   │   └── FileUpload.tsx
│   └── services/
│       ├── firebase.ts
│       ├── api.ts
│       └── auth.ts
│
├── server/
│   ├── package.json
│   ├── .env.example
│   ├── src/
│   │   ├── index.ts
│   │   ├── routes/
│   │   │   ├── auth.ts
│   │   │   ├── chat.ts
│   │   │   └── user.ts
│   │   ├── controllers/
│   │   │   ├── chatController.ts
│   │   │   ├── authController.ts
│   │   │   └── userController.ts
│   │   ├── middleware/
│   │   │   ├── auth.ts
│   │   │   ├── rateLimiter.ts
│   │   │   └── errorHandler.ts
│   │   ├── config/
│   │   │   └── firebase.ts
│   │   └── utils/
│   │       ├── openai.ts
│   │       └── gemini.ts
│   └── tsconfig.json
│
└── README.md
```

## 🔐 Rate Limiting

Sistem rate limiting yang smart:
- **15 menit** per window
- **30 requests** per user per window
- **Exponential backoff** untuk retry
- **Queue system** untuk pending requests

## 📖 API Endpoints

### Authentication
- `POST /api/auth/login` - Google OAuth login
- `POST /api/auth/logout` - Logout
- `GET /api/auth/me` - Get current user

### Chat
- `POST /api/chat/message` - Send message (ChatGPT + Gemini)
- `GET /api/chat/history` - Get chat history
- `DELETE /api/chat/history/:id` - Delete chat

### User
- `GET /api/user/profile` - Get user profile
- `PUT /api/user/profile` - Update profile
- `POST /api/user/upload` - Upload file

## 🚦 Getting Started

1. **Setup Firebase & API Keys** (lihat section Setup)
2. **Run Backend**: `cd server && npm start`
3. **Run Mobile App**: `cd mobile && expo start`
4. **Test di simulator atau physical device**

## 📝 Development

### Build Mobile App
```bash
cd mobile
eas build --platform ios   # iOS
eas build --platform android # Android
```

### Deploy Backend
```bash
# Deploy ke Heroku / Railway / Vercel
cd server
npm run build
```

## 🐛 Troubleshooting

### Firebase Connection Error
- Pastikan credentials di `.env` benar
- Check Firebase project security rules

### API Rate Limit
- Tunggu 15 menit atau upgrade API plan
- Check rate limiter logs di backend

### Expo Build Error
- Clear cache: `expo start -c`
- Update dependencies: `npm update`

## 📄 License

MIT

## 👨‍💻 Author

aliffadhil369-wq

---

**Happy Coding! 🎉**
