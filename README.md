Top Spicy Recipes from Allrecipes (Because Everything Else is for Extras)
- Project Overview & Origin

This project is a themed digital cookbook built as a creative fulfillment of The Odin Project (Foundations: Recipes Project). While the original assignment suggested sourcing recipes from Allrecipes, the initial iteration used custom placeholder recipes.

This version rectifies that while taking the project a step further: it functions as a piece of interactive fanart curated through the lens of Katsuki Bakugo from My Hero Academia. Every recipe chosen—from Spicy Thai Basil Chicken to Mapo Tofu—focuses strictly on high heat, intense flavor, and zero compromises, complete with custom vector iconography and an aggressive dark theme. 

Now that I am past of Foundations, I added the svg, as I have used it a couple of times by now, and using it in this project to get familiar with it.

Technical Implementation
1. Semantic HTML Structure

    The header,  contains site titles h1, explosive subtitles, and original Allrecipes source attribution links.

    main & section: Encloses primary content lists and detail reviews.

    article: Isolates single-subject recipe commentary on detail pages.

    nav: Encapsulates internal back-links for accessibility and clean document flow across subpages.

2. Stylesheet Design System (styles.css)

    Color Palette:

        Background: Pitch Dark (#121212) & Card Surface (#1e1e1e)

        Text: High-Contrast Off-White (#e0e0e0) & Pure White (#ffffff)

        Primary Accent / Heat: Fiery Orange (#FF4500) & Yellow (#FFCC00)

    Interactive States: Anchor links (<a>) transition color and underline on focus/hover.

    Card Borders: Left border accent (border-left: 4px solid #FF4500) highlights each recipe item.

    SVG Vector Graphics Guide

This project marks a continued deep-dive into Inline Scalable Vector Graphics (SVG). Unlike raster images (.png, .jpeg), SVGs are mathematical declarations of paths, shapes, and colors that render crisply at any scale or screen resolution without pixelation.
Anatomy of the Custom Explosion SVG
HTML

<svg class="explosion-icon" viewBox="0 0 100 100" width="22" height="22" aria-hidden="true">
  <!-- Outer Fiery Starburst -->
  <path fill="#FF4500" d="M50,2 L58,32 L88,14 L70,42 L98,50 L70,58 L88,86 L58,68 L50,98 L42,68 L12,86 L30,58 L2,50 L30,42 L12,14 L42,32 Z" />
  <!-- Inner Heat Layer -->
  <path fill="#FFCC00" d="M50,18 L55,38 L75,25 L63,44 L82,50 L63,56 L75,75 L55,62 L50,82 L45,62 L25,75 L37,56 L18,50 L37,44 L25,25 L45,38 Z" />
</svg>

Key Concepts Breakdown:viewBox="0 0 100 100": Defines the internal coordinate grid of the vector canvas ($x=0, y=0$ to $100\times100$ relative units).width & height Attributes: Controls the actual rendered pixel size on screen (e.g., width="22"). The viewBox scale adapts seamlessly to these dimensions.d="..." (Path Commands):M x,y (Move To): Placed cursor at starting coordinate without drawing.L x,y (Line To): Draws a straight line to target coordinate.Z (Close Path): Severs and seals the polygon back to the initial M position.Multi-layered Depth: Layering two stacked <path> shapes creates an outer explosive burst (#FF4500) and a vibrant inner core (#FFCC00).Accessibility (aria-hidden="true"): Ensures screen readers bypass purely aesthetic vector graphics.

Interactive CSS Animations with SVG

Because the SVGs are written directly as inline markup inside HTML, they can be styled and animated using simple CSS selectors:
CSS

/* Base SVG Icon Styling */
.explosion-icon {
  vertical-align: middle;
  margin-right: 8px;
  display: inline-block;
  transition: transform 0.2s ease-in-out; /* Smooth transition for hover states */
}

/* Dynamic Hover Interaction */
li:hover .explosion-icon {
  transform: scale(1.3) rotate(15deg); /* Scales up 30% and rotates on list item hover */
}