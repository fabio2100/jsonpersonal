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

## Key Features

✅ **Same Structure**: Both files use identical keys, only content differs  
✅ **Language Agnostic Code**: Write once, use with any language  
✅ **Easy Switching**: Change language by changing the endpoint URL  
✅ **Consistent API**: Same object structure across languages  

## Data Structure

Both APIs provide the same structure with the following sections:

- **datosPersonales**: Name, contact information, profession, photo, etc.
- **perfiles**: LinkedIn, GitHub, social media links
- **habilidades**: Hard skills, soft skills, technologies
- **idiomas**: Language proficiency and certifications
- **cursos**: Professional development courses
- **experienciaLaboral**: Professional background and roles
- **educacion**: Academic background
- **portfolio**: Projects with demos, repositories, and descriptions

## Usage Examples

### JavaScript/TypeScript
```javascript
// Function to get data in any language
async function getPersonalData(language = 'es') {
  const url = language === 'es' 
    ? 'https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data.json'
    : 'https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data-en.json';
  
  const response = await fetch(url);
  const data = await response.json();
  
  // Same structure for both languages!
  console.log(data.datosPersonales.nombre); // Always works
  console.log(data.portfolio); // Always works
  
  return data;
}

// Usage
const spanishData = await getPersonalData('es');
const englishData = await getPersonalData('en');
```

### React Hook Example
```javascript
function usePersonalData(language) {
  const [data, setData] = useState(null);
  
  useEffect(() => {
    const url = language === 'es' 
      ? 'https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data.json'
      : 'https://raw.githubusercontent.com/fabio2100/jsonpersonal/master/data-en.json';
    
    fetch(url)
      .then(response => response.json())
      .then(setData);
  }, [language]);
  
  return data;
}

// Component usage - same structure regardless of language
function Profile({ language }) {
  const data = usePersonalData(language);
  
  if (!data) return <div>Loading...</div>;
  
  return (
    <div>
      <h1>{data.datosPersonales.nombre}</h1>
      <p>{data.datosPersonales.acercaDeMi}</p>
      {data.portfolio.map(project => (
        <div key={project.nombre}>
          <h3>{project.nombre}</h3>
          <p>{project.descripcion}</p>
        </div>
      ))}
    </div>
  );
}
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
