<div align="center">

![header](https://capsule-render.vercel.app/api?type=waving&color=0:F8BBD0,50:CE93D8,100:B39DDB&height=180&section=header&text=NeuralAge&fontSize=36&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=LDM%20Based%20Facial%20Aging%20and%20De-Aging%20Platform&descAlignY=58&descSize=15)

</div>

## Overview

NeuralAge is a research platform for realistic facial age transformation. It wraps a Stable Diffusion image to image pipeline in a FastAPI service, letting a single portrait be pushed forward or backward across five distinct age brackets while keeping identity and skin realism intact.

## Key Features

### Five age bracket transformation
Every request can target child, teen, adult, middle aged, or senior, with the pipeline adjusting its behavior for each bracket individually rather than applying one generic aging filter.

### Custom CNN age classifier
A trained convolutional network estimates the subject's current age bracket before transformation, so the pipeline knows the real starting point instead of trusting user input alone.

### Gender aware prompt engineering
A gender classifier feeds into per bracket prompt construction, producing more realistic, gender consistent aging and de-aging results.

### Tuned diffusion parameters per bracket
Diffusion strength, guidance scale and step count are all tuned separately for each age bracket, since a child to teen transformation needs very different settings than an adult to senior one.

### Post processing for realism
Texture, contrast and sharpness adjustments are applied after generation to avoid the flat, overly smooth look that raw diffusion output can have on skin.

### Self contained REST API
Endpoints for `/predict`, `/age` and `/status` are exposed with CORS support, and the FastAPI service ships with an embedded HTML, CSS and JS front end so it can be deployed and used as a single app.


## Tech Stack

<div align="center">
<img src="https://tech-stack.wontory.dev/api/orbit?text=NeuralAge&slugs=fastapi,pytorch,opencv,python" alt="tech stack orbit" width="380" />
</div>

FastAPI for the backend and routing, PyTorch with Diffusers for the Stable Diffusion pipeline, a custom CNN for age classification, OpenCV for image handling, and a lightweight HTML, CSS and JS front end embedded directly in the service.

## How It Works

An uploaded image first passes through the CNN age and gender classifiers. Their outputs configure the diffusion pipeline's prompt, strength, guidance scale and step count for the requested target bracket. The generated image then goes through a post processing stage before being returned through the `/age` endpoint.

## Setup and Run

1. Install dependencies with `pip install -r requirements.txt`.
2. Download or point the config at the Stable Diffusion checkpoint used for aging.
3. Place the trained CNN age and gender classifier weights in `/models`.
4. Start the service with `uvicorn main:app --reload`.
5. POST an image to `/age` with a target bracket, or open the embedded front end in your browser to try it visually.

## Roadmap

- Add video based aging previews
- Expose a batch processing endpoint
- Publish benchmark comparisons across diffusion strengths

## Status

> **Status:** This repository was scaffolded from the project description on the author's resume. Source code is being migrated and added here in stages. Reach out using the contact links below if you would like early access to the implementation.

## Let's Connect

<div align="center">

[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rawish0922@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rawishsarfraz)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Rawishs-2882)
[![Phone](https://img.shields.io/badge/Call-+92--332--8747138-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](tel:+923328747138)

</div>

<div align="center">

![footer](https://capsule-render.vercel.app/api?type=waving&color=0:B39DDB,50:CE93D8,100:F8BBD0&height=80&section=footer)

</div>
