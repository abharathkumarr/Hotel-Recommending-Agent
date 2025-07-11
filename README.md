# Hotel Recommending AI Agent 

This project demonstrates an AI-powered hotel search and recommendation system. It leverages tools like LangChain, OpenAI, Chroma, Crew AI, and Gradio to build an intelligent system that automatically searches for hotels, reviews them, and suggests the best options based on user input. The system processes large hotel listing data, embeds them into a vector database, and retrieves relevant hotel information based on user queries. 

## Overview 

This project uses a variety of AI technologies to provide personalized hotel recommendations based on user input, such as location, check-in and check-out dates, number of guests, and budget. By using a series of custom-built agents and tools, the system is able to find and evaluate the best hotel options for a given criteria.

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/hotel-recommending-ai-agent.git
   cd hotel-recommending-ai-agent
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up your API keys:
   - Obtain an OpenAI API key and add it to the `.env` file.
   - Obtain a Google Places API key (optional) and also add it to `.env`.

## Setup

1. Load hotel listings from a `.json` file.
2. Extract and serialize relevant hotel details like name, address, price, rating, room info, etc.
3. Use LangChain’s `RecursiveCharacterTextSplitter` to chunk the data.
4. Embed the data using `OpenAIEmbeddings` and store it in a `Chroma` vector database.
5. Create a retriever to fetch relevant documents based on user queries.

## How It Works

- The serialized hotel data is chunked, embedded, and stored in a vector DB.
- A retriever fetches the most relevant hotel chunks.
- Two CrewAI tools are defined:
  - `BookingSearchTool` for finding hotels
  - `CalculatorTool` for simple computations
- Two agents are created:
  - `TravelExpert` to search for hotels
  - `HotelReviewer` to evaluate and rank hotels
- Tasks are defined for each agent and linked into a Crew flow.
- A `Gradio` UI allows users to input:
  - Location
  - Check-in / Check-out dates
  - Number of people
  - Budget
- The agents collaborate and return top hotel recommendations.

## Tools and Libraries

- **Python**
- **LangChain**
- **OpenAI**
- **ChromaDB**
- **Crew AI**
- **Gradio**
- **Google Places API** *(optional)*

## Usage

Run the project using:

```bash
python main.py
```

Use the Gradio UI to enter your travel details and receive recommended hotels in markdown format.

## Future Improvements

- Add filters for amenities, cancellation policy, and room types
- Display hotel images and maps in UI
- Integrate booking APIs for direct reservation
- Add support for multilingual input

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

