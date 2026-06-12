# Mzansi Eats – Responsiveness Audit and Improvements

## Project Overview

Mzansi Eats is a food delivery landing page designed to showcase popular South African dishes, provide customer contact information, and allow users to place food orders online.

As part of Sprint 2, a responsiveness audit was conducted to ensure the website provides an optimal user experience across different devices and screen sizes.

---

## Audit Scope

The website was tested using Chrome DevTools at the following screen widths:

* Mobile: 375px
* Tablet: 768px
* Desktop: 1280px

The objective was to identify layout and usability issues affecting responsiveness and implement appropriate fixes.

---

## Issues Identified

### 1. Hero Image Overflow

**Problem**

The hero image had a fixed width of 1200px, causing overflow on smaller screens.

**Original Code**

```css
.hero img {
    width: 1200px;
    height: 400px;
}
```

**Solution**

```css
.hero img {
    width: 100%;
    height: auto;
}
```

**Result**

The hero image now scales automatically to fit all screen sizes.

---

### 2. Product Cards Not Responsive

**Problem**

The menu section used a fixed four-column grid layout that exceeded the width of mobile devices.

**Original Code**

```css
.card-grid {
    grid-template-columns: repeat(4, 250px);
}
```

**Solution**

```css
.card-grid {
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
}
```

**Result**

Cards automatically adjust based on available screen width.

---

### 3. Contact Section Fixed Width

**Problem**

The contact container used a fixed width of 800px which caused layout issues on mobile devices.

**Original Code**

```css
.contact-inner {
    width: 800px;
}
```

**Solution**

```css
.contact-inner {
    width: 100%;
    max-width: 800px;
    margin: 0 auto;
}
```

**Result**

The contact section now adapts to all screen sizes while maintaining a maximum width on larger screens.

---

### 4. Contact Form Layout Issues

**Problem**

The contact section displayed two columns even on small screens.

**Original Code**

```css
.contact-grid {
    grid-template-columns: 1fr 1fr;
}
```

**Solution**

```css
@media (max-width: 768px) {
    .contact-grid {
        grid-template-columns: 1fr;
    }
}
```

**Result**

The contact form and contact information now stack vertically on mobile devices.

---

### 5. Navigation Layout Improvements

**Problem**

The navigation bar became crowded on smaller screens.

**Solution**

```css
@media (max-width: 768px) {
    header {
        flex-direction: column;
        text-align: center;
    }

    nav {
        flex-wrap: wrap;
        justify-content: center;
    }
}
```

**Result**

Navigation links remain accessible and readable across devices.

---

## Responsive Enhancements Added

The following media query was added to improve responsiveness:

```css
@media (max-width: 768px) {

    header {
        flex-direction: column;
        text-align: center;
    }

    nav {
        flex-wrap: wrap;
        justify-content: center;
    }

    .hero img {
        width: 100%;
        height: auto;
    }

    .hero-text h2 {
        font-size: 1.8rem;
    }

    .card-grid {
        grid-template-columns: 1fr;
    }

    .contact-inner {
        width: 100%;
    }

    .contact-grid {
        grid-template-columns: 1fr;
    }

    footer {
        flex-direction: column;
        text-align: center;
        gap: 10px;
    }
}
```

---

## Testing Results

| Device Width     | Status |
| ---------------- | ------ |
| 375px (Mobile)   | Passed |
| 768px (Tablet)   | Passed |
| 1280px (Desktop) | Passed |

---

## Technologies Used

* HTML5
* CSS3
* CSS Grid
* Flexbox
* Chrome DevTools

---
## Here are before and images for the landing page 
![Mzansi Eats Desktop View](./assets/banner/before%20375.png)
![Mzansi Eats Desktop View](./assets/banner/before%20768.png)
![Mzansi Eats Desktop View](./assets/banner/before%201280.png)
![Mzansi Eats Desktop View](./assets/banner/after%20375.png)
![Mzansi Eats Desktop View](./assets/banner/after%20768.png)
![Mzansi Eats Desktop View](./assets/banner/after%201280.png)

---
## Author

**Nonkululeko Mphoentle Maphanga**

Sprint 2 – Responsive Web Design Audit
