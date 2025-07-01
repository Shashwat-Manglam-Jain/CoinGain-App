CoinGain-App
Overview
CoinGain-App is a cross-platform React Native application designed to manage a coin-based reward system, enabling users to earn, spend, and manage coins through a user-friendly interface. Built with React Native and Expo, it supports iOS, Android, and web platforms. Key features include user management, coin transactions, reward creation and redemption, notifications, and analytics, all integrated with a backend API. The app supports a dark/light theme toggle and is optimized for both mobile and web experiences.
Features

User Management: Search, view, edit, and delete user profiles (name, mobile, location, unique code).
Coin Transactions: Earn, send, or spend coins using user ID, name, mobile, or unique code.
Reward Management: Create, edit, or delete rewards with details like name, price, points required, and image uploads (max 5MB).
Redemption Requests: Approve or reject user requests to redeem rewards for coins.
Notifications: View, dismiss, or clear system notifications for user activities and system updates.
Analytics: Display system metrics (total users, coins transacted, pending redemptions, available rewards) and user progress bars.
Theme Support: Toggle between dark and light modes for a personalized UI experience.
Reward Carousel: Auto-scrolling horizontal carousel for showcasing rewards, pausable on touch.
Cross-Platform: Responsive UI optimized for iOS, Android, and web.
Authentication: Secure JWT token storage using AsyncStorage for user sessions.

Screenshots

Note: Screenshots will be added to the screenshots/ folder to showcase the app's UI.
Tech Stack

Frontend: React Native, React Native Paper, Expo
Backend: Node.js with Express.js (update with your specific backend framework)
Storage: AsyncStorage for local user data and JWT tokens
Networking: Axios for API requests
Styling: React Native StyleSheet with dynamic theming
Icons: @expo/vector-icons (MaterialIcons, MaterialCommunityIcons)
Key Dependencies:
react-native
react-native-paper
@react-native-async-storage/async-storage
expo-document-picker
axios



Prerequisites

Node.js (v16 or higher)
npm or Yarn
Expo CLI (npm install -g expo-cli)
Backend API server (configure API_BASE_URL in src/utils/api.js)
Android Studio or Xcode for mobile development
Modern web browser for web testing

Installation

Clone the Repository:
git clone https://github.com/Shashwat-Manglam-Jain/CoinGain-App.git
cd CoinGain-App


Install Dependencies:
npm install

or
yarn install


Configure Environment:

Create src/utils/api.js with your backend API URL (see code block below).
Ensure your backend API server is running and accessible.


Run the App:

For mobile (Expo):npx expo start

Scan the QR code with the Expo Go app on iOS/Android or use an emulator.
For web:npx expo start --web

Open http://localhost:19006 in your browser.



Project Structure
CoinGain-App/
├── src/
│   ├── components/
│   │   └── ThemeToggle.js      # Theme toggle component for dark/light mode
│   ├── screens/
│   │   └── Dashboard.js        # Main dashboard screen
│   ├── utils/
│   │   └── api.js             # API base URL configuration
│   └── ThemeContext.js        # Theme context for UI customization
├── assets/
│   └── placeholder.avif        # Placeholder image for rewards
├── package.json               # Project dependencies and scripts
├── .gitignore                 # Git ignore file
├── LICENSE                    # License file
└── README.md                  # This file

Configuration Files
Below are the key configuration files to set up the project. Save each in the specified path.
src/utils/api.js
This file defines the backend API base URL.
export const API_BASE_URL = 'https://your-api-base-url.com';

Save as: src/utils/api.js
.gitignore
This file excludes unnecessary files from version control.
node_modules/
.expo/
*.env
src/utils/api.js
dist/
build/

Save as: .gitignore
LICENSE
The project uses the MIT License.
MIT License

Copyright (c) 2025 Shashwat Manglam Jain

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Save as: LICENSE
Usage

Login: Authenticate with user or admin credentials. User data and JWT tokens are stored in AsyncStorage.
Navigate Tabs:
Home: View account overview, manage coin transactions, and browse rewards in a carousel.
Users: Search, edit, delete, or send coins to users (admin only).
Rewards: Create, edit, or delete rewards with image uploads (admin only).
Notifications: View, dismiss, or approve redemption requests.
Analytics: Access system stats and user progress visualizations.


Theme Toggle: Switch between dark and light modes using the toggle in the Home tab.
Logout: Clear AsyncStorage and return to the login screen.

API Endpoints
The app interacts with the following backend API endpoints (update with your actual endpoints):

GET /fetchdata/admin/:adminId: Fetch all users for admin.
GET /datafetch/rewards/:adminId: Fetch available rewards.
GET /datafetch/notifications/:adminId: Fetch system notifications.
GET /datafetch/redemptions/:adminId: Fetch redemption requests.
PUT /fetchdata/user/:userId: Update user profile details.
DELETE /fetchdata/user/:userId: Delete a user.
POST /fetchdata/user/:userId/addcoin: Send coins to a user.
POST /fetchdata/admin/:adminId/reward: Create a new reward.
PUT /fetchdata/admin/reward/:rewardId: Update a reward.
DELETE /fetchdata/admin/reward/:rewardId: Delete a reward.
DELETE /fetchdata/notification/:notificationId: Clear a notification.
DELETE /fetchdata/notifications: Clear all notifications.
PUT /fetchdata/redemption/:redemptionId/approve: Approve a redemption request.
PUT /fetchdata/redemption/:redemptionId/reject: Reject a redemption request.

Development Notes

Error Handling: Uses Alert.alert for user-facing errors (e.g., API failures, invalid inputs).
Image Upload: Supports images up to 5MB (web: HTML input; mobile: expo-document-picker).
Performance: Optimized FlatList with initialNumToRender, maxToRenderPerBatch, and windowSize for smooth rendering.
Carousel: Rewards carousel auto-scrolls every 1 second, pausing on touch. Adjust interval in Dashboard.js if needed.
Debugging: Console logs for tab changes, data fetching, and carousel scrolling to aid debugging.
Known Issues:
Ensure API_BASE_URL is correctly set to avoid network errors.
Test image uploads on both web and mobile for compatibility.
Verify JWT authentication to prevent unauthorized API access.



Contributing

Fork the repository.
Create a feature branch:git checkout -b feature/your-feature


Commit your changes:git commit -m 'Add your feature'


Push to the branch:git push origin feature/your-feature


Open a Pull Request on GitHub.

License
This project is licensed under the MIT License. See the LICENSE section above for details.
Contact
For issues or feature requests, create a GitHub issue or contact shashwatmanglamjain@gmail.com.
Acknowledgements

React Native
Expo
React Native Paper
Axios
Inspired by Best-README-Template
