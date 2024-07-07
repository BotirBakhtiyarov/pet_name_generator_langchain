## Pets Name Generator Documentation

### Introduction
The Pets Name Generator is a Streamlit-based application that suggests names for pets based on their type and color. It uses LangChain to generate creative name suggestions using OpenAI's language model.

### Installation
1. **Clone the repository:**
   ```bash
   git clone https://github.com/BotirBakhtiyarov/pet_name_generator_langchain.git
   cd pet_name_generator_langchain
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

   Ensure you have set up your `.env` file with any necessary environment variables.

### Usage
1. **Run the application:**
   ```bash
   streamlit run main.py
   ```
   This command starts the Streamlit application.

2. **Generating Pet Names:**
   - Select the type of pet (e.g., Cat, Dog, Cow) from the dropdown menu.
   - Enter the color of the pet in the text area provided.
   - Click on the sidebar to generate a list of suggested names based on the pet type and color.

### Files and Structure
- **`main.py`**: Contains the Streamlit application code for user interaction.
- **`langchain_helper.py`**: Provides helper functions for generating pet names and using LangChain for natural language processing tasks.

### Functionality
- **`generate_pet_name(animal_type, pet_color)`**:
  - Uses OpenAI's language model to generate five cool names for a pet based on its type (`animal_type`) and color (`pet_color`).

- **`langchain_agent()`**:
  - Demonstrates the use of LangChain to perform tasks such as answering questions and performing calculations, leveraging external tools like Wikipedia.

### Example
An example use case:
```python
import langchain_helper as lch
import streamlit as st

st.title("Pets Name Generator")

user_animal_type = st.sidebar.selectbox("What is your pet?", ("Cat", "Dog", "Cow", "Horse", "Sheep"))

if user_animal_type in ["Cat", "Dog", "Cow", "Horse", "Sheep"]:
    pet_color = st.sidebar.text_area(label=f"What color is your {user_animal_type.lower()}?", max_chars=15)

if pet_color:
    response = lch.generate_pet_name(user_animal_type, pet_color)
    st.text(response)
```

### Contributing
- Contributions to this project are welcome. Fork the repository, make your changes, and submit a pull request with a detailed description of your enhancements.
- Ensure that your code follows the existing structure and is well-documented.

### Contact
- For questions or feedback, contact [Botir Bakhtiyarov](mailto:botirbakhtiyarovb@gmail.com).

