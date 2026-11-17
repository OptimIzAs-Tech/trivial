# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Trivial FDF — a single-page trivia game about "Festival de Fiestas" (FDF). The entire app lives in one file: `index.html`. No build tools, no dependencies, no framework.

## Architecture

- **Single HTML file** (`index.html`) containing all markup, CSS, and JavaScript inline.
- **Language**: Spanish (UI text, questions, explanations).
- **Three screens**: Welcome → Question → Results, toggled via `.screen.active` CSS class.
- **Question data**: the `questions` array in the `<script>` block. Each entry has `text`, `options`, `correct` (index), `layout` ("two-col" or "four-col"), and `explanation`.
- **Confetti**: canvas-based animation triggered on good results (≥50%).

## Development

Open `index.html` directly in a browser. No server or build step required.

To add a new question, append an object to the `questions` array following the existing format.

## Antes de hacer algo nuevo, mira lo que ya está hecho

<!-- comprobar-marca: justificado (es el nombre del repositorio del catálogo, no una marca de este proyecto) -->
Lo que ya existe en los proyectos de la organización está en el catálogo, el repositorio
`OptimIzAs-Tech/optimizas-catalogo`: `catalogo/MODULOS.md` tiene los módulos de ERP por
departamento y `proyectos/INDICE.md` todos los proyectos, cada uno con su ficha. Se lee con
`gh repo clone OptimIzAs-Tech/optimizas-catalogo` o, archivo a archivo, con
`gh api repos/OptimIzAs-Tech/optimizas-catalogo/contents/catalogo/MODULOS.md -H "Accept: application/vnd.github.raw"`.

Antes de construir un módulo, una pantalla o una función nueva:

1. Busca en el catálogo algo **igual o parecido** y dilo: en qué proyecto está, qué hace allí y
   qué habría que adaptar.
2. Si hay **varias versiones** de lo mismo en proyectos distintos, pregunta cuál se coge antes de
   empezar.
3. De otro proyecto se coge **solo el módulo**, con lo necesario para que funcione y se integre
   aquí, y **sin ningún dato de aquel cliente**: ni nombres, ni marca, ni datos fiscales, ni
   personas, ni configuración. Si este repositorio tiene comprobador de marca, pásalo antes del
   commit.
4. Este proyecto es **independiente**: no recibe versiones del núcleo ni cambios de otros
   proyectos, y lo que se hace aquí no sube al núcleo. Si otro proyecto lo necesita, lo coge de
   aquí.

El porqué está en el catálogo, en `decisiones/2026-11-17-proyectos-independientes.md`.
