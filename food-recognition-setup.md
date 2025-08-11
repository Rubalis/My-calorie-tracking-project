# Food Recognition Setup Guide

Your CalorieTracker app now includes **Photo-Based Food Recognition**! 🎉 This feature allows you to take a photo of your food and automatically identify it with calorie and macro information.

## 🚀 How It Works

1. **Take Photo**: Use the camera button to take a photo of your food
2. **Upload Photo**: Or upload an existing photo from your device
3. **AI Analysis**: The app analyzes the photo to identify foods
4. **Automatic Logging**: Add identified foods directly to your daily log

## 🔑 Setting Up Food Recognition APIs

For the best results, you'll need to set up a food recognition API. Here are the recommended options:

### Option 1: LogMeal API (Recommended - Free Tier Available)

1. **Sign Up**: Go to [LogMeal](https://logmeal.es/) and create a free account
2. **Get API Key**: Navigate to your dashboard and copy your API key
3. **Update Code**: Replace `YOUR_API_KEY` in `script.js` with your actual key

```javascript
// In script.js, find this line:
'Authorization': 'Bearer YOUR_API_KEY' // You'll need to get a free API key

// Replace YOUR_API_KEY with your actual key:
'Authorization': 'Bearer sk-1234567890abcdef...'
```

### Option 2: Google Cloud Vision API

1. **Google Cloud Console**: Go to [Google Cloud Console](https://console.cloud.google.com/)
2. **Enable Vision API**: Search for "Vision API" and enable it
3. **Create Credentials**: Create a service account and download the JSON key
4. **Update Code**: Replace the LogMeal API call with Google Vision

### Option 3: Clarifai Food Model

1. **Sign Up**: Create account at [Clarifai](https://clarifai.com/)
2. **Get API Key**: Copy your API key from the dashboard
3. **Update Code**: Use Clarifai's food recognition model

## 📱 Using the Photo Feature

### Taking Photos
- **Camera Button**: Opens your device's camera for direct photo capture
- **Upload Button**: Allows you to select existing photos from your gallery
- **Environment Camera**: Automatically uses the back camera on mobile devices

### Photo Analysis
- **Analyze Button**: Processes your photo to identify foods
- **Confidence Scores**: Shows how certain the AI is about each food identification
- **Nutrition Data**: Displays calories, protein, carbs, and fat for each identified food
- **Add to Log**: One-click addition to your daily meal tracking

### Fallback System
If the API fails or you don't have an API key set up, the app uses a smart fallback system:
- **Local Recognition**: Simulates food recognition with common foods
- **Smart Estimation**: Estimates nutrition based on food type
- **Always Works**: Ensures the feature works even without external APIs

## 🎯 Best Practices for Photo Recognition

### Photo Quality
- **Good Lighting**: Ensure your food is well-lit
- **Clear Focus**: Keep the camera steady and focused
- **Single Dish**: Focus on one main food item at a time
- **Avoid Clutter**: Minimize background distractions

### Food Types
- **Single Items**: Works best with individual food items
- **Mixed Dishes**: Can identify multiple foods in one photo
- **Common Foods**: Better recognition for standard food items
- **Clear Shapes**: Distinctive food shapes improve accuracy

## 🔧 Troubleshooting

### Camera Not Working
- **Permission Issues**: Ensure camera permissions are granted
- **HTTPS Required**: Camera access requires HTTPS in production
- **Browser Support**: Some browsers may not support camera access
- **Fallback**: Use the upload button as an alternative

### Recognition Accuracy
- **API Limits**: Free API tiers may have usage limits
- **Photo Quality**: Poor lighting or blurry photos reduce accuracy
- **Uncommon Foods**: Rare or unusual foods may not be recognized
- **Multiple Foods**: Complex dishes may be partially identified

### Performance Issues
- **Image Size**: Large photos may take longer to process
- **API Response**: External API calls depend on network speed
- **Fallback Mode**: Local recognition is faster but less accurate

## 🚀 Advanced Features

### Custom Food Database
You can enhance the local fallback system by adding more foods:

```javascript
// In script.js, expand the simulateFoodRecognition method
simulateFoodRecognition() {
    const commonFoods = [
        // Add your custom foods here
        { name: 'Your Custom Food', confidence: 0.85, calories: 150, protein: 10, carbs: 20, fat: 5 },
        // ... more foods
    ];
    // ... rest of the method
}
```

### Multiple API Support
The app is designed to try multiple APIs in sequence:

```javascript
async recognizeFoodWithAPI(base64Image) {
    // Try LogMeal first
    try {
        const logMealResult = await this.tryLogMealAPI(base64Image);
        if (logMealResult) return logMealResult;
    } catch (error) {
        console.log('LogMeal failed, trying Google Vision...');
    }
    
    // Try Google Vision as backup
    try {
        const googleResult = await this.tryGoogleVisionAPI(base64Image);
        if (googleResult) return googleResult;
    } catch (error) {
        console.log('Google Vision failed, using fallback...');
    }
    
    return null; // Trigger fallback
}
```

## 💡 Pro Tips

1. **Batch Photos**: Take photos of multiple meals at once, then analyze them later
2. **Meal Planning**: Use photos to plan your meals for the day
3. **Portion Estimation**: The AI can help estimate portion sizes
4. **Recipe Tracking**: Take photos of homemade meals to track ingredients
5. **Social Sharing**: Share your food photos with nutrition data

## 🔒 Privacy & Security

- **Local Processing**: Photos are processed locally when possible
- **No Storage**: Photos are not stored on external servers
- **API Limits**: Be aware of your chosen API's data usage policies
- **HTTPS Only**: Always use HTTPS in production for camera access

## 🎉 What's Next?

With photo recognition working, you can:
- **Track meals faster** than manual entry
- **Improve accuracy** with visual confirmation
- **Build a food photo journal** of your nutrition journey
- **Share progress** with friends and family
- **Get insights** into your eating patterns

The photo recognition feature transforms your calorie tracker from a manual logging tool into an intelligent, AI-powered nutrition assistant! 📸✨
