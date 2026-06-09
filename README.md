# volterra
<!DOCTYPE html>
<html lang="fr" data-theme="dark">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Volterra — La Référence Européenne de la Mobilité Électrique</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Syne:wght@700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
/* ============================================================
   VOLTERRA — DESIGN SYSTEM
   Navy Deep + Gold + Dark Mode Native
   ============================================================ */
:root {
  --navy:        #0A0F1E;
  --navy-mid:    #0F1829;
  --navy-light:  #162035;
  --navy-card:   #111827;
  --gold:        #C9A84C;
  --gold-light:  #E2C46A;
  --gold-dim:    #8A6D2F;
  --gold-glow:   rgba(201,168,76,0.18);
  --white:       #F0F2F7;
  --white-dim:   rgba(240,242,247,0.55);
  --white-faint: rgba(240,242,247,0.08);
  --accent-blue: #3B82F6;
  --accent-teal: #00D4AA;
  --danger:      #EF4444;
  --success:     #22C55E;

  --font-display: 'Syne', sans-serif;
  --font-body:    'Space Grotesk', sans-serif;
  --font-mono:    'JetBrains Mono', monospace;

  --radius-sm:  6px;
  --radius-md:  12px;
  --radius-lg:  20px;
  --radius-xl:  32px;

  --shadow-gold: 0 0 40px rgba(201,168,76,0.25);
  --shadow-card: 0 8px 40px rgba(0,0,0,0.5);
  --border-gold: 1px solid rgba(201,168,76,0.2);
  --border-dim:  1px solid rgba(240,242,247,0.06);

  --transition: all 0.3s cubic-bezier(0.4,0,0.2,1);
  --transition-slow: all 0.6s cubic-bezier(0.4,0,0.2,1);
}

/* ============================================================ RESET */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; overflow-x: hidden; }
body {
  background: var(--navy);
  color: var(--white);
  font-family: var(--font-body);
  font-size: 16px;
  line-height: 1.6;
  overflow-x: hidden;
}
::selection { background: var(--gold); color: var(--navy); }
::-webkit-scrollbar { width: 5px; }
::-webkit-scrollbar-track { background: var(--navy-mid); }
::-webkit-scrollbar-thumb { background: var(--gold); border-radius: 3px; }
img { display: block; max-width: 100%; }
a { color: inherit; text-decoration: none; }
button { cursor: pointer; font-family: var(--font-body); border: none; background: none; }

/* ============================================================ NOISE OVERLAY */
body::before {
  content: '';
  position: fixed; inset: 0; z-index: 0; pointer-events: none;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
  opacity: 0.4;
}

/* ============================================================ NAVBAR */
#navbar {
  position: fixed; top: 0; left: 0; right: 0; z-index: 1000;
  display: flex; align-items: center; justify-content: space-between;
  padding: 18px 48px;
  transition: var(--transition);
}
#navbar.scrolled {
  background: rgba(10,15,30,0.92);
  backdrop-filter: blur(20px);
  border-bottom: var(--border-gold);
  padding: 12px 48px;
}
.nav-logo {
  display: flex; align-items: center; gap: 10px;
  font-family: var(--font-display); font-size: 1.5rem; font-weight: 800;
  letter-spacing: -0.02em;
}
.nav-logo span { color: var(--gold); }
.nav-logo-icon {
  width: 36px; height: 36px;
  background: linear-gradient(135deg, var(--gold), var(--gold-dim));
  border-radius: 8px;
  display: flex; align-items: center; justify-content: center;
  font-size: 1.1rem;
}
.nav-links {
  display: flex; align-items: center; gap: 6px;
  list-style: none;
}
.nav-links a {
  padding: 8px 16px;
  font-size: 0.875rem; font-weight: 500;
  color: var(--white-dim);
  border-radius: var(--radius-sm);
  transition: var(--transition);
  position: relative;
}
.nav-links a:hover { color: var(--white); background: var(--white-faint); }
.nav-links a.active { color: var(--gold); }
.nav-actions {
  display: flex; align-items: center; gap: 12px;
}
.lang-toggle {
  display: flex; gap: 2px;
  background: var(--white-faint);
  border-radius: var(--radius-sm);
  padding: 3px;
}
.lang-btn {
  padding: 5px 12px;
  font-size: 0.75rem; font-weight: 600; font-family: var(--font-mono);
  color: var(--white-dim);
  border-radius: 4px;
  transition: var(--transition);
}
.lang-btn.active { background: var(--gold); color: var(--navy); }
.btn-primary {
  padding: 10px 24px;
  background: linear-gradient(135deg, var(--gold), var(--gold-dim));
  color: var(--navy);
  font-weight: 700; font-size: 0.875rem;
  border-radius: var(--radius-sm);
  transition: var(--transition);
  box-shadow: 0 4px 20px rgba(201,168,76,0.3);
}
.btn-primary:hover { transform: translateY(-2px); box-shadow: var(--shadow-gold); }
.btn-ghost {
  padding: 10px 24px;
  border: var(--border-gold);
  color: var(--gold);
  font-weight: 600; font-size: 0.875rem;
  border-radius: var(--radius-sm);
  transition: var(--transition);
}
.btn-ghost:hover { background: var(--gold-glow); }

/* ============================================================ HERO */
#hero {
  position: relative; min-height: 100vh;
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  text-align: center; overflow: hidden;
  padding: 120px 24px 80px;
}
.hero-video-wrap {
  position: absolute; inset: 0; z-index: 0; overflow: hidden;
}
.hero-video-wrap video {
  width: 100%; height: 100%; object-fit: cover;
  opacity: 0.18; filter: saturate(0.4);
}
.hero-video-wrap::after {
  content: '';
  position: absolute; inset: 0;
  background: radial-gradient(ellipse 80% 60% at 50% 60%, transparent 0%, var(--navy) 70%),
              linear-gradient(to bottom, var(--navy) 0%, transparent 20%, transparent 75%, var(--navy) 100%);
}
.hero-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  pointer-events: none;
}
.orb-1 {
  width: 600px; height: 600px;
  background: radial-gradient(circle, rgba(201,168,76,0.12), transparent 70%);
  top: -100px; left: 50%; transform: translateX(-50%);
  animation: orbFloat 8s ease-in-out infinite;
}
.orb-2 {
  width: 400px; height: 400px;
  background: radial-gradient(circle, rgba(59,130,246,0.08), transparent 70%);
  bottom: 10%; right: 10%;
  animation: orbFloat 12s ease-in-out infinite reverse;
}
.orb-3 {
  width: 300px; height: 300px;
  background: radial-gradient(circle, rgba(0,212,170,0.07), transparent 70%);
  top: 30%; left: 5%;
  animation: orbFloat 10s ease-in-out infinite 2s;
}
@keyframes orbFloat {
  0%, 100% { transform: translateY(0) scale(1); }
  50% { transform: translateY(-30px) scale(1.05); }
}
.hero-content { position: relative; z-index: 2; max-width: 860px; }
.hero-eyebrow {
  display: inline-flex; align-items: center; gap: 8px;
  background: var(--gold-glow);
  border: var(--border-gold);
  padding: 6px 18px;
  border-radius: 100px;
  font-size: 0.75rem; font-weight: 600; font-family: var(--font-mono);
  color: var(--gold);
  letter-spacing: 0.08em; text-transform: uppercase;
  margin-bottom: 28px;
  animation: fadeInDown 0.8s ease both;
}
.hero-eyebrow::before {
  content: '';
  width: 6px; height: 6px;
  background: var(--gold);
  border-radius: 50%;
  animation: pulse 2s ease-in-out infinite;
}
@keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.3} }
.hero-title {
  font-family: var(--font-display);
  font-size: clamp(2.8rem, 7vw, 6.5rem);
  font-weight: 800;
  line-height: 1.0;
  letter-spacing: -0.03em;
  margin-bottom: 24px;
  animation: fadeInUp 0.8s ease 0.1s both;
}
.hero-title .gold { color: var(--gold); }
.hero-title .gradient {
  background: linear-gradient(90deg, var(--gold-light), var(--accent-teal));
  -webkit-background-clip: text; -webkit-text-fill-color: transparent;
}
.hero-sub {
  font-size: 1.15rem;
  color: var(--white-dim);
  max-width: 560px;
  margin: 0 auto 40px;
  line-height: 1.7;
  animation: fadeInUp 0.8s ease 0.2s both;
}
.hero-actions {
  display: flex; align-items: center; justify-content: center; gap: 16px;
  flex-wrap: wrap;
  animation: fadeInUp 0.8s ease 0.3s both;
}
.hero-stats {
  display: flex; justify-content: center; gap: 48px;
  margin-top: 80px;
  animation: fadeInUp 0.8s ease 0.5s both;
  position: relative; z-index: 2;
}
.hero-stat .num {
  font-family: var(--font-display);
  font-size: 2.5rem; font-weight: 800;
  color: var(--gold);
  line-height: 1;
}
.hero-stat .label {
  font-size: 0.8rem;
  color: var(--white-dim);
  text-transform: uppercase;
  letter-spacing: 0.06em;
  margin-top: 4px;
}
.hero-scroll {
  position: absolute; bottom: 36px; left: 50%; transform: translateX(-50%);
  z-index: 2; display: flex; flex-direction: column; align-items: center; gap: 8px;
  color: var(--white-dim); font-size: 0.75rem; letter-spacing: 0.08em; text-transform: uppercase;
  animation: fadeIn 1s ease 1s both;
}
.scroll-line {
  width: 1px; height: 48px;
  background: linear-gradient(to bottom, var(--gold), transparent);
  animation: scrollPulse 2s ease-in-out infinite;
}
@keyframes scrollPulse { 0%{opacity:1} 50%{opacity:0.3} 100%{opacity:1} }

/* ============================================================ SECTION COMMONS */
section { position: relative; z-index: 1; }
.section-label {
  font-family: var(--font-mono);
  font-size: 0.7rem; font-weight: 500;
  color: var(--gold);
  letter-spacing: 0.12em; text-transform: uppercase;
  margin-bottom: 12px;
}
.section-title {
  font-family: var(--font-display);
  font-size: clamp(2rem, 4vw, 3.2rem);
  font-weight: 800;
  letter-spacing: -0.02em;
  line-height: 1.1;
  margin-bottom: 16px;
}
.section-sub {
  font-size: 1rem;
  color: var(--white-dim);
  max-width: 520px;
  line-height: 1.7;
}
.container { max-width: 1200px; margin: 0 auto; padding: 0 24px; }
.py-section { padding: 120px 0; }

/* ============================================================ TABS NAV */
#tabs-nav {
  position: sticky; top: 64px; z-index: 900;
  background: rgba(10,15,30,0.95);
  backdrop-filter: blur(20px);
  border-bottom: var(--border-dim);
  border-top: var(--border-dim);
}
.tabs-scroll {
  display: flex; gap: 2px;
  padding: 10px 24px;
  overflow-x: auto;
  scrollbar-width: none;
  max-width: 1200px; margin: 0 auto;
}
.tabs-scroll::-webkit-scrollbar { display: none; }
.tab-btn {
  display: flex; align-items: center; gap: 8px;
  padding: 8px 20px;
  font-size: 0.8rem; font-weight: 600;
  color: var(--white-dim);
  border-radius: var(--radius-sm);
  transition: var(--transition);
  white-space: nowrap;
  border: 1px solid transparent;
}
.tab-btn:hover { color: var(--white); background: var(--white-faint); }
.tab-btn.active {
  color: var(--gold);
  background: var(--gold-glow);
  border-color: rgba(201,168,76,0.25);
}
.tab-icon { font-size: 1rem; }

/* ============================================================ MARKETPLACE */
#marketplace { padding: 100px 0 80px; }
.marketplace-header {
  display: flex; justify-content: space-between; align-items: flex-end;
  margin-bottom: 48px; flex-wrap: wrap; gap: 24px;
}
.marketplace-filters {
  display: flex; gap: 10px; flex-wrap: wrap;
  margin-bottom: 32px;
}
.filter-chip {
  display: flex; align-items: center; gap: 6px;
  padding: 7px 16px;
  background: var(--navy-light);
  border: var(--border-dim);
  border-radius: 100px;
  font-size: 0.8rem; font-weight: 500;
  color: var(--white-dim);
  transition: var(--transition);
  cursor: pointer;
}
.filter-chip:hover, .filter-chip.active {
  border-color: var(--gold);
  color: var(--gold);
  background: var(--gold-glow);
}
.filter-search {
  display: flex; align-items: center; gap: 12px;
  background: var(--navy-light);
  border: var(--border-dim);
  border-radius: var(--radius-md);
  padding: 12px 20px;
  margin-bottom: 32px;
  max-width: 520px;
  transition: var(--transition);
}
.filter-search:focus-within { border-color: var(--gold); box-shadow: 0 0 0 3px var(--gold-glow); }
.filter-search input {
  background: none; border: none; outline: none;
  color: var(--white); font-family: var(--font-body); font-size: 0.9rem;
  flex: 1;
}
.filter-search input::placeholder { color: var(--white-dim); }
.grid-listings {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 24px;
}
.listing-card {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  overflow: hidden;
  transition: var(--transition);
  cursor: pointer;
}
.listing-card:hover {
  transform: translateY(-6px);
  border-color: rgba(201,168,76,0.3);
  box-shadow: var(--shadow-card), 0 0 30px rgba(201,168,76,0.1);
}
.listing-img {
  position: relative;
  height: 200px;
  overflow: hidden;
}
.listing-img-inner {
  width: 100%; height: 100%;
  display: flex; align-items: center; justify-content: center;
  font-size: 5rem;
  transition: transform 0.4s ease;
}
.listing-card:hover .listing-img-inner { transform: scale(1.08); }
.listing-badge {
  position: absolute; top: 12px; left: 12px;
  background: var(--gold);
  color: var(--navy);
  font-size: 0.65rem; font-weight: 700;
  padding: 4px 10px;
  border-radius: 100px;
  letter-spacing: 0.06em; text-transform: uppercase;
}
.listing-badge.premium { background: linear-gradient(135deg, #8B5CF6, #6D28D9); color: #fff; }
.listing-badge.new { background: var(--accent-teal); }
.listing-fav {
  position: absolute; top: 12px; right: 12px;
  width: 34px; height: 34px;
  background: rgba(10,15,30,0.7);
  backdrop-filter: blur(10px);
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 1rem;
  transition: var(--transition);
  border: var(--border-dim);
}
.listing-fav:hover { background: var(--gold); transform: scale(1.1); }
.listing-body { padding: 18px; }
.listing-meta {
  display: flex; justify-content: space-between; align-items: center;
  margin-bottom: 8px;
}
.listing-cat {
  font-size: 0.7rem; font-weight: 600; font-family: var(--font-mono);
  color: var(--gold); letter-spacing: 0.08em; text-transform: uppercase;
}
.listing-loc {
  font-size: 0.75rem; color: var(--white-dim);
  display: flex; align-items: center; gap: 4px;
}
.listing-name {
  font-size: 1rem; font-weight: 700; margin-bottom: 6px;
  color: var(--white);
}
.listing-specs {
  display: flex; gap: 12px;
  margin-bottom: 14px;
}
.spec-tag {
  font-size: 0.7rem; font-family: var(--font-mono);
  color: var(--white-dim);
  background: var(--white-faint);
  padding: 3px 8px;
  border-radius: 4px;
}
.listing-footer {
  display: flex; justify-content: space-between; align-items: center;
}
.listing-price {
  font-family: var(--font-display);
  font-size: 1.4rem; font-weight: 800;
  color: var(--gold);
}
.listing-price small {
  font-size: 0.7rem; font-weight: 500;
  color: var(--white-dim);
  font-family: var(--font-body);
  display: block; line-height: 1;
  text-decoration: line-through;
}
.btn-sm {
  padding: 7px 16px;
  font-size: 0.78rem; font-weight: 600;
  border-radius: var(--radius-sm);
  transition: var(--transition);
}
.btn-gold-sm {
  background: var(--gold);
  color: var(--navy);
}
.btn-gold-sm:hover { background: var(--gold-light); transform: translateY(-1px); }
.listing-seller {
  display: flex; align-items: center; gap: 8px;
  padding: 12px 18px;
  border-top: var(--border-dim);
}
.seller-avatar {
  width: 28px; height: 28px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--gold), var(--gold-dim));
  display: flex; align-items: center; justify-content: center;
  font-size: 0.7rem; font-weight: 700; color: var(--navy);
}
.seller-info { flex: 1; }
.seller-name { font-size: 0.78rem; font-weight: 600; }
.seller-stars { font-size: 0.65rem; color: var(--gold); }
.verified-badge {
  width: 18px; height: 18px;
  background: var(--accent-teal);
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 0.6rem;
}

/* ============================================================ RIDERS (SOCIAL) */
#riders { padding: 100px 0 80px; }
.social-layout {
  display: grid;
  grid-template-columns: 280px 1fr 320px;
  gap: 24px;
  align-items: start;
}
.social-sidebar {
  position: sticky; top: 130px;
}
.profile-card {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  overflow: hidden;
  margin-bottom: 16px;
}
.profile-cover {
  height: 80px;
  background: linear-gradient(135deg, var(--navy-light) 0%, rgba(201,168,76,0.15) 100%);
  position: relative;
}
.profile-avatar-wrap {
  position: absolute;
  bottom: -28px; left: 20px;
}
.profile-avatar {
  width: 56px; height: 56px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--gold), var(--gold-dim));
  border: 3px solid var(--navy-card);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.4rem;
}
.profile-body { padding: 36px 20px 20px; }
.profile-name {
  font-weight: 700; font-size: 1rem; margin-bottom: 2px;
}
.profile-handle {
  font-size: 0.78rem; color: var(--gold); font-family: var(--font-mono);
  margin-bottom: 10px;
}
.profile-bio { font-size: 0.82rem; color: var(--white-dim); margin-bottom: 16px; line-height: 1.5; }
.profile-stats {
  display: flex; gap: 0;
  border-top: var(--border-dim);
  padding-top: 16px;
}
.p-stat { flex: 1; text-align: center; }
.p-stat .n { font-weight: 700; font-size: 1.1rem; color: var(--white); }
.p-stat .l { font-size: 0.65rem; color: var(--white-dim); text-transform: uppercase; letter-spacing: 0.06em; }
.sidebar-widget {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  padding: 20px;
  margin-bottom: 16px;
}
.widget-title {
  font-size: 0.78rem; font-weight: 700;
  text-transform: uppercase; letter-spacing: 0.06em;
  color: var(--white-dim);
  margin-bottom: 14px;
}
.rider-suggestion {
  display: flex; align-items: center; gap: 10px;
  margin-bottom: 14px;
}
.rs-avatar {
  width: 36px; height: 36px; border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 1rem;
  flex-shrink: 0;
}
.rs-info { flex: 1; }
.rs-name { font-size: 0.83rem; font-weight: 600; }
.rs-meta { font-size: 0.7rem; color: var(--white-dim); }
.btn-follow {
  padding: 4px 12px;
  font-size: 0.72rem; font-weight: 700;
  border: 1px solid var(--gold);
  color: var(--gold);
  border-radius: 100px;
  transition: var(--transition);
}
.btn-follow:hover { background: var(--gold); color: var(--navy); }
.feed { display: flex; flex-direction: column; gap: 20px; }
.post-card {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  overflow: hidden;
  transition: var(--transition);
}
.post-header {
  display: flex; align-items: center; gap: 12px;
  padding: 16px 20px;
}
.post-avatar {
  width: 40px; height: 40px; border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 1.1rem;
  flex-shrink: 0;
}
.post-meta { flex: 1; }
.post-author { font-size: 0.9rem; font-weight: 700; }
.post-time { font-size: 0.72rem; color: var(--white-dim); }
.post-more {
  width: 32px; height: 32px;
  border-radius: 50%;
  background: var(--white-faint);
  display: flex; align-items: center; justify-content: center;
  font-size: 1rem;
  transition: var(--transition);
}
.post-more:hover { background: var(--gold-glow); color: var(--gold); }
.post-media {
  width: 100%; aspect-ratio: 16/9;
  display: flex; align-items: center; justify-content: center;
  font-size: 6rem;
  background: linear-gradient(135deg, var(--navy-light), rgba(201,168,76,0.06));
  position: relative; overflow: hidden;
}
.post-media::after {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(to top, rgba(10,15,30,0.5), transparent);
}
.post-body { padding: 16px 20px; }
.post-text { font-size: 0.9rem; color: var(--white-dim); margin-bottom: 12px; line-height: 1.6; }
.post-tags {
  display: flex; flex-wrap: wrap; gap: 6px;
  margin-bottom: 14px;
}
.post-tag {
  font-size: 0.72rem; font-family: var(--font-mono);
  color: var(--accent-blue);
  background: rgba(59,130,246,0.1);
  padding: 2px 8px; border-radius: 4px;
}
.post-actions {
  display: flex; gap: 6px;
  padding: 0 20px 16px;
}
.post-action {
  display: flex; align-items: center; gap: 6px;
  padding: 7px 16px;
  font-size: 0.8rem; font-weight: 500;
  color: var(--white-dim);
  background: var(--white-faint);
  border-radius: 100px;
  transition: var(--transition);
}
.post-action:hover { color: var(--gold); background: var(--gold-glow); }
.post-action.liked { color: #EF4444; background: rgba(239,68,68,0.1); }
.trending-sidebar .sidebar-widget:first-child { margin-top: 0; }
.trending-item {
  display: flex; align-items: center; gap: 10px;
  padding: 8px 0;
  border-bottom: var(--border-dim);
}
.trending-item:last-child { border-bottom: none; }
.trend-num {
  font-family: var(--font-mono); font-size: 0.75rem;
  color: var(--gold); width: 20px; flex-shrink: 0;
}
.trend-info { flex: 1; }
.trend-tag { font-size: 0.83rem; font-weight: 600; }
.trend-count { font-size: 0.7rem; color: var(--white-dim); }

/* ============================================================ MAP */
#map-section { padding: 100px 0 80px; }
.map-container {
  display: grid; grid-template-columns: 300px 1fr; gap: 24px;
  align-items: start;
}
.map-sidebar {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  overflow: hidden;
}
.map-sidebar-header {
  padding: 20px;
  border-bottom: var(--border-dim);
}
.map-sidebar-header h3 { font-size: 0.9rem; font-weight: 700; margin-bottom: 12px; }
.map-type-list { display: flex; flex-direction: column; gap: 6px; }
.map-type-item {
  display: flex; align-items: center; gap: 10px;
  padding: 10px 12px;
  border-radius: var(--radius-sm);
  transition: var(--transition);
  cursor: pointer;
}
.map-type-item:hover { background: var(--white-faint); }
.map-type-item.active { background: var(--gold-glow); }
.map-type-icon { font-size: 1.2rem; }
.map-type-info { flex: 1; }
.map-type-name { font-size: 0.83rem; font-weight: 600; }
.map-type-count { font-size: 0.7rem; color: var(--white-dim); }
.map-type-item.active .map-type-name { color: var(--gold); }
.map-points-list { padding: 16px; }
.map-point-item {
  display: flex; align-items: flex-start; gap: 10px;
  padding: 12px;
  border-radius: var(--radius-sm);
  border: var(--border-dim);
  margin-bottom: 8px;
  transition: var(--transition);
  cursor: pointer;
  background: var(--navy-mid);
}
.map-point-item:hover { border-color: rgba(201,168,76,0.3); background: var(--navy-light); }
.map-point-icon { font-size: 1.3rem; flex-shrink: 0; }
.map-point-info { flex: 1; }
.map-point-name { font-size: 0.83rem; font-weight: 600; margin-bottom: 2px; }
.map-point-loc { font-size: 0.7rem; color: var(--white-dim); }
.map-point-rating { font-size: 0.72rem; color: var(--gold); }
.fake-map {
  border-radius: var(--radius-lg);
  overflow: hidden;
  border: var(--border-dim);
  position: relative;
  background: var(--navy-light);
  min-height: 580px;
  display: flex; align-items: center; justify-content: center;
}
.map-canvas {
  width: 100%; height: 580px;
  position: relative; overflow: hidden;
}
.map-bg {
  width: 100%; height: 100%;
  background:
    radial-gradient(circle at 30% 40%, rgba(0,212,170,0.05), transparent 40%),
    radial-gradient(circle at 70% 60%, rgba(59,130,246,0.05), transparent 40%),
    repeating-linear-gradient(0deg, var(--border-dim) 0, transparent 1px, transparent 60px),
    repeating-linear-gradient(90deg, var(--border-dim) 0, transparent 1px, transparent 60px),
    var(--navy-light);
}
.map-pin {
  position: absolute;
  transform: translate(-50%, -100%);
  cursor: pointer;
  transition: var(--transition);
}
.map-pin:hover { transform: translate(-50%, -105%) scale(1.15); z-index: 10; }
.map-pin-inner {
  width: 36px; height: 36px;
  border-radius: 50% 50% 50% 0;
  transform: rotate(-45deg);
  display: flex; align-items: center; justify-content: center;
  box-shadow: 0 4px 15px rgba(0,0,0,0.4);
}
.map-pin-inner span {
  transform: rotate(45deg);
  font-size: 1rem;
}
.pin-spot .map-pin-inner { background: var(--gold); }
.pin-charge .map-pin-inner { background: var(--accent-teal); }
.pin-shop .map-pin-inner { background: var(--accent-blue); }
.pin-event .map-pin-inner { background: #8B5CF6; }
.pin-danger .map-pin-inner { background: var(--danger); }
.map-pin-tooltip {
  position: absolute;
  bottom: calc(100% + 8px); left: 50%; transform: translateX(-50%);
  background: var(--navy-card);
  border: var(--border-gold);
  border-radius: var(--radius-sm);
  padding: 8px 12px;
  font-size: 0.75rem; font-weight: 600;
  white-space: nowrap;
  opacity: 0; pointer-events: none;
  transition: var(--transition);
}
.map-pin:hover .map-pin-tooltip { opacity: 1; }
.map-controls {
  position: absolute; top: 16px; right: 16px;
  display: flex; flex-direction: column; gap: 8px;
}
.map-ctrl-btn {
  width: 40px; height: 40px;
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-sm);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.1rem;
  transition: var(--transition);
}
.map-ctrl-btn:hover { border-color: var(--gold); color: var(--gold); }
.map-legend {
  position: absolute; bottom: 16px; left: 16px;
  display: flex; gap: 12px; flex-wrap: wrap;
  background: rgba(10,15,30,0.85);
  backdrop-filter: blur(10px);
  border: var(--border-dim);
  border-radius: var(--radius-sm);
  padding: 10px 14px;
}
.legend-item {
  display: flex; align-items: center; gap: 5px;
  font-size: 0.7rem; color: var(--white-dim);
}
.legend-dot {
  width: 8px; height: 8px; border-radius: 50%;
}

/* ============================================================ EVENTS / SORTIES */
#sorties { padding: 100px 0 80px; }
.events-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
  gap: 24px;
}
.event-card {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  overflow: hidden;
  transition: var(--transition);
  cursor: pointer;
}
.event-card:hover {
  transform: translateY(-4px);
  border-color: rgba(201,168,76,0.25);
  box-shadow: var(--shadow-card);
}
.event-card.premium-event {
  border-color: rgba(139,92,246,0.3);
}
.event-header {
  padding: 24px;
  background: linear-gradient(135deg, var(--navy-light), rgba(201,168,76,0.05));
  border-bottom: var(--border-dim);
  position: relative;
}
.event-date-badge {
  position: absolute; top: 16px; right: 16px;
  background: var(--gold);
  color: var(--navy);
  border-radius: var(--radius-sm);
  padding: 6px 12px;
  text-align: center;
}
.event-date-badge .day {
  font-family: var(--font-display);
  font-size: 1.4rem; font-weight: 800; line-height: 1;
}
.event-date-badge .month {
  font-size: 0.65rem; font-weight: 700;
  text-transform: uppercase; letter-spacing: 0.06em;
}
.event-icon { font-size: 2.5rem; margin-bottom: 12px; }
.event-title { font-size: 1.1rem; font-weight: 700; margin-bottom: 6px; }
.event-loc { font-size: 0.8rem; color: var(--white-dim); display: flex; align-items: center; gap: 4px; }
.event-body { padding: 20px 24px; }
.event-stats {
  display: flex; gap: 20px; margin-bottom: 16px;
}
.ev-stat { display: flex; flex-direction: column; gap: 2px; }
.ev-stat .v { font-size: 0.85rem; font-weight: 700; }
.ev-stat .k { font-size: 0.7rem; color: var(--white-dim); font-family: var(--font-mono); }
.event-level {
  display: flex; gap: 4px; margin-bottom: 16px;
}
.level-dot {
  width: 8px; height: 8px; border-radius: 50%;
  background: var(--white-faint);
}
.level-dot.filled { background: var(--gold); }
.event-participants {
  display: flex; align-items: center; gap: 8px;
  margin-bottom: 16px;
}
.participants-avatars {
  display: flex;
}
.p-av {
  width: 26px; height: 26px;
  border-radius: 50%;
  border: 2px solid var(--navy-card);
  display: flex; align-items: center; justify-content: center;
  font-size: 0.7rem;
  margin-left: -8px;
}
.p-av:first-child { margin-left: 0; }
.event-footer {
  display: flex; justify-content: space-between; align-items: center;
  padding: 16px 24px;
  border-top: var(--border-dim);
}
.event-price { font-size: 0.85rem; font-weight: 700; }
.event-price .free { color: var(--accent-teal); }
.event-price .paid { color: var(--gold); }

/* ============================================================ BUYING GUIDE */
#guide { padding: 100px 0 80px; }
.guide-layout {
  display: grid; grid-template-columns: 320px 1fr; gap: 32px; align-items: start;
}
.guide-filters-panel {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  padding: 24px;
  position: sticky; top: 130px;
}
.guide-filters-panel h3 {
  font-size: 0.9rem; font-weight: 700; margin-bottom: 24px;
  display: flex; align-items: center; gap: 8px;
}
.filter-group { margin-bottom: 24px; }
.filter-group label {
  font-size: 0.75rem; font-weight: 600;
  text-transform: uppercase; letter-spacing: 0.08em;
  color: var(--white-dim);
  display: block; margin-bottom: 10px;
}
.range-track {
  position: relative; height: 4px;
  background: var(--white-faint);
  border-radius: 2px; margin-bottom: 10px;
}
.range-fill {
  position: absolute; height: 100%;
  background: linear-gradient(90deg, var(--gold), var(--gold-light));
  border-radius: 2px;
}
input[type=range] {
  width: 100%; margin: 0; -webkit-appearance: none;
  background: none; cursor: pointer;
}
input[type=range]::-webkit-slider-thumb {
  -webkit-appearance: none;
  width: 18px; height: 18px;
  border-radius: 50%;
  background: var(--gold);
  border: 3px solid var(--navy-card);
  box-shadow: 0 2px 8px rgba(201,168,76,0.4);
}
.range-labels {
  display: flex; justify-content: space-between;
  font-size: 0.72rem; color: var(--white-dim); font-family: var(--font-mono);
}
.toggle-group { display: flex; flex-direction: column; gap: 8px; }
.toggle-item {
  display: flex; justify-content: space-between; align-items: center;
  padding: 8px 0;
}
.toggle-item span { font-size: 0.83rem; }
.toggle {
  width: 38px; height: 21px;
  background: var(--white-faint);
  border-radius: 100px;
  position: relative;
  cursor: pointer;
  transition: var(--transition);
}
.toggle.on { background: var(--gold); }
.toggle::after {
  content: '';
  position: absolute; top: 3px; left: 3px;
  width: 15px; height: 15px;
  border-radius: 50%; background: var(--white);
  transition: var(--transition);
}
.toggle.on::after { left: calc(100% - 18px); }
.guide-results { display: flex; flex-direction: column; gap: 16px; }
.guide-result-card {
  display: flex; align-items: center; gap: 20px;
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  padding: 20px;
  transition: var(--transition);
  cursor: pointer;
  position: relative;
  overflow: hidden;
}
.guide-result-card:hover { border-color: rgba(201,168,76,0.3); transform: translateX(4px); }
.guide-result-card.recommended::before {
  content: '⭐ RECOMMANDÉ';
  position: absolute; top: 0; right: 0;
  background: var(--gold);
  color: var(--navy);
  font-size: 0.6rem; font-weight: 800;
  letter-spacing: 0.08em;
  padding: 4px 12px;
  border-radius: 0 var(--radius-lg) 0 var(--radius-sm);
}
.guide-result-icon { font-size: 3.5rem; flex-shrink: 0; }
.guide-result-info { flex: 1; }
.guide-result-name { font-size: 1rem; font-weight: 700; margin-bottom: 4px; }
.guide-result-brand { font-size: 0.78rem; color: var(--gold); font-family: var(--font-mono); margin-bottom: 8px; }
.guide-result-specs {
  display: flex; flex-wrap: wrap; gap: 6px; margin-bottom: 10px;
}
.guide-score {
  text-align: center; flex-shrink: 0;
}
.score-circle {
  width: 64px; height: 64px;
  border-radius: 50%;
  border: 3px solid var(--gold);
  display: flex; flex-direction: column; align-items: center; justify-content: center;
  background: var(--gold-glow);
  margin-bottom: 6px;
}
.score-num {
  font-family: var(--font-display);
  font-size: 1.2rem; font-weight: 800; color: var(--gold); line-height: 1;
}
.score-label { font-size: 0.55rem; color: var(--white-dim); text-transform: uppercase; letter-spacing: 0.06em; }
.guide-result-price {
  font-family: var(--font-display);
  font-size: 1.5rem; font-weight: 800; color: var(--white);
}

/* ============================================================ AI ASSISTANT */
#ai-section { padding: 100px 0 80px; }
.ai-layout {
  display: grid; grid-template-columns: 1fr 420px; gap: 32px; align-items: start;
}
.ai-chat {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  overflow: hidden;
  display: flex; flex-direction: column;
  min-height: 580px;
}
.ai-chat-header {
  padding: 20px 24px;
  border-bottom: var(--border-dim);
  display: flex; align-items: center; gap: 12px;
}
.ai-avatar {
  width: 42px; height: 42px;
  border-radius: var(--radius-sm);
  background: linear-gradient(135deg, var(--gold), var(--gold-dim));
  display: flex; align-items: center; justify-content: center;
  font-size: 1.2rem;
  position: relative;
}
.ai-status {
  position: absolute; bottom: -2px; right: -2px;
  width: 12px; height: 12px;
  background: var(--accent-teal);
  border-radius: 50%;
  border: 2px solid var(--navy-card);
}
.ai-info { flex: 1; }
.ai-name { font-size: 0.9rem; font-weight: 700; }
.ai-subtitle { font-size: 0.72rem; color: var(--accent-teal); }
.ai-messages {
  flex: 1; padding: 24px;
  display: flex; flex-direction: column; gap: 16px;
  overflow-y: auto;
}
.msg {
  display: flex; gap: 10px;
  max-width: 85%;
}
.msg.bot { align-self: flex-start; }
.msg.user { align-self: flex-end; flex-direction: row-reverse; }
.msg-avatar {
  width: 30px; height: 30px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 0.8rem;
  flex-shrink: 0;
}
.msg.bot .msg-avatar { background: linear-gradient(135deg, var(--gold), var(--gold-dim)); }
.msg.user .msg-avatar { background: var(--accent-blue); }
.msg-bubble {
  padding: 12px 16px;
  border-radius: var(--radius-md);
  font-size: 0.88rem; line-height: 1.6;
}
.msg.bot .msg-bubble {
  background: var(--navy-light);
  border: var(--border-dim);
  border-top-left-radius: 4px;
  color: var(--white);
}
.msg.user .msg-bubble {
  background: linear-gradient(135deg, var(--gold), var(--gold-dim));
  color: var(--navy);
  font-weight: 500;
  border-top-right-radius: 4px;
}
.msg-product {
  display: flex; align-items: center; gap: 12px;
  background: var(--navy-card);
  border: var(--border-gold);
  border-radius: var(--radius-sm);
  padding: 10px;
  margin-top: 8px;
}
.msg-product-icon { font-size: 2rem; }
.msg-product-info { flex: 1; }
.msg-product-name { font-size: 0.83rem; font-weight: 700; }
.msg-product-price { font-size: 0.78rem; color: var(--gold); font-family: var(--font-mono); }
.msg-product-score { font-size: 0.7rem; color: var(--accent-teal); }
.ai-quick-replies {
  display: flex; flex-wrap: wrap; gap: 6px; padding: 0 24px 16px;
}
.quick-reply {
  padding: 6px 12px;
  font-size: 0.75rem; font-weight: 500;
  background: var(--white-faint);
  border: var(--border-dim);
  color: var(--white-dim);
  border-radius: 100px;
  transition: var(--transition);
}
.quick-reply:hover { background: var(--gold-glow); border-color: var(--gold); color: var(--gold); }
.ai-input-wrap {
  padding: 16px 24px;
  border-top: var(--border-dim);
  display: flex; gap: 10px; align-items: flex-end;
}
.ai-input {
  flex: 1;
  background: var(--navy-light);
  border: var(--border-dim);
  border-radius: var(--radius-md);
  padding: 12px 16px;
  color: var(--white);
  font-family: var(--font-body); font-size: 0.88rem;
  resize: none;
  min-height: 44px; max-height: 120px;
  outline: none;
  transition: var(--transition);
}
.ai-input:focus { border-color: var(--gold); }
.ai-input::placeholder { color: var(--white-dim); }
.ai-send {
  width: 44px; height: 44px;
  border-radius: var(--radius-sm);
  background: linear-gradient(135deg, var(--gold), var(--gold-dim));
  color: var(--navy);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.1rem;
  transition: var(--transition);
  flex-shrink: 0;
}
.ai-send:hover { transform: scale(1.05); box-shadow: var(--shadow-gold); }
.ai-sidebar { display: flex; flex-direction: column; gap: 20px; }
.ai-feature-card {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  padding: 22px;
  transition: var(--transition);
}
.ai-feature-card:hover { border-color: rgba(201,168,76,0.2); }
.ai-feat-icon {
  width: 44px; height: 44px;
  border-radius: var(--radius-sm);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.3rem;
  margin-bottom: 14px;
}
.ai-feat-title { font-size: 0.9rem; font-weight: 700; margin-bottom: 6px; }
.ai-feat-desc { font-size: 0.8rem; color: var(--white-dim); line-height: 1.5; }

/* ============================================================ MARKET PRICES */
#cote { padding: 100px 0 80px; }
.cote-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; }
.cote-card {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  padding: 24px;
  transition: var(--transition);
}
.cote-card:hover { border-color: rgba(201,168,76,0.2); }
.cote-card-header {
  display: flex; justify-content: space-between; align-items: flex-start;
  margin-bottom: 20px;
}
.cote-model { display: flex; align-items: center; gap: 12px; }
.cote-icon { font-size: 2rem; }
.cote-model-name { font-size: 0.95rem; font-weight: 700; }
.cote-model-brand { font-size: 0.73rem; color: var(--gold); font-family: var(--font-mono); }
.cote-trend {
  display: flex; flex-direction: column; align-items: flex-end; gap: 4px;
}
.cote-change {
  font-family: var(--font-mono);
  font-size: 0.85rem; font-weight: 700;
  padding: 3px 8px; border-radius: 4px;
}
.cote-change.up { background: rgba(34,197,94,0.1); color: var(--success); }
.cote-change.down { background: rgba(239,68,68,0.1); color: var(--danger); }
.cote-prices {
  display: grid; grid-template-columns: 1fr 1fr 1fr;
  gap: 12px; margin-bottom: 20px;
}
.cote-price-item { text-align: center; }
.cote-price-label { font-size: 0.65rem; text-transform: uppercase; letter-spacing: 0.06em; color: var(--white-dim); margin-bottom: 4px; }
.cote-price-val { font-family: var(--font-display); font-size: 1.1rem; font-weight: 800; }
.cote-price-val.neuf { color: var(--white); }
.cote-price-val.occasion { color: var(--gold); }
.cote-price-val.bas { color: var(--accent-teal); }
.cote-mini-chart { height: 60px; position: relative; }
.mini-chart-svg { width: 100%; height: 100%; }
.cote-footer {
  display: flex; justify-content: space-between;
  font-size: 0.72rem; color: var(--white-dim);
  padding-top: 16px; border-top: var(--border-dim);
  font-family: var(--font-mono);
}

/* ============================================================ RANKINGS */
#rankings { padding: 100px 0 80px; }
.rankings-tabs {
  display: flex; gap: 8px; margin-bottom: 32px; flex-wrap: wrap;
}
.rank-tab {
  padding: 8px 20px;
  font-size: 0.8rem; font-weight: 600;
  color: var(--white-dim);
  background: var(--white-faint);
  border-radius: 100px;
  transition: var(--transition);
}
.rank-tab.active { background: var(--gold); color: var(--navy); }
.rankings-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 24px; }
.ranking-list {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  overflow: hidden;
}
.ranking-list-header {
  padding: 18px 20px;
  background: linear-gradient(135deg, var(--navy-light), rgba(201,168,76,0.04));
  border-bottom: var(--border-dim);
  font-size: 0.85rem; font-weight: 700;
  display: flex; align-items: center; gap: 8px;
}
.rank-item {
  display: flex; align-items: center; gap: 14px;
  padding: 14px 20px;
  border-bottom: var(--border-dim);
  transition: var(--transition);
}
.rank-item:last-child { border-bottom: none; }
.rank-item:hover { background: var(--white-faint); }
.rank-pos {
  font-family: var(--font-display);
  font-size: 1.2rem; font-weight: 800;
  width: 28px; text-align: center; flex-shrink: 0;
}
.rank-pos.gold { color: var(--gold); }
.rank-pos.silver { color: #B0B8C4; }
.rank-pos.bronze { color: #CD7F32; }
.rank-icon { font-size: 1.8rem; flex-shrink: 0; }
.rank-info { flex: 1; }
.rank-name { font-size: 0.88rem; font-weight: 700; }
.rank-brand { font-size: 0.72rem; color: var(--gold); font-family: var(--font-mono); }
.rank-score { text-align: right; }
.rank-value { font-family: var(--font-mono); font-size: 0.85rem; font-weight: 700; color: var(--white); }
.rank-bar-wrap { width: 80px; height: 4px; background: var(--white-faint); border-radius: 2px; margin-top: 4px; }
.rank-bar { height: 100%; background: var(--gold); border-radius: 2px; transition: width 1s ease; }

/* ============================================================ DIGITAL LOGBOOK */
#carnet { padding: 100px 0 80px; }
.carnet-layout { display: grid; grid-template-columns: 1fr 380px; gap: 32px; align-items: start; }
.vehicle-select-wrap {
  margin-bottom: 24px;
  display: flex; gap: 12px; flex-wrap: wrap;
}
.vehicle-card-select {
  display: flex; align-items: center; gap: 12px;
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-md);
  padding: 14px 18px;
  cursor: pointer;
  transition: var(--transition);
  flex: 1; min-width: 160px;
}
.vehicle-card-select.active { border-color: var(--gold); background: var(--gold-glow); }
.vehicle-card-select-icon { font-size: 2rem; }
.vehicle-card-select-info { flex: 1; }
.vehicle-card-select-name { font-size: 0.83rem; font-weight: 700; }
.vehicle-card-select-km { font-size: 0.72rem; color: var(--gold); font-family: var(--font-mono); }
.carnet-main {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  overflow: hidden;
}
.carnet-header {
  padding: 24px;
  background: linear-gradient(135deg, var(--navy-light), rgba(201,168,76,0.06));
  border-bottom: var(--border-dim);
}
.vehicle-big-display {
  display: flex; align-items: center; gap: 20px;
}
.vehicle-big-icon { font-size: 4rem; }
.vehicle-big-name { font-family: var(--font-display); font-size: 1.5rem; font-weight: 800; }
.vehicle-big-brand { font-size: 0.83rem; color: var(--gold); font-family: var(--font-mono); margin-bottom: 8px; }
.vehicle-km-display {
  display: flex; align-items: baseline; gap: 4px;
}
.vehicle-km-num { font-family: var(--font-mono); font-size: 1.8rem; font-weight: 700; color: var(--gold); }
.vehicle-km-unit { font-size: 0.8rem; color: var(--white-dim); }
.carnet-serial {
  font-size: 0.72rem; font-family: var(--font-mono);
  color: var(--white-dim);
  margin-top: 6px;
  display: flex; align-items: center; gap: 6px;
}
.serial-badge {
  background: var(--white-faint);
  padding: 2px 8px; border-radius: 4px;
  font-size: 0.65rem; color: var(--white-dim);
}
.carnet-tabs-inner {
  display: flex; gap: 0;
  border-bottom: var(--border-dim);
}
.carnet-tab {
  flex: 1; padding: 14px;
  font-size: 0.78rem; font-weight: 600;
  color: var(--white-dim);
  text-align: center;
  border-bottom: 2px solid transparent;
  transition: var(--transition);
}
.carnet-tab.active { color: var(--gold); border-bottom-color: var(--gold); }
.carnet-tab:hover { color: var(--white); }
.carnet-entries { padding: 20px; }
.carnet-entry {
  display: flex; align-items: flex-start; gap: 14px;
  padding: 14px 0;
  border-bottom: var(--border-dim);
}
.carnet-entry:last-child { border-bottom: none; }
.entry-icon-wrap {
  width: 38px; height: 38px;
  border-radius: var(--radius-sm);
  display: flex; align-items: center; justify-content: center;
  font-size: 1rem;
  flex-shrink: 0;
}
.entry-maint { background: rgba(34,197,94,0.1); }
.entry-repair { background: rgba(239,68,68,0.1); }
.entry-modif { background: rgba(139,92,246,0.1); }
.entry-km { background: rgba(201,168,76,0.1); }
.entry-info { flex: 1; }
.entry-title { font-size: 0.85rem; font-weight: 700; margin-bottom: 2px; }
.entry-desc { font-size: 0.75rem; color: var(--white-dim); }
.entry-meta {
  text-align: right; flex-shrink: 0;
}
.entry-date { font-size: 0.7rem; color: var(--white-dim); font-family: var(--font-mono); }
.entry-cost { font-size: 0.83rem; font-weight: 700; color: var(--gold); }
.carnet-sidebar { display: flex; flex-direction: column; gap: 16px; }
.carnet-widget {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  padding: 20px;
}
.carnet-widget-title { font-size: 0.78rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.06em; color: var(--white-dim); margin-bottom: 14px; }
.health-bar-item { margin-bottom: 12px; }
.health-bar-label { display: flex; justify-content: space-between; font-size: 0.78rem; margin-bottom: 5px; }
.health-bar-track { height: 6px; background: var(--white-faint); border-radius: 3px; }
.health-bar-fill { height: 100%; border-radius: 3px; transition: width 1s ease; }
.health-bar-fill.good { background: var(--success); }
.health-bar-fill.ok { background: var(--gold); }
.health-bar-fill.bad { background: var(--danger); }
.antivol-status {
  display: flex; align-items: center; gap: 10px;
  padding: 12px;
  background: rgba(34,197,94,0.08);
  border: 1px solid rgba(34,197,94,0.2);
  border-radius: var(--radius-sm);
}
.antivol-icon { font-size: 1.5rem; }
.antivol-info { flex: 1; }
.antivol-label { font-size: 0.83rem; font-weight: 700; color: var(--success); }
.antivol-desc { font-size: 0.7rem; color: var(--white-dim); }

/* ============================================================ GAMIFICATION */
#gamification { padding: 100px 0 80px; }
.gamif-layout { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 20px; }
.gamif-card {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-lg);
  padding: 24px;
  text-align: center;
  transition: var(--transition);
}
.gamif-card:hover { transform: translateY(-4px); border-color: rgba(201,168,76,0.2); box-shadow: var(--shadow-card); }
.gamif-icon-wrap {
  width: 72px; height: 72px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 2rem;
  margin: 0 auto 16px;
}
.gamif-card-title { font-size: 0.95rem; font-weight: 700; margin-bottom: 8px; }
.gamif-card-desc { font-size: 0.8rem; color: var(--white-dim); line-height: 1.5; }
.xp-bar-wrap { margin-top: 16px; }
.xp-bar-label { display: flex; justify-content: space-between; font-size: 0.72rem; margin-bottom: 6px; }
.xp-bar-track { height: 8px; background: var(--white-faint); border-radius: 4px; }
.xp-bar-fill {
  height: 100%; border-radius: 4px;
  background: linear-gradient(90deg, var(--gold), var(--gold-light));
  transition: width 1.2s ease;
}
.badges-grid { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 14px; justify-content: center; }
.badge-item {
  width: 44px; height: 44px;
  border-radius: var(--radius-sm);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.3rem;
  transition: var(--transition);
  cursor: pointer;
  position: relative;
}
.badge-item:hover { transform: scale(1.15); }
.badge-item.earned { filter: none; }
.badge-item.locked { filter: grayscale(1) opacity(0.35); }
.badge-item.earned::after {
  content: '';
  position: absolute; inset: 0;
  border-radius: var(--radius-sm);
  border: 1px solid var(--gold);
  pointer-events: none;
}
.leaderboard-mini { margin-top: 14px; }
.lb-row {
  display: flex; align-items: center; gap: 10px;
  padding: 8px 0;
  border-bottom: var(--border-dim);
}
.lb-row:last-child { border-bottom: none; }
.lb-rank { font-family: var(--font-mono); font-size: 0.75rem; width: 20px; color: var(--gold); }
.lb-name { flex: 1; font-size: 0.83rem; }
.lb-xp { font-family: var(--font-mono); font-size: 0.75rem; color: var(--white-dim); }

/* ============================================================ PRICING */
#pricing { padding: 100px 0 80px; }
.pricing-grid {
  display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px;
  max-width: 900px; margin: 0 auto;
}
.pricing-card {
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-xl);
  padding: 32px;
  transition: var(--transition);
  position: relative;
  overflow: hidden;
}
.pricing-card:hover { transform: translateY(-6px); }
.pricing-card.popular {
  border-color: var(--gold);
  background: linear-gradient(135deg, var(--navy-card), rgba(201,168,76,0.05));
  box-shadow: var(--shadow-gold);
}
.pricing-popular-badge {
  position: absolute; top: 0; right: 0;
  background: var(--gold);
  color: var(--navy);
  font-size: 0.65rem; font-weight: 800;
  letter-spacing: 0.06em; text-transform: uppercase;
  padding: 6px 16px;
  border-radius: 0 var(--radius-xl) 0 var(--radius-sm);
}
.pricing-plan { font-size: 0.75rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.1em; color: var(--white-dim); margin-bottom: 8px; }
.pricing-price {
  font-family: var(--font-display);
  font-size: 2.8rem; font-weight: 800;
  line-height: 1; margin-bottom: 4px;
}
.pricing-price .currency { font-size: 1.2rem; vertical-align: super; }
.pricing-price .period { font-size: 0.9rem; font-weight: 500; color: var(--white-dim); font-family: var(--font-body); }
.pricing-desc { font-size: 0.82rem; color: var(--white-dim); margin-bottom: 24px; line-height: 1.5; }
.pricing-features { margin-bottom: 28px; display: flex; flex-direction: column; gap: 10px; }
.pricing-feature {
  display: flex; gap: 10px; align-items: flex-start;
  font-size: 0.83rem;
}
.pricing-feature .check { color: var(--accent-teal); flex-shrink: 0; margin-top: 2px; }
.pricing-feature .cross { color: var(--white-dim); flex-shrink: 0; margin-top: 2px; opacity: 0.4; }

/* ============================================================ PRO ACCOUNTS */
#pro { padding: 100px 0 80px; }
.pro-card {
  background: linear-gradient(135deg, var(--navy-card), rgba(201,168,76,0.04));
  border: var(--border-gold);
  border-radius: var(--radius-xl);
  padding: 48px;
  display: flex; gap: 48px; align-items: center;
  position: relative; overflow: hidden;
}
.pro-card::before {
  content: '';
  position: absolute; top: -60px; right: -60px;
  width: 280px; height: 280px;
  background: radial-gradient(circle, rgba(201,168,76,0.1), transparent 70%);
  pointer-events: none;
}
.pro-features-grid {
  display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px;
  margin-top: 32px;
}
.pro-feat-item {
  display: flex; gap: 10px; align-items: flex-start;
  background: var(--white-faint);
  border-radius: var(--radius-sm);
  padding: 12px;
}
.pro-feat-icon { font-size: 1.3rem; flex-shrink: 0; }
.pro-feat-text { font-size: 0.82rem; color: var(--white-dim); line-height: 1.4; }
.pro-feat-text strong { color: var(--white); display: block; font-size: 0.85rem; margin-bottom: 2px; }

/* ============================================================ FOOTER */
footer {
  background: var(--navy-mid);
  border-top: var(--border-dim);
  padding: 80px 0 40px;
}
.footer-grid {
  display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 48px;
  margin-bottom: 60px;
}
.footer-brand p { font-size: 0.85rem; color: var(--white-dim); line-height: 1.7; max-width: 280px; margin: 14px 0 20px; }
.footer-socials { display: flex; gap: 10px; }
.social-btn {
  width: 38px; height: 38px;
  background: var(--white-faint);
  border: var(--border-dim);
  border-radius: var(--radius-sm);
  display: flex; align-items: center; justify-content: center;
  font-size: 0.9rem;
  transition: var(--transition);
}
.social-btn:hover { background: var(--gold-glow); border-color: var(--gold); }
.footer-col h4 { font-size: 0.78rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.08em; color: var(--white-dim); margin-bottom: 16px; }
.footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 10px; }
.footer-col ul li a { font-size: 0.85rem; color: var(--white-dim); transition: var(--transition); }
.footer-col ul li a:hover { color: var(--gold); }
.footer-bottom {
  display: flex; justify-content: space-between; align-items: center;
  padding-top: 32px; border-top: var(--border-dim);
  font-size: 0.78rem; color: var(--white-dim);
  flex-wrap: wrap; gap: 16px;
}
.footer-bottom .gold { color: var(--gold); }

/* ============================================================ SECTION DIVIDERS */
.section-divider {
  text-align: center;
  padding: 20px 0;
  position: relative;
}
.section-divider::before {
  content: '';
  position: absolute; top: 50%; left: 0; right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--border-dim), transparent);
}
.section-divider span {
  position: relative; z-index: 1;
  background: var(--navy);
  padding: 0 16px;
  color: var(--gold); font-size: 0.8rem; font-family: var(--font-mono);
}

/* ============================================================ MODAL */
.modal-overlay {
  position: fixed; inset: 0; z-index: 2000;
  background: rgba(0,0,0,0.7);
  backdrop-filter: blur(8px);
  display: flex; align-items: center; justify-content: center;
  opacity: 0; pointer-events: none;
  transition: opacity 0.3s ease;
  padding: 20px;
}
.modal-overlay.open { opacity: 1; pointer-events: all; }
.modal {
  background: var(--navy-card);
  border: var(--border-gold);
  border-radius: var(--radius-xl);
  padding: 36px;
  max-width: 480px; width: 100%;
  transform: translateY(20px);
  transition: transform 0.3s ease;
  position: relative;
}
.modal-overlay.open .modal { transform: translateY(0); }
.modal-close {
  position: absolute; top: 16px; right: 16px;
  width: 34px; height: 34px;
  border-radius: 50%;
  background: var(--white-faint);
  display: flex; align-items: center; justify-content: center;
  font-size: 0.9rem;
  transition: var(--transition);
}
.modal-close:hover { background: var(--danger); }
.modal-title { font-family: var(--font-display); font-size: 1.5rem; font-weight: 800; margin-bottom: 6px; }
.modal-sub { font-size: 0.85rem; color: var(--white-dim); margin-bottom: 28px; }
.modal-input-group { display: flex; flex-direction: column; gap: 14px; }
.modal-input {
  background: var(--navy-light);
  border: var(--border-dim);
  border-radius: var(--radius-md);
  padding: 14px 18px;
  color: var(--white); font-family: var(--font-body); font-size: 0.9rem;
  outline: none; transition: var(--transition);
}
.modal-input:focus { border-color: var(--gold); }
.modal-input::placeholder { color: var(--white-dim); }
.modal-cta { width: 100%; padding: 14px; font-size: 0.95rem; font-weight: 700; border-radius: var(--radius-md); margin-top: 8px; }
.modal-divider { display: flex; align-items: center; gap: 12px; margin: 16px 0; }
.modal-divider::before, .modal-divider::after { content: ''; flex: 1; height: 1px; background: var(--border-dim); }
.modal-divider span { font-size: 0.75rem; color: var(--white-dim); }
.social-login { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
.social-login-btn {
  display: flex; align-items: center; justify-content: center; gap: 8px;
  padding: 11px;
  background: var(--white-faint);
  border: var(--border-dim);
  border-radius: var(--radius-sm);
  font-size: 0.82rem; font-weight: 600; color: var(--white);
  transition: var(--transition);
}
.social-login-btn:hover { background: var(--navy-light); border-color: rgba(240,242,247,0.15); }
.modal-footer { text-align: center; margin-top: 20px; font-size: 0.78rem; color: var(--white-dim); }
.modal-footer a { color: var(--gold); }

/* ============================================================ TOAST */
.toast-container {
  position: fixed; bottom: 24px; right: 24px; z-index: 3000;
  display: flex; flex-direction: column; gap: 10px; align-items: flex-end;
}
.toast {
  display: flex; align-items: center; gap: 10px;
  background: var(--navy-card);
  border: var(--border-dim);
  border-radius: var(--radius-md);
  padding: 12px 18px;
  font-size: 0.85rem;
  box-shadow: var(--shadow-card);
  transform: translateX(120%);
  transition: transform 0.3s ease;
  min-width: 260px;
}
.toast.show { transform: translateX(0); }
.toast.success { border-color: rgba(34,197,94,0.4); }
.toast.error { border-color: rgba(239,68,68,0.4); }
.toast-icon { font-size: 1.1rem; }

/* ============================================================ ANIMATIONS */
@keyframes fadeInDown {
  from { opacity: 0; transform: translateY(-20px); }
  to { opacity: 1; transform: translateY(0); }
}
@keyframes fadeInUp {
  from { opacity: 0; transform: translateY(24px); }
  to { opacity: 1; transform: translateY(0); }
}
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

/* Scroll animations */
.reveal {
  opacity: 0;
  transform: translateY(32px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}
.reveal.visible { opacity: 1; transform: translateY(0); }
.reveal-left { opacity: 0; transform: translateX(-32px); transition: opacity 0.6s ease, transform 0.6s ease; }
.reveal-left.visible { opacity: 1; transform: translateX(0); }
.reveal-right { opacity: 0; transform: translateX(32px); transition: opacity 0.6s ease, transform 0.6s ease; }
.reveal-right.visible { opacity: 1; transform: translateX(0); }

/* Stagger delays */
.delay-1 { transition-delay: 0.1s; }
.delay-2 { transition-delay: 0.2s; }
.delay-3 { transition-delay: 0.3s; }
.delay-4 { transition-delay: 0.4s; }
.delay-5 { transition-delay: 0.5s; }

/* ============================================================ RESPONSIVE */
@media (max-width: 1100px) {
  .social-layout { grid-template-columns: 1fr; }
  .trending-sidebar { display: none; }
  .social-sidebar { position: static; }
  .cote-grid { grid-template-columns: 1fr; }
  .rankings-grid { grid-template-columns: 1fr; }
  .gamif-layout { grid-template-columns: 1fr 1fr; }
  .footer-grid { grid-template-columns: 1fr 1fr; gap: 32px; }
}
@media (max-width: 900px) {
  .map-container { grid-template-columns: 1fr; }
  .guide-layout { grid-template-columns: 1fr; }
  .guide-filters-panel { position: static; }
  .ai-layout { grid-template-columns: 1fr; }
  .carnet-layout { grid-template-columns: 1fr; }
  .pricing-grid { grid-template-columns: 1fr; max-width: 380px; }
  .pro-card { flex-direction: column; padding: 32px; }
}
@media (max-width: 768px) {
  #navbar { padding: 14px 20px; }
  #navbar.scrolled { padding: 10px 20px; }
  .nav-links { display: none; }
  .hero-stats { gap: 24px; }
  .hero-stat .num { font-size: 1.8rem; }
  .social-layout { grid-template-columns: 1fr; }
  .gamif-layout { grid-template-columns: 1fr; }
  .footer-grid { grid-template-columns: 1fr; gap: 24px; }
}
</style>
</head>
<body>

<!-- ============================================================ NAVBAR -->
<nav id="navbar">
  <div class="nav-logo">
    <div class="nav-logo-icon">⚡</div>
    VOLT<span>ERRA</span>
  </div>
  <ul class="nav-links">
    <li><a href="#marketplace" data-en="Marketplace" data-fr="Marketplace">Marketplace</a></li>
    <li><a href="#riders" data-en="Riders" data-fr="Riders">Riders</a></li>
    <li><a href="#map-section" data-en="Map" data-fr="Carte">Carte</a></li>
    <li><a href="#sorties" data-en="Events" data-fr="Sorties">Sorties</a></li>
    <li><a href="#guide" data-en="Guide" data-fr="Guide">Guide</a></li>
    <li><a href="#ai-section" data-en="AI" data-fr="IA">IA</a></li>
    <li><a href="#pricing" data-en="Pricing" data-fr="Prix">Prix</a></li>
  </ul>
  <div class="nav-actions">
    <div class="lang-toggle">
      <button class="lang-btn active" data-lang="fr">FR</button>
      <button class="lang-btn" data-lang="en">EN</button>
    </div>
    <button class="btn-ghost" onclick="openModal('login')" data-en="Sign in" data-fr="Connexion">Connexion</button>
    <button class="btn-primary" onclick="openModal('signup')" data-en="Get started" data-fr="Commencer">Commencer</button>
  </div>
</nav>

<!-- ============================================================ HERO -->
<section id="hero">
  <div class="hero-video-wrap">
    <video autoplay muted loop playsinline>
      <source src="https://assets.mixkit.co/videos/preview/mixkit-man-riding-an-electric-scooter-through-a-futuristic-city-38799-large.mp4" type="video/mp4">
    </video>
  </div>
  <div class="hero-orb orb-1"></div>
  <div class="hero-orb orb-2"></div>
  <div class="hero-orb orb-3"></div>

  <div class="hero-content">
    <div class="hero-eyebrow" data-en="⚡ The European Reference — Electric Mobility" data-fr="⚡ La Référence Européenne — Mobilité Électrique">
      ⚡ La Référence Européenne — Mobilité Électrique
    </div>
    <h1 class="hero-title">
      Ride<br>
      <span class="gradient">Smarter.</span><br>
      Ride <span class="gold">Together.</span>
    </h1>
    <p class="hero-sub" data-en="The ultra-premium European marketplace, community and intelligence for electric personal mobility. Buy, sell, connect, explore." data-fr="La marketplace, communauté et intelligence ultra-premium de la mobilité électrique personnelle en Europe. Acheter, vendre, connecter, explorer.">
      La marketplace, communauté et intelligence ultra-premium de la mobilité électrique personnelle en Europe. Acheter, vendre, connecter, explorer.
    </p>
    <div class="hero-actions">
      <button class="btn-primary" onclick="openModal('signup')" style="padding:14px 36px;font-size:1rem;" data-en="Join Volterra" data-fr="Rejoindre Volterra">Rejoindre Volterra</button>
      <button class="btn-ghost" style="padding:14px 28px;font-size:0.95rem;" onclick="scrollToSection('marketplace')" data-en="Explore marketplace" data-fr="Explorer la marketplace">Explorer la marketplace</button>
    </div>
  </div>

  <div class="hero-stats">
    <div class="hero-stat reveal delay-1">
      <div class="num" data-count="47000">0</div>
      <div class="label" data-en="Active users" data-fr="Utilisateurs actifs">Utilisateurs actifs</div>
    </div>
    <div class="hero-stat reveal delay-2">
      <div class="num" data-count="12000">0</div>
      <div class="label" data-en="Active listings" data-fr="Annonces actives">Annonces actives</div>
    </div>
    <div class="hero-stat reveal delay-3">
      <div class="num" data-count="18">0</div>
      <div class="label" data-en="Countries" data-fr="Pays couverts">Pays couverts</div>
    </div>
    <div class="hero-stat reveal delay-4">
      <div class="num" data-count="98">0</div>
      <div class="label" data-en="% Satisfaction" data-fr="% Satisfaction">% Satisfaction</div>
    </div>
  </div>

  <div class="hero-scroll">
    <div class="scroll-line"></div>
    <span data-en="scroll" data-fr="défiler">défiler</span>
  </div>
</section>

<!-- ============================================================ TABS NAV -->
<div id="tabs-nav">
  <div class="tabs-scroll">
    <button class="tab-btn active" onclick="scrollToSection('marketplace')"><span class="tab-icon">🛒</span><span data-en="Marketplace" data-fr="Marketplace">Marketplace</span></button>
    <button class="tab-btn" onclick="scrollToSection('riders')"><span class="tab-icon">👥</span><span data-en="Riders" data-fr="Riders">Riders</span></button>
    <button class="tab-btn" onclick="scrollToSection('map-section')"><span class="tab-icon">🗺️</span><span data-en="Map" data-fr="Carte">Carte</span></button>
    <button class="tab-btn" onclick="scrollToSection('sorties')"><span class="tab-icon">🏁</span><span data-en="Events" data-fr="Sorties">Sorties</span></button>
    <button class="tab-btn" onclick="scrollToSection('guide')"><span class="tab-icon">🔍</span><span data-en="Buy Guide" data-fr="Guide d'achat">Guide d'achat</span></button>
    <button class="tab-btn" onclick="scrollToSection('ai-section')"><span class="tab-icon">🤖</span><span data-en="AI Volterra" data-fr="IA Volterra">IA Volterra</span></button>
    <button class="tab-btn" onclick="scrollToSection('cote')"><span class="tab-icon">📊</span><span data-en="Market Prices" data-fr="Cote du marché">Cote du marché</span></button>
    <button class="tab-btn" onclick="scrollToSection('rankings')"><span class="tab-icon">🏆</span><span data-en="Rankings" data-fr="Classements">Classements</span></button>
    <button class="tab-btn" onclick="scrollToSection('carnet')"><span class="tab-icon">📓</span><span data-en="Logbook" data-fr="Carnet numérique">Carnet numérique</span></button>
    <button class="tab-btn" onclick="scrollToSection('gamification')"><span class="tab-icon">⭐</span><span data-en="Gamification" data-fr="Gamification">Gamification</span></button>
    <button class="tab-btn" onclick="scrollToSection('pricing')"><span class="tab-icon">💎</span><span data-en="Premium" data-fr="Premium">Premium</span></button>
  </div>
</div>

<!-- ============================================================ MARKETPLACE -->
<section id="marketplace" class="py-section">
  <div class="container">
    <div class="marketplace-header">
      <div>
        <div class="section-label" data-en="Tab 01 — Buy & Sell" data-fr="Onglet 01 — Achat & Vente">Onglet 01 — Achat & Vente</div>
        <h2 class="section-title reveal" data-en="The Electric<br>Marketplace" data-fr="La Marketplace<br>Électrique">La Marketplace<br>Électrique</h2>
        <p class="section-sub reveal delay-1" data-en="Buy and sell electric scooters, bikes, monowheel and accessories with confidence." data-fr="Achetez et vendez trottinettes, vélos électriques, monoroues et accessoires en toute confiance.">Achetez et vendez trottinettes, vélos électriques, monoroues et accessoires en toute confiance.</p>
      </div>
      <button class="btn-primary reveal" onclick="openModal('sell')" data-en="+ Post an ad" data-fr="+ Déposer une annonce">+ Déposer une annonce</button>
    </div>

    <div class="filter-search reveal">
      <span>🔍</span>
      <input type="text" id="listingSearch" placeholder="Rechercher un modèle, marque, ville..." data-placeholder-en="Search model, brand, city..." data-placeholder-fr="Rechercher un modèle, marque, ville...">
    </div>

    <div class="marketplace-filters reveal">
      <button class="filter-chip active" data-filter="all" data-en="All" data-fr="Tout">Tout</button>
      <button class="filter-chip" data-filter="trottinette" data-en="E-Scooters" data-fr="Trottinettes">🛴 Trottinettes</button>
      <button class="filter-chip" data-filter="velo" data-en="E-Bikes" data-fr="Vélos électriques">🚲 Vélos électriques</button>
      <button class="filter-chip" data-filter="monoroue" data-en="Monowheels" data-fr="Monoroues">🔵 Monoroues</button>
      <button class="filter-chip" data-filter="scooter" data-en="Scooters" data-fr="Scooters">🛵 Scooters</button>
      <button class="filter-chip" data-filter="accessoire" data-en="Accessories" data-fr="Accessoires">🎽 Accessoires</button>
      <button class="filter-chip" data-filter="piece" data-en="Parts" data-fr="Pièces">🔧 Pièces</button>
    </div>

    <div class="grid-listings" id="listingsGrid">
      <!-- Cards injected by JS -->
    </div>

    <div style="text-align:center;margin-top:40px;" class="reveal">
      <button class="btn-ghost" style="padding:12px 32px;" onclick="loadMoreListings()" data-en="Load more listings" data-fr="Charger plus d'annonces">Charger plus d'annonces</button>
    </div>
  </div>
</section>

<div class="section-divider"><span>RIDERS</span></div>

<!-- ============================================================ RIDERS -->
<section id="riders" class="py-section">
  <div class="container">
    <div class="section-label" data-en="Tab 02 — Social Network" data-fr="Onglet 02 — Réseau Social">Onglet 02 — Réseau Social</div>
    <h2 class="section-title reveal" data-en="The Riders Community" data-fr="La Communauté Riders">La Communauté Riders</h2>

    <div class="social-layout">
      <!-- LEFT SIDEBAR -->
      <div class="social-sidebar">
        <div class="profile-card reveal">
          <div class="profile-cover">
            <div class="profile-avatar-wrap">
              <div class="profile-avatar">⚡</div>
            </div>
          </div>
          <div class="profile-body">
            <div class="profile-name">Alexandre D.</div>
            <div class="profile-handle">@alexride_paris</div>
            <div class="profile-bio" data-en="Dualtron Thunder rider. 8,420 km in the streets of Paris. Tuner & enthusiast." data-fr="Rider Dualtron Thunder. 8 420 km dans les rues de Paris. Tuner & passionné.">Rider Dualtron Thunder. 8 420 km dans les rues de Paris. Tuner & passionné.</div>
            <div class="profile-stats">
              <div class="p-stat"><div class="n">247</div><div class="l" data-en="Posts" data-fr="Posts">Posts</div></div>
              <div class="p-stat"><div class="n">4.2k</div><div class="l" data-en="Followers" data-fr="Abonnés">Abonnés</div></div>
              <div class="p-stat"><div class="n">189</div><div class="l" data-en="Following" data-fr="Abonnements">Abonnements</div></div>
            </div>
          </div>
        </div>

        <div class="sidebar-widget reveal delay-1">
          <div class="widget-title" data-en="Suggested riders" data-fr="Riders suggérés">Riders suggérés</div>
          <div class="rider-suggestion">
            <div class="rs-avatar" style="background:rgba(59,130,246,0.15)">🏍️</div>
            <div class="rs-info"><div class="rs-name">SpeedFreak_Lyon</div><div class="rs-meta">OneWheel GT · 3.8k km</div></div>
            <button class="btn-follow" onclick="followUser(this)" data-en="Follow" data-fr="Suivre">Suivre</button>
          </div>
          <div class="rider-suggestion">
            <div class="rs-avatar" style="background:rgba(139,92,246,0.15)">🛴</div>
            <div class="rs-info"><div class="rs-name">MarcoPolo_Berlin</div><div class="rs-meta">Dualtron X2 · 12.1k km</div></div>
            <button class="btn-follow" onclick="followUser(this)" data-en="Follow" data-fr="Suivre">Suivre</button>
          </div>
          <div class="rider-suggestion">
            <div class="rs-avatar" style="background:rgba(0,212,170,0.15)">🚲</div>
            <div class="rs-info"><div class="rs-name">VeloElec_Brussels</div><div class="rs-meta">Specialized Turbo · 6.5k km</div></div>
            <button class="btn-follow" onclick="followUser(this)" data-en="Follow" data-fr="Suivre">Suivre</button>
          </div>
        </div>
      </div>

      <!-- FEED -->
      <div class="feed" id="socialFeed">
        <!-- Injected by JS -->
      </div>

      <!-- RIGHT SIDEBAR -->
      <div class="trending-sidebar">
        <div class="sidebar-widget reveal">
          <div class="widget-title" data-en="Trending" data-fr="Tendances">Tendances</div>
          <div id="trendingList"></div>
        </div>
        <div class="sidebar-widget reveal delay-1">
          <div class="widget-title" data-en="Live events" data-fr="Événements en direct">Événements en direct</div>
          <div style="font-size:0.82rem;color:var(--white-dim)">
            <div style="padding:8px 0;border-bottom:var(--border-dim);display:flex;gap:8px;align-items:center">
              <span style="color:var(--danger);font-size:0.65rem;font-family:var(--font-mono);background:rgba(239,68,68,0.1);padding:2px 8px;border-radius:100px">● LIVE</span>
              <span data-en="Paris Night Ride — 34 riders" data-fr="Paris Night Ride — 34 riders">Paris Night Ride — 34 riders</span>
            </div>
            <div style="padding:8px 0;display:flex;gap:8px;align-items:center">
              <span style="color:var(--accent-teal);font-size:0.65rem;font-family:var(--font-mono);background:rgba(0,212,170,0.1);padding:2px 8px;border-radius:100px">SOON</span>
              <span data-en="Berlin E-Fest — 2h" data-fr="Berlin E-Fest — 2h">Berlin E-Fest — 2h</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="section-divider"><span>CARTE</span></div>

<!-- ============================================================ MAP -->
<section id="map-section" class="py-section">
  <div class="container">
    <div class="section-label" data-en="Tab 03 — Community Map" data-fr="Onglet 03 — Carte Communautaire">Onglet 03 — Carte Communautaire</div>
    <h2 class="section-title reveal" data-en="Explore Europe<br>Together" data-fr="Explorer l'Europe<br>Ensemble">Explorer l'Europe<br>Ensemble</h2>
    <p class="section-sub reveal delay-1" style="margin-bottom:40px" data-en="Spots, routes, charging stations, workshops — added and validated by the community." data-fr="Spots, parcours, bornes de recharge, ateliers — ajoutés et validés par la communauté.">Spots, parcours, bornes de recharge, ateliers — ajoutés et validés par la communauté.</p>

    <div class="map-container">
      <div class="map-sidebar reveal">
        <div class="map-sidebar-header">
          <h3 data-en="Filter by type" data-fr="Filtrer par type">Filtrer par type</h3>
          <div class="map-type-list">
            <div class="map-type-item active" onclick="filterMap(this, 'all')">
              <span class="map-type-icon">📍</span>
              <div class="map-type-info">
                <div class="map-type-name" data-en="All points" data-fr="Tous les points">Tous les points</div>
                <div class="map-type-count">2,841 points</div>
              </div>
            </div>
            <div class="map-type-item" onclick="filterMap(this, 'spot')">
              <span class="map-type-icon">🏄</span>
              <div class="map-type-info">
                <div class="map-type-name" data-en="Spots" data-fr="Spots">Spots</div>
                <div class="map-type-count">847 spots</div>
              </div>
            </div>
            <div class="map-type-item" onclick="filterMap(this, 'charge')">
              <span class="map-type-icon">⚡</span>
              <div class="map-type-info">
                <div class="map-type-name" data-en="Charging stations" data-fr="Bornes de recharge">Bornes de recharge</div>
                <div class="map-type-count">1,203 bornes</div>
              </div>
            </div>
            <div class="map-type-item" onclick="filterMap(this, 'shop')">
              <span class="map-type-icon">🔧</span>
              <div class="map-type-info">
                <div class="map-type-name" data-en="Workshops" data-fr="Ateliers">Ateliers</div>
                <div class="map-type-count">412 ateliers</div>
              </div>
            </div>
            <div class="map-type-item" onclick="filterMap(this, 'event')">
              <span class="map-type-icon">🎉</span>
              <div class="map-type-info">
                <div class="map-type-name" data-en="Events" data-fr="Événements">Événements</div>
                <div class="map-type-count">198 events</div>
              </div>
            </div>
            <div class="map-type-item" onclick="filterMap(this, 'danger')">
              <span class="map-type-icon">⚠️</span>
              <div class="map-type-info">
                <div class="map-type-name" data-en="Danger zones" data-fr="Zones de vigilance">Zones de vigilance</div>
                <div class="map-type-count">181 zones</div>
              </div>
            </div>
          </div>
        </div>
        <div class="map-points-list" id="mapPointsList"></div>
      </div>

      <div class="fake-map reveal delay-1">
        <div class="map-canvas" id="mapCanvas">
          <div class="map-bg" id="mapBg"></div>
          <!-- Pins injected by JS -->
          <div class="map-controls">
            <button class="map-ctrl-btn" title="Zoom +">＋</button>
            <button class="map-ctrl-btn" title="Zoom -">－</button>
            <button class="map-ctrl-btn" title="Locate me">◎</button>
            <button class="map-ctrl-btn" title="Add point" onclick="showToast('success','Point ajouté ! Merci pour votre contribution 🙏')">＋📍</button>
          </div>
          <div class="map-legend">
            <div class="legend-item"><div class="legend-dot" style="background:var(--gold)"></div><span data-en="Spot" data-fr="Spot">Spot</span></div>
            <div class="legend-item"><div class="legend-dot" style="background:var(--accent-teal)"></div><span data-en="Charge" data-fr="Borne">Borne</span></div>
            <div class="legend-item"><div class="legend-dot" style="background:var(--accent-blue)"></div><span data-en="Shop" data-fr="Atelier">Atelier</span></div>
            <div class="legend-item"><div class="legend-dot" style="background:#8B5CF6"></div><span data-en="Event" data-fr="Event">Event</span></div>
            <div class="legend-item"><div class="legend-dot" style="background:var(--danger)"></div><span data-en="Danger" data-fr="Danger">Danger</span></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="section-divider"><span>SORTIES</span></div>

<!-- ============================================================ SORTIES -->
<section id="sorties" class="py-section">
  <div class="container">
    <div class="section-label" data-en="Tab 04 — Events & Rides" data-fr="Onglet 04 — Sorties & Événements">Onglet 04 — Sorties & Événements</div>
    <h2 class="section-title reveal" data-en="Join the Next<br>Adventure" data-fr="Rejoindre la Prochaine<br>Aventure">Rejoindre la Prochaine<br>Aventure</h2>
    <p class="section-sub reveal delay-1" style="margin-bottom:40px" data-en="Group rides, events, meetups — create or join, track positions live." data-fr="Rides en groupe, événements, meetups — créez ou rejoignez, tracez les positions en direct.">Rides en groupe, événements, meetups — créez ou rejoignez, tracez les positions en direct.</p>
    <div class="events-grid" id="eventsGrid">
      <!-- Injected by JS -->
    </div>
  </div>
</section>

<div class="section-divider"><span>GUIDE D'ACHAT</span></div>

<!-- ============================================================ GUIDE -->
<section id="guide" class="py-section">
  <div class="container">
    <div class="section-label" data-en="Tab 05 — Buy Guide" data-fr="Onglet 05 — Guide d'Achat">Onglet 05 — Guide d'Achat</div>
    <h2 class="section-title reveal" data-en="Find Your<br>Perfect Ride" data-fr="Trouver Votre<br>Ride Idéal">Trouver Votre<br>Ride Idéal</h2>

    <div class="guide-layout">
      <div class="guide-filters-panel reveal">
        <h3>🎯 <span data-en="Your criteria" data-fr="Vos critères">Vos critères</span></h3>

        <div class="filter-group">
          <label data-en="Budget" data-fr="Budget">Budget</label>
          <div class="range-track"><div class="range-fill" id="budgetFill" style="left:0;width:65%"></div></div>
          <input type="range" id="budgetRange" min="200" max="5000" value="1500" oninput="updateRange('budget', this.value)">
          <div class="range-labels"><span>200€</span><span id="budgetVal">1 500€</span><span>5 000€</span></div>
        </div>

        <div class="filter-group">
          <label data-en="Daily distance" data-fr="Distance quotidienne">Distance quotidienne</label>
          <div class="range-track"><div class="range-fill" id="distFill" style="left:0;width:40%"></div></div>
          <input type="range" id="distRange" min="5" max="80" value="25" oninput="updateRange('dist', this.value)">
          <div class="range-labels"><span>5 km</span><span id="distVal">25 km</span><span>80 km</span></div>
        </div>

        <div class="filter-group">
          <label data-en="Rider weight (kg)" data-fr="Poids rider (kg)">Poids rider (kg)</label>
          <div class="range-track"><div class="range-fill" id="weightFill" style="left:0;width:55%"></div></div>
          <input type="range" id="weightRange" min="40" max="130" value="75" oninput="updateRange('weight', this.value)">
          <div class="range-labels"><span>40 kg</span><span id="weightVal">75 kg</span><span>130 kg</span></div>
        </div>

        <div class="filter-group">
          <label data-en="Options" data-fr="Options">Options</label>
          <div class="toggle-group">
            <div class="toggle-item"><span data-en="Portability" data-fr="Transportable">Transportable</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
            <div class="toggle-item"><span data-en="Waterproof IP67" data-fr="Étanche IP67">Étanche IP67</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
            <div class="toggle-item"><span data-en="Speed +25 km/h" data-fr="Vitesse +25 km/h">Vitesse +25 km/h</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
            <div class="toggle-item"><span data-en="For beginners" data-fr="Débutant">Débutant</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
          </div>
        </div>

        <button class="btn-primary" style="width:100%;padding:12px;margin-top:8px;" onclick="runGuide()" data-en="🔍 Search" data-fr="🔍 Rechercher">🔍 Rechercher</button>
      </div>

      <div class="guide-results" id="guideResults">
        <!-- Injected by JS -->
      </div>
    </div>
  </div>
</section>

<div class="section-divider"><span>IA VOLTERRA</span></div>

<!-- ============================================================ AI -->
<section id="ai-section" class="py-section">
  <div class="container">
    <div class="section-label" data-en="Tab 06 — AI Volterra" data-fr="Onglet 06 — IA Volterra">Onglet 06 — IA Volterra</div>
    <h2 class="section-title reveal" data-en="Your Electric<br>Intelligence" data-fr="Votre Intelligence<br>Électrique">Votre Intelligence<br>Électrique</h2>
    <p class="section-sub reveal delay-1" style="margin-bottom:40px" data-en="Advice, diagnostics, price estimation, regulations — your AI co-pilot." data-fr="Conseils, diagnostics, estimation de prix, réglementation — votre co-pilote IA.">Conseils, diagnostics, estimation de prix, réglementation — votre co-pilote IA.</p>

    <div class="ai-layout">
      <div class="ai-chat reveal">
        <div class="ai-chat-header">
          <div class="ai-avatar">🤖<div class="ai-status"></div></div>
          <div class="ai-info">
            <div class="ai-name">Volt — IA Volterra</div>
            <div class="ai-subtitle" data-en="● Active — 0ms response" data-fr="● Actif — 0ms de réponse">● Actif — 0ms de réponse</div>
          </div>
          <div style="font-size:0.72rem;font-family:var(--font-mono);color:var(--white-dim)" data-en="Gemini 2.0" data-fr="Gemini 2.0">Gemini 2.0</div>
        </div>
        <div class="ai-messages" id="aiMessages">
          <div class="msg bot">
            <div class="msg-avatar">⚡</div>
            <div class="msg-bubble" data-en="Hello! I'm Volt, your electric mobility AI. I can help you choose a vehicle, diagnose a fault, estimate a price, understand European regulations... What would you like to know?" data-fr="Bonjour ! Je suis Volt, votre IA de mobilité électrique. Je peux vous aider à choisir un véhicule, diagnostiquer une panne, estimer un prix, comprendre la réglementation européenne... Que souhaitez-vous savoir ?">Bonjour ! Je suis Volt, votre IA de mobilité électrique. Je peux vous aider à choisir un véhicule, diagnostiquer une panne, estimer un prix, comprendre la réglementation européenne... Que souhaitez-vous savoir ?</div>
          </div>
        </div>
        <div class="ai-quick-replies" id="quickReplies">
          <button class="quick-reply" onclick="sendAIMessage(this.textContent)">💰 Estimer mon prix de revente</button>
          <button class="quick-reply" onclick="sendAIMessage(this.textContent)">🔧 Diagnostiquer une panne</button>
          <button class="quick-reply" onclick="sendAIMessage(this.textContent)">📋 Réglementation française</button>
          <button class="quick-reply" onclick="sendAIMessage(this.textContent)">🔍 Comparer deux modèles</button>
        </div>
        <div class="ai-input-wrap">
          <textarea class="ai-input" id="aiInput" rows="1" placeholder="Posez votre question à Volt..." data-placeholder-en="Ask Volt anything..." data-placeholder-fr="Posez votre question à Volt..." onkeydown="aiInputKey(event)"></textarea>
          <button class="ai-send" onclick="sendAIMessage()">➤</button>
        </div>
      </div>

      <div class="ai-sidebar">
        <div class="ai-feature-card reveal">
          <div class="ai-feat-icon" style="background:rgba(201,168,76,0.1)">🎯</div>
          <div class="ai-feat-title" data-en="Smart recommendation" data-fr="Recommandation intelligente">Recommandation intelligente</div>
          <div class="ai-feat-desc" data-en="Tell us your budget, weight and distance — Volt recommends the 3 ideal models with pros/cons." data-fr="Dites votre budget, poids et distance — Volt recommande les 3 modèles idéaux avec pour/contre.">Dites votre budget, poids et distance — Volt recommande les 3 modèles idéaux avec pour/contre.</div>
        </div>
        <div class="ai-feature-card reveal delay-1">
          <div class="ai-feat-icon" style="background:rgba(239,68,68,0.1)">🔧</div>
          <div class="ai-feat-title" data-en="Visual diagnosis" data-fr="Diagnostic visuel">Diagnostic visuel</div>
          <div class="ai-feat-desc" data-en="Upload a photo of your vehicle — Volt detects defects, wear and estimates repair costs." data-fr="Téléchargez une photo de votre véhicule — Volt détecte les défauts, l'usure et estime les coûts de réparation.">Téléchargez une photo de votre véhicule — Volt détecte les défauts, l'usure et estime les coûts de réparation.</div>
        </div>
        <div class="ai-feature-card reveal delay-2">
          <div class="ai-feat-icon" style="background:rgba(34,197,94,0.1)">📝</div>
          <div class="ai-feat-title" data-en="Auto ad generation" data-fr="Génération d'annonce auto">Génération d'annonce auto</div>
          <div class="ai-feat-desc" data-en="A few details + one photo — Volt writes the perfect listing to maximize your sale." data-fr="Quelques détails + une photo — Volt rédige l'annonce parfaite pour maximiser votre vente.">Quelques détails + une photo — Volt rédige l'annonce parfaite pour maximiser votre vente.</div>
        </div>
        <div class="ai-feature-card reveal delay-3">
          <div class="ai-feat-icon" style="background:rgba(139,92,246,0.1)">⚖️</div>
          <div class="ai-feat-title" data-en="European regulation" data-fr="Réglementation européenne">Réglementation européenne</div>
          <div class="ai-feat-desc" data-en="Speed limits, equipment, insurance, allowed zones — always up to date for all EU countries." data-fr="Vitesses limites, équipements, assurance, zones autorisées — toujours à jour pour tous les pays EU.">Vitesses limites, équipements, assurance, zones autorisées — toujours à jour pour tous les pays EU.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="section-divider"><span>COTE DU MARCHÉ</span></div>

<!-- ============================================================ COTE -->
<section id="cote" class="py-section">
  <div class="container">
    <div class="section-label" data-en="Tab 07 — Market Prices" data-fr="Onglet 07 — Cote du Marché">Onglet 07 — Cote du Marché</div>
    <h2 class="section-title reveal" data-en="Market Prices<br>in Real Time" data-fr="La Cote du Marché<br>en Temps Réel">La Cote du Marché<br>en Temps Réel</h2>
    <p class="section-sub reveal delay-1" style="margin-bottom:40px" data-en="Track prices of every model: new, average used, 6-month history." data-fr="Suivez les prix de chaque modèle : neuf, occasion moyen, historique 6 mois.">Suivez les prix de chaque modèle : neuf, occasion moyen, historique 6 mois.</p>
    <div class="cote-grid" id="coteGrid">
      <!-- Injected by JS -->
    </div>
  </div>
</section>

<div class="section-divider"><span>CLASSEMENTS</span></div>

<!-- ============================================================ RANKINGS -->
<section id="rankings" class="py-section">
  <div class="container">
    <div class="section-label" data-en="Tab 08 — Rankings" data-fr="Onglet 08 — Classements">Onglet 08 — Classements</div>
    <h2 class="section-title reveal" data-en="European<br>Rankings" data-fr="Classements<br>Européens">Classements<br>Européens</h2>

    <div class="rankings-tabs">
      <button class="rank-tab active" onclick="switchRankTab(this,'fiabilite')" data-en="Most reliable" data-fr="Plus fiables">Plus fiables</button>
      <button class="rank-tab" onclick="switchRankTab(this,'ventes')" data-en="Best sellers" data-fr="Plus vendus">Plus vendus</button>
      <button class="rank-tab" onclick="switchRankTab(this,'rapport')" data-en="Best value" data-fr="Meilleur rapport">Meilleur rapport</button>
      <button class="rank-tab" onclick="switchRankTab(this,'autonomie')" data-en="Best range" data-fr="Meilleure autonomie">Meilleure autonomie</button>
    </div>

    <div class="rankings-grid" id="rankingsGrid">
      <!-- Injected by JS -->
    </div>
  </div>
</section>

<div class="section-divider"><span>CARNET NUMÉRIQUE</span></div>

<!-- ============================================================ CARNET -->
<section id="carnet" class="py-section">
  <div class="container">
    <div class="section-label" data-en="Tab 09 — Digital Logbook" data-fr="Onglet 09 — Carnet Numérique">Onglet 09 — Carnet Numérique</div>
    <h2 class="section-title reveal" data-en="Your Vehicle's<br>Digital Memory" data-fr="La Mémoire Numérique<br>de Votre Véhicule">La Mémoire Numérique<br>de Votre Véhicule</h2>

    <div class="carnet-layout">
      <div>
        <div class="vehicle-select-wrap reveal">
          <div class="vehicle-card-select active" onclick="selectVehicle(this,'Dualtron Thunder 2')">
            <div class="vehicle-card-select-icon">🛴</div>
            <div class="vehicle-card-select-info">
              <div class="vehicle-card-select-name">Dualtron Thunder 2</div>
              <div class="vehicle-card-select-km">8 420 km</div>
            </div>
          </div>
          <div class="vehicle-card-select" onclick="selectVehicle(this,'Ninebot Max G30')">
            <div class="vehicle-card-select-icon">🛴</div>
            <div class="vehicle-card-select-info">
              <div class="vehicle-card-select-name">Ninebot Max G30</div>
              <div class="vehicle-card-select-km">3 150 km</div>
            </div>
          </div>
          <div class="vehicle-card-select" onclick="selectVehicle(this,'Inmotion V12')">
            <div class="vehicle-card-select-icon">🔵</div>
            <div class="vehicle-card-select-info">
              <div class="vehicle-card-select-name">Inmotion V12</div>
              <div class="vehicle-card-select-km">1 890 km</div>
            </div>
          </div>
        </div>

        <div class="carnet-main reveal delay-1">
          <div class="carnet-header">
            <div class="vehicle-big-display">
              <div class="vehicle-big-icon">🛴</div>
              <div>
                <div class="vehicle-big-name" id="carnetVehicleName">Dualtron Thunder 2</div>
                <div class="vehicle-big-brand">Minimotors · 2022</div>
                <div class="vehicle-km-display">
                  <div class="vehicle-km-num" id="carnetKm">8 420</div>
                  <div class="vehicle-km-unit">km</div>
                </div>
                <div class="carnet-serial">
                  <span data-en="Serial:" data-fr="N° série:">N° série:</span>
                  <span class="serial-badge">DTH2-FR-2022-04471</span>
                  <span class="verified-badge" title="Vérifié">✓</span>
                </div>
              </div>
            </div>
          </div>
          <div class="carnet-tabs-inner">
            <div class="carnet-tab active" onclick="switchCarnetTab(this,'entretien')" data-en="Maintenance" data-fr="Entretien">Entretien</div>
            <div class="carnet-tab" onclick="switchCarnetTab(this,'reparations')" data-en="Repairs" data-fr="Réparations">Réparations</div>
            <div class="carnet-tab" onclick="switchCarnetTab(this,'modifs')" data-en="Mods" data-fr="Modifications">Modifications</div>
            <div class="carnet-tab" onclick="switchCarnetTab(this,'documents')" data-en="Docs" data-fr="Documents">Documents</div>
          </div>
          <div class="carnet-entries" id="carnetEntries">
            <!-- Injected by JS -->
          </div>
        </div>
      </div>

      <div class="carnet-sidebar">
        <div class="carnet-widget reveal">
          <div class="carnet-widget-title" data-en="Vehicle health" data-fr="Santé du véhicule">Santé du véhicule</div>
          <div class="health-bar-item">
            <div class="health-bar-label"><span data-en="Battery" data-fr="Batterie">Batterie</span><span style="color:var(--success)">87%</span></div>
            <div class="health-bar-track"><div class="health-bar-fill good" style="width:87%"></div></div>
          </div>
          <div class="health-bar-item">
            <div class="health-bar-label"><span data-en="Tires" data-fr="Pneus">Pneus</span><span style="color:var(--gold)">61%</span></div>
            <div class="health-bar-track"><div class="health-bar-fill ok" style="width:61%"></div></div>
          </div>
          <div class="health-bar-item">
            <div class="health-bar-label"><span data-en="Brakes" data-fr="Freins">Freins</span><span style="color:var(--success)">79%</span></div>
            <div class="health-bar-track"><div class="health-bar-fill good" style="width:79%"></div></div>
          </div>
          <div class="health-bar-item">
            <div class="health-bar-label"><span data-en="Motors" data-fr="Moteurs">Moteurs</span><span style="color:var(--danger)">43%</span></div>
            <div class="health-bar-track"><div class="health-bar-fill bad" style="width:43%"></div></div>
          </div>
        </div>

        <div class="carnet-widget reveal delay-1">
          <div class="carnet-widget-title" data-en="Anti-theft protection" data-fr="Protection anti-vol">Protection anti-vol</div>
          <div class="antivol-status">
            <div class="antivol-icon">🔒</div>
            <div class="antivol-info">
              <div class="antivol-label" data-en="Protected" data-fr="Protégé">Protégé</div>
              <div class="antivol-desc" data-en="Registered — alert active" data-fr="Enregistré — alerte active">Enregistré — alerte active</div>
            </div>
          </div>
        </div>

        <div class="carnet-widget reveal delay-2">
          <div class="carnet-widget-title" data-en="Estimated resale value" data-fr="Valeur de revente estimée">Valeur de revente estimée</div>
          <div style="text-align:center;padding:12px 0">
            <div style="font-family:var(--font-display);font-size:2.2rem;font-weight:800;color:var(--gold)">1 850€</div>
            <div style="font-size:0.75rem;color:var(--white-dim);margin-top:4px" data-en="Based on 23 similar sales" data-fr="Basé sur 23 ventes similaires">Basé sur 23 ventes similaires</div>
            <div style="font-size:0.72rem;color:var(--success);margin-top:6px">▲ +120€ vs mois dernier</div>
          </div>
          <button class="btn-primary" style="width:100%;padding:10px;font-size:0.82rem;" onclick="showToast('success','Votre annonce a été générée par l\'IA ✨')" data-en="📝 Generate ad" data-fr="📝 Générer l'annonce">📝 Générer l'annonce</button>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="section-divider"><span>GAMIFICATION</span></div>

<!-- ============================================================ GAMIFICATION -->
<section id="gamification" class="py-section">
  <div class="container">
    <div class="section-label" data-en="Tab 11 — Gamification" data-fr="Onglet 11 — Gamification">Onglet 11 — Gamification</div>
    <h2 class="section-title reveal" data-en="Level Up<br>Every Ride" data-fr="Progresser à Chaque<br>Kilomètre">Progresser à Chaque<br>Kilomètre</h2>
    <p class="section-sub reveal delay-1" style="margin-bottom:40px" data-en="Earn XP, unlock badges, climb the European leaderboard." data-fr="Gagnez des XP, débloquez des badges, grimpez dans le classement européen.">Gagnez des XP, débloquez des badges, grimpez dans le classement européen.</p>

    <div class="gamif-layout">
      <div class="gamif-card reveal">
        <div class="gamif-icon-wrap" style="background:linear-gradient(135deg,rgba(201,168,76,0.15),rgba(201,168,76,0.05));border:1px solid rgba(201,168,76,0.2)">⚡</div>
        <div class="gamif-card-title" data-en="Experience Points" data-fr="Points d'expérience">Points d'expérience</div>
        <div class="gamif-card-desc" data-en="Gain XP for every ride, sale, purchase, publication and map contribution." data-fr="Gagnez des XP pour chaque ride, vente, achat, publication et contribution à la carte.">Gagnez des XP pour chaque ride, vente, achat, publication et contribution à la carte.</div>
        <div class="xp-bar-wrap">
          <div class="xp-bar-label"><span>Niveau 7 — Élite Rider</span><span style="color:var(--gold)">3420/5000 XP</span></div>
          <div class="xp-bar-track"><div class="xp-bar-fill" id="xpBar" style="width:0%"></div></div>
        </div>
      </div>

      <div class="gamif-card reveal delay-1">
        <div class="gamif-icon-wrap" style="background:linear-gradient(135deg,rgba(139,92,246,0.15),rgba(139,92,246,0.05));border:1px solid rgba(139,92,246,0.2)">🏅</div>
        <div class="gamif-card-title" data-en="Badges & Achievements" data-fr="Badges & Accomplissements">Badges & Accomplissements</div>
        <div class="gamif-card-desc" data-en="100 km, 1000 km, 5000 km, 10000 km and many more exclusive badges." data-fr="100 km, 1 000 km, 5 000 km, 10 000 km et bien d'autres badges exclusifs.">100 km, 1 000 km, 5 000 km, 10 000 km et bien d'autres badges exclusifs.</div>
        <div class="badges-grid">
          <div class="badge-item earned" title="100 km" style="background:rgba(201,168,76,0.1)">🥉</div>
          <div class="badge-item earned" title="500 km" style="background:rgba(201,168,76,0.1)">🥈</div>
          <div class="badge-item earned" title="1000 km" style="background:rgba(201,168,76,0.1)">🥇</div>
          <div class="badge-item earned" title="5000 km" style="background:rgba(201,168,76,0.1)">👑</div>
          <div class="badge-item earned" title="Vendeur" style="background:rgba(34,197,94,0.1)">💰</div>
          <div class="badge-item earned" title="Cartographe" style="background:rgba(59,130,246,0.1)">🗺️</div>
          <div class="badge-item locked" title="10000 km" style="background:rgba(240,242,247,0.05)">⭐</div>
          <div class="badge-item locked" title="Ambassadeur" style="background:rgba(240,242,247,0.05)">🌟</div>
        </div>
      </div>

      <div class="gamif-card reveal delay-2">
        <div class="gamif-icon-wrap" style="background:linear-gradient(135deg,rgba(0,212,170,0.15),rgba(0,212,170,0.05));border:1px solid rgba(0,212,170,0.2)">🏆</div>
        <div class="gamif-card-title" data-en="European Leaderboard" data-fr="Classement Européen">Classement Européen</div>
        <div class="gamif-card-desc" data-en="City, region, country, Europe — compete and climb the global ranking." data-fr="Ville, région, pays, Europe — compétez et grimpez dans le classement mondial.">Ville, région, pays, Europe — compétez et grimpez dans le classement mondial.</div>
        <div class="leaderboard-mini" id="leaderboard">
          <!-- Injected by JS -->
        </div>
      </div>
    </div>
  </div>
</section>

<div class="section-divider"><span>PREMIUM</span></div>

<!-- ============================================================ PRICING -->
<section id="pricing" class="py-section">
  <div class="container">
    <div style="text-align:center;margin-bottom:60px">
      <div class="section-label" data-en="Choose your plan" data-fr="Choisissez votre plan">Choisissez votre plan</div>
      <h2 class="section-title reveal" style="margin-bottom:12px" data-en="Simple,<br>transparent pricing" data-fr="Des Tarifs<br>Simples et Transparents">Des Tarifs<br>Simples et Transparents</h2>
    </div>

    <div class="pricing-grid">
      <div class="pricing-card reveal">
        <div class="pricing-plan" data-en="Free" data-fr="Gratuit">Gratuit</div>
        <div class="pricing-price"><span class="currency">€</span>0<span class="period">/mois</span></div>
        <div class="pricing-desc" data-en="Discover Volterra and sell your first vehicles." data-fr="Découvrez Volterra et vendez vos premiers véhicules.">Découvrez Volterra et vendez vos premiers véhicules.</div>
        <div class="pricing-features">
          <div class="pricing-feature"><span class="check">✓</span><span data-en="2 free listings" data-fr="2 annonces gratuites">2 annonces gratuites</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Social profile" data-fr="Profil social">Profil social</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Community map" data-fr="Carte communautaire">Carte communautaire</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="20 price alerts" data-fr="20 alertes prix">20 alertes prix</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Digital logbook (1 vehicle)" data-fr="Carnet numérique (1 véhicule)">Carnet numérique (1 véhicule)</span></div>
          <div class="pricing-feature"><span class="cross">✗</span><span style="color:var(--white-dim)" data-en="AI Volt (limited)" data-fr="IA Volt (limitée)">IA Volt (limitée)</span></div>
          <div class="pricing-feature"><span class="cross">✗</span><span style="color:var(--white-dim)" data-en="Advanced analytics" data-fr="Analyses avancées">Analyses avancées</span></div>
        </div>
        <button class="btn-ghost modal-cta" onclick="openModal('signup')" data-en="Get started for free" data-fr="Commencer gratuitement">Commencer gratuitement</button>
      </div>

      <div class="pricing-card popular reveal delay-1">
        <div class="pricing-popular-badge" data-en="MOST POPULAR" data-fr="LE PLUS POPULAIRE">LE PLUS POPULAIRE</div>
        <div class="pricing-plan" data-en="Premium" data-fr="Premium">Premium</div>
        <div class="pricing-price" style="color:var(--gold)"><span class="currency">€</span>9.99<span class="period">/mois</span></div>
        <div class="pricing-desc" data-en="For passionate riders who want the full Volterra experience." data-fr="Pour les riders passionnés qui veulent l'expérience Volterra complète.">Pour les riders passionnés qui veulent l'expérience Volterra complète.</div>
        <div class="pricing-features">
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Unlimited listings" data-fr="Annonces illimitées">Annonces illimitées</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Free ad boosts" data-fr="Boosts d'annonces offerts">Boosts d'annonces offerts</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Unlimited AI Volt" data-fr="IA Volt illimitée">IA Volt illimitée</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Unlimited price alerts" data-fr="Alertes prix illimitées">Alertes prix illimitées</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Unlimited logbook" data-fr="Carnet numérique illimité">Carnet numérique illimité</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Premium events access" data-fr="Accès sorties premium">Accès sorties premium</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Premium badge" data-fr="Badge premium">Badge premium</span></div>
        </div>
        <button class="btn-primary modal-cta" onclick="openModal('signup')" data-en="Start Premium" data-fr="Démarrer Premium">Démarrer Premium</button>
      </div>

      <div class="pricing-card reveal delay-2">
        <div class="pricing-plan" data-en="Pro" data-fr="Pro">Pro</div>
        <div class="pricing-price"><span class="currency">€</span>19<span class="period">/mois</span></div>
        <div class="pricing-desc" data-en="For shops, repairers, dealers and brands." data-fr="Pour les magasins, réparateurs, revendeurs et marques.">Pour les magasins, réparateurs, revendeurs et marques.</div>
        <div class="pricing-features">
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Everything in Premium" data-fr="Tout le Premium">Tout le Premium</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Pro business page" data-fr="Page professionnelle">Page professionnelle</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Native advertising" data-fr="Publicités natives">Publicités natives</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Advanced statistics" data-fr="Statistiques avancées">Statistiques avancées</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Official brand pages" data-fr="Pages officielles marques">Pages officielles marques</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="Priority support" data-fr="Support prioritaire">Support prioritaire</span></div>
          <div class="pricing-feature"><span class="check">✓</span><span data-en="API access" data-fr="Accès API">Accès API</span></div>
        </div>
        <button class="btn-ghost modal-cta" onclick="openModal('pro')" data-en="Contact sales" data-fr="Contacter les ventes">Contacter les ventes</button>
      </div>
    </div>
  </div>
</section>

<!-- ============================================================ FOOTER -->
<footer>
  <div class="container">
    <div class="footer-grid">
      <div class="footer-brand">
        <div class="nav-logo" style="font-size:1.3rem">
          <div class="nav-logo-icon" style="width:32px;height:32px;font-size:1rem">⚡</div>
          VOLT<span>ERRA</span>
        </div>
        <p data-en="The ultra-premium European platform for personal electric mobility. Ecosystem, community, marketplace and artificial intelligence — all in one app." data-fr="La plateforme européenne ultra-premium de la mobilité électrique personnelle. Écosystème, communauté, marketplace et intelligence artificielle — tout en une seule app.">La plateforme européenne ultra-premium de la mobilité électrique personnelle. Écosystème, communauté, marketplace et intelligence artificielle — tout en une seule app.</p>
        <div class="footer-socials">
          <a href="#" class="social-btn" title="Instagram">📸</a>
          <a href="#" class="social-btn" title="Twitter/X">🐦</a>
          <a href="#" class="social-btn" title="TikTok">🎵</a>
          <a href="#" class="social-btn" title="YouTube">▶️</a>
          <a href="#" class="social-btn" title="Discord">💬</a>
        </div>
      </div>
      <div class="footer-col">
        <h4 data-en="Platform" data-fr="Plateforme">Plateforme</h4>
        <ul>
          <li><a href="#marketplace" data-en="Marketplace" data-fr="Marketplace">Marketplace</a></li>
          <li><a href="#riders" data-en="Riders Community" data-fr="Communauté Riders">Communauté Riders</a></li>
          <li><a href="#map-section" data-en="Community Map" data-fr="Carte communautaire">Carte communautaire</a></li>
          <li><a href="#sorties" data-en="Events" data-fr="Sorties">Sorties</a></li>
          <li><a href="#ai-section" data-en="AI Volt" data-fr="IA Volt">IA Volt</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4 data-en="Tools" data-fr="Outils">Outils</h4>
        <ul>
          <li><a href="#cote" data-en="Market Prices" data-fr="Cote du marché">Cote du marché</a></li>
          <li><a href="#guide" data-en="Buy Guide" data-fr="Guide d'achat">Guide d'achat</a></li>
          <li><a href="#carnet" data-en="Digital Logbook" data-fr="Carnet numérique">Carnet numérique</a></li>
          <li><a href="#rankings" data-en="Rankings" data-fr="Classements">Classements</a></li>
          <li><a href="#gamification" data-en="Gamification" data-fr="Gamification">Gamification</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4 data-en="Company" data-fr="Société">Société</h4>
        <ul>
          <li><a href="#" data-en="About" data-fr="À propos">À propos</a></li>
          <li><a href="#" data-en="Blog" data-fr="Blog">Blog</a></li>
          <li><a href="#" data-en="Careers" data-fr="Carrières">Carrières</a></li>
          <li><a href="#" data-en="Press" data-fr="Presse">Presse</a></li>
          <li><a href="#" data-en="Contact" data-fr="Contact">Contact</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <div>© 2025 <span class="gold">Volterra</span> — <span data-en="All rights reserved" data-fr="Tous droits réservés">Tous droits réservés</span></div>
      <div style="display:flex;gap:20px">
        <a href="#" data-en="Privacy" data-fr="Confidentialité">Confidentialité</a>
        <a href="#" data-en="Terms" data-fr="CGU">CGU</a>
        <a href="#" data-en="Legal" data-fr="Mentions légales">Mentions légales</a>
      </div>
      <div style="font-family:var(--font-mono);font-size:0.72rem;color:var(--white-dim)">
        <span data-en="Made with ⚡ in Europe" data-fr="Fait avec ⚡ en Europe">Fait avec ⚡ en Europe</span>
      </div>
    </div>
  </div>
</footer>

<!-- ============================================================ MODALS -->
<div class="modal-overlay" id="modalOverlay" onclick="if(event.target===this)closeModal()">
  <div class="modal" id="modalBox">
    <button class="modal-close" onclick="closeModal()">✕</button>
    <div id="modalContent"></div>
  </div>
</div>

<!-- ============================================================ TOAST -->
<div class="toast-container" id="toastContainer"></div>

<!-- ============================================================ JAVASCRIPT -->
<script>
/* ============================================================
   DATA
   ============================================================ */
const LISTINGS = [
  { id:1, name:'Dualtron Thunder 2', cat:'trottinette', price:2100, oldPrice:2800, emoji:'🛴', loc:'Paris 11e', km:'4 200 km', watt:'5400W', brand:'Minimotors', badge:'Vérifié', seller:'AlexRide', rating:'★★★★★', color:'rgba(201,168,76,0.06)' },
  { id:2, name:'Ninebot Max G30E II', cat:'trottinette', price:480, oldPrice:699, emoji:'🛴', loc:'Lyon 3e', km:'1 800 km', watt:'350W', brand:'Segway-Ninebot', badge:'Premium', seller:'PierreElec', rating:'★★★★☆', color:'rgba(139,92,246,0.06)' },
  { id:3, name:'Specialized Turbo Vado 5.0', cat:'velo', price:3400, oldPrice:4200, emoji:'🚲', loc:'Bordeaux', km:'820 km', watt:'565Wh', brand:'Specialized', badge:'Nouveau', seller:'CycloPro', rating:'★★★★★', color:'rgba(0,212,170,0.06)' },
  { id:4, name:'Inmotion V12 HT', cat:'monoroue', price:1650, oldPrice:null, emoji:'🔵', loc:'Toulouse', km:'2 100 km', watt:'2200W', brand:'Inmotion', badge:'Vérifié', seller:'UniWheelFan', rating:'★★★★☆', color:'rgba(59,130,246,0.06)' },
  { id:5, name:'Xiaomi P1S', cat:'scooter', price:790, oldPrice:1099, emoji:'🛵', loc:'Marseille', km:'3 400 km', watt:'300W', brand:'Xiaomi', badge:null, seller:'MotoElec13', rating:'★★★☆☆', color:'rgba(201,168,76,0.03)' },
  { id:6, name:'Casque EVO Jet', cat:'accessoire', price:89, oldPrice:null, emoji:'⛑️', loc:'Nantes', km:null, watt:null, brand:'HJC', badge:'Nouveau', seller:'SafeRider', rating:'★★★★★', color:'rgba(0,212,170,0.04)' },
  { id:7, name:'Citroën Ami Electric', cat:'scooter', price:5200, oldPrice:7400, emoji:'🚗', loc:'Paris 8e', km:'6 100 km', watt:'6kW', brand:'Citroën', badge:'Premium', seller:'UrbanElec', rating:'★★★★☆', color:'rgba(139,92,246,0.06)' },
  { id:8, name:'Pneumatique 10x2.5 CST', cat:'piece', price:24, oldPrice:null, emoji:'🔧', loc:'En ligne', km:null, watt:null, brand:'CST', badge:null, seller:'PiècesElec', rating:'★★★★☆', color:'rgba(201,168,76,0.03)' },
];

const POSTS = [
  { author:'SpeedFreak_Lyon', handle:'@speedfreak_lyon', emoji:'🏍️', time:'il y a 2h', text:'Sortie nocturne sur les quais de la Saône avec 12 riders. Vue incroyable sur la ville ! Mon Dualtron X2 a mangé 38 km sans broncher 🔥', tags:['#DualtronX2','#Lyon','#NightRide','#ElectricMobility'], media:'🌃', likes:184, comments:23, shares:12, bg:'linear-gradient(135deg,rgba(201,168,76,0.08),rgba(10,15,30,0.95))' },
  { author:'VeloElec_Brussels', handle:'@veloelec_bxl', emoji:'🚲', time:'il y a 5h', text:'Test longue distance : Bruxelles → Gand en Specialized Turbo Vado 5.0. 63 km avec 1 seule recharge ! La technologie eBike 2024 c\'est fou 🚀', tags:['#SpecializedTurbo','#Brussels','#EBike','#LongRange'], media:'🌄', likes:267, comments:41, shares:28, bg:'linear-gradient(135deg,rgba(0,212,170,0.06),rgba(10,15,30,0.95))' },
  { author:'MarcoPolo_Berlin', handle:'@marcopolo_berlin', emoji:'🛴', time:'il y a 1j', text:'Ma nouvelle setup : Dualtron X2 + suspension upgrade + lumières LED custom. 12 000 km au compteur, toujours aussi fun 💛', tags:['#DualtronX2','#CustomBuild','#Berlin','#Volterra'], media:'✨', likes:521, comments:78, shares:64, bg:'linear-gradient(135deg,rgba(139,92,246,0.06),rgba(10,15,30,0.95))' },
];

const TRENDING = [
  { tag:'#DualtronX2', count:'2.4k posts' }, { tag:'#NightRide', count:'1.8k posts' },
  { tag:'#EBike2024', count:'1.2k posts' }, { tag:'#TrottinetteParis', count:'940 posts' },
  { tag:'#InmotionV12', count:'820 posts' }, { tag:'#Volterra', count:'650 posts' },
];

const MAP_PINS = [
  { type:'spot', x:22, y:25, label:'Spot Esplanade', color:'var(--gold)', emoji:'🏄' },
  { type:'charge', x:45, y:40, label:'Borne Vattenfall', color:'var(--accent-teal)', emoji:'⚡' },
  { type:'shop', x:65, y:30, label:'AtlierElec PRO', color:'var(--accent-blue)', emoji:'🔧' },
  { type:'event', x:35, y:60, label:'Night Ride Paris', color:'#8B5CF6', emoji:'🎉' },
  { type:'charge', x:72, y:65, label:'Borne Fastned', color:'var(--accent-teal)', emoji:'⚡' },
  { type:'spot', x:82, y:22, label:'Spot Bassin Trocadéro', color:'var(--gold)', emoji:'🏄' },
  { type:'danger', x:55, y:72, label:'Zone radar', color:'var(--danger)', emoji:'⚠️' },
  { type:'charge', x:15, y:58, label:'Borne Total Energy', color:'var(--accent-teal)', emoji:'⚡' },
  { type:'spot', x:60, y:52, label:'Promenade des Arts', color:'var(--gold)', emoji:'🏄' },
  { type:'shop', x:30, y:38, label:'E-Ride Store', color:'var(--accent-blue)', emoji:'🔧' },
];

const MAP_POINTS = [
  { icon:'🏄', name:'Spot Esplanade', loc:'Paris 15e', rating:'★★★★★', type:'spot' },
  { icon:'⚡', name:'Borne Vattenfall', loc:'Paris 8e', rating:'★★★★☆', type:'charge' },
  { icon:'🔧', name:'AtlierElec PRO', loc:'Paris 11e', rating:'★★★★★', type:'shop' },
  { icon:'🎉', name:'Night Ride — 22 juin', loc:'Paris Rive Gauche', rating:'★★★★☆', type:'event' },
];

const EVENTS = [
  { icon:'🌃', title:'Paris Night Ride', loc:'Pont d\'Iéna, Paris', day:'22', month:'JUIN', dist:'28 km', level:3, participants:['🧑','👩','🧔','👨','🙋'], count:'34/50 riders', free:true, price:'Gratuit', diff:['🟡','🟡','🟡','⚫','⚫'] },
  { icon:'🏁', title:'Lyon Speed Tour', loc:'Quais de Saône, Lyon', day:'29', month:'JUIN', dist:'45 km', level:4, participants:['👩','🧔','🧑','🙋'], count:'18/30 riders', free:false, price:'12€', diff:['🔴','🔴','🔴','🔴','⚫'] },
  { icon:'🌿', title:'Brussels Discovery Ride', loc:'Parc Cinquantenaire, BXL', day:'05', month:'JUIL', dist:'22 km', level:1, participants:['🧑','👩','🧔'], count:'41/60 riders', free:true, price:'Gratuit', diff:['🟢','⚫','⚫','⚫','⚫'] },
  { icon:'⚡', title:'Berlin E-Fest 2025', loc:'Tempelhof, Berlin', day:'12', month:'JUIL', dist:'60 km', level:5, participants:['🧔','👨','👩','🧑','🙋'], count:'127/200 riders', free:false, price:'25€', diff:['🔴','🔴','🔴','🔴','🔴'] },
];

const GUIDE_RESULTS = [
  { icon:'🛴', name:'Dualtron Victor', brand:'Minimotors', specs:['60 km', '65 km/h', '25 kg', 'IP55'], price:'1 490€', score:94, recommended:true },
  { icon:'🛴', name:'Kaabo Wolf Warrior 11+', brand:'Kaabo', specs:['70 km', '80 km/h', '35 kg', 'IP54'], price:'1 699€', score:89, recommended:false },
  { icon:'🛴', name:'Ninebot Max G30D', brand:'Segway', specs:['65 km', '25 km/h', '18 kg', 'IP55'], price:'699€', score:82, recommended:false },
  { icon:'🚲', name:'Cube Reaction Hybrid Pro 625', brand:'Cube', specs:['120 km', '25 km/h', '23 kg', 'IP44'], price:'1 299€', score:78, recommended:false },
];

const COTE_DATA = [
  { icon:'🛴', name:'Dualtron Thunder 2', brand:'Minimotors', neuf:'2 899€', occasion:'2 100€', bas:'1 600€', change:'+3.2%', up:true },
  { icon:'🛴', name:'Ninebot Max G30', brand:'Segway-Ninebot', neuf:'699€', occasion:'480€', bas:'320€', change:'-1.5%', up:false },
  { icon:'🔵', name:'Inmotion V12 HT', brand:'Inmotion', neuf:'2 199€', occasion:'1 650€', bas:'1 200€', change:'+5.1%', up:true },
  { icon:'🚲', name:'Specialized Turbo Vado 5.0', brand:'Specialized', neuf:'4 200€', occasion:'3 100€', bas:'2 400€', change:'+1.8%', up:true },
];

const RANKINGS_DATA = {
  fiabilite: [
    { icon:'🛴', name:'Ninebot Max G30', brand:'Minimotors', value:'9.4/10', bar:94 },
    { icon:'🚲', name:'Specialized Turbo Vado', brand:'Specialized', value:'9.2/10', bar:92 },
    { icon:'🛴', name:'Kaabo Wolf Warrior', brand:'Kaabo', value:'8.9/10', bar:89 },
    { icon:'🔵', name:'Inmotion V12', brand:'Inmotion', value:'8.7/10', bar:87 },
    { icon:'🛵', name:'Xiaomi Mi Scooter 4 Pro', brand:'Xiaomi', value:'8.5/10', bar:85 },
  ],
  ventes: [
    { icon:'🛴', name:'Ninebot Max G30', brand:'Segway-Ninebot', value:'4 210 ventes', bar:100 },
    { icon:'🛴', name:'Xiaomi Essential', brand:'Xiaomi', value:'3 820 ventes', bar:91 },
    { icon:'🛴', name:'Dualtron Thunder 2', brand:'Minimotors', value:'2 140 ventes', bar:51 },
    { icon:'🚲', name:'Orbea Gain M20i', brand:'Orbea', value:'1 870 ventes', bar:44 },
    { icon:'🛵', name:'Sunra Lika', brand:'Sunra', value:'1 420 ventes', bar:34 },
  ],
  rapport: [
    { icon:'🛴', name:'Xiaomi Essential 2', brand:'Xiaomi', value:'8.8/10', bar:88 },
    { icon:'🛴', name:'Ninebot E45', brand:'Segway-Ninebot', value:'8.5/10', bar:85 },
    { icon:'🚲', name:'Cube Reaction Pro 400', brand:'Cube', value:'8.3/10', bar:83 },
    { icon:'🔵', name:'Begode RS19', brand:'Begode', value:'8.1/10', bar:81 },
    { icon:'🛴', name:'Kaabo Mantis Pro', brand:'Kaabo', value:'7.9/10', bar:79 },
  ],
  autonomie: [
    { icon:'🛴', name:'Dualtron Eagle Pro', brand:'Minimotors', value:'120 km', bar:100 },
    { icon:'🚲', name:'Specialized Turbo Como 5.0', brand:'Specialized', value:'115 km', bar:96 },
    { icon:'🔵', name:'Inmotion V12 HT', brand:'Inmotion', value:'110 km', bar:92 },
    { icon:'🛴', name:'Kaabo Wolf King GTR', brand:'Kaabo', value:'95 km', bar:79 },
    { icon:'🚲', name:'Trek Allant+ 9.9', brand:'Trek', value:'90 km', bar:75 },
  ]
};

const CARNET_ENTRIES = {
  entretien: [
    { icon:'🔧', cls:'entry-maint', title:'Remplacement pneus avant/arrière', desc:'Pneus CST 10x2.5 — 4 200 km', date:'12/05/2024', cost:'68€' },
    { icon:'🛢️', cls:'entry-maint', title:'Graissage roulements + vérif moteur', desc:'Préventif — 3 500 km', date:'18/03/2024', cost:'0€' },
    { icon:'🔋', cls:'entry-maint', title:'Calibration BMS batterie', desc:'Cellules équilibrées — capacité: 92%', date:'05/01/2024', cost:'0€' },
    { icon:'🔩', cls:'entry-maint', title:'Serrage boulonnerie complète', desc:'Vérification tous les 1 000 km', date:'14/11/2023', cost:'0€' },
  ],
  reparations: [
    { icon:'⚡', cls:'entry-repair', title:'Remplacement contrôleur moteur droit', desc:'Panne capteur Hall — atelier certifié', date:'28/02/2024', cost:'180€' },
    { icon:'🔦', cls:'entry-repair', title:'Réparation éclairage avant', desc:'Câble rompu — soudure + protection', date:'15/10/2023', cost:'25€' },
  ],
  modifs: [
    { icon:'✨', cls:'entry-modif', title:'Installation poignées Odi Lock-On', desc:'Ergonomie améliorée — custom grip', date:'03/04/2024', cost:'42€' },
    { icon:'💡', cls:'entry-modif', title:'LEDs sous-platine RGB', desc:'Clignotants intégrés + ambiance', date:'20/12/2023', cost:'35€' },
    { icon:'🛡️', cls:'entry-modif', title:'Bumper aluminium custom', desc:'Protection deck CNC — anodisé noir', date:'02/09/2023', cost:'95€' },
  ],
  documents: [
    { icon:'📄', cls:'entry-km', title:'Facture d\'achat originale', desc:'Vendeur : ElectricStore Paris — 2022', date:'15/06/2022', cost:'2 799€' },
    { icon:'📋', cls:'entry-km', title:'Certificat de conformité UE', desc:'CE 2019/631 — valable EU', date:'15/06/2022', cost:'—' },
  ]
};

const LEADERBOARD = [
  { name:'ZenRider_42', xp:'47,200 XP', em:'🥇' },
  { name:'SpeedQueen_EU', xp:'42,800 XP', em:'🥈' },
  { name:'EuroRider99', xp:'38,150 XP', em:'🥉' },
  { name:'AlexRide_Paris', xp:'34,420 XP (Vous)', em:'4' },
  { name:'TurboTrottin', xp:'31,000 XP', em:'5' },
];

const AI_RESPONSES = {
  default: [
    { text:'Je peux analyser ça pour vous ! Avec votre budget et vos critères, voici ma recommandation principale :', product:{ icon:'🛴', name:'Dualtron Victor Lite', price:'1 290€', score:'93/100 — Rapport qualité/prix exceptionnel' } },
    { text:'Excellente question ! La réglementation française stipule que les EDPM (Engins de Déplacement Personnel Motorisés) sont limités à 25 km/h sur voie publique. La trottinette doit être équipée de feux avant/arrière, sonnette et frein. Aucun permis requis mais âge minimum 12 ans.' },
    { text:'D\'après notre base de données et 847 ventes similaires, la valeur de revente estimée de ce modèle est entre 1 650€ et 2 100€ selon l\'état. Le marché est actuellement favorable (+3.2% sur 30 jours). 📈' },
  ]
};

/* ============================================================
   RENDER FUNCTIONS
   ============================================================ */
function renderListings(filter = 'all') {
  const grid = document.getElementById('listingsGrid');
  const filtered = filter === 'all' ? LISTINGS : LISTINGS.filter(l => l.cat === filter);
  grid.innerHTML = filtered.map(l => `
    <div class="listing-card reveal" onclick="showToast('success','Annonce ouverte !')">
      <div class="listing-img" style="background:${l.color}">
        <div class="listing-img-inner">${l.emoji}</div>
        ${l.badge ? `<div class="listing-badge ${l.badge === 'Premium' ? 'premium' : l.badge === 'Nouveau' ? 'new' : ''}">${l.badge}</div>` : ''}
        <div class="listing-fav" onclick="event.stopPropagation();toggleFav(this)">🤍</div>
      </div>
      <div class="listing-body">
        <div class="listing-meta">
          <span class="listing-cat">${l.brand}</span>
          <span class="listing-loc">📍 ${l.loc}</span>
        </div>
        <div class="listing-name">${l.name}</div>
        <div class="listing-specs">
          ${l.km ? `<span class="spec-tag">📍 ${l.km}</span>` : ''}
          ${l.watt ? `<span class="spec-tag">⚡ ${l.watt}</span>` : ''}
        </div>
        <div class="listing-footer">
          <div class="listing-price">
            ${l.oldPrice ? `<small>${l.oldPrice}€</small>` : ''}
            ${l.price}€
          </div>
          <button class="btn-sm btn-gold-sm">Voir →</button>
        </div>
      </div>
      <div class="listing-seller">
        <div class="seller-avatar">${l.seller.substring(0,2)}</div>
        <div class="seller-info">
          <div class="seller-name">${l.seller}</div>
          <div class="seller-stars">${l.rating}</div>
        </div>
        <div class="verified-badge">✓</div>
      </div>
    </div>
  `).join('');
  observeReveal();
}

function renderFeed() {
  const feed = document.getElementById('socialFeed');
  feed.innerHTML = POSTS.map(p => `
    <div class="post-card reveal">
      <div class="post-header">
        <div class="post-avatar" style="background:linear-gradient(135deg,rgba(201,168,76,0.15),rgba(201,168,76,0.05))">${p.emoji}</div>
        <div class="post-meta">
          <div class="post-author">${p.author} <span style="font-size:0.72rem;color:var(--white-dim);font-weight:400">${p.handle}</span></div>
          <div class="post-time">${p.time}</div>
        </div>
        <div class="post-more">···</div>
      </div>
      <div class="post-media" style="background:${p.bg}"><span style="z-index:1">${p.media}</span></div>
      <div class="post-body">
        <div class="post-text">${p.text}</div>
        <div class="post-tags">${p.tags.map(t => `<span class="post-tag">${t}</span>`).join('')}</div>
      </div>
      <div class="post-actions">
        <button class="post-action" onclick="likePost(this)">❤️ ${p.likes}</button>
        <button class="post-action" onclick="showToast('success','Commentaire posté !')">💬 ${p.comments}</button>
        <button class="post-action" onclick="showToast('success','Partagé !')">↗️ ${p.shares}</button>
      </div>
    </div>
  `).join('');
  observeReveal();
}

function renderTrending() {
  const list = document.getElementById('trendingList');
  if (!list) return;
  list.innerHTML = TRENDING.map((t, i) => `
    <div class="trending-item">
      <span class="trend-num">${(i+1).toString().padStart(2,'0')}</span>
      <div class="trend-info"><div class="trend-tag">${t.tag}</div><div class="trend-count">${t.count}</div></div>
    </div>
  `).join('');
}

function renderMapPins() {
  const canvas = document.getElementById('mapCanvas');
  MAP_PINS.forEach(pin => {
    const el = document.createElement('div');
    el.className = `map-pin pin-${pin.type}`;
    el.style.left = `${pin.x}%`;
    el.style.top = `${pin.y}%`;
    el.innerHTML = `<div class="map-pin-inner"><span>${pin.emoji}</span></div><div class="map-pin-tooltip">${pin.label}</div>`;
    el.addEventListener('click', () => showToast('success', `${pin.label} sélectionné !`));
    canvas.appendChild(el);
  });
}

function renderMapPoints() {
  const list = document.getElementById('mapPointsList');
  list.innerHTML = MAP_POINTS.map(p => `
    <div class="map-point-item" onclick="showToast('success','${p.name} sélectionné sur la carte !')">
      <div class="map-point-icon">${p.icon}</div>
      <div class="map-point-info">
        <div class="map-point-name">${p.name}</div>
        <div class="map-point-loc">${p.loc}</div>
        <div class="map-point-rating">${p.rating}</div>
      </div>
    </div>
  `).join('');
}

function renderEvents() {
  const grid = document.getElementById('eventsGrid');
  grid.innerHTML = EVENTS.map(e => `
    <div class="event-card ${e.free ? '' : 'premium-event'} reveal">
      <div class="event-header">
        <div class="event-date-badge"><div class="day">${e.day}</div><div class="month">${e.month}</div></div>
        <div class="event-icon">${e.icon}</div>
        <div class="event-title">${e.title}</div>
        <div class="event-loc">📍 ${e.loc}</div>
      </div>
      <div class="event-body">
        <div class="event-stats">
          <div class="ev-stat"><div class="v">${e.dist}</div><div class="k">DISTANCE</div></div>
          <div class="ev-stat"><div class="v">Niv. ${e.level}/5</div><div class="k">NIVEAU</div></div>
          <div class="ev-stat"><div class="v">${e.count.split('/')[0]}<small>/${e.count.split('/')[1]}</small></div><div class="k">RIDERS</div></div>
        </div>
        <div class="event-level">${e.diff.map(d => `<span style="font-size:0.6rem">${d}</span>`).join('')}</div>
        <div class="event-participants">
          <div class="participants-avatars">${e.participants.map(a => `<div class="p-av" style="background:rgba(201,168,76,0.1)">${a}</div>`).join('')}</div>
          <span style="font-size:0.8rem;color:var(--white-dim)">${e.count}</span>
        </div>
      </div>
      <div class="event-footer">
        <div class="event-price">${e.free ? `<span class="free">Gratuit</span>` : `<span class="paid">${e.price}</span>`}</div>
        <button class="btn-sm btn-gold-sm" onclick="joinEvent(this)" data-en="Join" data-fr="Rejoindre">Rejoindre</button>
      </div>
    </div>
  `).join('');
  observeReveal();
}

function renderGuide() {
  const results = document.getElementById('guideResults');
  results.innerHTML = GUIDE_RESULTS.map(r => `
    <div class="guide-result-card ${r.recommended ? 'recommended' : ''} reveal" onclick="showToast('success','${r.name} — détails complets')">
      <div class="guide-result-icon">${r.icon}</div>
      <div class="guide-result-info">
        <div class="guide-result-brand">${r.brand}</div>
        <div class="guide-result-name">${r.name}</div>
        <div class="guide-result-specs">${r.specs.map(s => `<span class="spec-tag">${s}</span>`).join('')}</div>
        <div class="guide-result-price">${r.price}</div>
      </div>
      <div class="guide-score">
        <div class="score-circle"><div class="score-num">${r.score}</div><div class="score-label">SCORE</div></div>
        <button class="btn-sm btn-gold-sm" style="font-size:0.7rem" onclick="event.stopPropagation();showToast('success','Voir l\'annonce')">Voir</button>
      </div>
    </div>
  `).join('');
  observeReveal();
}

function renderCote() {
  const grid = document.getElementById('coteGrid');
  grid.innerHTML = COTE_DATA.map(c => `
    <div class="cote-card reveal">
      <div class="cote-card-header">
        <div class="cote-model">
          <div class="cote-icon">${c.icon}</div>
          <div><div class="cote-model-name">${c.name}</div><div class="cote-model-brand">${c.brand}</div></div>
        </div>
        <div class="cote-trend">
          <div class="cote-change ${c.up ? 'up' : 'down'}">${c.change}</div>
          <div style="font-size:0.65rem;color:var(--white-dim);font-family:var(--font-mono)">30 jours</div>
        </div>
      </div>
      <div class="cote-prices">
        <div class="cote-price-item"><div class="cote-price-label">NEUF</div><div class="cote-price-val neuf">${c.neuf}</div></div>
        <div class="cote-price-item"><div class="cote-price-label">OCCASION MOY.</div><div class="cote-price-val occasion">${c.occasion}</div></div>
        <div class="cote-price-item"><div class="cote-price-label">BAS MARCHÉ</div><div class="cote-price-val bas">${c.bas}</div></div>
      </div>
      <div class="cote-mini-chart">${renderMiniChart()}</div>
      <div class="cote-footer">
        <span>📊 Basé sur 847 ventes</span>
        <span>⏱️ Mis à jour il y a 2h</span>
      </div>
    </div>
  `).join('');
  observeReveal();
}

function renderMiniChart() {
  const points = Array.from({length:7}, () => 30 + Math.random()*30);
  const max = Math.max(...points), min = Math.min(...points);
  const normalize = v => 55 - ((v - min) / (max - min)) * 45;
  const pts = points.map((p,i) => `${i*(100/6)},${normalize(p)}`).join(' ');
  const areaEnd = `${6*(100/6)},60 0,60`;
  return `<svg viewBox="0 0 100 60" class="mini-chart-svg" preserveAspectRatio="none">
    <defs><linearGradient id="g${Math.random().toString(36).substr(2,5)}" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0%" stop-color="#C9A84C" stop-opacity="0.3"/>
      <stop offset="100%" stop-color="#C9A84C" stop-opacity="0"/>
    </linearGradient></defs>
    <polyline points="${pts}" fill="none" stroke="#C9A84C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
  </svg>`;
}

function renderRankings(type = 'fiabilite') {
  const grid = document.getElementById('rankingsGrid');
  const data = RANKINGS_DATA[type];
  const posClass = ['gold','silver','bronze','',''];
  grid.innerHTML = `
    <div class="ranking-list reveal">
      <div class="ranking-list-header">🏆 <span>${type === 'fiabilite' ? 'Plus fiables' : type === 'ventes' ? 'Plus vendus' : type === 'rapport' ? 'Meilleur rapport qualité/prix' : 'Meilleure autonomie'} — Europe</span></div>
      ${data.map((r,i) => `
        <div class="rank-item">
          <div class="rank-pos ${posClass[i]}">${i+1}</div>
          <div class="rank-icon">${r.icon}</div>
          <div class="rank-info"><div class="rank-name">${r.name}</div><div class="rank-brand">${r.brand}</div></div>
          <div class="rank-score">
            <div class="rank-value">${r.value}</div>
            <div class="rank-bar-wrap"><div class="rank-bar" style="width:0%" data-width="${r.bar}%"></div></div>
          </div>
        </div>
      `).join('')}
    </div>
    <div class="ranking-list reveal delay-2">
      <div class="ranking-list-header">📊 <span>Classement France</span></div>
      ${data.slice(0,3).map((r,i) => `
        <div class="rank-item">
          <div class="rank-pos ${posClass[i]}">${i+1}</div>
          <div class="rank-icon">${r.icon}</div>
          <div class="rank-info"><div class="rank-name">${r.name}</div><div class="rank-brand">${r.brand}</div></div>
          <div class="rank-score">
            <div class="rank-value">${r.value}</div>
            <div class="rank-bar-wrap"><div class="rank-bar" style="width:0%" data-width="${r.bar}%"></div></div>
          </div>
        </div>
      `).join('')}
      <div style="padding:14px 20px;text-align:center">
        <button class="btn-ghost" style="padding:8px 20px;font-size:0.78rem" onclick="showToast('success','Classement complet chargé !')">Voir tout le classement France</button>
      </div>
    </div>
  `;
  observeReveal();
  setTimeout(() => animateRankBars(), 400);
}

function renderCarnetEntries(type = 'entretien') {
  const entries = CARNET_ENTRIES[type] || [];
  const el = document.getElementById('carnetEntries');
  el.innerHTML = entries.map(e => `
    <div class="carnet-entry">
      <div class="entry-icon-wrap ${e.cls}">${e.icon}</div>
      <div class="entry-info">
        <div class="entry-title">${e.title}</div>
        <div class="entry-desc">${e.desc}</div>
      </div>
      <div class="entry-meta">
        <div class="entry-date">${e.date}</div>
        <div class="entry-cost">${e.cost}</div>
      </div>
    </div>
  `).join('') + `<div style="padding:14px 0;text-align:center">
    <button class="btn-ghost" style="padding:8px 20px;font-size:0.78rem" onclick="showToast('success','Entrée ajoutée !')">+ Ajouter une entrée</button>
  </div>`;
}

function renderLeaderboard() {
  const el = document.getElementById('leaderboard');
  if (!el) return;
  el.innerHTML = LEADERBOARD.map(r => `
    <div class="lb-row">
      <div class="lb-rank">${r.em}</div>
      <div class="lb-name">${r.name}</div>
      <div class="lb-xp">${r.xp}</div>
    </div>
  `).join('');
}

/* ============================================================
   INTERACTIONS
   ============================================================ */
function toggleFav(btn) {
  const isLiked = btn.textContent === '❤️';
  btn.textContent = isLiked ? '🤍' : '❤️';
  btn.style.background = isLiked ? 'rgba(10,15,30,0.7)' : 'rgba(239,68,68,0.8)';
  showToast(isLiked ? 'error' : 'success', isLiked ? 'Retiré des favoris' : '❤️ Ajouté aux favoris !');
}

function likePost(btn) {
  btn.classList.toggle('liked');
  const count = parseInt(btn.textContent.replace('❤️ ',''));
  btn.textContent = `❤️ ${btn.classList.contains('liked') ? count+1 : count-1}`;
}

function followUser(btn) {
  const isFollowing = btn.textContent === 'Suivi ✓' || btn.textContent === 'Following ✓';
  btn.textContent = isFollowing ? 'Suivre' : 'Suivi ✓';
  btn.style.background = isFollowing ? '' : 'var(--gold)';
  btn.style.color = isFollowing ? '' : 'var(--navy)';
  showToast('success', isFollowing ? 'Désabonné' : 'Vous suivez maintenant ce rider !');
}

function joinEvent(btn) {
  const isJoined = btn.dataset.joined;
  if (isJoined) { btn.textContent = currentLang === 'fr' ? 'Rejoindre' : 'Join'; btn.style.background=''; delete btn.dataset.joined; }
  else { btn.textContent = '✓ Inscrit'; btn.style.background='var(--accent-teal)'; btn.dataset.joined='1'; showToast('success','🏁 Inscrit ! Bon ride !'); }
}

function filterMap(el, type) {
  document.querySelectorAll('.map-type-item').forEach(i => i.classList.remove('active'));
  el.classList.add('active');
  showToast('success', `Filtre "${el.querySelector('.map-type-name').textContent}" appliqué`);
}

function updateRange(type, val) {
  if (type === 'budget') {
    document.getElementById('budgetVal').textContent = parseInt(val).toLocaleString('fr-FR') + '€';
    document.getElementById('budgetFill').style.width = ((val-200)/(5000-200)*100)+'%';
  } else if (type === 'dist') {
    document.getElementById('distVal').textContent = val + ' km';
    document.getElementById('distFill').style.width = ((val-5)/(80-5)*100)+'%';
  } else {
    document.getElementById('weightVal').textContent = val + ' kg';
    document.getElementById('weightFill').style.width = ((val-40)/(130-40)*100)+'%';
  }
}

function runGuide() {
  showToast('success', '🔍 Analyse IA en cours...');
  setTimeout(() => { renderGuide(); showToast('success', '✅ 4 modèles recommandés !'); }, 800);
}

function switchRankTab(btn, type) {
  document.querySelectorAll('.rank-tab').forEach(t => t.classList.remove('active'));
  btn.classList.add('active');
  renderRankings(type);
}

function switchCarnetTab(tab, type) {
  document.querySelectorAll('.carnet-tab').forEach(t => t.classList.remove('active'));
  tab.classList.add('active');
  renderCarnetEntries(type);
}

function selectVehicle(el, name) {
  document.querySelectorAll('.vehicle-card-select').forEach(v => v.classList.remove('active'));
  el.classList.add('active');
  document.getElementById('carnetVehicleName').textContent = name;
  const kms = {'Dualtron Thunder 2':'8 420', 'Ninebot Max G30':'3 150', 'Inmotion V12':'1 890'};
  document.getElementById('carnetKm').textContent = kms[name] || '—';
}

function loadMoreListings() {
  showToast('success', 'Chargement de nouvelles annonces...');
}

/* ============================================================
   AI CHAT
   ============================================================ */
let aiTyping = false;
function sendAIMessage(text) {
  if (aiTyping) return;
  const input = document.getElementById('aiInput');
  const msg = text || input.value.trim();
  if (!msg) return;
  input.value = '';

  const messages = document.getElementById('aiMessages');
  messages.innerHTML += `<div class="msg user"><div class="msg-avatar">👤</div><div class="msg-bubble">${msg}</div></div>`;
  messages.scrollTop = messages.scrollHeight;

  aiTyping = true;
  const typingEl = document.createElement('div');
  typingEl.className = 'msg bot';
  typingEl.innerHTML = `<div class="msg-avatar">⚡</div><div class="msg-bubble" style="display:flex;gap:6px;align-items:center"><span style="animation:pulse 1s infinite">●</span><span style="animation:pulse 1s infinite 0.2s">●</span><span style="animation:pulse 1s infinite 0.4s">●</span></div>`;
  messages.appendChild(typingEl);
  messages.scrollTop = messages.scrollHeight;

  setTimeout(() => {
    typingEl.remove();
    const resp = AI_RESPONSES.default[Math.floor(Math.random() * AI_RESPONSES.default.length)];
    let html = `<div class="msg bot"><div class="msg-avatar">⚡</div><div class="msg-bubble">${resp.text}`;
    if (resp.product) {
      html += `<div class="msg-product"><div class="msg-product-icon">${resp.product.icon}</div><div class="msg-product-info"><div class="msg-product-name">${resp.product.name}</div><div class="msg-product-price">${resp.product.price}</div><div class="msg-product-score">${resp.product.score}</div></div></div>`;
    }
    html += `</div></div>`;
    messages.innerHTML += html;
    messages.scrollTop = messages.scrollHeight;
    aiTyping = false;
  }, 1400);
}

function aiInputKey(e) {
  if (e.key === 'Enter' && !e.shiftKey) { e.preventDefault(); sendAIMessage(); }
}

/* ============================================================
   MODALS
   ============================================================ */
const MODAL_CONTENT = {
  login: () => `
    <div class="modal-title" data-fr="Bon retour !" data-en="Welcome back!">Bon retour !</div>
    <div class="modal-sub" data-fr="Connectez-vous à votre compte Volterra" data-en="Sign in to your Volterra account">Connectez-vous à votre compte Volterra</div>
    <div class="modal-input-group">
      <input class="modal-input" type="email" placeholder="Email" />
      <input class="modal-input" type="password" placeholder="Mot de passe" />
      <button class="btn-primary modal-cta" onclick="showToast('success','Connexion réussie !')">Se connecter</button>
    </div>
    <div class="modal-divider"><span>ou</span></div>
    <div class="social-login">
      <button class="social-login-btn" onclick="showToast('success','Connexion Google !')">🔵 Google</button>
      <button class="social-login-btn" onclick="showToast('success','Connexion Apple !')">🍎 Apple</button>
    </div>
    <div class="modal-footer">Pas de compte ? <a href="#" onclick="openModal('signup')">S'inscrire</a></div>
  `,
  signup: () => `
    <div class="modal-title">Rejoindre Volterra</div>
    <div class="modal-sub">La référence européenne de la mobilité électrique</div>
    <div class="modal-input-group">
      <input class="modal-input" type="text" placeholder="Nom d'utilisateur" />
      <input class="modal-input" type="email" placeholder="Email" />
      <input class="modal-input" type="password" placeholder="Mot de passe" />
      <button class="btn-primary modal-cta" onclick="showToast('success','🎉 Bienvenue sur Volterra !')">Créer mon compte</button>
    </div>
    <div class="modal-divider"><span>ou</span></div>
    <div class="social-login">
      <button class="social-login-btn" onclick="showToast('success','Inscription Google !')">🔵 Google</button>
      <button class="social-login-btn" onclick="showToast('success','Inscription Apple !')">🍎 Apple</button>
    </div>
    <div class="modal-footer">Déjà membre ? <a href="#" onclick="openModal('login')">Se connecter</a></div>
  `,
  sell: () => `
    <div class="modal-title">Déposer une annonce</div>
    <div class="modal-sub">L'IA Volterra va générer votre annonce automatiquement</div>
    <div class="modal-input-group">
      <input class="modal-input" type="text" placeholder="Modèle (ex: Dualtron Thunder 2)" />
      <input class="modal-input" type="number" placeholder="Prix demandé (€)" />
      <input class="modal-input" type="text" placeholder="Kilométrage" />
      <input class="modal-input" type="text" placeholder="Ville" />
      <button class="btn-primary modal-cta" onclick="showToast('success','✨ Annonce générée par IA !')">🤖 Générer avec l'IA</button>
    </div>
  `,
  pro: () => `
    <div class="modal-title">Compte Professionnel</div>
    <div class="modal-sub">Pour les magasins, réparateurs, marques et revendeurs</div>
    <div class="modal-input-group">
      <input class="modal-input" type="text" placeholder="Nom de l'entreprise" />
      <input class="modal-input" type="text" placeholder="SIRET / TVA" />
      <input class="modal-input" type="email" placeholder="Email professionnel" />
      <button class="btn-primary modal-cta" onclick="showToast('success','Demande Pro envoyée ! Notre équipe vous contactera.')">Demander un compte Pro</button>
    </div>
  `
};

function openModal(type) {
  const overlay = document.getElementById('modalOverlay');
  const content = document.getElementById('modalContent');
  content.innerHTML = MODAL_CONTENT[type]();
  overlay.classList.add('open');
  applyLang(currentLang);
}

function closeModal() { document.getElementById('modalOverlay').classList.remove('open'); }

/* ============================================================
   TOAST
   ============================================================ */
function showToast(type, msg) {
  const container = document.getElementById('toastContainer');
  const toast = document.createElement('div');
  toast.className = `toast ${type}`;
  toast.innerHTML = `<span class="toast-icon">${type === 'success' ? '✅' : '❌'}</span><span>${msg}</span>`;
  container.appendChild(toast);
  requestAnimationFrame(() => { requestAnimationFrame(() => toast.classList.add('show')); });
  setTimeout(() => { toast.classList.remove('show'); setTimeout(() => toast.remove(), 300); }, 3000);
}

/* ============================================================
   LANGUAGE
   ============================================================ */
let currentLang = 'fr';
function applyLang(lang) {
  currentLang = lang;
  document.querySelectorAll('[data-fr]').forEach(el => {
    const txt = el.getAttribute(`data-${lang}`);
    if (txt) { if (el.innerHTML.includes('<') && !el.classList.contains('hero-eyebrow')) el.innerHTML = txt; else el.textContent = txt; }
  });
  document.querySelectorAll('[data-placeholder-fr]').forEach(el => { el.placeholder = el.getAttribute(`data-placeholder-${lang}`) || el.placeholder; });
  document.querySelectorAll('.lang-btn').forEach(b => b.classList.toggle('active', b.dataset.lang === lang));
}

document.querySelectorAll('.lang-btn').forEach(btn => {
  btn.addEventListener('click', () => applyLang(btn.dataset.lang));
});

/* ============================================================
   NAVBAR SCROLL + TABS
   ============================================================ */
window.addEventListener('scroll', () => {
  const navbar = document.getElementById('navbar');
  if (window.scrollY > 40) navbar.classList.add('scrolled');
  else navbar.classList.remove('scrolled');

  const sections = ['marketplace','riders','map-section','sorties','guide','ai-section','cote','rankings','carnet','gamification','pricing'];
  const tabs = document.querySelectorAll('.tab-btn');
  sections.forEach((id, i) => {
    const el = document.getElementById(id);
    if (el) {
      const rect = el.getBoundingClientRect();
      if (rect.top < 200 && rect.bottom > 200) { tabs.forEach(t => t.classList.remove('active')); if(tabs[i]) tabs[i].classList.add('active'); }
    }
  });
});

function scrollToSection(id) {
  const el = document.getElementById(id);
  if (el) el.scrollIntoView({ behavior:'smooth', block:'start' });
}

/* ============================================================
   REVEAL ON SCROLL
   ============================================================ */
function observeReveal() {
  const obs = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); } });
  }, { threshold: 0.1, rootMargin:'0px 0px -40px 0px' });
  document.querySelectorAll('.reveal, .reveal-left, .reveal-right').forEach(el => { if(!el.classList.contains('visible')) obs.observe(el); });
}

function animateRankBars() {
  document.querySelectorAll('.rank-bar[data-width]').forEach(bar => {
    setTimeout(() => { bar.style.width = bar.dataset.width; }, 100);
  });
}

/* ============================================================
   COUNTER ANIMATION
   ============================================================ */
function animateCounter(el, target) {
  let current = 0;
  const duration = 1800;
  const step = target / (duration / 16);
  const timer = setInterval(() => {
    current = Math.min(current + step, target);
    el.textContent = Math.floor(current).toLocaleString('fr-FR') + (target < 100 ? '' : '');
    if (current >= target) clearInterval(timer);
  }, 16);
}

const counterObs = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      const target = parseInt(e.target.dataset.count);
      animateCounter(e.target, target);
      counterObs.unobserve(e.target);
    }
  });
}, { threshold: 0.5 });
document.querySelectorAll('[data-count]').forEach(el => counterObs.observe(el));

/* ============================================================
   XP BAR ANIMATION
   ============================================================ */
const xpObs = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      const bar = document.getElementById('xpBar');
      if (bar) setTimeout(() => { bar.style.width = '68.4%'; }, 200);
      xpObs.unobserve(e.target);
    }
  });
}, { threshold: 0.3 });
const gamifSection = document.getElementById('gamification');
if (gamifSection) xpObs.observe(gamifSection);

/* ============================================================
   FILTER CHIPS
   ============================================================ */
document.querySelectorAll('.filter-chip').forEach(chip => {
  chip.addEventListener('click', function() {
    document.querySelectorAll('.filter-chip').forEach(c => c.classList.remove('active'));
    this.classList.add('active');
    renderListings(this.dataset.filter);
  });
});

/* ============================================================
   SEARCH
   ============================================================ */
document.addEventListener('DOMContentLoaded', () => {
  const search = document.getElementById('listingSearch');
  if (search) {
    search.addEventListener('input', function() {
      const q = this.value.toLowerCase();
      const grid = document.getElementById('listingsGrid');
      const cards = grid.querySelectorAll('.listing-card');
      cards.forEach(card => {
        const name = card.querySelector('.listing-name')?.textContent.toLowerCase() || '';
        card.style.display = name.includes(q) || q === '' ? '' : 'none';
      });
    });
  }
});

/* ============================================================
   INIT
   ============================================================ */
renderListings();
renderFeed();
renderTrending();
renderMapPins();
renderMapPoints();
renderEvents();
renderGuide();
renderCote();
renderRankings();
renderCarnetEntries();
renderLeaderboard();
observeReveal();

// Animate rank bars after initial render
setTimeout(animateRankBars, 500);
</script>
</body>
</html> 
