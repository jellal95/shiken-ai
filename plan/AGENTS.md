# ShikenAI - Agent Specifications

## Purpose
This document contains specifications for AI agents working on ShikenAI project.

## Project Context
ShikenAI is a CPNS preparation platform powered by AI, targeting Indonesian graduates (20-35 years old).

## Key Technologies
- Backend: Laravel 13 (API-first)
- Admin: Filament v4
- Database: PostgreSQL
- Cache/Leaderboard: Redis
- AI Tutor: Google NotebookLM (MVP) → RAG (Phase 2)
- OCR: Google Vision API
- Format Soal: GPT-4o-mini

## Agent Specializations

### Laravel Agents
When working on ShikenAI, use these specialized agents:
- **laravel-claude-agents:eloquent-specialist** - Database & Eloquent ORM
- **laravel-claude-agents:laravel-api-developer** - API endpoints & resources
- **laravel-claude-agents:laravel-architect** - Architecture decisions
- **laravel-claude-agents:laravel-security-auditor** - Security reviews
- **laravel-claude-agents:laravel-testing-expert** - Test writing (Pest/PHPUnit)

## Key PRD Points
- **Pricing**: Free (Rp0), Pro (Rp79.000/bulan)
- **Beta**: 20 users limit
- **Email**: bang.acnologia@gmail.com
- **Features**: AI Tutor, CAT Simulation, Mastery Heatmap, Monthly Leaderboard

## Reference
See plan/PRD.md for full product requirements.
