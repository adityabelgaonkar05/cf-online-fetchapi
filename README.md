# cf-online-fetchapi
Fetches Codeforces Test Cases from provided link
POST your codeforces problem link on ['https://cf-online-fetchapi.onrender.com/test-cases'](https://cf-online-fetchapi.onrender.com/test-cases) 

```typescript
const [testCases, setTestCases] = useState<Array<[string, string]> | null>(null);

const fetchTestCases = async () => {
        try {
            const response = await fetch('https://cf-online-fetchapi.onrender.com/test-cases', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({ url })
            });
            const data = await response.json();
            setTestCases([[data.input, data.output]]);
        } catch (error) {
            console.error('Error fetching test cases:', error);
        }
    };
```
