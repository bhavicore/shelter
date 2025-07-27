# Emergency Shelter Location System

A real-time web application for locating and navigating to emergency shelters during crisis situations. Built with React, TypeScript, Express.js, and Leaflet maps.

## 🚀 Features

### Core Functionality
- **Real-time Shelter Tracking**: Live updates of shelter occupancy every 30 seconds
- **Interactive Map**: Visual shelter locations with color-coded occupancy indicators
- **Smart Routing**: Dijkstra's algorithm for optimal pathfinding to shelters
- **Location Services**: Automatic user location detection and nearest shelter selection
- **Advanced Filtering**: Filter shelters by food availability, space, and occupancy levels

### User Interface
- **Responsive Design**: Mobile-first design that works on all devices
- **Real-time Updates**: Live occupancy data and availability status
- **Visual Indicators**: Color-coded markers for quick shelter assessment
- **Route Planning**: Distance and time estimates with turn-by-turn directions

## 🏗️ Architecture

### Frontend (React + TypeScript)
- **Components**: Modular React components with TypeScript
- **State Management**: React hooks for local state management
- **Maps**: Leaflet.js for interactive mapping
- **Styling**: Tailwind CSS with custom UI components

### Backend (Express.js)
- **API Server**: Express.js server on port 5000
- **Real-time Data**: Simulated occupancy updates
- **Static Serving**: Serves both API and client application

### Key Technologies
- React 18 with TypeScript
- Express.js server
- Leaflet.js for maps
- Tailwind CSS for styling
- Wouter for routing

## 📁 Project Structure

```
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/          # Page components
│   │   ├── services/       # API and business logic
│   │   ├── types/          # TypeScript type definitions
│   │   └── data/           # Static data and configuration
├── server/                 # Backend Express server
│   ├── index.ts           # Main server entry point
│   ├── routes.ts          # API route definitions
│   └── vite.ts            # Development server setup
└── shared/                # Shared types and schemas
```

## 🚀 Getting Started

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn package manager

### Installation & Development

1. **Clone and Install**:
   ```bash
   npm install
   ```

2. **Start Development Server**:
   ```bash
   npm run dev
   ```

3. **Access Application**:
   - Open your browser to `http://localhost:5000`
   - The application serves both frontend and API from port 5000

### Building for Production

```bash
npm run build
npm start
```

## 🎯 How It Works

### Real-time Occupancy Updates
The application simulates real-world shelter occupancy through the `ShelterOccupancyService`:

1. **Update Cycle**: Every 30 seconds, the service checks each shelter
2. **Change Probability**: 30% chance each shelter will have occupancy changes
3. **Dynamic Updates**: Occupancy can increase or decrease within capacity limits
4. **Live Sync**: All connected clients receive updates simultaneously

### Pathfinding Algorithm
Uses Dijkstra's algorithm for optimal route calculation:
- Considers distance, capacity, and current occupancy
- Factors in hazard risks for safer routing
- Provides estimated travel time and distance

### Filter System
Advanced filtering options:
- **Food Availability**: Show only shelters with food services
- **Space Availability**: Filter by available capacity
- **Occupancy Levels**: Filter by Low (0-25%), Medium (25-50%), High (50-90%), or Full (90%+)

## 📱 User Interface

### Main Components

1. **Interactive Map** (`ShelterMap.tsx`)
   - Displays shelter locations with markers
   - Color-coded occupancy indicators
   - Real-time route visualization

2. **Filter Panel** (`FilterPanel.tsx`)
   - Desktop filter controls
   - Selected shelter information
   - Route details and external navigation

3. **Mobile Filter Panel** (`MobileFilterPanel.tsx`)
   - Mobile-optimized filter interface
   - Collapsible design for small screens

4. **Info Window** (`InfoWindow.tsx`)
   - Detailed shelter information
   - Occupancy status and available resources

### Color Coding System
- 🟢 **Green**: Low occupancy (0-25%)
- 🟡 **Yellow**: Medium occupancy (25-50%)
- 🟠 **Orange**: High occupancy (50-90%)
- 🔴 **Red**: Full capacity (90%+)

## 🔧 Configuration

### Shelter Data
Shelter information is configured in `client/src/data/shelterData.ts`:
```typescript
{
  id: number,
  name: string,
  latitude: number,
  longitude: number,
  hasFood: boolean,
  hasSpace: boolean,
  capacity: number,
  currentOccupancy: number
}
```

### Update Intervals
- **Location Updates**: Every 10 seconds
- **Occupancy Updates**: Every 30 seconds
- **Map Refresh**: Real-time based on data changes

## 🚀 Deployment

This application is designed to run on Replit:

1. **Development**: Automatic hot-reload with Vite
2. **Production**: Built and served from Express server
3. **Port Configuration**: Uses port 5000 (Replit standard)

## 🛠️ Development

### Available Scripts
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm start` - Start production server
- `npm run check` - TypeScript type checking

### Key Services
- **pathfindingService.ts**: Implements Dijkstra's algorithm for routing
- **shelterOccupancyService.ts**: Manages real-time occupancy updates
- **shelter.ts**: Type definitions and utility functions

## 📊 Technical Details

### Performance Optimizations
- Memoized calculations for distance and routing
- Efficient re-rendering with React hooks
- Debounced location updates
- Optimized map rendering

### Browser Compatibility
- Modern browsers with ES6+ support
- Geolocation API support required
- Responsive design for mobile devices

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📝 License

MIT License - see LICENSE file for details

## 📞 Support

For support and questions, please refer to the project documentation or create an issue in the repository.

---

**Emergency Shelter Location System** - Helping communities stay safe during emergencies with real-time shelter information and intelligent routing.
