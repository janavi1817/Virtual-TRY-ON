# Wall Art & Frame Virtual Try-On

AI-powered web application for virtually trying on wall art, frames, murals, and gallery layouts in any interior space.

## Tech Stack

- **Frontend**: Next.js 14 (App Router), TypeScript, Tailwind CSS, Shadcn/UI, Fabric.js, Three.js
- **Backend**: Node.js + Express.js, TypeScript, Socket.io, Prisma, PostgreSQL, Redis
- **ML Service**: Python FastAPI, SAM, ZoeDepth, CLIP, Stable Diffusion XL, BLIP-2
- **Infrastructure**: Docker, Kubernetes, AWS S3, CloudFront

## Local Development Setup

### Prerequisites

- Node.js 18+
- Python 3.10+
- Docker & Docker Compose
- PostgreSQL 15+
- Redis 7+

### Quick Start

```bash
# Clone the repository
git clone <repo-url>
cd wall-art-tryon

# Start infrastructure services
docker-compose up -d postgres redis

# Setup Frontend
cd frontend
npm install
cp .env.example .env.local
npm run dev

# Setup Backend (new terminal)
cd backend
npm install
cp .env.example .env
npx prisma migrate dev
npm run dev

# Setup ML Service (new terminal)
cd ml-service
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt
cp .env.example .env
uvicorn app.main:app --reload --port 8000
```

### Docker Compose (Full Stack)

```bash
docker-compose up --build
```

Services will be available at:
- Frontend: http://localhost:3000
- Backend API: http://localhost:4000
- ML Service: http://localhost:8000
- PostgreSQL: localhost:5432
- Redis: localhost:6379

## Project Structure

```
wall-art-tryon/
├── frontend/          # Next.js 14 App
├── backend/           # Node.js Express API
├── ml-service/        # Python FastAPI ML Service
├── docker/            # Docker configurations
└── k8s/               # Kubernetes manifests
```

## Features

1. **Room Photo Upload & Wall Detection** - AI-powered wall segmentation
2. **Art Placement & Frame Try-On** - Perspective-correct virtual placement
3. **Lighting Simulation** - Realistic lighting and shadow effects
4. **AI Style Matching** - CLIP-based art recommendations
5. **AI Art Generation** - Custom artwork via Stable Diffusion XL
6. **Gallery Wall Planner** - Multi-art layout engine
7. **AR Mode** - WebXR-based augmented reality
8. **Space-Type Adaptation** - Context-aware suggestions
9. **Collaborative Mode** - Real-time multi-user sessions
10. **Marketplace Integration** - Shop real products
11. **Measurement & Hanging Guide** - PDF export with exact measurements
12. **Before/After & Social Sharing** - Share designs on social media

## Environment Variables

See `.env.example` files in each service directory for required configuration.

## License

MIT
