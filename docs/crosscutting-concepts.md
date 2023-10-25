---
title: Crosscutting Concepts
---

# Data Fetching
For Data fetching use a REST API provided by the [backend](building-block-view.md#backend).

## Frontend Data Fetching
In the frontend we use a library called [Tanstack Query](https://tanstack.com/query/latest) which simplifies the common data fetching tasks a lot.

### Example

=== "TypeScript"
    ```ts title="Onboarding.tsx"
    async function getCurriculums(): Promise<Curriculum[]> {
        const { data } = await axios.get<CurriculumResponse[]>(`${import.meta.env.VITE_BACKEND_API_URL}/curriculums`); 
        return data.map((curriculum) => ({ value: curriculum.title, label: curriculum.title, year: curriculum.year }));
    }

    const {
        isLoading: curriculumsLoading,
        error: curriculumsError,
        data: curriculumsData,
    } = useQuery({
        queryKey: ['curriculums'], // (1)
        queryFn: getCurriculums,
    });

    if (yearsLoading || curriculumsLoading) {
            return <h2>Loading</h2>;
        }
    ```

    1.  Key which is used for caching

=== "JavaScript"
    ```js title="Onboarding.jsx"
    async function getCurriculums() {
        const { data } = await axios.get(`${import.meta.env.VITE_BACKEND_API_URL}/curriculums`); 
        return data.map((curriculum) => ({ value: curriculum.title, label: curriculum.title, year: curriculum.year }));
    }

    const {
        isLoading: curriculumsLoading,
        error: curriculumsError,
        data: curriculumsData,
    } = useQuery({
        queryKey: ['curriculums'], // (1)
        queryFn: getCurriculums,
    });

    if (yearsLoading || curriculumsLoading) {
            return <h2>Loading</h2>;
        }
    ```
    
    1.  Key which is used for caching




