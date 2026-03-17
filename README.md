# OHRS-Django 🏨

**Online Hotel Reservation System** built with Django, featuring a modern web interface with HTML, CSS, and JavaScript.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Database Schema](#database-schema)
- [Frontend](#frontend)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## 🎯 Overview

**OHRS-Django** is an Online Hotel Reservation System designed to simplify hotel bookings and management. The system provides a user-friendly interface for customers to search, view, and reserve hotel rooms, while offering management tools for hotel administrators to manage rooms, rates, and reservations.

This project leverages Django's powerful backend framework combined with responsive frontend technologies to deliver a seamless hotel reservation experience.

---

## ✨ Features

### For Customers
- 🔍 **Room Search & Filtering** - Find hotels and rooms based on preferences
- 📅 **Date Selection** - Easy-to-use date pickers for check-in and check-out
- 💳 **Booking Management** - Create, view, and manage reservations
- 👤 **User Authentication** - Secure login and account management
- ⭐ **Ratings & Reviews** - View and submit guest reviews
- 📧 **Booking Confirmations** - Email notifications for reservations

### For Hotel Administrators
- 🏢 **Hotel Management** - Create and update hotel information
- 🛏️ **Room Management** - Add, edit, and manage room inventories
- 💰 **Rate Management** - Set and adjust room pricing
- 📊 **Reservation Analytics** - View booking statistics and trends
- 👨‍💼 **Staff Management** - Manage hotel staff accounts
- 📈 **Revenue Reports** - Track earnings and occupancy rates

---

## 🛠️ Tech Stack

### Backend
- **Django 3.x+** - Web framework and ORM
- **Python 3.8+** - Programming language
- **SQLite/PostgreSQL** - Database

### Frontend
- **HTML5** - Structure and markup
- **CSS3** - Styling and responsive design (52.6% of codebase)
- **JavaScript** - Interactivity and dynamic features (39.5% of codebase)
- **Bootstrap/Custom CSS** - Responsive UI components

### Tools & Libraries
- **Django REST Framework** (optional) - API endpoints
- **Django Crispy Forms** - Form rendering
- **Pillow** - Image processing
- **python-decouple** - Environment variable management

---

## 📁 Project Structure

```
OHRS-Django/
│
├── HotelReservation/          # Main Django project
│   ├── manage.py              # Django management script
│   ├── requirements.txt        # Python dependencies
│   │
│   ├── hotel/                 # Hotel management app
│   │   ├── models.py          # Hotel, Room, Amenity models
│   │   ├── views.py           # Hotel listing and detail views
│   │   ├── urls.py            # URL routing
│   │   ├── forms.py           # Hotel forms
│   │   └── templates/
│   │
│   ├── reservation/           # Reservation app
│   │   ├── models.py          # Reservation, Booking models
│   │   ├── views.py           # Booking views
│   │   ├── urls.py            # URL routing
│   │   ├── forms.py           # Reservation forms
│   │   └── templates/
│   │
│   ├── accounts/              # User authentication
│   │   ├── models.py          # Custom user model
│   │   ├── views.py           # Login, register, profile views
│   │   ├── urls.py            # Auth URL routing
│   │   ├── forms.py           # Login and registration forms
│   │   └── templates/
│   │
│   ├── static/                # Static files
│   │   ├── css/               # Stylesheets
│   │   ├── js/                # JavaScript files
│   │   └── images/            # Images and icons
│   │
│   ├── templates/             # HTML templates
│   │   ├── base.html          # Base template
│   │   ├── home.html          # Homepage
│   │   ├── navbar.html        # Navigation
│   │   └── footer.html        # Footer
│   │
│   └── settings.py            # Django settings and configuration
│
├── README.md                  # This file
├── .gitignore                 # Git ignore file
└── LICENSE                    # License file
```

---

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- Git
- Virtual environment tool (venv or virtualenv)

### Step-by-Step Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/prashannaLeo/OHRS-Django.git
   cd OHRS-Django
   ```

2. **Create Virtual Environment**
   ```bash
   python -m venv venv
   
   # Activate virtual environment
   # On Windows:
   venv\Scripts\activate
   
   # On macOS/Linux:
   source venv/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Navigate to Project Directory**
   ```bash
   cd HotelReservation
   ```

5. **Apply Migrations**
   ```bash
   python manage.py migrate
   ```

6. **Create Superuser**
   ```bash
   python manage.py createsuperuser
   ```

7. **Load Sample Data** (Optional)
   ```bash
   python manage.py loaddata sample_data
   ```

8. **Run Development Server**
   ```bash
   python manage.py runserver
   ```

   The application will be available at `http://127.0.0.1:8000/`

---

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the project root:

```env
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1

# Database
DATABASE_URL=sqlite:///db.sqlite3

# Email Configuration
EMAIL_BACKEND=django.core.mail.backends.smtp.EmailBackend
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USE_TLS=True
EMAIL_HOST_USER=your-email@gmail.com
EMAIL_HOST_PASSWORD=your-password

# AWS S3 (Optional)
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
```

### Settings.py Configuration

Key settings to customize:
- `DEBUG` - Set to `False` in production
- `ALLOWED_HOSTS` - Add your domain
- `DATABASES` - Configure your database
- `INSTALLED_APPS` - Add custom apps
- `STATIC_URL` - Static files URL
- `MEDIA_URL` - Media files URL

---

## 📖 Usage

### For Customers

1. **Register/Login**
   - Navigate to `/accounts/register/`
   - Fill in the registration form
   - Or login with existing credentials

2. **Search Hotels**
   - Click on "Browse Hotels" or use the search bar
   - Filter by location, date, and preferences
   - View hotel details and room availability

3. **Make a Reservation**
   - Select a hotel and room
   - Choose check-in and check-out dates
   - Review pricing and confirm booking
   - Receive confirmation email

4. **Manage Reservations**
   - Visit "My Bookings" in your profile
   - View, modify, or cancel reservations
   - Download booking receipts

### For Administrators

1. **Access Admin Panel**
   ```
   http://127.0.0.1:8000/admin/
   ```

2. **Manage Hotels**
   - Add new hotels
   - Update hotel information
   - Upload hotel images

3. **Manage Rooms**
   - Add rooms to hotels
   - Set room types and amenities
   - Adjust pricing

4. **View Reservations**
   - Monitor all bookings
   - Update reservation status
   - Handle cancellations

---

## 🔌 API Endpoints

### Hotels
- `GET /api/hotels/` - List all hotels
- `GET /api/hotels/<id>/` - Get hotel details
- `POST /api/hotels/` - Create new hotel (admin)
- `PUT /api/hotels/<id>/` - Update hotel (admin)
- `DELETE /api/hotels/<id>/` - Delete hotel (admin)

### Rooms
- `GET /api/rooms/` - List all rooms
- `GET /api/rooms/<id>/` - Get room details
- `POST /api/rooms/` - Create new room (admin)
- `PUT /api/rooms/<id>/` - Update room (admin)

### Reservations
- `GET /api/reservations/` - List user's reservations
- `POST /api/reservations/` - Create new reservation
- `GET /api/reservations/<id>/` - Get reservation details
- `PUT /api/reservations/<id>/` - Update reservation
- `DELETE /api/reservations/<id>/` - Cancel reservation

### Authentication
- `POST /api/auth/login/` - User login
- `POST /api/auth/register/` - User registration
- `POST /api/auth/logout/` - User logout

---

## 🗄️ Database Schema

### Core Models

**Hotel**
- `id` (PK)
- `name`
- `description`
- `location`
- `address`
- `phone_number`
- `email`
- `rating`
- `image`
- `created_at`
- `updated_at`

**Room**
- `id` (PK)
- `hotel_id` (FK)
- `room_number`
- `room_type`
- `capacity`
- `price_per_night`
- `amenities`
- `is_available`
- `created_at`
- `updated_at`

**Reservation**
- `id` (PK)
- `user_id` (FK)
- `room_id` (FK)
- `check_in_date`
- `check_out_date`
- `total_price`
- `status` (pending, confirmed, cancelled)
- `created_at`
- `updated_at`

**User**
- `id` (PK)
- `username`
- `email`
- `password`
- `first_name`
- `last_name`
- `phone_number`
- `is_staff`
- `is_active`

---

## 🎨 Frontend

### Pages

1. **Homepage** (`/`)
   - Hotel search bar
   - Featured hotels carousel
   - User testimonials

2. **Hotel List** (`/hotels/`)
   - Filterable hotel listings
   - Sorting options
   - Hotel cards with ratings

3. **Hotel Detail** (`/hotels/<id>/`)
   - Full hotel information
   - Room listings
   - Reviews and ratings

4. **Booking Page** (`/booking/<room_id>/`)
   - Date picker
   - Guest information form
   - Price calculation

5. **Dashboard** (`/dashboard/`)
   - User profile
   - Booking history
   - Saved preferences

### Responsive Design
- Mobile-first approach
- CSS Grid and Flexbox layouts
- Bootstrap integration for responsive components
- Touch-friendly interface

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the Repository**
   ```bash
   git clone https://github.com/yourusername/OHRS-Django.git
   ```

2. **Create a Feature Branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```

3. **Commit Changes**
   ```bash
   git commit -m 'Add amazing feature'
   ```

4. **Push to Branch**
   ```bash
   git push origin feature/amazing-feature
   ```

5. **Open a Pull Request**
   - Describe your changes
   - Reference any related issues
   - Wait for review and feedback

### Coding Standards
- Follow PEP 8 for Python code
- Use meaningful variable and function names
- Add docstrings to functions and classes
- Write unit tests for new features
- Keep commits atomic and descriptive

---

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 📧 Contact

**Author:** Prashanna Leo  
**GitHub:** [@prashannaLeo](https://github.com/prashannaLeo)  
**Email:** prashanna@example.com

---

## 🙏 Acknowledgments

- Django community for the excellent framework
- Contributors and testers
- Hotel industry partners for requirements and feedback

---

## 📚 Additional Resources

- [Django Documentation](https://docs.djangoproject.com/)
- [Django REST Framework](https://www.django-rest-framework.org/)
- [MDN Web Docs](https://developer.mozilla.org/)
- [Bootstrap Documentation](https://getbootstrap.com/docs/)

---

**Last Updated:** March 17, 2026  
**Version:** 1.0.0

---

*Made with ❤️ by Prashanna Leo*
