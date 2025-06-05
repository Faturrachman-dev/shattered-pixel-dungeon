# Project Brief: Shattered Pixel Dungeon - Productivity Integration

## Overview
Shattered Pixel Dungeon is an open-source roguelike RPG with pixel art graphics. It's a fork of the original Pixel Dungeon by Watabou, with many enhancements, new content, and improvements to the game mechanics. Our goal is to understand the game architecture and mechanics to create a productivity integration that transforms task management into an engaging RPG experience.

## Vision
Transform Shattered Pixel Dungeon into a gamified productivity platform where real-world tasks and habits are integrated with game progression, rewards, and mechanics. This integration aims to make productivity more engaging by leveraging the game's existing systems of progression, rewards, and challenges.

## Current Goal
The current goal is to thoroughly understand the game's architecture, document core systems, and identify integration points for productivity features. We've successfully built and tested the Android version and are now focusing on code analysis and conceptual development of productivity features.

## Project Technology Stack
- **Core:** LibGDX game development framework
- **Languages:** Java
- **Build System:** Gradle
- **Platforms:** Android (primary focus), Desktop (secondary)

## Repository Structure
- **core:** Contains the main game logic, mechanics, and assets
- **android:** Android-specific implementation
- **desktop:** Desktop-specific implementation
- **services:** Additional services like updates and news
- **SPD-classes:** Custom classes for the game

## Key Components to Understand
- **Game Loop & Progression:** How the game manages turns, levels, and character advancement
- **Save/Load System:** How game state is persisted
- **Reward Mechanics:** How items, gold, and experience are awarded
- **UI System:** How the interface is structured for potential extensions
- **Event System:** How game events are triggered and processed

## Current Status
- Game builds successfully for Android
- APK runs correctly on test device
- Initial code exploration completed
- Focus shifted to detailed documentation and analysis
- Conceptualizing integration points for productivity features

## Productivity Integration Concepts
- Link real-world tasks to in-game rewards and progression
- Use game characters as productivity avatars
- Transform task lists into dungeon levels with completion-based rewards
- Track productivity metrics and visualize as game statistics
- Implement achievement system tied to real-world goals 