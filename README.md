# AzureAI-MLStudio-BikeRental-EndPoints

Welcome to the **AzureAI MLStudio BikeRental Endpoints** repository! In this project, we explore the world of bike rentals using Azure AI services and the powerful capabilities of Azure Machine Learning Studio. Our focus is on creating and configuring endpoints to make predictions related to bike rentals.

## Overview
- **AzureAI**: This section showcases our expertise in Microsoft's Azure platform, specifically its AI services.
- **MLStudio**: We leverage Azure Machine Learning Studio to build, train, and deploy machine learning models.
- **BikeRental**: Our project revolves around bike rental data, where we predict rental counts and configure endpoints for easy access.

## Contents
1. **Introduction**: Learn about the purpose of this project and its significance.
2. **Getting Started**: Follow step-by-step instructions to set up and run our code.
3. **Dependencies**: Understand any prerequisites or dependencies required for successful execution.
4. **Endpoint Configuration**: Dive into the details of how we configure endpoints for our bike rental predictions.
5. **Contributing**: Interested in contributing? Find out how you can get involved.
6. **License**: Review the licensing terms for this project.

## Data Export and Git Integration

We exported data from Azure AI Studio in CSV and JSONL formats. The exported files were saved locally and then added to this Git repository. Here are the steps we followed:

1. Navigate to the repository directory in the terminal: `cd /d/reposGitHub/AzureAI-MLStudio-BikeRental-EndPoints`
2. Add the files to Git: `git add results_oxygen_bike-automl/results-mslearn-yellow_oxygen_bike-automl.csv` and `git add results_oxygen_bike-automl/results-mslearn-yellow_oxygen_bike-automl.jsonl`
3. Commit the changes: `git commit -m "Add exported data files from Machine Learning Studio Laboratorioai900>Jobs>mslearn-yellow_oxygen_bike-rental"`
4. Push the changes to GitHub: `git push`

Feel free to explore our code, experiment with the endpoints, and contribute to our bike rental prediction journey! 🚴‍♂️📊

# Bike Rental Prediction Service

This service predicts the number of bike rentals for a specific day, based on various factors such as day, month, year, season, holiday, weekday, working day, weather situation, temperature, feels-like temperature, humidity, and wind speed.

# How to Use the Service with Python
You can also use the service with Python. Here is an example of how you can do this:

```python
import os
import requests
import json

# Endpoint URL
url = 'http://599ecad4-5061-4cf3-88ec-7caf2ae8f9a8.eastus.azurecontainer.io/score'

# If the service is authenticated, get the key from the environment variable
key = os.getenv('YOUR_KEY_ENV_VAR')

# Define the data input for your model
data = {
  "Inputs": {
    "data": [
      {
        "day": 2,
        "mnth": 3,
        "year": 2024,
        "season": 0,
        "holiday": 0,
        "weekday": 0,
        "workingday": 0,
        "weathersit": 0,
        "temp": 0.0,
        "atemp": 0.0,
        "hum": 0.0,
        "windspeed": 0.0
      }
    ]
  },
  "GlobalParameters": 0.0
}

# Convert to JSON string
input_data = json.dumps(data)

# Set the content type
headers = {'Content-Type': 'application/json'}

# If authentication is enabled, set the authorization header
if key:
    headers['Authorization'] = f'Bearer {key}'

# Make the request and display the response
resp = requests.post(url, input_data, headers=headers)
print(resp.json())
```

## Configuração do Projeto

1. Clone o repositório: `git clone https://github.com/yourusername/AzureAI-MLStudio-BikeRental-EndPoints.git`
2. Navegue até o diretório do projeto: `cd AzureAI-MLStudio-BikeRental-EndPoints`
3. Instale as dependências: `pip install -r requirements.txt`
4. Defina as variáveis de ambiente: `export YOUR_KEY_ENV_VAR=yourkey`
5. Inicie o serviço: `python app.py`

##Documentação da API

Nosso serviço expõe um endpoint POST em `/score` para prever aluguéis de bicicletas. O corpo da solicitação deve ser um objeto JSON com a seguinte estrutura:

./json
```json
{
  "Inputs": {
    "data": [
      {
        "day": 2,
        "mnth": 3,
        "year": 2024,
        "season": 0,
        "holiday": 0,
        "weekday": 0,
        "workingday": 0,
        "weathersit": 0,
        "temp": 0.0,
        "atemp": 0.0,
        "hum": 0.0,
        "windspeed": 0.0
      }
    ]
  },
  "GlobalParameters": 0.0
}
```

## Test result
```output
{
  "1 item": {},
  "Results": [
    {
      "1 item": {},
      "0": "float521.4241745722384"
    }
  ]
}
```
# This output represents

 the response from the prediction service. It's a JSON object that contains the predicted bike rental count for the specific input data you provided.

Here's a breakdown:

1. `"1 item": {}` - This seems to be a placeholder or an unused field in the response. It doesn't provide any meaningful information in its current form.
2. `"Results"` - This is an array that contains the prediction results.
3. `"1 item": {}` - Similar to the previous `"1 item"`, this seems to be a placeholder or an unused field in the result object.
4. `"0": "float521.4241745722384"` - This is the actual prediction result. The key "0" is the index of the result in the array, and the value `"float521.4241745722384"` is the predicted bike rental count. The `"float"` prefix might indicate that this is a `floating-point number`.
5. Please note that the structure of this output is a bit unusual for a prediction service. Typically, you would expect something more straightforward, like `{"predicted_rental_count": 521.4241745722384}`. If you have control over the prediction service, you might want to consider simplifying the output structure.


## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## Informações de Contato

Se você tiver alguma dúvida ou quiser contribuir, mas não sabe como, entre em contato conosco em [your-email@example.com](mailto:your-email@example.com).

## Agradecimentos

Gostaríamos de agradecer a todos que contribuíram para este projeto, especialmente [John Doe](https://github.com/johndoe) por sua ajuda inestimável.


---

*Inspired by the power of AzureAI and fueled by MLStudio, our BikeRental Endpoints project aims to revolutionize the way we predict bike rentals.* 🌟

---

For more information, visit the [official documentation](https://learn.microsoft.com/en-us/azure/devops/repos/git/create-a-readme?view=azure-devops). 📚

Origem: 04/04/2024 <br>
(1) Create a readme for your Git repo - Azure Repos | Microsoft Learn. https://learn.microsoft.com/en-us/azure/devops/repos/git/create-a-readme?view=azure-devops. <br>
(2) readme.so. https://readme.so/. <br>
(3) azure-devops-docs/docs/repos/git/create-a-readme.md at main ... - GitHub. https://github.com/MicrosoftDocs/azure-devops-docs/blob/main/docs/repos/git/create-a-readme.md.
