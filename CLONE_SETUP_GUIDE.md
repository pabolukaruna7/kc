# 🔧 KitchenCloud - Setup After Cloning

## ⚠️ **IMPORTANT: Correct Setup After Git Clone**

If you're getting "index.html not found" error, follow these **EXACT STEPS**:

### **Step 1: Clone Repository**

```bash
git clone https://github.com/pabolukaruna7/kitchencloud.git
cd kitchencloud
```

### **Step 2: Install All Dependencies (CRITICAL)**

```bash
# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install

# Go back to project root
cd ..
```

### **Step 3: Start Servers in CORRECT ORDER**

**Terminal 1 (Backend Server):**

```bash
cd backend
npm run dev
# OR: node server.js

# You should see:
# "Server running on port 5000"
# "MongoDB connected"
```

**Terminal 2 (Frontend Server):**

```bash
cd frontend
npm start

# You should see:
# "webpack compiled successfully"
# "Local: http://localhost:3000"
```

### **Step 4: Access Application**

- **Frontend:** http://localhost:3000 ← **This is your main app!**
- **Backend API:** http://localhost:5000 ← **This is just the API**

## 🚨 **COMMON MISTAKES & FIXES**

### **Problem 1: "index.html not found"**

**Cause:** Trying to access backend URL instead of frontend  
**Fix:** Go to http://localhost:3000 (NOT 5000)

### **Problem 2: "Cannot GET /"**

**Cause:** Frontend server not running
**Fix:**

```bash
cd frontend
npm install  # Make sure dependencies are installed
npm start    # Start the React server
```

### **Problem 3: "Module not found"**

**Cause:** Dependencies not installed
**Fix:**

```bash
# Delete node_modules and reinstall
cd backend
rm -rf node_modules
npm install

cd ../frontend
rm -rf node_modules
npm install
```

### **Problem 4: "Port already in use"**

**Fix:**

```bash
# Kill existing processes
taskkill /F /IM node.exe
# Then restart servers
```

## ✅ **Complete Setup Checklist**

- [ ] Git clone completed
- [ ] `cd kitchencloud`
- [ ] `cd backend && npm install` ✅
- [ ] `cd ../frontend && npm install` ✅
- [ ] Backend running: `cd backend && npm run dev` ✅
- [ ] Frontend running: `cd frontend && npm start` ✅
- [ ] Can access http://localhost:3000 ✅
- [ ] Can register new user ✅
- [ ] Can login ✅
- [ ] Can add recipe ✅

## 🎯 **Quick Commands (Copy & Paste)**

```bash
# Complete setup in one go:
git clone https://github.com/pabolukaruna7/kitchencloud.git
cd kitchencloud
cd backend && npm install && cd ../frontend && npm install && cd ..

# Start backend (Terminal 1):
cd backend && npm run dev

# Start frontend (Terminal 2):
cd frontend && npm start

# Open browser to: http://localhost:3000
```

## 🌐 **URLs Explained**

| URL                   | Purpose            | What You See                               |
| --------------------- | ------------------ | ------------------------------------------ |
| http://localhost:3000 | **React Frontend** | 🎨 Full KitchenCloud website               |
| http://localhost:5000 | **Express API**    | 📋 JSON: "KitchenCloud API Server Running" |

**Always use localhost:3000 for the actual application!**
