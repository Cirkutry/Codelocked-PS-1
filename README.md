<h3>Simple Applications Bot</h3>

## Overview
This is the site built for problem statement 1 for the Code Locked interview. Problem statement is as follows:

> Challenge 1: 🚀 Mars Habitat Resource Tracker Site
> Goal: Create a simple website dashboard for a newly established research habitat (e.g.,
> Olympus Mons Base). The dashboard must clearly display current, fictional vital statistics for
> the habitat (Oxygen level, Power remaining, Water recycling rate) and feature a section for
> the crew's operational log/status updates.
> Mandatory Features:
> 1. "Manual Override" Button: A prominent button that, when clicked, changes the
> background color of the main status display (e.g., from green to critical red) and
> overlays a large "EMERGENCY" banner, demonstrating basic front-end
> manipulation logic.
> 2. Resource Bar Visualization: Use styling to create simple progress bars or visual
> gauges (not just numbers) to represent the current levels of at least two vital
> resources (e.g., Oxygen and Power).
> 3. Crew Status Filter: Implement a simple toggle or button that allows the user to
> switch the crew log display between "Active Missions" and "Rest/Standby" entries,
> requiring basic logic to toggle visibility/data.

The site is built in Svelte-kit and is styled with ShadcnUI components powered by TailwindCSS and Typescript.

## Features
- Has a dark mode switcher with info panels on the status of the habitat.
- Has gallery and auto playing carousels to showcase pictures.

## Setup

1. Clone the repository
```bash
git clone https://github.com/Cirkutry/Codelocked-PS-1.git
cd Codelocked-PS-1
```

2. Install dependencies
```bash
npm install
```

3. Start the dev server

```bash
npm run dev
```
The server will run and give the localhost url to view the site!

## License
The code for the site is licensed under the [GPLv3 license](https://github.com/Cirkutry/Codelocked-PS-1/blob/main/LICENSE).