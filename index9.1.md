1. Updated HTML Code (index.html)
(Note: Step 2 is verified with the proper viewport meta tag in the <head>)

HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!-- Step 2: Verify viewport meta tag for mobile scaling -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aperture & Co. | Mobile-First Gallery</title>
    <link rel="stylesheet" href="style.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&family=Playfair+Display:wght@600&display=swap" rel="stylesheet">
</head>
<body>

    <!-- Header Section -->
    <header class="site-header">
        <h1>Aperture & Co.</h1>
        <p>A curated collection of modern architectural and landscape photography.</p>
    </header>

    <!-- Main Grid Layout -->
    <main class="gallery-container">
        
        <article class="gallery-item">
            <img src="https://images.unsplash.com/photo-1513694203232-719a280e022f?auto=format&fit=crop&w=800&q=80" alt="Minimalist Interior">
            <div class="overlay">
                <h3>Minimalist Spaces</h3>
                <p>Architecture • Tokyo</p>
            </div>
        </article>

        <article class="gallery-item wide">
            <img src="https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?auto=format&fit=crop&w=1200&q=80" alt="Foggy Pine Forest">
            <div class="overlay">
                <h3>Misty Horizons</h3>
                <p>Landscape • Pacific Northwest</p>
            </div>
        </article>

        <article class="gallery-item">
            <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=800&q=80" alt="Tropical Coastline">
            <div class="overlay">
                <h3>Coastal Serenity</h3>
                <p>Seascape • Amalfi Coast</p>
            </div>
        </article>

        <article class="gallery-item">
            <img src="https://images.unsplash.com/photo-1519681393784-d120267933ba?auto=format&fit=crop&w=800&q=80" alt="Starry Night Sky">
            <div class="overlay">
                <h3>Stargazer</h3>
                <p>Night • Swiss Alps</p>
            </div>
        </article>

        <article class="gallery-item tall">
            <img src="https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?auto=format&fit=crop&w=800&q=80" alt="Modern Skyscraper">
            <div class="overlay">
                <h3>Vertical Geometry</h3>
                <p>Urban • Chicago</p>
            </div>
        </article>

        <article class="gallery-item">
            <img src="https://images.unsplash.com/photo-1447752875215-b2761acb3c5d?auto=format&fit=crop&w=800&q=80" alt="Autumn Forest Path">
            <div class="overlay">
                <h3>Autumn Tones</h3>
                <p>Nature • Vermont</p>
            </div>
        </article>

        <article class="gallery-item">
            <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=800&q=80" alt="Yosemite Valley">
            <div class="overlay">
                <h3>Granite Monoliths</h3>
                <p>Adventure • Yosemite</p>
            </div>
        </article>

    </main>

    <!-- Footer Section -->
    <footer class="site-footer">
        <p>&copy; 2026 Aperture & Co. All rights reserved. Mobile-First CSS Grid.</p>
    </footer>

</body>
</html>
2. Mobile-First CSS Code (style.css)
(Note: Steps 3, 4, 5, and 7 are implemented here using base mobile styles followed by progressive min-width breakpoints).

CSS
/* --- Global Styles & Reset --- */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Inter', sans-serif;
    background-color: #0f172a;
    color: #f8fafc;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    overflow-x: hidden; /* Step 7: Prevent horizontal overflow */
}

/* --- Step 3: Base CSS for Mobile Screens First (Single Column) --- */
.site-header {
    text-align: center;
    padding: 30px 16px 20px 16px;
}

.site-header h1 {
    font-family: 'Playfair Display', serif;
    font-size: 2.2rem;
    margin-bottom: 8px;
    color: #ffffff;
}

.site-header p {
    color: #94a3b8;
    font-size: 0.9rem;
    font-weight: 300;
}

.gallery-container {
    display: grid;
    grid-template-columns: 1fr; /* Default mobile view: 1 column */
    grid-auto-rows: 260px;
    gap: 16px;
    width: 90%;
    max-width: 1200px;
    margin: 0 auto 40px auto;
}

.gallery-item {
    position: relative;
    border-radius: 10px;
    overflow: hidden;
    background-color: #1e293b;
    min-width: 0; /* Prevents grid blowout from text/images */
}

.gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: cover; /* Prevents image distortion */
    display: block;
}

.overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    padding: 20px 16px 16px 16px;
    background: linear-gradient(to top, rgba(15, 23, 42, 0.95) 0%, rgba(15, 23, 42, 0) 100%);
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
}

.overlay h3 {
    font-size: 1.1rem;
    font-weight: 600;
    color: #ffffff;
    margin-bottom: 4px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis; /* Step 7: Prevent text overflow */
}

.overlay p {
    font-size: 0.8rem;
    color: #cbd5e1;
}

.site-footer {
    text-align: center;
    padding: 24px;
    background-color: #0b0f19;
    color: #64748b;
    font-size: 0.85rem;
    margin-top: auto;
    border-top: 1px solid #1e293b;
}


/* ==========================================================
   STEPS 4 & 5: Media Queries & Breakpoints (Min-Width Approach)
   ========================================================== */

/* --- Breakpoint 1: Tablet View (min-width: 640px) --- */
@media (min-width: 640px) {
    .site-header {
        padding: 40px 20px 24px 20px;
    }
    
    .site-header h1 {
        font-size: 2.5rem;
    }

    .gallery-container {
        grid-template-columns: repeat(2, 1fr); /* Switch to 2 columns for tablets */
        gap: 20px;
    }
}

/* --- Breakpoint 2: Desktop View (min-width: 1024px) --- */
@media (min-width: 1024px) {
    .site-header {
        padding: 50px 20px 30px 20px;
    }

    .site-header h1 {
        font-size: 2.8rem;
    }

    .gallery-container {
        grid-template-columns: repeat(3, 1fr); /* Switch to 3 columns for desktops */
        grid-auto-rows: 280px;
        gap: 24px;
    }

    /* Enable explicit spans on desktop screens where extra space is available */
    .gallery-item.wide {
        grid-column: span 2;
    }

    .gallery-item.tall {
        grid-row: span 2;
    }

    .gallery-item {
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .gallery-item:hover {
        transform: translateY(-5px);
        box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.4);
    }
}
Assignment Checklist & Verification:
Viewport Meta Tag: Verified in the HTML <head> (<meta name="viewport" content="width=device-width, initial-scale=1.0">).

Mobile-First CSS Architecture: Base rules default to a clean, stacked single-column layout optimized for mobile screens.

Media Queries & Breakpoints: Implemented two distinct breakpoints using min-width (640px for tablets and 1024px for desktops) to scale columns and grid spans progressively.

Testing in Device Mode (Steps 6 & 7): Controlled horizontal overflow via overflow-x: hidden, grid item min-width: 0, and text-overflow: ellipsis so elements never clip or overlap on small viewports.