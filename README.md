import React from "react";
import { NavigationContainer } from "@react-navigation/native";
import { createStackNavigator } from "@react-navigation/stack";
import { createBottomTabNavigator } from "@react-navigation/bottom-tabs";
import HomeScreen from "./screens/HomeScreen";
import DestinationSearchScreen from "./screens/DestinationSearchScreen";
import DestinationDetailsScreen from "./screens/DestinationDetailsScreen";
import TripPlanningScreen from "./screens/TripPlanningScreen";
import ItineraryScreen from "./screens/ItineraryScreen";
import OfflineMapsScreen from "./screens/OfflineMapsScreen";
import BookingScreen from "./screens/BookingScreen";
import FoodDiscoveryScreen from "./screens/FoodDiscoveryScreen";
import BudgetManagementScreen from "./screens/BudgetManagementScreen";
import ProfileScreen from "./screens/ProfileScreen";
import AuthScreen from "./screens/AuthScreen";
import { View } from "react-native";
import NavigationBar from "./components/NavigationBar";
import AIAssistant from "./components/AIAssistant";
import TripPlannerComponent from "./components/TripPlannerComponent";
import OfflineMapComponent from "./components/OfflineMapComponent";
import ItineraryComponent from "./components/ItineraryComponent";
import BookingComponent from "./components/BookingComponent";
import TrainBookingComponent from "./components/TrainBookingComponent";
import FlightBookingComponent from "./components/FlightBookingComponent";
import TravelPackagesComponent from "./components/TravelPackagesComponent";
import "nativewind";

const Stack = createStackNavigator();
const Tab = createBottomTabNavigator();

function MainTabs() {
  return (
    <Tab.Navigator screenOptions={{ headerShown: false }}>
      <Tab.Screen name="Home" component={HomeScreen} />
      <Tab.Screen name="Search" component={DestinationSearchScreen} />
      <Tab.Screen name="Plan" component={TripPlanningScreen} />
      <Tab.Screen name="Itinerary" component={ItineraryScreen} />
      <Tab.Screen name="Profile" component={ProfileScreen} />
    </Tab.Navigator>
  );
}

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator screenOptions={{ headerShown: false }}>
        <Stack.Screen name="Main" component={MainTabs} />
        <Stack.Screen name="DestinationDetails" component={DestinationDetailsScreen} />
        <Stack.Screen name="OfflineMaps" component={OfflineMapsScreen} />
        <Stack.Screen name="Booking" component={BookingScreen} />
        <Stack.Screen name="TrainBooking" component={TrainBookingComponent} />
        <Stack.Screen name="FlightBooking" component={FlightBookingComponent} />
        <Stack.Screen name="TravelPackages" component={TravelPackagesComponent} />
        <Stack.Screen name="Food" component={FoodDiscoveryScreen} />
        <Stack.Screen name="Budget" component={BudgetManagementScreen} />
        <Stack.Screen name="Auth" component={AuthScreen} />
      </Stack.Navigator>
      <View className="absolute bottom-4 right-4">
        <AIAssistant />
      </View>
    </NavigationContainer>
  );
}

