# Smart Parking Slot Booking System

A Smart Parking Slot Booking System developed using ServiceNow to simplify parking slot reservation, vehicle management, QR-based booking verification, check-in/check-out, notifications, and administrative monitoring.

## Project Overview

The application allows users to search for available parking slots, reserve a slot, manage their bookings, receive a QR-based parking pass, and cancel bookings.

Security personnel can verify bookings and perform vehicle check-in and check-out.

Administrators can manage parking locations, parking slots, bookings, and monitor parking activity through dashboards.

## Technologies Used

- ServiceNow
- ServiceNow Studio
- Service Portal
- Scripted REST API
- GlideRecord
- GlideAggregate
- Business Rules
- Scheduled Script Executions
- Access Control Lists (ACLs)
- Notifications
- GitHub Source Control

## Main Tables

- Parking Location
- Parking Slot
- Vehicle
- Parking Booking
- Parking Entry Log

## Main Features

### Parking Booking

- View available parking slots
- Select parking location
- Select vehicle
- Choose start and end time
- Generate booking automatically
- Prevent double booking

### QR Verification

Each confirmed booking generates:

- Booking Number
- Verification Token
- QR Verification URL
- QR Code

The QR code can be scanned to verify whether a parking booking is valid.

### Check-In and Check-Out

Security personnel can:

- Verify a booking
- Check in a vehicle
- Record check-in time
- Check out a vehicle
- Record check-out time

Parking Entry Log records are created and updated automatically.

### Automatic Slot Management

Parking slot status changes automatically:

- Available → Reserved when booking is confirmed
- Reserved → Available after completion
- Reserved → Available after cancellation
- Reserved → Available after booking expiry

### Booking Expiry

A Scheduled Script Execution checks expired confirmed bookings and automatically changes them to:

`Expired`

The associated parking slot is then released.

### Email Notifications

Notifications are generated for:

- Booking Confirmation
- Booking Cancellation
- Vehicle Check-In
- Booking Expiry

### Role-Based Access

The application contains three main roles:

#### Parking User

- Book parking slots
- View own bookings
- View booking details
- Cancel bookings

#### Parking Security

- Verify parking bookings
- Check in vehicles
- Check out vehicles
- Work with parking entry logs

#### Parking Admin

- Access administrative dashboard
- Manage parking slots
- Manage parking locations
- Manage bookings
- View application statistics

## Service Portal Frontend

The project includes a custom Service Portal frontend.

Main pages include:

- Smart Parking Home
- Book Parking Slot
- My Bookings
- Booking Details
- Security Verification
- Admin Dashboard

## Smart Parking Dashboard

The dashboard provides statistics such as:

- Total Parking Slots
- Available Slots
- Reserved Slots
- Total Bookings
- Confirmed Bookings
- Completed Bookings
- Cancelled Bookings
- Expired Bookings

## Booking Workflow

User selects parking details

↓  

Booking is created

↓  

Booking Number generated

↓  

Verification Token generated

↓  

QR Verification URL generated

↓  

QR Code generated

↓  

Parking Slot reserved

↓  

Confirmation notification generated

↓  

Security verifies booking

↓  

Vehicle Check-In

↓  

Parking Entry Log created

↓  

Vehicle Check-Out

↓  

Booking completed

↓  

Parking Slot becomes available again

## Security

The application uses ServiceNow ACLs and custom roles to restrict access.

Users can only access functionality appropriate to their assigned role.

Direct access to protected Security and Admin pages is also validated using role checks.

## Testing

The application was tested for:

- Successful parking booking
- Double-booking prevention
- QR verification
- Vehicle check-in
- Vehicle check-out
- Parking entry log creation
- Booking cancellation validation
- Automatic booking expiry
- Slot release
- Email notifications
- User role access
- Security role access
- Admin role access

## Future Enhancements

Possible future improvements include:

- Online payment integration
- Real-time parking sensors
- Mobile application
- Number plate recognition
- Navigation to parking slots
- Advanced analytics
- SMS notifications

## Author

Developed as a ServiceNow Smart Parking Slot Booking project.
