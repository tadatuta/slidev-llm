<template>
  <div class="global-bg">
    <!-- Mesh gradient blurred blobs -->
    <div class="blob blob-1"></div>
    <div class="blob blob-2"></div>
    <div class="blob blob-3"></div>

    <!-- SVG Isohypse Pattern -->
    <svg class="iso-pattern" viewBox="0 0 960 540" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="iso-grad" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#004E64" stop-opacity="0.25" />
          <stop offset="35%" stop-color="#00FA9A" stop-opacity="0.12" />
          <stop offset="65%" stop-color="#5D2E8C" stop-opacity="0.15" />
          <stop offset="100%" stop-color="#D68C45" stop-opacity="0.1" />
        </linearGradient>
      </defs>
      <!-- Isohypse contour lines — flowing, never crossing -->
      <path d="M-50,420 Q120,380 240,400 T480,370 T720,390 T1010,360" fill="none" stroke="url(#iso-grad)" stroke-width="0.6" opacity="0.4"/>
      <path d="M-50,440 Q150,410 280,425 T520,395 T760,415 T1010,385" fill="none" stroke="url(#iso-grad)" stroke-width="0.5" opacity="0.3"/>
      <path d="M-50,460 Q100,435 260,448 T500,420 T740,440 T1010,410" fill="none" stroke="url(#iso-grad)" stroke-width="0.4" opacity="0.25"/>
      <path d="M-50,480 Q180,458 310,470 T540,445 T780,462 T1010,435" fill="none" stroke="url(#iso-grad)" stroke-width="0.5" opacity="0.2"/>
      <path d="M-50,500 Q130,480 270,490 T510,468 T750,485 T1010,460" fill="none" stroke="url(#iso-grad)" stroke-width="0.3" opacity="0.15"/>

      <!-- Upper isohypses (subtle) -->
      <path d="M-50,80 Q200,60 400,90 T700,65 T1010,85" fill="none" stroke="url(#iso-grad)" stroke-width="0.4" opacity="0.15"/>
      <path d="M-50,100 Q180,85 350,105 T650,80 T1010,100" fill="none" stroke="url(#iso-grad)" stroke-width="0.3" opacity="0.1"/>
      <path d="M-50,120 Q220,105 420,118 T720,95 T1010,115" fill="none" stroke="url(#iso-grad)" stroke-width="0.35" opacity="0.12"/>
    </svg>

    <!-- Slide number -->
    <div v-if="$nav.currentLayout !== 'cover'" class="slide-num">
      {{ $nav.currentPage }} / {{ $nav.total }}
    </div>
  </div>
</template>

<style>
.global-bg {
  position: absolute;
  inset: 0;
  overflow: hidden;
  pointer-events: none;
  z-index: 0;
}

/* Mesh gradient blobs — Gaussian Blur effect */
.blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(120px);
  opacity: 0.35;
  will-change: transform;
}

.blob-1 {
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, #004E64 0%, transparent 70%);
  top: -15%;
  left: -10%;
  animation: float-1 18s ease-in-out infinite;
}

.blob-2 {
  width: 400px;
  height: 400px;
  background: radial-gradient(circle, #5D2E8C 0%, transparent 70%);
  top: 50%;
  right: -8%;
  animation: float-2 22s ease-in-out infinite;
}

.blob-3 {
  width: 350px;
  height: 350px;
  background: radial-gradient(circle, #D68C45 0%, transparent 70%);
  bottom: -10%;
  left: 40%;
  opacity: 0.2;
  animation: float-3 20s ease-in-out infinite;
}

@keyframes float-1 {
  0%, 100% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(40px, 30px) scale(1.1); }
}

@keyframes float-2 {
  0%, 100% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(-30px, -40px) scale(1.05); }
}

@keyframes float-3 {
  0%, 100% { transform: translate(0, 0) scale(1); }
  50% { transform: translate(25px, -20px) scale(1.08); }
}

/* SVG pattern layer */
.iso-pattern {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  opacity: 0.7;
}

/* Slide number */
.slide-num {
  position: absolute;
  bottom: 16px;
  right: 24px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.75rem;
  color: rgba(230, 232, 240, 0.3);
  letter-spacing: 0.1em;
  z-index: 10;
}
</style>
