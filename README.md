# NeuralAge

FastAPI research platform performing facial age progression and regression across five age brackets using a Stable Diffusion (Latent Diffusion Model) image-to-image pipeline.

## Features
- Age transformation across 5 brackets: child, teen, adult, middle-aged, senior
- Custom CNN-based age classifier plus a gender classifier driving gender-aware, per-bracket prompt engineering
- Tuned diffusion strength, guidance scale, and step count per age bracket
- Post-processing (texture, contrast, sharpness) for lifelike skin aging effects
- REST endpoints: `/predict`, `/age`, `/status`, with CORS support

## Tech Stack
FastAPI, Stable Diffusion / Diffusers, PyTorch, OpenCV, HTML/CSS/JS (embedded frontend)

## Setup & Run
1. `pip install -r requirements.txt`
2. Download/point to the Stable Diffusion checkpoint used for aging.
3. Run `uvicorn main:app --reload`.
4. POST an image to `/age` with a target bracket to receive the transformed result.

## Status
This repository was scaffolded from the project description in the author's resume. Source code is being migrated/added here — check back for updates, or reach out below.

## 📫 Contact
- **Email:** rawish0922@gmail.com
- **Phone:** +92-332-8747138
- **LinkedIn:** [linkedin.com/in/rawishsarfraz](https://linkedin.com/in/rawishsarfraz)
- **GitHub:** [github.com/Rawishs-2882](https://github.com/Rawishs-2882)

