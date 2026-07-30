const fs = require('fs');

const imgBuffer = fs.readFileSync('c:/Users/ACER/Desktop/CODEFEST-2026-AK-INNOVATORS/assets/astronaut_nobg.png');
const base64Str = imgBuffer.toString('base64');

const svgHeader = `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 360" width="100%" height="100%">
  <defs>
    <!-- Dark Background Gradient -->
    <linearGradient id="bg-grad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#090212"/>
      <stop offset="50%" stop-color="#140524"/>
      <stop offset="100%" stop-color="#090212"/>
    </linearGradient>

    <!-- Dome/Arc Gradient -->
    <radialGradient id="dome-grad" cx="50%" cy="100%" r="90%">
      <stop offset="0%" stop-color="#c026d3"/>
      <stop offset="35%" stop-color="#9333ea"/>
      <stop offset="70%" stop-color="#581c87"/>
      <stop offset="100%" stop-color="#2e1065"/>
    </radialGradient>

    <!-- Glow Filter -->
    <filter id="glow" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur stdDeviation="8" result="blur" />
      <feComposite in="SourceGraphic" in2="blur" operator="over" />
    </filter>
    
    <filter id="text-glow">
      <feGaussianBlur stdDeviation="4" result="blur" />
      <feComponentTransfer in="blur" result="glow1">
        <feFuncA type="linear" slope="0.6"/>
      </feComponentTransfer>
      <feMerge>
        <feMergeNode in="glow1" />
        <feMergeNode in="SourceGraphic" />
      </feMerge>
    </filter>

    <clipPath id="avatar-clip">
      <circle cx="0" cy="0" r="44" />
    </clipPath>
  </defs>

  <!-- Background Base -->
  <rect width="1200" height="360" fill="url(#bg-grad)"/>

  <!-- Dome / Arch Curve -->
  <path d="M 0,360 L 0,160 Q 250,160 400,100 Q 600,-20 800,100 Q 950,160 1200,160 L 1200,360 Z" fill="url(#dome-grad)" opacity="0.95"/>

  <!-- Arch Accent Glow Line -->
  <path d="M 0,160 Q 250,160 400,100 Q 600,-20 800,100 Q 950,160 1200,160" fill="none" stroke="#e879f9" stroke-width="3" filter="url(#glow)" opacity="0.8"/>

  <!-- Top Center Astronaut Avatar Badge -->
  <g transform="translate(600, 85)">
    <!-- Outer Glow Ring -->
    <circle r="48" fill="#090212" stroke="#d8b4fe" stroke-width="3.5" filter="url(#glow)"/>
    <!-- Inner Dark Circle -->
    <circle r="44" fill="#140524" />
    <!-- Transparent Astronaut Image -->
    <g clip-path="url(#avatar-clip)">
      <image href="data:image/png;base64,${base64Str}" x="-44" y="-44" width="88" height="88" preserveAspectRatio="xMidYMid slice" />
    </g>
  </g>

  <!-- Main Title: HELLO WORLD -->
  <text x="600" y="210" text-anchor="middle" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif" font-weight="900" font-size="46" fill="#FFFFFF" letter-spacing="7" filter="url(#text-glow)">HELLO WORLD</text>
  
  <!-- Subtitle: WELCOME TO MY PROFILE -->
  <text x="600" y="248" text-anchor="middle" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif" font-weight="700" font-size="14" fill="#f0abfc" letter-spacing="5">WELCOME TO MY PROFILE</text>

  <!-- Left Side: Web Link & Tech Stripes -->
  <g transform="translate(100, 195)">
    <!-- Globe Icon Circle -->
    <circle cx="20" cy="0" r="14" fill="#1e0a38" stroke="#a855f7" stroke-width="1.5"/>
    <!-- Globe Icon -->
    <circle cx="20" cy="0" r="8" fill="none" stroke="#e879f9" stroke-width="1.2"/>
    <ellipse cx="20" cy="0" rx="4" ry="8" fill="none" stroke="#e879f9" stroke-width="1"/>
    <line x1="12" y1="0" x2="28" y2="0" stroke="#e879f9" stroke-width="1"/>
    <!-- URL Text -->
    <text x="44" y="5" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif" font-weight="600" font-size="14" fill="#e9d5ff" letter-spacing="1">https://saizosuya.github.io</text>

    <!-- Decorative Slanted Stripes /// -->
    <g transform="translate(44, 30)" opacity="0.6">
      <polygon points="0,22 18,0 32,0 14,22" fill="none" stroke="#c026d3" stroke-width="1.8"/>
      <polygon points="20,22 38,0 52,0 34,22" fill="none" stroke="#c026d3" stroke-width="1.8"/>
      <polygon points="40,22 58,0 72,0 54,22" fill="none" stroke="#c026d3" stroke-width="1.8"/>
    </g>
  </g>

  <!-- Right Side: Email & Tech Stripes -->
  <g transform="translate(770, 195)">
    <!-- Email Icon Circle -->
    <circle cx="20" cy="0" r="14" fill="#1e0a38" stroke="#a855f7" stroke-width="1.5"/>
    <!-- Mail Envelope Icon -->
    <rect x="13" y="-5" width="14" height="10" rx="1.5" fill="none" stroke="#e879f9" stroke-width="1.2"/>
    <path d="M 13,-4 L 20,1 L 27,-4" fill="none" stroke="#e879f9" stroke-width="1.2"/>
    <!-- Email Text -->
    <text x="44" y="5" font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif" font-weight="600" font-size="14" fill="#e9d5ff" letter-spacing="1">kritansharms05@gmail.com</text>

    <!-- Decorative Slanted Stripes /// -->
    <g transform="translate(240, 30)" opacity="0.6">
      <polygon points="0,22 18,0 32,0 14,22" fill="none" stroke="#c026d3" stroke-width="1.8"/>
      <polygon points="20,22 38,0 52,0 34,22" fill="none" stroke="#c026d3" stroke-width="1.8"/>
      <polygon points="40,22 58,0 72,0 54,22" fill="none" stroke="#c026d3" stroke-width="1.8"/>
    </g>
  </g>
</svg>`;

fs.writeFileSync('c:/Users/ACER/Desktop/CODEFEST-2026-AK-INNOVATORS/assets/header.svg', svgHeader);
console.log('Successfully updated header.svg with transparent astronaut badge!');
