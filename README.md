

# nexaFit 

---

# nexaFit 

Welcome to the **nexaFit Monorepo**, which houses both the **backend** and **frontend** components of the nexaFit platform. nexaFit is a comprehensive nutrition and wellness platform that offers calorie prediction, meal planning, and a community forum for user engagement.

---

## Features

### Backend Features

1. **Post-Workout Burnt Calorie Prediction**
    - Uses a trained **XGBoost model** to predict calories burnt based on user input.
    - Inputs include gender, age, height, weight, workout duration, heart rate, and body temperature.
2. **Meal Planning**
    - Integrates with the **Spoonacular API** to generate weekly meal plans.
    - Supports dietary preferences, calorie limits, and intolerance filtering.
3. **Forum**
    - Allows users to create posts, comment on discussions, and engage with the community.
    - Features tagging, pagination, and comment tracking for meaningful discussions.
4. **User Management**
    - Handles user profile creation, updates, and retrieval.

### Frontend Features

1. **User Dashboard**
    - Displays daily caloric intake, nutritional data, and suggested meal plans.
    - Visualizes calorie predictions using charts.
2. **Authentication**
    - User registration and login powered by **Clerk**.
3. **Meal Planning**
    - Fetches weekly meal plans from the backend.
4. **Forum**
    - Enables users to participate in discussions, share motivation, and engage with the community.
5. **Responsive Design**
    - Optimized for mobile and desktop views.

---

## Tech Stack

### Backend

- **Framework**: FastAPI
- **Database**: MongoDB Atlas
- **Machine Learning Model**: XGBoost
- **Containerization**: Docker


### Frontend

- **Framework**: React
- **Styling**: TailwindCSS
- **Deployment**: Vercel
- **HTTP Client**: Axios
- **Authentication**: Clerk

---

## Monorepo Directory Structure

```plaintext
.
├── backend/                  # Backend directory
│   ├── .dockerignore         # Files ignored by Docker
│   ├── .env                  # Environment variables (not included in repo)
│   ├── .gitignore            # Git ignore rules
│   ├── calorie_predictor.json # Trained XGBoost model
│   ├── database.py           # MongoDB configurations and database operations
│   ├── Dockerfile            # Docker build instructions
│   ├── forum.py              # Forum feature routes and logic
│   ├── main.py               # FastAPI entry point
│   ├── ml_predictor.py       # Calorie prediction logic (ML integration)
│   ├── models.py             # Pydantic models for validation and serialization
│   ├── requirements.txt      # Python dependencies
│   └── std_scaler.bin        # Pre-fitted scaler for input normalization
├── frontend/                 # Frontend directory
│   ├── public/               # Static assets (e.g., images, favicon)
│   ├── src/
│   │   ├── components/       # Reusable React components
│   │   ├── pages/            # Page-level components (e.g., Dashboard, Forum)
│   │   ├── styles/           # TailwindCSS configuration files
│   │   └── App.js            # Main React application entry point
│   ├── .env                  # Environment variables (not included in repo)
│   ├── package.json          # Project metadata and dependencies
│   └── tailwind.config.js    # TailwindCSS configuration file
└── README.md                 # Monorepo documentation (this file)
```

---

## Installation

### Prerequisites

- Python 3.9+
- Node.js (v16+)
- Docker (optional for containerization)
- MongoDB Atlas account (for backend database)
- Spoonacular API key (for meal planning)

---

### Backend Setup

1. Navigate to the `backend` directory:

```bash
cd backend/
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Set up environment variables:
Create a `.env` file in the `backend` directory with the following keys:

```env
MONGODB_URI=&lt;your_mongodb_uri&gt;
DATABASE_NAME=&lt;your_database_name&gt;
SPOONACULAR_API_KEY=&lt;your_spoonacular_api_key&gt;
CALORIE_MODEL_PATH=calorie_predictor.json
```

4. Run the application:

```bash
uvicorn main:app --reload
```

5. Access the API documentation at `http://127.0.0.1:8000/docs`.

---

### Frontend Setup

1. Navigate to the `frontend` directory:

```bash
cd frontend/
```

2. Install dependencies:

```bash
npm install
```

3. Set up environment variables:
Create a `.env` file in the `frontend` directory with the following keys:

```bash
REACT_APP_API_URL=&lt;your-backend-api-url&gt;
REACT_APP_CLERK_FRONTEND_API=&lt;your-clerk-frontend-api-key&gt;
```

4. Start the development server:

```bash
npm run dev
```

5. Build for production:

```bash
npm run build
```

6. Run production build locally:

```bash
npm start
```


---

## Running with Docker

### Backend

1. Navigate to the `backend` directory:

```bash
cd backend/
```

2. Build the Docker image:

```bash
docker build -t nexafit-backend .
```

3. Run the container:

```bash
docker run --env-file .env -p 8000:8000 nexafit-backend
```

4. Access the API at `http://127.0.0.1:8000`.

### Frontend

The frontend can be deployed on Vercel or served locally using any static file server after building:

```bash
npm run build &amp;&amp; serve -s build 
```

---

## Deployment

### Backend Deployment

The backend can be deployed on any cloud provider or container orchestration platform like AWS ECS or Kubernetes.

### Frontend Deployment

The frontend is optimized for deployment on platforms like Vercel or Netlify.

To deploy on Vercel:

1. Push changes to your GitHub repository.
2. Link your repository to Vercel.
3. Configure environment variables in Vercel settings.
4. Deploy!

---

## Contributing

We welcome contributions! To contribute:

1. Fork this repository.
2. Create a new branch (`git checkout -b feature-name`).
3. Commit your changes (`git commit -m "Add feature"`).
4. Push to your branch (`git push origin feature-name`).
5. Open a pull request.

---

## License

This project is licensed under the MIT License.

---

## Contact

For questions or support, please contact [ezahpizza](https://github.com/ezahpizza).

<div>⁂</div>

[^1]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/51749027/03e7f5fe-c85e-4f38-8509-dfe0c34bb20e/models.py

[^2]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/51749027/d4fa731c-0957-4793-9a1f-75ebdbe082bb/main.py

[^3]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/51749027/34067aeb-9fe0-4571-b923-b4a0b5249393/database.py

[^4]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/51749027/fb50f2d5-0420-45bc-9941-0343fab33f19/forum.py

[^5]: https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/51749027/64510e34-1946-455e-9b13-540ff5d7a78b/ml_predictor.py

