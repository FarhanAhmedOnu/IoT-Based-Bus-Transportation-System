# IoT-Based Smart Bus Transportation System

## Project Overview
An IoT-based smart bus transportation system that provides real-time bus tracking, route planning, and automated fare calculation using QR codes and digital payments.

## Table of Contents
- [Introduction](#introduction)
- [Objectives](#objectives)
- [System Architecture](#system-architecture)
- [Hardware Components](#hardware-components)
- [Implementation](#implementation)
- [Features](#features)
- [Web Application](#web-application)
- [Limitations](#limitations)
- [Future Work](#future-work)
- [Conclusion](#conclusion)

## Introduction
This IoT-based Smart Bus Transportation System offers a user-friendly solution for efficient urban travel. It enables real-time bus tracking and route viewing, allowing passengers to easily locate buses and plan their journeys. The system incorporates automated fare calculation via QR codes and supports seamless digital payments.

## Objectives
1. **Real-Time Tracking** - Provide passengers with live bus locations using GPS and IoT
2. **Route Search** - Enable users to search and plan journeys efficiently
3. **Automated Fare Calculation** - Use QR codes to measure travel time/distance for accurate billing
4. **Seamless Payments** - Integrate digital payment methods (bKash, Rocket) for convenience
5. **User Accessibility** - Offer web-based interface for tracking, payments, and pickup requests
6. **Data Management** - Store and sync data via Firebase/ThingSpeak for reliability

## System Architecture

### Three-Layer Architecture

#### 1. Device Layer (Bus)
- **ESP32 Microcontroller**
- Neo-6M GPS Module
- SIM800 2G SIM Module
- OLED Display
- Power Supply

#### 2. Cloud/Server Layer
- **ThingSpeak** - GPS data processing
- **Firebase** - User authentication, route metadata, real-time sync
- **Backend APIs** - Data processing and management
- **Mozilla Location Services** - IP-based location

#### 3. Web Interface Layer
- **Passenger View**: Live bus tracking, route search, payments
- **Manager Dashboard**: Fleet monitoring, analytics
- **Frontend**: Tailwind CSS, Leaflet maps

## Hardware Components

### Main Components
1. **ESP32 WROOM 32** - Main microcontroller
2. **Neo-6M GPS Module** - Location tracking
3. **SIM800 2G SIM Module** - Cellular communication
4. **OLED Display** - Show QR codes and information
5. **Power Supply** - System power management

## Pin Connections Table

| ESP32 Pin | Component | Connection | Notes |
|-----------|-----------|------------|--------|
| 5V | SIM800 Module | VCC | Power supply |
| GND | SIM800 Module | GND | Ground |
| GPIO16 | SIM800 Module | TXD | Serial transmit |
| GPIO17 | SIM800 Module | RXD | Serial receive |
| 3.3V | Neo-6M GPS Module | VCC | Power supply |
| GND | Neo-6M GPS Module | GND | Ground |
| GPIO4 | Neo-6M GPS Module | TX | GPS transmit |
| GPIO2 | Neo-6M GPS Module | RX | GPS receive |
| 3.3V | OLED Display | VCC | Power supply |
| GND | OLED Display | GND | Ground |
| GPIO21 | OLED Display | SDA | I2C data |
| GPIO22 | OLED Display | SCL | I2C clock |
| 5V | Power Supply | VIN | Main power input |
| GND | Power Supply | GND | Common ground |



### Prototype Module
- Positioned at bus entrance
- Contains ESP32, GPS module, and SIM module
- Displays QR codes for website access and payments

### QR Code System
- **Large QR Code**: Directs to website
- **Display QR Code**: For payment page access
- **Scanning Process**: 
  - Passenger scans QR when entering and exiting
  - System calculates fare based on time and distance

## Features

### Core Functionalities
- **Real-time bus tracking** on interactive maps
- **Route search** from source to destination
- **ETA display** based on live data
- **Digital payments** (bKash, Rocket)
- **Pickup request** system for cabs/carts
- **User authentication** system

### Web Application Features

#### Home Page
- Real-time map viewing
- Bus search functionality
- Payment options
- Journey planning form

#### Bus Tracking
- Live location on map
- Current speed and coordinates
- Next stop information
- ETA calculations

#### Route Search
- Source and destination input
- Available buses display
- Route details and pricing
- Live location tracking

#### Payment System
- Due amount calculation
- Multiple payment methods (bKash, Rocket)
- Payment history storage in Firebase

#### Pickup Request System
- Location sharing for cab requests
- Driver view of pickup locations
- Real-time request monitoring

## Web Application Interface

### Technologies Used
- **Frontend**: Tailwind CSS, Leaflet.js for maps
- **Backend**: Firebase, ThingSpeak
- **Location Services**: Mozilla open source servers
- **Authentication**: Firebase Auth

### Pages Structure
```
/
├── Home Page
├── Real-time Map
├── Bus Search
├── Payment Portal
├── Login/Registration
├── Pickup Request
└── Admin Dashboard
```

## Limitations

1. **Initialization Time**: System takes 5-10 minutes to initialize
2. **Location Accuracy**: Limited accuracy in Mozilla location services
3. **Area Coverage**: Works well only in open areas
4. **GPS Dependency**: Requires clear GPS signal for accurate tracking

## Future Work

### Planned Enhancements
1. **Mobile App Development**: Native Android/iOS applications
2. **AI-based ETA Prediction**: Machine learning models for accurate arrival predictions
3. **Driver Interface**: Dedicated dashboard for bus drivers
4. **Data Analytics Portal**: Advanced analytics for performance insights
5. **Government Integration**: Sync with official transport authorities

### Technical Improvements
- Reduced initialization time
- Improved location accuracy
- Enhanced GPS performance in urban areas
- Better error handling and reliability

## Conclusion

The IoT-based Smart Bus Transportation System provides a comprehensive solution for modern urban transportation needs. By integrating real-time tracking, automated fare calculation, and digital payments, it significantly enhances the commuting experience. While current limitations exist in initialization time and location accuracy, the system provides a solid foundation for future improvements and scalability in public transportation management.

## Setup Instructions

### Hardware Setup
1. Connect ESP32 with GPS and SIM modules
2. Configure power supply
3. Install module at bus entrance
4. Ensure proper antenna placement

### Software Setup
1. Configure Firebase project
2. Set up ThingSpeak channels
3. Deploy web application
4. Configure payment gateways

### Usage
1. Passengers scan QR code to access system
2. Track buses in real-time
3. Search for optimal routes
4. Make digital payments
5. Request additional pickup services

