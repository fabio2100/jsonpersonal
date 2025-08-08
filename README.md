# Personal Data API

This repository serves as a personal data API providing information about Fabio Squizzato in both Spanish and English.

## Available Endpoints

### Spanish (Default)
- **URL:** `https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data.json`
- **Language:** Spanish
- **Content:** Complete personal information in Spanish

### English
- **URL:** `https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data-en.json`
- **Language:** English
- **Content:** Complete personal information in English

## Data Structure

The API provides the following information:

- **Personal Data**: Name, contact information, profession, photo, etc.
- **Social Profiles**: LinkedIn, GitHub, social media links
- **Skills**: Hard skills, soft skills, technologies
- **Languages**: Language proficiency and certifications
- **Courses**: Professional development courses
- **Work Experience**: Professional background and roles
- **Education**: Academic background
- **Portfolio**: Projects with demos, repositories, and descriptions

## Usage Examples

### JavaScript/TypeScript
```javascript
// Spanish version
const response = await fetch('https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data.json');
const dataES = await response.json();

// English version
const responseEN = await fetch('https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data-en.json');
const dataEN = await responseEN.json();
```

### Python
```python
import requests

# Spanish version
response = requests.get('https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data.json')
data_es = response.json()

# English version
response_en = requests.get('https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data-en.json')
data_en = response_en.json()
```

### cURL
```bash
# Spanish version
curl https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data.json

# English version
curl https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data-en.json
```

## CORS Policy

This API is served through GitHub's raw content delivery, which allows cross-origin requests. You can use it directly from any web application without CORS issues.

## Rate Limiting

GitHub's raw content delivery has rate limiting policies. For production applications with high traffic, consider:
- Implementing client-side caching
- Using a CDN
- Hosting the files on a dedicated API service

## Data Updates

The data is manually updated. Check the commit history for the latest changes.

## License

This data is provided for portfolio and professional networking purposes.

## Contact

- **Email**: squizzato.fabio@gmail.com
- **LinkedIn**: [linkedin.com/in/squizzato-fabio](https://www.linkedin.com/in/squizzato-fabio/)
- **GitHub**: [github.com/fabio2100](https://github.com/fabio2100)
