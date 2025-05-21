# Sintassi spicciola

* Accesso al JSON di un insegnamento

  ```python
        url = "https://unipi.coursecatalogue.cineca.it/api/v1/attivitaFormativa"
        params = {
            "aaOfferta": annoOfferta,
            "corso": "WFI-LM",
            "annoOrdinamento": 2023,
            "ad": codiceESSE3,
            "coorte": coorte,
            "pds": pds
        }
        response = requests.get(url, params=params)
  ```

* Accesso al JSON di un corso

  ```python
        url = f"https://unipi.coursecatalogue.cineca.it/api/v1/corso/{anno}/{codiceGDA}"
        response = requests.get(url)
  ```

* Query insegnamenti (POST)

  ```python
      url = "https://unipi.coursecatalogue.cineca.it/api/v1/ricercaInsegnamenti"
      payload = {
        "insegnamento": "",
        "docente": None,
        "anno_imm": None,
        "anno_off": "2024",   
        "dipartimento": 10184,
        "ssdSearchString": None,
        "tipoCorso": None,
        "lingua": None,
        "corsiSearchString": None
      }
      headers = {"Content-Type": "application/json"}
      response = requests.post(url, json=payload, headers=headers)
  ```

* Query corsi (POST)

  ```python
      url = "https://unipi.coursecatalogue.cineca.it/api/v1/ricercaCorsi"
      payload = {
        "searchString": "fisica",
        "anno": "2024",
        "tipoCorso": None,
        "sede": None,
        "lingua": None,
        "dipartimento": None,
        "interateneo": None,
        "area": None
      }
      headers = {"Content-Type": "application/json"}
      response = requests.post(url, json=payload, headers=headers)
  ```

