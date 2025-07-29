# ALX Travel Listings API

A Django REST API for property listings, bookings, and reviews.

## Features

- **Listings Management**: Create and manage property listings
- **Booking System**: Handle reservations with status tracking
- **Review System**: Collect and display guest reviews
- **User Authentication**: JWT and session-based auth
- **Data Seeding**: Pre-populate database with sample data

## Models

### Listing
- Property details (title, description, amenities)
- Pricing and capacity info
- Host relationship

### Booking
- Date ranges and pricing
- Status tracking (pending/confirmed/completed)
- Guest and listing relationships

### Review
- Rating system (1-5 stars)
- Comments
- Linked to specific bookings

## Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/alx_travel_app_0x00.git
   cd alx_travel_app_0x00
   ```

2. **Set up virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate     # Windows
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure database**:
   ```bash
   python manage.py migrate
   ```

5. **Seed sample data**:
   ```bash
   python manage.py seed
   ```

## API Endpoints 

### Listings  
- **GET** `/api/listings/` – List all listings  
- **POST** `/api/listings/` – Create a new listing (auto-sets host)  
- **GET** `/api/listings/{id}/` – Retrieve a listing  
- **PUT/PATCH** `/api/listings/{id}/` – Update a listing  
- **DELETE** `/api/listings/{id}/` – Delete a listing  

### Bookings  
- **GET** `/api/bookings/` – List all bookings  
- **POST** `/api/bookings/` – Create a new booking (auto-sets guest, validates dates)  
- **GET** `/api/bookings/{id}/` – Retrieve a booking  
- **PUT/PATCH** `/api/bookings/{id}/` – Update a booking  
- **DELETE** `/api/bookings/{id}/` – Delete a booking  

### Reviews  
- **GET** `/api/reviews/` – List all reviews  
- **POST** `/api/reviews/` – Create a review (validates rating 1-5)  
- **GET** `/api/reviews/{id}/` – Retrieve a review  
- **PUT/PATCH** `/api/reviews/{id}/` – Update a review  
- **DELETE** `/api/reviews/{id}/` – Delete a review  

## Usage Examples

**Get all listings**:
```bash
curl http://localhost:8000/api/listings/
```

**Create booking**:
```bash
curl -X POST http://localhost:8000/api/bookings/ \
  -H "Content-Type: application/json" \
  -d '{"listing": 1, "start_date": "2023-12-01", "end_date": "2023-12-05"}'
```

## Testing

Run the test suite with:
```bash
python manage.py test
```

## Seeding Data

Populate the database with sample data:
```bash
python manage.py seed
```

