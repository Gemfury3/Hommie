# Real Estate Django Web App - Replit Setup

## Overview
A Django-based real estate website that allows users to browse property listings and enables realtors to list their properties. The application features multi-language support (English and German) and includes user authentication, property search, and contact functionality.

## Current State
- **Framework**: Django 3.2.25
- **Database**: SQLite3
- **Server**: Running on port 5000
- **Status**: Fully functional and ready for development

## Project Structure
- `accounts/` - User authentication and realtor management
- `core/` - Core functionality (address, country, state models)
- `listings/` - Property listings and types
- `contacts/` - Contact forms and messaging
- `documents/` - File uploads for listings
- `project/` - Django project settings and configuration
- `templates/` - HTML templates
- `media/` - User uploaded files
- `static/` - CSS, JavaScript, images

## Recent Changes (Nov 23, 2025)
- Upgraded Django from 3.1.7 to 3.2.25 for Python 3.12 compatibility
- Configured for Replit environment with ALLOWED_HOSTS set to accept all hosts
- Created database migrations for all apps
- Removed django-allauth temporarily (old version incompatible with modern setuptools)
- Installed production dependencies (gunicorn, whitenoise)
- Configured deployment with autoscale mode using Gunicorn

## Dependencies
Core packages installed:
- Django==3.2.25
- django-crispy-forms
- django-crum
- django-import-export
- django-modeltranslation
- django-translation-flags
- Pillow
- geopy
- openpyxl
- tablib
- pytz
- gunicorn
- whitenoise

## Configuration Notes
- SECRET_KEY uses environment variable with fallback to development key
- DEBUG is currently True (should be False in production)
- Static files served from `project/static/` and collected to `static/`
- Media files uploaded to `media/`
- Multi-language support with German (de) and English (en)
- Default timezone: Europe/Berlin

## Known Issues
- django-allauth removed due to setuptools compatibility issues
  - Social authentication (Google OAuth) not currently available
  - Can be re-enabled with newer compatible version if needed
- Model warnings about AutoField (cosmetic, not critical)

## Development Workflow
1. Start server: Workflow "Django Development Server" auto-starts
2. Access admin: `/admin/` (need to create superuser first)
3. Create superuser: `python manage.py createsuperuser`
4. View site: Main URL redirects to `/en/` (English version)

## Deployment
Configured for Replit autoscale deployment using:
- Gunicorn WSGI server
- 2 worker processes
- Port 5000 binding
- Reuse port enabled for zero-downtime restarts
