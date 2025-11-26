# JSONPlaceholder API - Data validation & handling .csv files for iterations

Automated validation of all JSONPlaceholder GET endpoints to ensure consistent data structure and type integrity across the API.

## 🚀 What It Does
- **Tests 5 API endpoints** dynamically from a CSV file
- **Validates data types** across multiple response properties  
- **Samples 5 items** from each endpoint
- **Uses Equivalence Partitioning** for property validation

## 🛠️ Technical Approach
- **Data-Driven Testing**: CSV file drives endpoint iteration
- **Dynamic Validation**: Single test script handles multiple data structures
- **Smart Sampling**: Tests 5 items per endpoint (configurable)
- **Property Checking**: Only validates properties that exist in each endpoint

## 📊 Test Coverage
| Endpoint | Properties Validated|
|----------|---------------------|
| `/posts` | userId, id, title, body|
| `/comments` | postId, id, email, body|
| `/albums` | userId, id, title|
| `/users` | id, name, email, etc.|
| `/todos` | userId, id, title, completed|

## 💡 Key Features
- **Single script** validates multiple endpoints
- **Automatic property detection** - only tests existing fields
- **Performance optimized** - limits sample size
- **Easy to extend** - add endpoints via CSV

## 🚀 Quick Start
1. Import `JSONPlaceholderAPI_data_validation.postman_collection` into Postman
2. Run Collection Runner with `endpoints.csv` as data file
3. View consolidated test results across all endpoints
