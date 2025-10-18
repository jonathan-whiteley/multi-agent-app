# Company Rebranding Guide for Multi-Agent BI App

## LLM Prompt for Complete Company Rebrand

Use this comprehensive prompt when you need to rebrand the application from one company to another:

---

**COMPREHENSIVE REBRANDING REQUEST**

Please help me rebrand this Chainlit Multi-Agent BI application from **[CURRENT_COMPANY]** to **[NEW_COMPANY]**. I need you to make ALL necessary changes to completely swap the branding while maintaining the same functionality.

## NEW COMPANY INFORMATION:
- **Company Name**: [NEW_COMPANY_NAME]
- **Primary Brand Color** (hex): [#PRIMARY_COLOR] 
- **Secondary/Darker Brand Color** (hex): [#SECONDARY_COLOR]
- **Company Black/Dark Color** (hex): [#DARK_COLOR] (if different from standard black)
- **Tagline/Slogan**: [COMPANY_TAGLINE]
- **Logo Files**: [Provide paths to new logo files]
  - Main logo: [path_to_main_logo.svg]
  - Chat avatar: [path_to_avatar_image.png/svg]

## REQUIRED CHANGES:

### 1. REMOVE OLD COMPANY FILES
Please delete ALL files related to [CURRENT_COMPANY]:
- Remove any company-specific logo files in `src/app/public/images/`
- Remove any company-specific HTML files in `src/app/public/html/`
- Remove any company-specific JS files in `src/app/public/js/`
- Remove any company-specific CSS sections or files

**IMPORTANT**: If renaming files instead of deleting, ensure all references to old filenames are updated throughout the codebase.

### 2. LOGO UPDATES
- **Homepage Logo**: Update `logo_file_url` in `.chainlit/config.toml` to new main logo
- **Login Page Logo**: Update `login_page_image` in `.chainlit/config.toml` to new main logo  
- **Chat Avatar**: Update `avatar_url` in `.chainlit/config.toml` to new avatar image
- **CSS Avatar**: Update avatar CSS in `custom-branding.css` to use new avatar image

### 3. COLOR SCHEME UPDATES

#### In `public/theme.json` - Update ALL instances of color values:
**Light Mode Section:**
- `--primary`: Convert [#PRIMARY_COLOR] to HSL format
- `--accent`: Convert [#PRIMARY_COLOR] to HSL format  
- `--border`: Convert [#PRIMARY_COLOR] to HSL format
- `--ring`: Convert [#PRIMARY_COLOR] to HSL format
- `--sidebar-foreground`: Convert [#PRIMARY_COLOR] to HSL format
- `--sidebar-primary`: Convert [#PRIMARY_COLOR] to HSL format
- `--sidebar-accent-foreground`: Convert [#PRIMARY_COLOR] to HSL format
- `--sidebar-border`: Convert [#PRIMARY_COLOR] to HSL format
- `--sidebar-ring`: Convert [#PRIMARY_COLOR] to HSL format

**Dark Mode Section:**
- Update the same variables as light mode with identical HSL values

#### In `public/css/custom-branding.css` - Update ALL color references:
**Color Replacements:**
- Replace ALL instances of current company primary color with [#PRIMARY_COLOR]
- Replace ALL instances of current company secondary color with [#SECONDARY_COLOR]  
- Replace ALL instances of current company dark color with [#DARK_COLOR]
- Update CSS custom properties in `:root` section
- Update all `background`, `border-color`, `color`, and `box-shadow` properties
- Update all gradient definitions to use new colors
- Update RGBA/HSL color variations with transparency

**Class Name Updates:**
- Rename ALL company-specific CSS classes (e.g., `.caseys-*` → `.[new-company]-*`)
- Update class references in HTML files that use renamed classes
- Ensure consistent naming convention throughout

**Text and Content:**
- Update CSS comments that reference old company name
- Change any content in `::before` and `::after` pseudo-elements
- Update company-specific icons/emojis in CSS content

### 4. TEXT AND BRANDING UPDATES

#### In `custom-branding.css`:
- Update header content `::before` and `::after` pseudo-elements with new company name and tagline
- Update sidebar branding text 
- Update any company-specific text in CSS comments
- Update watermark/background elements if present

#### In `.chainlit/config.toml`:
- Update `name` field if it contains company reference
- Update any company-specific comments

### 5. HTML FILES
**File Operations:**
- Rename company-specific HTML files (e.g., `little-caesars-banner.html` → `[new-company]-banner.html`)
- Update file references in any imports or links

**Content Updates:**
- **Page Titles**: Update `<title>` tags to reference new company
- **CSS Classes**: Change all company-specific CSS classes (e.g., `.caesars-*` → `.[new-company]-*`)
- **Colors**: Update all embedded CSS colors to new brand palette
- **Text Content**: Replace all company names and slogans
- **Icons/Emojis**: Update company-specific visual elements
- **Meta Tags**: Update any meta descriptions or keywords
- **CSS Links**: Ensure links to CSS files are correct if files were renamed

### 6. JAVASCRIPT FILES  
**File Operations:**
- Rename company-specific JS files (e.g., `little-caesars-banner.js` → `[new-company]-banner.js`)
- Update any imports or references to renamed JS files

**Code Updates:**
- **Function Names**: Rename all company-specific functions (e.g., `addCaesarsBanner()` → `add[NewCompany]Banner()`)
- **Variable Names**: Update company-specific variable names
- **Element IDs**: Change element IDs from old company to new (e.g., `caesars-banner` → `[new-company]-banner`)
- **Brand Text**: Replace all company name strings in JavaScript
- **Colors**: Update all hex color values to new brand colors
- **Icons/Emojis**: Replace company-specific emojis or icons
- **Taglines**: Update any slogans or taglines in JavaScript strings
- **CSS Classes**: Update any dynamically added CSS classes with company names

### 7. UTILITY CLASSES
Update any CSS utility classes like:
- `.caseys-badge` → `.[new-company]-badge`
- `.caseys-alert` → `.[new-company]-alert`  
- `.caseys-highlight` → `.[new-company]-highlight`
- Update their color schemes to match new brand

### 8. RESPONSIVE DESIGN
Ensure all responsive breakpoints maintain new branding:
- Mobile header adjustments
- Tablet/desktop layout changes
- Color consistency across all screen sizes

### 9. LOADING DEMO UPDATES
Update `src/app/public/html/loading-demo.html`:
- **Page Title**: Update to reference new company
- **CSS Links**: Ensure correct path to custom-branding.css
- **Button Colors**: Update all button background colors to new brand colors
- **Content**: Update header text and any company references
- **Icons**: Replace company-specific emojis or icons

### 10. HOVER STATES AND ANIMATIONS
Update all interactive states:
- Button hover colors
- Link hover effects  
- Animation color schemes
- Focus states and rings

### 10. VERIFICATION CHECKLIST
After completing changes, verify:
- [ ] No references to old company name remain
- [ ] All colors match new brand palette  
- [ ] Both light and dark modes work correctly
- [ ] All logos display properly
- [ ] Chat avatar appears correctly
- [ ] Hover states use new colors
- [ ] Responsive design maintains branding
- [ ] No old company files remain

## COLOR CONVERSION HELPER
To convert hex colors to HSL for theme.json:
- Use online tools or calculate manually
- Format as "hue saturation% lightness%" (e.g., "0 98% 49%")
- Ensure consistency between light and dark modes

## IMPORTANT NOTES:
- Test the application after making changes
- Keep a backup of current configuration before rebranding
- Ensure new logo files are optimized for web use
- Verify color contrast meets accessibility standards
- Check that new colors work well in both light and dark themes

---

## Usage Instructions

1. Copy this prompt
2. Replace all `[PLACEHOLDER]` values with actual company information
3. Provide the new logo files to the LLM
4. Run the prompt to get comprehensive rebranding assistance
5. Test thoroughly after implementation

## File Locations Quick Reference

### Key Files to Update:
- `src/app/.chainlit/config.toml` - Main configuration
- `src/app/public/theme.json` - Theme colors (both light/dark modes)  
- `src/app/public/css/custom-branding.css` - All styling and branding
- `src/app/public/images/` - Logo and image assets
- `src/app/public/html/` - Any branded HTML content
- `src/app/public/js/` - Any branded JavaScript

### Color Properties in theme.json:
```json
"--primary": "HSL_VALUE",
"--accent": "HSL_VALUE", 
"--border": "HSL_VALUE",
"--ring": "HSL_VALUE",
"--sidebar-foreground": "HSL_VALUE",
"--sidebar-primary": "HSL_VALUE",
"--sidebar-accent-foreground": "HSL_VALUE", 
"--sidebar-border": "HSL_VALUE",
"--sidebar-ring": "HSL_VALUE"
```

### Common CSS Properties to Update:
- `background`, `background-color`
- `border`, `border-color` 
- `color`
- `box-shadow`
- Linear gradients
- CSS custom properties in `:root`

## DETAILED REBRANDING EXAMPLES

### Example: Little Caesars → Casey's Conversion
Based on actual implementation, here are specific examples of changes:

#### 1. Configuration Changes (`config.toml`):
```toml
# OLD:
logo_file_url = "public/images/Little_Caesars_logo.svg"
login_page_image = "public/images/Little_Caesars_logo.svg"

# NEW:
logo_file_url = "public/images/Casey's_logo.svg"  
login_page_image = "public/images/Casey's_logo.svg"
avatar_url = "public/images/caseys_mini.png"
```

#### 2. Color Replacements (`custom-branding.css`):
```css
/* OLD Little Caesars Colors: */
#E7612A (orange) → #fb0303 (Casey's red)
#ff6000 (orange) → #fb0303 (Casey's red)
#ff4444 (light orange) → #d90202 (darker Casey's red)

/* OLD RGBA: */
rgba(231, 97, 42, 0.3) → rgba(251, 3, 3, 0.3)
```

#### 3. Text Replacements:
```css
/* OLD: */
content: "🍕 LITTLE CAESARS";
content: "HOT-N-READY!";

/* NEW: */  
content: "🏪 CASEY'S";
content: "HERE FOR YOU!";
```

#### 4. CSS Class Renaming:
```css
/* OLD: */
.caesars-badge, .caesars-alert, .caesars-highlight

/* NEW: */
.caseys-badge, .caseys-alert, .caseys-highlight
```

#### 5. JavaScript Function Updates:
```javascript
// OLD:
function addCaesarsBanner()
element.id = 'caesars-banner'
brandText.textContent = 'LITTLE CAESARS'

// NEW:
function addCaseysBanner()  
element.id = 'caseys-banner'
brandText.textContent = 'CASEY\'S'
```

#### 6. File Renaming:
```
OLD → NEW:
little-caesars-banner.js → caseys-banner.js
little-caesars-banner.html → caseys-banner.html
Little_Caesars_logo.svg → Casey's_logo.svg
```

#### 7. Theme.json HSL Updates:
```json
// OLD (Orange):
"--primary": "17 80% 54%"

// NEW (Casey's Red):  
"--primary": "0 98% 49%"
```

### Quick Search & Replace Patterns:
Use these patterns for efficient rebranding:

1. **Color Codes**: Search for old hex values, replace with new
2. **Company Names**: Search case-insensitive for old company name
3. **CSS Classes**: Search for `.oldcompany-` pattern  
4. **Element IDs**: Search for `oldcompany-` in JavaScript
5. **File References**: Search for old company filename patterns
6. **Comments**: Search for old company name in comments

This guide ensures complete and consistent rebranding across the entire application.
