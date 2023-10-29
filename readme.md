# CONSUMIENDO API JSONPLACEHOLDER [POST]

### Funcionalidades:
```
-> Crear una UI para Post [✅]
```
![image](https://github.com/xZeroAM/jsonplaceholder-api/assets/91385164/9c3ade78-5610-45e2-8c86-6457ec932b34)

```
- Listar los posts [✅] /Post
```
![image](https://github.com/xZeroAM/jsonplaceholder-api/assets/91385164/d8f7ea69-bc4c-4dd9-9317-5f75af37b599)

```
-> Crear post [✅] /Post/Create
```
![image](https://github.com/xZeroAM/jsonplaceholder-api/assets/91385164/0d7a58a0-9672-4e2c-b1cd-702defef6740)

![image](https://github.com/xZeroAM/jsonplaceholder-api/assets/91385164/350ea3da-a775-4c54-bf5d-3dcc4a0ccd6e)

![image](https://github.com/xZeroAM/jsonplaceholder-api/assets/91385164/77943b01-38aa-4b8e-b69c-a331959cd277)
```
- Mirar un Post [✅]  /Post/GetPost/1
```
![image](https://github.com/xZeroAM/jsonplaceholder-api/assets/91385164/2e5d0e04-7ece-41b0-80d0-90e2ce71a783)
```
- Actualizar un Post [✅] /Post/Update/{id}
```
  ### Post antes de actualizar {id = 1}
![image](https://github.com/xZeroAM/jsonplaceholder-api/assets/91385164/1e82bbce-c71a-4f97-adbe-1dc2f3641ecd)
![image](https://github.com/xZeroAM/jsonplaceholder-api/assets/91385164/ef5bd254-ff31-4e8c-989a-7826268b69a6)
![image](https://github.com/xZeroAM/jsonplaceholder-api/assets/91385164/957d27f9-e03d-4881-9b0a-6ce7c6f0be6e)

```
- Eliminar un Post [✅] /Post/Delete/{id}
```
``` C#
public async Task<String> DeletePost(int id)
        {
            try
            {
                string url = $"{API_URL}{id}";

                HttpResponseMessage response = await httpClient.DeleteAsync(url);

                if (response.IsSuccessStatusCode)
                {
                    string responseJson = await response.Content.ReadAsStringAsync();
                    Console.WriteLine(responseJson);
                    Console.WriteLine("Status Code: " + response.StatusCode);
                    return response.StatusCode.ToString();
                }
                else
                {
                    _logger.LogError($"Error al eliminar el post. Codigo: {response.StatusCode}");
                }
            }
            catch (Exception ex)
            {
                _logger.LogError($"Error API: {ex.Message}");
            }

            return "No se pudo eliminar";
        }
```

### Recibimos una respuesta 200 OK en la terminal
![image](https://github.com/xZeroAM/jsonplaceholder-api/assets/91385164/6bbd87d9-2fcb-4096-913b-10fa91b416b7)
