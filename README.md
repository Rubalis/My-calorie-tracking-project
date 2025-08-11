# 🍎 CalorieTracker - Smart Nutrition Tracking App

A beautiful, modern web-based calorie tracking application that helps you monitor your daily nutrition intake with an intuitive interface and powerful analytics.

## ✨ Features

- **📊 Daily Nutrition Tracking**: Log your meals with detailed macro breakdowns
- **🔍 AI-Powered Food Search**: Search through thousands of foods with instant results
- **📱 Progressive Web App**: Install on your iPhone like a native app
- **📸 Photo Food Recognition**: Take photos of your food for automatic identification and logging
- **📈 Visual Analytics**: Beautiful charts showing your daily progress
- **💾 Local Storage**: Your data stays on your device for privacy
- **🎨 Modern Design**: Beautiful glassmorphism UI with responsive design
- **⚡ Performance Optimized**: Fast and smooth experience with smart caching

### 🎯 **Daily Nutrition Tracking**
- Track calories, protein, carbs, and fat intake
- Set daily nutrition goals (customizable)
- Visual progress bars and real-time updates
- Automatic daily reset for fresh tracking

### 🍽️ **Meal Organization**
- Organize foods by meal type (Breakfast, Lunch, Dinner, Snacks)
- Easy tab navigation between meals
- Add/remove foods from specific meals
- Clean, organized meal lists

### 🔍 **Food Management**
- **Quick Add**: Pre-loaded common foods with accurate nutrition data
- **Search**: Built-in food database with popular items
- **Custom Foods**: Add your own foods with custom nutrition values
- **Smart Search**: Automatic suggestions and fallback to custom entry

### 📊 **Analytics & Charts**
- **Daily Calories Chart**: Visual representation of consumed vs. remaining calories
- **Macro Distribution**: Doughnut charts showing protein, carbs, and fat breakdown
- **Real-time Updates**: Charts update automatically as you add/remove foods
- **Responsive Design**: Beautiful charts that work on all devices

### 💾 **Data Persistence**
- Local storage for data persistence
- Automatic daily data reset
- No account required - your data stays on your device

### 📱 **Responsive Design**
- Works perfectly on desktop, tablet, and mobile
- Modern glassmorphism design with beautiful gradients
- Smooth animations and hover effects
- Optimized for touch devices

## 🚀 Getting Started

### Quick Start
1. **Download** all files to a folder
2. **Open** `index.html` in your web browser
3. **Start tracking** your nutrition immediately!

### AI-Powered Food Search Setup
1. **Get API Keys**: Sign up at [Nutritionix Developer Portal](https://developer.nutritionix.com/)
2. **Update Keys**: Replace the API keys in `script.js` with your own
3. **Enjoy**: Instant food search with thousands of options!

### Photo Recognition Setup
1. **Choose API**: Set up a food recognition API (see `food-recognition-setup.md`)
2. **Get API Key**: Obtain your API key from the chosen service
3. **Update Code**: Replace `YOUR_API_KEY` in `script.js`
4. **Start Using**: Take photos of your food for automatic identification!

## 🎮 How to Use

### **1. Add Foods to Your Day**
- **Quick Add**: Click any of the quick-add buttons for common foods
- **Search**: Type a food name and click search
- **Custom**: Use the custom food form for foods not in the database

### **2. Organize by Meals**
- Click on meal tabs (Breakfast, Lunch, Dinner, Snacks)
- Add foods to the appropriate meal
- Switch between meals to see what you've eaten

### **3. Monitor Your Progress**
- View daily totals in the summary cards
- Watch the calorie progress bar fill up
- Check charts for visual nutrition breakdown

### **4. Manage Your Foods**
- Delete foods you've added by mistake
- All changes are automatically saved
- Data persists between browser sessions

## 🎨 Design Features

### **Modern UI Elements**
- Glassmorphism design with backdrop blur effects
- Beautiful gradient backgrounds
- Smooth hover animations
- Professional color scheme

### **Interactive Components**
- Hover effects on buttons and cards
- Smooth transitions and animations
- Responsive grid layouts
- Touch-friendly mobile interface

### **Visual Feedback**
- Success notifications when adding foods
- Progress bars and charts
- Color-coded nutrition information
- Clear visual hierarchy

## 🛠️ Technical Details

### **Built With**
- **HTML5**: Semantic markup and modern structure
- **CSS3**: Grid, Flexbox, CSS Variables, Animations
- **Vanilla JavaScript**: ES6+ classes and modern APIs
- **Chart.js**: Beautiful, responsive charts
- **Local Storage**: Client-side data persistence

### **Browser Support**
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+
- Mobile browsers (iOS Safari, Chrome Mobile)

### **Performance Features**
- Efficient DOM manipulation
- Optimized chart rendering
- Minimal external dependencies
- Fast local storage operations

## 🔧 Customization

### **Modify Daily Targets**
Edit the `targets` object in `script.js`:
```javascript
this.targets = {
    calories: 2000,    // Your daily calorie goal
    protein: 150,      // Your daily protein goal (g)
    carbs: 250,        // Your daily carbs goal (g)
    fat: 65           // Your daily fat goal (g)
};
```

### **Add More Quick Foods**
Extend the `getQuickFoodData` method in `script.js`:
```javascript
const quickFoods = {
    // ... existing foods ...
    yogurt: { name: 'Greek Yogurt', calories: 130, protein: 23, carbs: 9, fat: 0.5 },
    // Add more foods here
};
```

### **Customize Colors**
Modify CSS variables in `styles.css`:
```css
:root {
    --primary-color: #667eea;
    --secondary-color: #764ba2;
    --success-color: #48bb78;
    /* Add more custom colors */
}
```

## 📱 Mobile Experience

The app is fully optimized for mobile devices:
- Touch-friendly buttons and interactions
- Responsive grid layouts
- Mobile-optimized charts
- Swipe-friendly meal navigation
- Optimized for portrait and landscape orientations

## 🔒 Privacy & Data

- **100% Local**: All data stays on your device
- **No Tracking**: No analytics or external data collection
- **No Accounts**: No login required, no data sent to servers
- **Your Control**: Delete data anytime by clearing browser storage

## 🚀 Future Enhancements

Potential features for future versions:
- Weekly/monthly nutrition reports
- Food barcode scanning
- Recipe creation and tracking
- Social sharing features
- Export data to CSV/PDF
- Dark mode toggle
- Multiple user profiles
- Integration with fitness apps

## 🤝 Contributing

Feel free to enhance this app:
1. Fork the repository
2. Create a feature branch
3. Make your improvements
4. Submit a pull request

## 📄 License

This project is open source and available under the MIT License.

## 🆘 Support

If you encounter any issues:
1. Check that your browser supports modern JavaScript
2. Ensure all files are in the same directory
3. Try refreshing the page
4. Check browser console for error messages

---

**Enjoy tracking your nutrition with CalorieTracker! 🎉**

*Built with ❤️ using modern web technologies*

## 📸 Photo Recognition Feature

The app now includes **AI-powered photo recognition** for food logging:

### How It Works
- **Take Photo**: Use your device's camera to capture food images
- **Upload Photo**: Or select existing photos from your gallery
- **AI Analysis**: The app identifies foods and estimates nutrition
- **Auto-Logging**: Add identified foods directly to your daily log

### Setup Required
- **API Key**: Get a free API key from LogMeal, Google Vision, or Clarifai
- **HTTPS**: Required for camera access in production
- **Permissions**: Grant camera access when prompted

### Fallback System
- **Local Recognition**: Works even without external APIs
- **Smart Estimation**: Estimates nutrition based on food type
- **Always Available**: Feature works in all scenarios

See `food-recognition-setup.md` for detailed setup instructions!
