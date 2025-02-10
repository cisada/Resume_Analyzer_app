# LinkedIn Post Generator

## Overview

The **LinkedIn Post Generator** is a tool designed to help LinkedIn influencers automate their content creation process. By leveraging **Lama 3.2** and **LangChain**, the tool extracts key topics from previous posts and provides tailored writing assistance. This project aims to streamline content creation, enhance engagement with followers, and simplify the process of generating high-quality LinkedIn posts.

The tool utilizes **Bright Data** for data collection, ensuring access to fresh, pre-collected datasets without the need for complex web scraping scripts. The project also emphasizes the importance of environment variables for secure API key management and prompt engineering for effective data extraction using language models.

## Features

- **Data Collection**: Utilizes Bright Data to gather LinkedIn posts, ensuring a fresh and relevant dataset.
- **JSON Object Creation**: Formats LinkedIn posts into JSON objects for efficient data handling and future enhancements.
- **Environment Variables**: Securely manages API keys and sensitive information.
- **Prompt Engineering**: Optimizes data extraction using language models.
- **Tag Unification**: Standardizes tags in the dataset for consistency and clarity.
- **Data Manipulation**: Loads JSON data into a pandas DataFrame for easy querying and filtering.
- **Dynamic Post Generation**: Incorporates examples dynamically based on specific topics to align with desired writing styles.

## Installation

To get started with the LinkedIn Post Generator, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/linkedin-post-generator.git
   cd linkedin-post-generator
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Environment Variables**:
   Create a `.env` file in the root directory and add your API keys and other sensitive information:
   ```plaintext
   BRIGHT_DATA_API_KEY=your_bright_data_api_key
   LANGCHAIN_API_KEY=your_langchain_api_key
   LAMA_API_KEY=your_lama_api_key
   ```

4. **Run the Application**:
   ```bash
   python main.py
   ```

## Usage

### Data Collection

The tool uses Bright Data to collect LinkedIn posts. Ensure you have a valid API key and configure it in the `.env` file.

### JSON Object Creation

LinkedIn posts are formatted into JSON objects for easier data handling. Example:

```json
{
  "post_id": "12345",
  "content": "This is a sample LinkedIn post.",
  "topics": ["technology", "AI"],
  "language": "en",
  "tags": ["tech", "artificial intelligence"]
}
```

### Data Manipulation

Load JSON data into a pandas DataFrame for querying and filtering:

```python
import pandas as pd

# Load JSON data into a DataFrame
df = pd.read_json('linkedin_posts.json')

# Filter posts by language and topic
filtered_posts = df[(df['language'] == 'en') & (df['topics'].apply(lambda x: 'technology' in x)]
```

### Dynamic Post Generation

Generate LinkedIn posts dynamically based on specific topics:

```python
from post_generator import generate_post

# Generate a post on a specific topic
post = generate_post(topic="AI", language="en")
print(post)
```

## Contributing

We welcome contributions! Please follow these steps to contribute:

1. **Fork the Repository**:
   ```bash
   git fork https://github.com/yourusername/linkedin-post-generator.git
   ```

2. **Create a New Branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Commit Your Changes**:
   ```bash
   git commit -m "Add your commit message here"
   ```

4. **Push to the Branch**:
   ```bash
   git push origin feature/your-feature-name
   ```

5. **Open a Pull Request**: Go to the repository on GitHub and open a pull request with a detailed description of your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.




---

**Note**: This project is under active development. Stay tuned for more features and improvements!
