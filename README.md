[index.html](https://github.com/user-attachments/files/29322467/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Grandpa Adventure — The Big One</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --rust: #8B3A0F;
  --rust-lt: #F5ECD7;
  --rust-mid: #C4622D;
  --sand: #FAF6EE;
  --sand-mid: #EFE8D8;
  --ink: #1C1410;
  --ink-mid: #4A3728;
  --muted: #8A7060;
  --sage: #4A6741;
  --sage-lt: #E8F0E5;
  --gold: #8B6914;
  --gold-lt: #FFF4D6;
  --slate: #2C4A6B;
  --slate-lt: #E4EDF5;
  --success: #2E6B3A;
  --success-lt: #E4F2E7;
  --danger: #8B1A1A;
  --danger-lt: #FAE8E8;
  --info: #1A5280;
  --info-lt: #E4F0FA;
  --border: rgba(139,58,15,0.15);
  --border-strong: rgba(139,58,15,0.3);
  --radius-sm: 6px;
  --radius-md: 10px;
  --radius-lg: 14px;
  --shadow: 0 1px 3px rgba(28,20,16,0.08);
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: 'Inter', sans-serif;
  background: var(--sand);
  color: var(--ink);
  min-height: 100vh;
  font-size: 14px;
  line-height: 1.6;
}

/* ── Header ── */
.site-header {
  background: var(--rust);
  padding: 2.5rem 1.5rem 2rem;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.site-header::before {
  content: '';
  position: absolute;
  inset: 0;
  background: repeating-linear-gradient(
    -45deg,
    transparent,
    transparent 20px,
    rgba(255,255,255,0.03) 20px,
    rgba(255,255,255,0.03) 21px
  );
}
.site-header h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(1.8rem, 5vw, 2.8rem);
  font-weight: 600;
  color: #fff;
  letter-spacing: -0.01em;
  line-height: 1.2;
  position: relative;
}
.site-header .tagline {
  font-size: 0.85rem;
  color: rgba(255,255,255,0.75);
  margin-top: 0.5rem;
  letter-spacing: 0.04em;
  text-transform: uppercase;
  position: relative;
}
.route-banner {
  background: rgba(0,0,0,0.2);
  margin: 1.25rem -1.5rem -2rem;
  padding: 0.75rem 1.5rem;
  font-size: 0.78rem;
  color: rgba(255,255,255,0.85);
  letter-spacing: 0.02em;
  line-height: 1.7;
  position: relative;
}

/* ── Layout ── */
.main {
  max-width: 860px;
  margin: 0 auto;
  padding: 2rem 1rem 4rem;
}

/* ── Stats ── */
.stats {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  margin-bottom: 1.5rem;
}
.stat {
  background: #fff;
  border: 0.5px solid var(--border);
  border-radius: var(--radius-md);
  padding: 0.75rem 1rem;
  box-shadow: var(--shadow);
}
.stat-label { font-size: 0.7rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.06em; margin-bottom: 2px; }
.stat-val { font-size: 1.4rem; font-weight: 600; color: var(--rust); }

/* ── Filters ── */
.filter-section { margin-bottom: 1.25rem; }
.filter-section-label { font-size: 0.7rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.06em; margin-bottom: 0.5rem; }
.filters { display: flex; gap: 6px; flex-wrap: wrap; }
.fb {
  font-size: 0.72rem;
  padding: 4px 10px;
  border-radius: 20px;
  border: 1px solid var(--border-strong);
  background: transparent;
  cursor: pointer;
  color: var(--ink-mid);
  font-family: 'Inter', sans-serif;
  transition: all 0.15s;
  white-space: nowrap;
}
.fb:hover { background: var(--rust-lt); border-color: var(--rust); color: var(--rust); }
.fb.on { background: var(--rust); border-color: var(--rust); color: #fff; }

/* ── Action buttons ── */
.actions { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 2rem; }
.btn {
  font-family: 'Inter', sans-serif;
  font-size: 0.78rem;
  font-weight: 500;
  padding: 8px 16px;
  border-radius: var(--radius-sm);
  border: 1px solid var(--border-strong);
  background: #fff;
  color: var(--ink-mid);
  cursor: pointer;
  transition: all 0.15s;
  box-shadow: var(--shadow);
}
.btn:hover { background: var(--rust-lt); border-color: var(--rust); color: var(--rust); }
.btn.primary { background: var(--rust); border-color: var(--rust); color: #fff; }
.btn.primary:hover { background: var(--rust-mid); }

/* ── Legs ── */
.leg {
  background: #fff;
  border: 0.5px solid var(--border);
  border-radius: var(--radius-lg);
  margin-bottom: 1rem;
  box-shadow: var(--shadow);
  overflow: hidden;
}
.leg-header {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 14px 16px;
  cursor: pointer;
  user-select: none;
  transition: background 0.12s;
  background: var(--rust-lt);
  border-bottom: 0.5px solid var(--border);
}
.leg-header:hover { background: var(--sand-mid); }
.leg-icon { font-size: 1.25rem; width: 28px; text-align: center; flex-shrink: 0; }
.leg-text { flex: 1; min-width: 0; }
.leg-title { font-family: 'Playfair Display', serif; font-size: 1rem; font-weight: 600; color: var(--rust); }
.leg-sub { font-size: 0.72rem; color: var(--muted); margin-top: 1px; }
.leg-badge {
  font-size: 0.68rem;
  background: var(--rust);
  color: #fff;
  border-radius: 20px;
  padding: 2px 9px;
  white-space: nowrap;
  flex-shrink: 0;
  font-weight: 500;
}
.leg-badge.empty { background: var(--sand-mid); color: var(--muted); }
.leg-chevron { font-size: 1rem; color: var(--muted); transition: transform 0.2s; flex-shrink: 0; }
.leg-chevron.open { transform: rotate(180deg); }
.leg-body { padding: 0 16px 16px; }

/* ── Section labels ── */
.slbl {
  font-size: 0.65rem;
  font-weight: 600;
  letter-spacing: 0.08em;
  color: var(--muted);
  text-transform: uppercase;
  margin: 16px 0 8px;
  display: flex;
  align-items: center;
  gap: 8px;
}
.slbl::after { content: ''; flex: 1; height: 0.5px; background: var(--border); }

/* ── Stop cards ── */
.sg { display: flex; flex-direction: column; gap: 6px; }
.sc {
  border: 0.5px solid var(--border);
  border-radius: var(--radius-md);
  padding: 10px 12px;
  display: flex;
  align-items: flex-start;
  gap: 10px;
  cursor: pointer;
  transition: border-color 0.12s, background 0.12s;
  background: #fff;
}
.sc:hover { border-color: var(--rust-mid); background: #fff9f5; }
.sc.ck { border-color: var(--sage); background: var(--sage-lt); }
.sc.sq { border-style: dashed; }
.sc.sq.ck { border-style: dashed; }

/* Checkbox */
.chk {
  width: 18px; height: 18px;
  border-radius: 4px;
  border: 1.5px solid var(--border-strong);
  flex-shrink: 0;
  margin-top: 1px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.12s;
  background: #fff;
  color: transparent;
  font-size: 11px;
}
.sc.ck .chk { background: var(--sage); border-color: var(--sage); color: #fff; }

/* Stop content */
.si { flex: 1; min-width: 0; }
.stop-top { display: flex; align-items: flex-start; gap: 6px; flex-wrap: wrap; margin-bottom: 4px; }
.sn { font-size: 0.82rem; font-weight: 600; color: var(--ink); line-height: 1.3; }
.tgs { display: flex; gap: 4px; flex-wrap: wrap; margin-bottom: 5px; }
.tg {
  font-size: 0.65rem;
  padding: 2px 7px;
  border-radius: 10px;
  font-weight: 600;
  letter-spacing: 0.02em;
  white-space: nowrap;
}
.tg-star    { background: var(--gold-lt);    color: var(--gold); }
.tg-rock    { background: var(--info-lt);    color: var(--info); }
.tg-cave    { background: #F0EBE3;  color: #5A4A3A; }
.tg-ghost   { background: #EEEEEE;  color: #555; }
.tg-history { background: #EEEAE4;  color: #5A4A30; }
.tg-view    { background: var(--slate-lt);   color: var(--slate); }
.tg-dark    { background: #1C1C2E;  color: #C8B4F8; }
.tg-weird   { background: #F3EAFF;  color: #6A3A8A; }
.tg-train   { background: var(--success-lt); color: var(--success); }
.tg-ranger  { background: var(--success-lt); color: var(--success); }
.tg-nature  { background: var(--sage-lt);    color: var(--sage); }
.tg-art     { background: #F0E8F8;  color: #5A2A8A; }
.tg-alien   { background: #E3FFEA;  color: #0A6A20; }
.tg-hot     { background: var(--danger-lt);  color: var(--danger); }
.tg-swim    { background: #DCF0FF;  color: #0A5080; }
.tg-eat     { background: var(--gold-lt);    color: var(--gold); }
.tg-coffee  { background: #F5EDE0;  color: #6B3D00; }
.tg-bakery  { background: #FFF0E4;  color: #A04010; }
.tg-diner   { background: var(--gold-lt);    color: var(--gold); }
.tg-drive   { background: var(--slate-lt);   color: var(--slate); }

.sdesc { font-size: 0.78rem; color: var(--ink-mid); line-height: 1.55; }
.sdrv { font-size: 0.7rem; color: var(--muted); margin-top: 5px; display: flex; align-items: center; gap: 4px; }
.sdrv::before { content: '→'; font-size: 0.7rem; color: var(--rust-mid); }

/* ── Route preview ── */
.rp {
  background: #fff;
  border: 0.5px solid var(--border);
  border-radius: var(--radius-md);
  padding: 1rem 1.25rem;
  margin-bottom: 1.5rem;
  box-shadow: var(--shadow);
  display: none;
}
.rp-label { font-size: 0.68rem; text-transform: uppercase; letter-spacing: 0.08em; color: var(--muted); margin-bottom: 8px; font-weight: 600; }
.rp-stops { font-size: 0.8rem; line-height: 1.9; color: var(--muted); }
.rp-stops .act { color: var(--rust); font-weight: 500; }

/* ── Print button ── */
.print-btn {
  position: fixed;
  bottom: 1.5rem;
  right: 1.5rem;
  background: var(--rust);
  color: #fff;
  border: none;
  border-radius: 28px;
  padding: 12px 22px;
  font-family: 'Inter', sans-serif;
  font-size: 0.82rem;
  font-weight: 600;
  cursor: pointer;
  box-shadow: 0 4px 16px rgba(139,58,15,0.35);
  transition: all 0.15s;
  z-index: 100;
}
.print-btn:hover { background: var(--rust-mid); transform: translateY(-1px); box-shadow: 0 6px 20px rgba(139,58,15,0.4); }

/* ── Legend ── */
.legend {
  background: #fff;
  border: 0.5px solid var(--border);
  border-radius: var(--radius-md);
  padding: 1rem 1.25rem;
  margin-bottom: 1.5rem;
  box-shadow: var(--shadow);
}
.legend-title { font-size: 0.68rem; text-transform: uppercase; letter-spacing: 0.08em; color: var(--muted); margin-bottom: 10px; font-weight: 600; }
.legend-grid { display: flex; flex-wrap: wrap; gap: 6px; }

/* ── Notes ── */
.note-toggle {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  margin-top: 6px;
  font-size: 0.7rem;
  color: var(--muted);
  cursor: pointer;
  user-select: none;
  background: none;
  border: none;
  padding: 0;
  font-family: 'Inter', sans-serif;
  transition: color 0.12s;
}
.note-toggle:hover { color: var(--rust); }
.note-toggle.has-note { color: var(--rust-mid); font-weight: 600; }
.note-toggle .nt-icon { font-size: 0.75rem; transition: transform 0.15s; }
.note-toggle.open .nt-icon { transform: rotate(90deg); }
.note-area {
  display: none;
  margin-top: 6px;
}
.note-area.open { display: block; }
.note-ta {
  width: 100%;
  min-height: 60px;
  border: 1px solid var(--border-strong);
  border-radius: var(--radius-sm);
  padding: 8px 10px;
  font-family: 'Inter', sans-serif;
  font-size: 0.75rem;
  color: var(--ink);
  background: var(--gold-lt);
  resize: vertical;
  line-height: 1.5;
  transition: border-color 0.12s;
}
.note-ta:focus { outline: none; border-color: var(--rust); background: #fffef8; }
.note-ta::placeholder { color: var(--muted); }

/* ── Leg notes ── */
.leg-note-bar {
  display: flex;
  align-items: flex-start;
  gap: 8px;
  padding: 10px 14px;
  background: var(--gold-lt);
  border-bottom: 0.5px solid var(--border);
  cursor: pointer;
}
.leg-note-bar:hover { background: #fff8e6; }
.leg-note-label {
  font-size: 0.68rem;
  font-weight: 600;
  color: var(--gold);
  text-transform: uppercase;
  letter-spacing: 0.06em;
  white-space: nowrap;
  margin-top: 1px;
}
.leg-note-preview {
  font-size: 0.72rem;
  color: var(--ink-mid);
  flex: 1;
  min-width: 0;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  font-style: italic;
}
.leg-note-area { display: none; }
.leg-note-area.open {
  display: block;
  padding: 0 14px 12px;
  background: var(--gold-lt);
  border-bottom: 0.5px solid var(--border);
}
.leg-note-ta {
  width: 100%;
  min-height: 52px;
  border: 1px solid var(--border-strong);
  border-radius: var(--radius-sm);
  padding: 8px 10px;
  font-family: 'Inter', sans-serif;
  font-size: 0.75rem;
  color: var(--ink);
  background: #fffef8;
  resize: vertical;
  line-height: 1.5;
}
.leg-note-ta:focus { outline: none; border-color: var(--rust); }
.leg-note-ta::placeholder { color: var(--muted); }

/* ── Tab navigation ── */
.tab-nav {
  display: flex;
  gap: 0;
  margin-bottom: 1.5rem;
  border: 0.5px solid var(--border-strong);
  border-radius: var(--radius-md);
  overflow: hidden;
  background: #fff;
  box-shadow: var(--shadow);
}
.tab-btn {
  flex: 1;
  padding: 11px 16px;
  font-family: 'Inter', sans-serif;
  font-size: 0.82rem;
  font-weight: 500;
  border: none;
  background: transparent;
  color: var(--muted);
  cursor: pointer;
  transition: all 0.15s;
  border-right: 0.5px solid var(--border);
  line-height: 1.3;
}
.tab-btn:last-child { border-right: none; }
.tab-btn:hover { background: var(--rust-lt); color: var(--rust); }
.tab-btn.active { background: var(--rust); color: #fff; font-weight: 600; }
.tab-panel { display: none; }
.tab-panel.active { display: block; }

/* ── Calendar ── */
.cal-intro {
  background: #fff;
  border: 0.5px solid var(--border);
  border-radius: var(--radius-md);
  padding: 1rem 1.25rem;
  margin-bottom: 1.25rem;
  box-shadow: var(--shadow);
  font-size: 0.82rem;
  color: var(--ink-mid);
  line-height: 1.6;
}
.cal-intro strong { color: var(--rust); }
.cal-day {
  background: #fff;
  border: 0.5px solid var(--border);
  border-radius: var(--radius-lg);
  margin-bottom: 1rem;
  box-shadow: var(--shadow);
  overflow: hidden;
}
.cal-day-header {
  display: flex;
  align-items: stretch;
  cursor: pointer;
  user-select: none;
}
.cal-day-header:hover .cal-day-title-block { background: var(--sand-mid); }
.cal-date-block {
  min-width: 72px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 12px 10px;
  flex-shrink: 0;
}
.cal-month { font-size: 0.62rem; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; opacity: 0.85; }
.cal-day-num { font-family: 'Playfair Display', serif; font-size: 1.8rem; font-weight: 600; line-height: 1; }
.cal-dow { font-size: 0.65rem; font-weight: 600; letter-spacing: 0.06em; text-transform: uppercase; opacity: 0.75; margin-top: 2px; }
.cal-day-title-block {
  flex: 1;
  padding: 12px 14px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
  transition: background 0.12s;
  border-left: 0.5px solid var(--border);
}
.cal-day-title { font-family: 'Playfair Display', serif; font-size: 1rem; font-weight: 600; color: var(--ink); }
.cal-day-sub { font-size: 0.72rem; color: var(--muted); margin-top: 2px; }
.cal-chevron { font-size: 1rem; color: var(--muted); transition: transform 0.2s; flex-shrink: 0; }
.cal-chevron.open { transform: rotate(180deg); }

/* Day type color coding */
.cal-day.drive .cal-date-block { background: var(--slate); color: #fff; }
.cal-day.drive .cal-day-header:hover .cal-day-title-block { background: var(--slate-lt); }
.cal-day.redwood .cal-date-block { background: var(--sage); color: #fff; }
.cal-day.redwood .cal-day-header:hover .cal-day-title-block { background: var(--sage-lt); }
.cal-day.tahoe .cal-date-block { background: var(--info); color: #fff; }
.cal-day.tahoe .cal-day-header:hover .cal-day-title-block { background: var(--info-lt); }
.cal-day.home .cal-date-block { background: var(--rust); color: #fff; }
.cal-day.home .cal-day-header:hover .cal-day-title-block { background: var(--rust-lt); }
.cal-day.slc .cal-date-block { background: var(--gold); color: #fff; }
.cal-day.slc .cal-day-header:hover .cal-day-title-block { background: var(--gold-lt); }

/* Day body */
.cal-day-body { display: none; border-top: 0.5px solid var(--border); }
.cal-day-body.open { display: block; }

/* Sections within a day */
.cal-section {
  padding: 12px 16px;
  border-bottom: 0.5px solid var(--border);
}
.cal-section:last-child { border-bottom: none; }
.cal-section-label {
  display: flex;
  align-items: center;
  gap: 7px;
  font-size: 0.68rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin-bottom: 10px;
}
.cal-section-label .sl-icon { font-size: 0.9rem; }

/* Section types */
.cal-section.drive-section .cal-section-label { color: var(--slate); }
.cal-section.drive-section { background: var(--slate-lt); }
.cal-section.daytime .cal-section-label { color: var(--sage); }
.cal-section.daytime { background: var(--sage-lt); }
.cal-section.evening .cal-section-label { color: var(--rust); }
.cal-section.evening { background: var(--rust-lt); }
.cal-section.notes-section .cal-section-label { color: var(--gold); }
.cal-section.notes-section { background: var(--gold-lt); }
.cal-section.logistics .cal-section-label { color: var(--slate); }
.cal-section.logistics { background: #F8F8F8; }

/* Activity items */
.cal-items { display: flex; flex-direction: column; gap: 7px; }
.cal-item {
  background: rgba(255,255,255,0.7);
  border-radius: var(--radius-sm);
  padding: 8px 11px;
  border-left: 3px solid transparent;
}
.cal-item.must { border-left-color: var(--gold); }
.cal-item.opt { border-left-color: var(--border-strong); opacity: 0.85; }
.cal-item-name {
  font-size: 0.8rem;
  font-weight: 600;
  color: var(--ink);
  margin-bottom: 2px;
  display: flex;
  align-items: center;
  gap: 5px;
}
.cal-item-name .opt-badge {
  font-size: 0.62rem;
  background: var(--sand-mid);
  color: var(--muted);
  border-radius: 6px;
  padding: 1px 5px;
  font-weight: 500;
}
.cal-item-desc { font-size: 0.74rem; color: var(--ink-mid); line-height: 1.5; }
.cal-item-note { font-size: 0.7rem; color: var(--muted); margin-top: 3px; font-style: italic; }

/* Cal day note */
.cal-note-bar {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 16px;
  background: var(--gold-lt);
  border-top: 0.5px solid var(--border);
  cursor: pointer;
  font-size: 0.72rem;
}
.cal-note-bar:hover { background: #fff8e0; }
.cal-note-label { font-weight: 600; color: var(--gold); font-size: 0.68rem; text-transform: uppercase; letter-spacing: 0.06em; white-space: nowrap; }
.cal-note-preview { color: var(--ink-mid); font-style: italic; flex: 1; min-width: 0; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.cal-note-area { display: none; padding: 0 16px 12px; background: var(--gold-lt); }
.cal-note-area.open { display: block; }
.cal-note-ta {
  width: 100%;
  min-height: 52px;
  border: 1px solid var(--border-strong);
  border-radius: var(--radius-sm);
  padding: 8px 10px;
  font-family: 'Inter', sans-serif;
  font-size: 0.75rem;
  color: var(--ink);
  background: #fffef8;
  resize: vertical;
  line-height: 1.5;
}
.cal-note-ta:focus { outline: none; border-color: var(--rust); }
.cal-note-ta::placeholder { color: var(--muted); }

/* Drive log */
.drive-log {
  font-size: 0.75rem;
  color: var(--ink-mid);
  line-height: 1.7;
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.drive-seg {
  display: flex;
  align-items: baseline;
  gap: 8px;
}
.drive-seg-route { font-weight: 600; color: var(--slate); }
.drive-seg-detail { color: var(--muted); }
.drive-total {
  margin-top: 6px;
  padding-top: 6px;
  border-top: 0.5px solid var(--border);
  font-size: 0.72rem;
  color: var(--muted);
  font-style: italic;
}

/* ── Print styles ── */
@media print {
  body { background: #fff; font-size: 11px; }
  .site-header { background: #8B3A0F !important; -webkit-print-color-adjust: exact; print-color-adjust: exact; padding: 1.5rem; }
  .print-btn, .actions, .filters, .filter-section, .fb { display: none !important; }
  .main { padding: 1rem; }
  .leg { break-inside: avoid; box-shadow: none; border: 1px solid #ddd; }
  .sc { break-inside: avoid; }
  .sc:not(.ck) { display: none !important; }
  .leg-body[style*="display: none"] { display: block !important; }
  .leg-header { background: #F5ECD7 !important; -webkit-print-color-adjust: exact; print-color-adjust: exact; }
  .leg-chevron { display: none; }
  .stats { display: none; }
  .legend { display: none; }
  .rp { display: none !important; }
  .slbl { display: flex !important; }
  .sg .sc:not(.ck) { display: none; }
  .tab-nav { display: none !important; }
  .tab-panel { display: block !important; }
  .cal-day-body { display: block !important; }
  .cal-note-area { display: block !important; }
  .cal-note-ta { background: #fffef0 !important; border: 0.5px solid #ccc !important; min-height: unset !important; resize: none; }
  .cal-item.opt { opacity: 1; }
  .note-toggle { display: none !important; }
  .note-area { display: block !important; }
  .note-ta { background: #fffef0 !important; border: 0.5px solid #ccc !important; min-height: unset !important; resize: none; }
  .leg-note-bar { cursor: default; }
  .leg-note-area { display: block !important; }
  .leg-note-ta { background: #fffef0 !important; border: 0.5px solid #ccc !important; min-height: unset !important; resize: none; }
}

@media (max-width: 600px) {
  .stats { grid-template-columns: repeat(2, 1fr); }
  .site-header h1 { font-size: 1.6rem; }
}
</style>
</head>
<body>

<header class="site-header">
  <h1>Grandpa Adventure — The Big One</h1>
  <p class="tagline">Denver · Southwest · Big Bend · Four Corners · Utah · Home</p>
  <div class="route-banner">
    Denver &rarr; Raton &rarr; Roswell &rarr; Carlsbad &rarr; White Sands &rarr; Marfa &rarr; Big Bend &rarr; Tucson &rarr; Coronado Trail &rarr; Canyon de Chelly &rarr; Ship Rock &rarr; Monument Valley &rarr; Grand Canyon &rarr; Zion &rarr; Bryce &rarr; Capitol Reef &rarr; Nine Mile Canyon &rarr; Helper &rarr; Salt Lake City
    <br><span style="color:rgba(255,255,255,0.7);font-size:0.72rem;">Grandpa flies home from SLC &nbsp;&middot;&nbsp; Kiddo &amp; you continue west &rarr; Nevada &rarr; Sequoia &rarr; Redwoods &rarr; Coast &rarr; Tahoe</span>
    <br><span style="color:rgba(255,255,255,0.45);font-size:0.68rem;">Solid cards = main stops &nbsp;&middot;&nbsp; Dashed = side quests &nbsp;&middot;&nbsp; Check what sounds good &nbsp;&middot;&nbsp; Print shows only checked stops</span>
  </div>
</header>

<main class="main">

  <div class="tab-nav">
    <button class="tab-btn active" onclick="showTab('planner',this)">🗺️ Stop Planner<br><span style="font-size:0.68rem;font-weight:400;opacity:0.8">Check stops, build your route</span></button>
    <button class="tab-btn" onclick="showTab('grandpa',this)">👴 Grandpa Leg<br><span style="font-size:0.68rem;font-weight:400;opacity:0.8">July 3–11 day-by-day</span></button>
    <button class="tab-btn" onclick="showTab('calendar',this)">🌲 California Leg<br><span style="font-size:0.68rem;font-weight:400;opacity:0.8">July 11–21 day-by-day</span></button>
  </div>

  <!-- ══ TAB 1: STOP PLANNER ══ -->
  <div class="tab-panel active" id="tab-planner">

  <div class="stats">
    <div class="stat"><div class="stat-label">Stops checked</div><div class="stat-val" id="s-ck">0</div></div>
    <div class="stat"><div class="stat-label">Must-dos in</div><div class="stat-val" id="s-st">0 / 0</div></div>
    <div class="stat"><div class="stat-label">Food finds in</div><div class="stat-val" id="s-fd">0</div></div>
    <div class="stat"><div class="stat-label">Total stops</div><div class="stat-val" id="s-tt">0</div></div>
  </div>

  <div class="legend">
    <div class="legend-title">Stop types</div>
    <div class="legend-grid" id="legend-grid"></div>
  </div>

  <div class="filter-section">
    <div class="filter-section-label">Filter by type</div>
    <div class="filters" id="frow"></div>
  </div>

  <div class="actions">
    <button class="btn" onclick="chkAll()">Check all</button>
    <button class="btn" onclick="clrAll()">Clear all</button>
    <button class="btn" onclick="chkStars()">Must-dos only</button>
    <button class="btn" onclick="chkFood()">Food &amp; coffee only</button>
    <button class="btn" onclick="chkHot()">Hot springs &amp; swims</button>
    <button class="btn" onclick="chkDark()">Dark sky sites</button>
    <button class="btn primary" onclick="window.print()">&#x2399; Print my trip</button>
  </div>

  <div class="rp" id="rp">
    <div class="rp-label">Your selected route</div>
    <div class="rp-stops" id="rp-stops"></div>
  </div>

  <div id="legs"></div>

  </div><!-- end tab-planner -->

  <!-- ══ TAB 2: GRANDPA LEG ══ -->
  <div class="tab-panel" id="tab-grandpa">
    <div class="cal-intro">
      <strong>July 3–11, 2025</strong> — The Grandpa chapter. Flies into Denver July 3rd, 2 rest days, hits the road July 5th.
      6 nights: Denver → Durango → Carlsbad → White Sands → Grand Canyon South Rim → Monument Valley → SLC.
      Grandpa flies home from Salt Lake City mid-morning July 11th.
      <br><br>
      <strong style="color:var(--danger)">⚠️ Book now:</strong> El Tovar / Bright Angel Lodge South Rim (xanterra.com) · The View Hotel Monument Valley (theviewhotel.com) · Both sell out in July.
    </div>
    <div id="grandpa-days"></div>
    <div style="text-align:center;padding:1rem 0;font-size:0.75rem;color:var(--muted);">
      ↑ Click any day header to expand · Notes auto-save to your browser
    </div>
  </div><!-- end tab-grandpa -->

  <!-- ══ TAB 3: CALIFORNIA CALENDAR ══ -->
  <div class="tab-panel" id="tab-calendar">
    <div class="cal-intro">
      <strong>July 11–21, 2025</strong> — The California chapter. Grandpa flies home from SLC, partner joins, you head west.
      Partner works Mon–Wed; daytime is you &amp; the kiddo. Evenings and Thu–Sun are full family.
      Base: Jedediah Smith Redwoods / Crescent City area. Then coastal drive to Tahoe Thursday, home Sunday.
      Each day is collapsible — click the header to expand. Gold border = must-do. Grey border = optional.
      Notes save automatically.
    </div>
    <div id="cal-days"></div>
    <div style="text-align:center;padding:1rem 0;font-size:0.75rem;color:var(--muted);">
      ↑ Click any day header to expand · Notes auto-save to your browser
    </div>
  </div><!-- end tab-calendar -->

</main>

<button class="print-btn" onclick="window.print()">&#x2399; Print my trip</button>

<script>
const FTYPES = [
  {k:'all',l:'All stops'},
  {k:'star',l:'⭐ Must-do'},
  {k:'eat',l:'🍔 Diner / local eats'},
  {k:'bakery',l:'🥐 Bakery / pastry'},
  {k:'coffee',l:'☕ Coffee'},
  {k:'hot',l:'♨️ Hot springs'},
  {k:'swim',l:'🏊 Swimming hole'},
  {k:'dark',l:'🌌 Dark sky'},
  {k:'view',l:'🏔️ Scenic pull-off'},
  {k:'rock',l:'🪨 Rockhound'},
  {k:'cave',l:'🔦 Cave'},
  {k:'ghost',l:'👻 Ghost town'},
  {k:'train',l:'🚂 Train ride'},
  {k:'art',l:'🎨 Art / museum'},
  {k:'alien',l:'🛸 Alien / UFO'},
  {k:'weird',l:'🤪 Weird Americana'},
  {k:'ranger',l:'🌲 Ranger program'},
];

const TL = {
  star:'must-do', rock:'rockhound', cave:'cave', ghost:'ghost town',
  train:'train', art:'art/museum', alien:'alien/UFO',
  hot:'hot spring', swim:'swim hole', dark:'dark sky',
  view:'scenic pull-off', eat:'local eats', coffee:'coffee',
  bakery:'bakery', diner:'diner', weird:'weird americana',
  ranger:'ranger program', nature:'nature', history:'history', drive:'scenic drive'
};

const DATA = [
  {id:'co', ico:'🗺️', t:'Colorado — heading south', s:'Denver to the New Mexico border', stops:[
    {id:'c1',n:'Worth the Drive Bakery — Monte Vista CO',tg:['bakery','star'],sq:true,d:'Amish-run bakery on a country road in the San Luis Valley — famous for cinnamon rolls that are almost impossible to finish alone. 4.9 stars. Open Tue–Sat 8am. The name is not ironic.',dr:'Monte Vista CO — 35 min off I-25 via US-160, right on the way south'},
    {id:'c2',n:'Rosemount Museum — Pueblo CO',tg:['art','history'],sq:true,d:'Stunning 37-room Victorian mansion built in 1893. A small museum that genuinely needs the patronage. Completely unexpected in Pueblo and completely worth it.',dr:'~1.5 hrs from Denver on I-25'},
    {id:'c3',n:'A.R. Mitchell Museum — Trinidad CO',tg:['art','history'],sq:true,d:'Largest collection of Harvey Dunn and Harold von Schmidt Western art originals anywhere. Beautiful brick Santa Fe Trail town. The Corazon de Trinidad is a National Historic District.',dr:'~3 hrs from Denver on I-25'},
    {id:'c4',n:'Raton Pass & St. James Hotel — Cimarron NM',tg:['star','history','view'],sq:false,d:'The Santa Fe Trail came right through Raton Pass. The St. James Hotel in Cimarron has bullet holes in the ceiling from when it was the most dangerous saloon in the territory. Kit Carson, Jesse James, and Buffalo Bill all passed through.',dr:'~4 hrs from Denver — Cimarron is 30 min east of Raton on NM-21'},
  ]},
  {id:'nm', ico:'🛸', t:'New Mexico — Roswell to White Sands', s:'Aliens, the best burger in America, and white gypsum desert', stops:[
    {id:'n1',n:'Roswell — International UFO Museum',tg:['star','alien','art'],sq:false,d:'Wonderfully, sincerely bizarre — crash debris replicas, alien autopsy dioramas, declassified government documents. The town has fully committed and the result is kitsch at its most earnest. Grandpa will be magnificently grumpy or absolutely delighted. Either outcome is correct.',dr:'~2 hrs south of Raton on US-285'},
    {id:'n2',n:'Bottomless Lakes State Park',tg:['swim','nature'],sq:true,d:'Seven sinkhole lakes with vivid blue-green water near Roswell. Swimming, kayaking, easy half-day. Good post-alien decompression.',dr:'15 min east of Roswell'},
    {id:'n3',n:'The Owl Bar & Cafe — San Antonio NM',tg:['star','eat','diner'],sq:false,d:'Open since 1945. The green chile cheeseburger against which all others are judged. Manhattan Project scientists ate here between shifts at Trinity Site. The 25-foot mahogany bar is from Conrad Hilton\'s first hotel. On average summer days they serve 600–700 burgers. Order the green chile cheese fries too.',dr:'San Antonio NM on US-380 — right on the route between Socorro and Truth or Consequences'},
    {id:'n4',n:'Buckhorn Tavern — San Antonio NM',tg:['eat','diner'],sq:true,d:'The Owl Bar\'s friendly rival across the street — also famous for green chile cheeseburgers. Same tiny town. This may be the highest concentration of legendary burgers per capita anywhere in the world.',dr:'Literally across the street from the Owl Bar'},
    {id:'n5',n:'Carlsbad Caverns NP — the Big Room',tg:['star','cave'],sq:false,d:'14 acres of cathedral space 750 feet underground. The Big Room, the Bottomless Pit, cave pearls, formations the size of houses. Walk in through the Natural Entrance — a mile-long descent through the cave mouth — or take the elevator down.',dr:'~1.5 hrs SE of Roswell — allow at least 3 hours'},
    {id:'n6',n:'Carlsbad Caverns — bat flight at sunset',tg:['star','ranger'],sq:false,d:'Hundreds of thousands of Mexican free-tailed bats spiral out of the cave mouth at dusk in a column that can last 20 minutes. Free, no reservation needed — just show up at the outdoor amphitheater before sunset. Rangers narrate. Nothing else like this anywhere.',dr:'Same site as Carlsbad Caverns — check nps.gov/cave for the exact announced time for your date'},
    {id:'n7',n:'White Sands NP',tg:['star','view','dark'],sq:false,d:'Pure white gypsum dunes stretching to the horizon — NASA tests rovers here because it resembles another planet. Arrive late afternoon and stay for sunset. The light turns every dune pink and gold. The gift shop rents sleds. Stunning dark sky after hours.',dr:'~1.5 hrs west of Carlsbad — overnight Alamogordo or Las Cruces'},
    {id:'n8',n:'White Sands — sled the dunes',tg:['star'],sq:false,d:'Rent sleds at the visitor center gift shop. Kids and grandpas will be launching themselves down dunes for an hour. This is not optional. This is the whole thing.',dr:'Inside White Sands NP — sleds $25 deposit, returnable'},
    {id:'n9',n:'Truth or Consequences — hot springs + rockhound',tg:['hot','rock'],sq:true,d:'Natural hot springs on the Rio Grande in the town that renamed itself in 1950 to win a radio contest — and kept it. Soak at one of several bathhouses, then walk the Caballo Mountain washes for free BLM agate, jasper, and druzy quartz.',dr:'~1.5 hrs north of White Sands on I-25'},
    {id:'n10',n:'Three Rivers Petroglyph Site',tg:['history','view'],sq:true,d:'Over 21,000 petroglyphs on a ridge north of Alamogordo — one of the largest petroglyph sites in the Southwest, Jornada Mogollon culture 900–1400 AD. Almost nobody goes. Free BLM. Easy walking.',dr:'~50 min north of Alamogordo on US-54'},
  ]},
  {id:'tx', ico:'🔥', t:'Trans-Pecos Texas — Marfa & Big Bend', s:'Desert art colony, unexplained lights, and the most remote national park', stops:[
    {id:'t1',n:'Frama Coffee & Pastry — Marfa TX',tg:['star','coffee','bakery'],sq:false,d:'One of the best espresso programs in the Trans-Pecos — serious, intentional coffee in a seriously remote place. Pastries rotate daily and are genuinely excellent. The kind of place you don\'t expect to find here and don\'t want to leave.',dr:'Downtown Marfa'},
    {id:'t2',n:'Food Shark — Marfa TX',tg:['star','eat'],sq:false,d:'Legendary Marfa lunch truck serving Mediterranean-inspired food in the Chihuahuan Desert. The Marfalafel is famous. An absurdly good food program for a town of 1,700.',dr:'Downtown Marfa — weekday lunch, check current hours'},
    {id:'t3',n:'Chinati Foundation',tg:['star','art'],sq:false,d:'Donald Judd moved here in the 1970s and created one of the most significant permanent art installations on Earth — 100 large aluminum boxes in 15 former artillery sheds, positioned to interact with the desert light all day long. Also Dan Flavin neon light installations. One of the most important art sites in America, and it\'s in a town of 1,700.',dr:'In Marfa — tours Wed–Sun, book at chinati.org'},
    {id:'t4',n:'Marfa Lights viewing area',tg:['alien','weird','view'],sq:false,d:'Unexplained lights appearing on the horizon southeast of town most nights. The official viewing pullout is 9 miles east on US-90. Nobody knows what they are. Atmospheric refraction? Alien craft? Worth sitting out for an hour after dark with snacks.',dr:'9 miles east of Marfa on US-90 — free, always open'},
    {id:'t5',n:'Prada Marfa',tg:['art','weird'],sq:true,d:'A permanent fake Prada storefront in the middle of the desert, stocked with real Prada goods that are never for sale. Elmgreen & Dragset, 2005. Absurd and brilliant. The kiddo will have opinions.',dr:'37 miles NW of Marfa on US-90'},
    {id:'t6',n:'Davis Mountains Scenic Loop & McDonald Observatory',tg:['drive','view','dark'],sq:true,d:'Texas\'s most scenic mountain drive — TX-118 through Fort Davis and McDonald Observatory at 6,791 feet. The observatory has public star parties. Beautiful high desert with unexpected greenery.',dr:'TX-118 from Marfa — makes a good loop before heading south to Big Bend'},
    {id:'t7',n:'Big Bend — Santa Elena Canyon',tg:['star','nature'],sq:false,d:'The Rio Grande cutting through 1,500-foot limestone walls. The trail is 1.7 miles round trip and is one of the great short hikes in any national park. The canyon is so narrow it blocks midday sun. You can see Mexico from inside the canyon. Wade across the river in places.',dr:'~70 miles south of Marfa inside Big Bend NP'},
    {id:'t8',n:'Big Bend — Chisos Basin Lodge',tg:['star','nature'],sq:false,d:'Mountains inside the desert park — the only hotel inside the park. High elevation means cooler temperatures than the desert floor. The Basin Loop trail has remarkable views in every direction.',dr:'Inside Big Bend NP — book early at recreation.gov'},
    {id:'t9',n:'Big Bend — Rio Grande Hot Springs',tg:['hot'],sq:true,d:'A 105°F natural hot spring right on the Rio Grande with Mexico on the opposite bank. Ruins of a 1920s resort and bathhouse are right there. Soak in the rock pool and look across the river.',dr:'Inside Big Bend NP — dirt road, high clearance helpful'},
    {id:'t10',n:'Big Bend — rowboat to Mexico (Boquillas)',tg:['weird','history'],sq:true,d:'A man rows you across the Rio Grande for a couple dollars to the tiny village of Boquillas del Carmen. Get a cold drink, buy a handmade wire sculpture from a local artist, be in Mexico for an hour. Fully legal official border crossing.',dr:'Inside Big Bend NP — Boquillas Canyon overlook road'},
  ]},
  {id:'az', ico:'🎨', t:'Arizona — Tucson & the Coronado Trail', s:'Italian gelato in the desert, world-class coffee, fire agate, and mountain switchbacks', stops:[
    {id:'a1',n:'Viro\'s Real Italian Bakery — Tucson',tg:['star','bakery'],sq:false,d:'Open since 1986, bringing authentic Sicilian pastry traditions to the Sonoran Desert. The dessert case has been described by multiple reviewers as "the eighth wonder of the world." Homemade gelato. Lobster tails, cannoli, pistachio cookies, fresh pasta. Owner Vito Croce has been on Tucson\'s east side for over 20 years. A complete and total surprise.',dr:'Tucson east side — call ahead for hours, limited seating'},
    {id:'a2',n:'Barrio Bread — Tucson',tg:['star','bakery'],sq:true,d:'James Beard Award for Outstanding Baker 2022. Named best bakery in Arizona for 2025/2026. Owner Don Guerra uses local heritage grain. Baguettes, focaccia, Cubano rolls, Old World rye, Einkorn loaves. Open Tue–Sat 9am–1pm or until sold out.',dr:'18 S. Eastbourne Ave., Tucson — get there early, it sells out'},
    {id:'a3',n:'Presta Coffee Roasters — Tucson',tg:['star','coffee'],sq:false,d:'Named one of the World\'s 100 Best Coffee Shops in 2025. Three Tucson locations — roastery at 2502 N. 1st Ave. and the Mercado San Agustin courtyard location are both excellent. For the coffee snob in the group, this is the destination stop.',dr:'Tucson — roastery at 2502 N. 1st Ave. or Mercado San Agustin courtyard'},
    {id:'a4',n:'Maynard Dixon Museum — Tucson',tg:['star','art'],sq:false,d:'The only museum in the world solely dedicated to Dixon\'s life and work. Just expanded to 3,000 sq ft. His actual easel, walking cane, original oils, drawings, letters, and poetry. A recreation of his San Francisco studio. The documentary on-site is essential — watch it first. Tue–Sat 10am–5pm.',dr:'6866 E. Sunrise Dr., Suite 150, Tucson — (520) 722-7798'},
    {id:'a5',n:'Mission San Xavier del Bac',tg:['star','history'],sq:false,d:'The White Dove of the Desert — arguably the finest Spanish colonial mission in North America, still an active O\'odham parish. Built 1783–1797. The white-plastered baroque interior is extraordinary. The hilltop view of the Sonoran Desert from the chapel courtyard is beautiful.',dr:'15 min south of downtown Tucson on San Xavier Rd'},
    {id:'a6',n:'Bisbee — Queen Mine underground tour',tg:['star','ghost','cave'],sq:false,d:'Old copper mining city built into the Mule Mountains canyon walls. The Queen Mine tour goes underground by mine cart — hard hat, headlamp, complete experience. The town itself is wonderfully strange: Victorian buildings on stairway streets, artists, great food. One of Arizona\'s finest ghost towns.',dr:'~1.5 hrs SE of Tucson — book at queenminetour.com'},
    {id:'a7',n:'Tombstone — OK Corral & Boot Hill',tg:['ghost','history'],sq:true,d:'Yes, it\'s touristy. It\'s also genuinely historic. The OK Corral, Bird Cage Theatre, and Boot Hill Graveyard take a few good hours. The Courthouse State Historic Park is the most substantive stop.',dr:'~1 hr SE of Tucson on AZ-80'},
    {id:'a8',n:'Coronado Trail — US-191 north',tg:['star','drive','view'],sq:false,d:'One of the great unsung scenic drives in America — 123 miles of switchbacks through the Apache-Sitgreaves National Forest, climbing to nearly 9,000 feet before descending to the desert. Mountain meadows, canyon overlooks, Apache country, almost zero traffic. Named for the conquistador who passed through in 1540. Fill the tank in Clifton before you go up.',dr:'From Clifton/Safford — allow 3–4 hrs for the road itself, more for stops'},
    {id:'a9',n:'Clifton AZ — jail carved in the cliff face',tg:['ghost','history'],sq:false,d:'Genuine old copper-mining town in a canyon. The old jail was carved directly into the cliff face above the river. The Morenci mine above town is one of the largest open-pit copper mines on Earth — visible from road overlooks. Good lunch stop.',dr:'South end of the Coronado Trail'},
    {id:'a10',n:'Black Hills Rockhound Area — fire agate',tg:['rock','star'],sq:false,d:'Free BLM fire agate site near Safford, right off Hwy 191 on the Coronado Trail route. Fire agate only occurs in Arizona, southern California, and Mexico. No permit needed. Dig within 2 feet of the surface. The nodules look like dull brown grapes — spray with water to test for the iridescent fire inside. Early morning only in June.',dr:'~20 miles NE of Safford off Hwy 191 near milepost 141'},
  ]},
  {id:'sw', ico:'🏰', t:'Four Corners — Ancient World', s:'Canyon de Chelly, Ship Rock, Monument Valley, the great ancestral homeland', stops:[
    {id:'s1',n:'Canyon de Chelly — rim drive',tg:['star','history','view'],sq:false,d:'Continuously inhabited for nearly 5,000 years and still home to Navajo families today. The White House Ruins trail descends 600 feet to the canyon floor below a cliff dwelling tucked into the rock. The rim drive has 12 overlooks, each with a distinct view. Spider Rock — two sandstone spires rising 800 feet from the canyon floor — is the most dramatic.',dr:'~2 hrs from Safford — visitor center in Chinle AZ'},
    {id:'s2',n:'Canyon de Chelly — Navajo guide to canyon floor',tg:['star','ranger'],sq:true,d:'The canyon floor requires a Navajo guide — worth every penny. The petroglyphs invisible from the rim, the full scale of the walls from below, the living canyon with farming families still working it. Book in advance through the visitor center.',dr:'Contact Canyon de Chelly visitor center or authorized Navajo tour operators'},
    {id:'s3',n:'Hubbell Trading Post — Ganado AZ',tg:['history'],sq:false,d:'Oldest operating trading post on the Navajo Nation, established 1878. Still selling rugs, jewelry, crafts. The Hubbell family home is open for tours. A National Historic Site that genuinely feels like time stopped.',dr:'15 min from Canyon de Chelly on AZ-264'},
    {id:'s4',n:'Ship Rock — Tsé Bit\'a\'í',tg:['star','view','nature'],sq:false,d:'A volcanic neck rising 1,583 feet from absolutely flat desert floor — the hardened magma plug left after a volcano eroded away over 30 million years. Sacred to the Navajo. Drive dirt roads right to the base. The volcanic dikes radiating outward are as dramatic as the spire itself. Nothing else on Earth looks like this.',dr:'Near Shiprock NM — just off US-491, ~1.5 hrs north of Canyon de Chelly'},
    {id:'s5',n:'Monument Valley — The View Hotel',tg:['star','view'],sq:false,d:'Designed so most rooms face the Mittens and Merrick Butte directly — you wake up and the spires are just there. Sunrise and sunset from this hotel are among the great travel experiences of the American West. On the Navajo Nation.',dr:'Book immediately once you have dates — sells out in summer. Views are worth the extra cost.'},
    {id:'s6',n:'Monument Valley — Navajo jeep tour',tg:['star','ranger'],sq:false,d:'The valley floor requires a Navajo guide. Ancient ruins, the Wave formation, the Ear of the Wind — none of it visible from the road. Two to three hour tours available. The kiddo will never forget this.',dr:'Book at The View Hotel front desk or in advance through Navajo-owned tour operators'},
    {id:'s7',n:'Hovenweep NM — canyon rim towers',tg:['history','star'],sq:true,d:'Ancestral Puebloan towers and stone structures on canyon rims circa 1200 AD. Almost no visitors. The Little Ruin Canyon loop visits six tower complexes in 2 miles. The towers align to solstice sunrise and sunset. Haunting and beautiful.',dr:'~1.5 hrs east of Monument Valley — nps.gov/hove'},
    {id:'s8',n:'Natural Bridges NM — dark sky',tg:['dark','star','history'],sq:true,d:'Three massive natural stone bridges with ancestral Puebloan ruins beneath two of them. The first International Dark Sky Park in the world. Ranger star programs. The night sky here is extraordinary.',dr:'~1.5 hrs north of Monument Valley on UT-95'},
  ]},
  {id:'gc', ico:'🌊', t:'Grand Canyon & Page', s:'The big one, slot canyons, and the great bend in the river', stops:[
    {id:'g1',n:'Grand Canyon — Desert View Watchtower',tg:['star','history','view'],sq:false,d:'Enter from the east via Desert View — far less congested than the main village. Mary Colter\'s 1932 Watchtower is a masterpiece of Southwest architecture, built to echo ancestral Puebloan designs. Views stretch across the canyon and the Painted Desert beyond.',dr:'~2.5 hrs from Monument Valley via US-160 west and US-89 north'},
    {id:'g2',n:'Grand Canyon — South Rim',tg:['star','view'],sq:false,d:'Mather Point, Yavapai Point, Bright Angel. Free shuttle buses on the west end — take the first bus of the day. Hermit\'s Rest at the end of the line is another Mary Colter building. The Colorado River is 4,500 feet below you. Let that sink in.',dr:'Inside Grand Canyon NP — get on shuttles early, all summer crowds'},
    {id:'g3',n:'Grand Canyon Railway — Williams to the Rim',tg:['train','star'],sq:true,d:'Vintage steam or diesel train from Williams to the South Rim — 65 miles each way, cowboy entertainment on board, dramatic canyon arrival. One of the great American train rides. Grandpa will love this enormously.',dr:'Departs Williams depot ~9:30am daily — book at thetrain.com, sells out'},
    {id:'g4',n:'Vermilion Cliffs — condors and color',tg:['view','nature'],sq:true,d:'3,000-foot red and orange cliffs along US-89A between Page and Kanab. California condors were reintroduced here — often visible from pull-offs along the road. Stunning cliff scenery all along this stretch.',dr:'US-89A between Page and Kanab'},
    {id:'g5',n:'Antelope Canyon — Upper or Lower',tg:['star','nature'],sq:false,d:'The most photographed slot canyon in the world — narrow sandstone walls sculpted by flash floods into flowing curves, with shafts of light dropping from above. Guided Navajo tours only. Upper Antelope is easier to walk; Lower Antelope is more dramatic.',dr:'Page AZ — book 2-3 weeks ahead in summer, both fill up. Upper: tsebiighani.navajonationparks.org'},
    {id:'g6',n:'Horseshoe Bend',tg:['star','view'],sq:false,d:'The Colorado River making a 270-degree horseshoe bend 1,000 feet below — one of the most dramatic viewpoints in the Southwest. 1.5-mile round-trip walk from the highway. Afternoon light turns the canyon walls orange.',dr:'5 min south of Page AZ on US-89 — parking fee only'},
  ]},
  {id:'ut', ico:'🌲', t:'Utah Canyon Country — Zion to Capitol Reef', s:'Hoodoos, slot canyons, pioneer orchards, the goblins, and a Beard-nominated farm', stops:[
    {id:'u1',n:'Kanab UT — Little Hollywood',tg:['history'],sq:true,d:'Hundreds of Westerns and TV shows filmed here — Gunsmoke, Planet of the Apes, The Lone Ranger. The Western Legends Museum is fun. Excellent overnight base between Grand Canyon and Zion.',dr:'~1 hr north of Page on US-89'},
    {id:'u2',n:'Coral Pink Sand Dunes SP',tg:['nature','view'],sq:true,d:'Pink sand dunes in a bowl of Navajo sandstone — completely different color palette from White Sands. ATV rentals available. Good 45-minute stop.',dr:'Off US-89 between Kanab and Zion — 9 miles on Hancock Road'},
    {id:'u3',n:'Zion NP — main canyon',tg:['star','nature'],sq:false,d:'The Virgin River has carved a cathedral canyon through Navajo sandstone with walls rising 2,000 feet. Mandatory free shuttle in summer — get on the first bus of the day. The scale inside the canyon is staggering.',dr:'~45 min from Kanab via US-89 and UT-9'},
    {id:'u4',n:'Zion Narrows — wade bottom up',tg:['star','swim'],sq:false,d:'Wade upstream through the Virgin River between slot canyon walls just 20 feet apart. No permit needed for the bottom-up approach. Rent canyoneering waterproof boots in Springdale. The kiddo will love every single step of this.',dr:'Inside Zion — end of the Riverside Walk paved trail'},
    {id:'u5',n:'Maynard Dixon Home & Studio — Mount Carmel UT',tg:['star','art'],sq:false,d:'Dixon\'s actual home and working studio on UT-9 — directly on the road between Zion\'s east entrance and US-89, zero detour required. Run by the Thunderbird Foundation. His painting cabin on the high bluff, the hillside where his ashes are scattered. This is the place behind the Tucson collection.',dr:'On UT-9 between Zion east entrance and US-89 — call ahead: (435) 648-2288'},
    {id:'u6',n:'Bryce Canyon NP — the hoodoo amphitheater',tg:['star','view','nature'],sq:false,d:'Not a canyon — an amphitheater of thousands of orange and red limestone hoodoos eroding from the Paunsaugunt Plateau. More vivid color than anywhere else in Utah. 8,000–9,000 ft elevation means noticeably cooler than the desert below. Sunrise Point is extraordinary.',dr:'~1.5 hrs from Zion via US-89'},
    {id:'u7',n:'Bryce Canyon — dark sky stargazing',tg:['dark','star'],sq:true,d:'One of the darkest skies in the lower 48 — on a moonless night the Milky Way casts visible shadows. The annual Astronomy Festival draws professional astronomers. Rangers run evening star programs all summer long.',dr:'Inside Bryce Canyon NP — evening programs at visitor center amphitheater'},
    {id:'u8',n:'UT-12 Scenic Byway',tg:['star','drive','view'],sq:false,d:'Arguably the most beautiful highway in Utah — 124 miles from Bryce through Red Canyon, past Anasazi State Park, over the Hogback (road runs along an actual ridge spine with 1,000-ft drop-offs on both sides), through Grand Staircase-Escalante. Do not rush this road. It is the destination.',dr:'Bryce Canyon to Torrey — allow 3–4 hours, stop at every overlook'},
    {id:'u9',n:"Hell's Backbone Grill — Boulder UT",tg:['eat','star'],sq:false,d:'The most remote fine-dining restaurant in the continental United States, in a town of 240 people. James Beard Outstanding Restaurant nominee. Farm-to-table Four Corners cuisine from their own six-acre organic farm out back. Founded by former Grand Canyon river guides who taught themselves to cook. Reserve ahead — packed every night.',dr:'Boulder UT on UT-12 — directly on the scenic byway. hellsbackbonegrill.com'},
    {id:'u10',n:'Capitol Reef NP + Fruita orchards',tg:['star','history','eat'],sq:false,d:'The Waterpocket Fold — a 100-mile wrinkle in the Earth\'s crust. The pioneer settlement of Fruita: working orchards (cherries and early apricots in June — pay by the pound on the honor system at the trees), a one-room schoolhouse, a historic farmhouse, and petroglyphs on nearly every canyon wall. Far fewer visitors than Zion or Bryce.',dr:'~2 hrs from Bryce on UT-12 — Torrey UT has excellent lodging and restaurants nearby'},
    {id:'u11',n:'Goblin Valley SP',tg:['star','weird','nature'],sq:false,d:'A bowl of thousands of mushroom-shaped Entrada sandstone hoodoos you can scramble among freely with no trails. Kids go completely feral with delight. A Star Wars filming location that looks exactly like it. Grandpa and the kiddo will be equally enchanted by this place.',dr:'~40 min from Capitol Reef on UT-24 near Hanksville'},
  ]},
  {id:'slc', ico:'🏔️', t:'North to Salt Lake City — Grandpa\'s send-off', s:'Helper, Nine Mile Canyon, the Great Salt Lake, and SLC farewell', stops:[
    {id:'slc1',n:'Nine Mile Canyon — longest art gallery in the world',tg:['star','history','view'],sq:false,d:'A 40-mile canyon east of Price with thousands of Fremont culture petroglyphs and pictographs on the walls — more rock art per mile than anywhere in North America. Panels of bighorn sheep, hunting scenes, and geometric figures stretching for miles. Almost nobody comes here. Drive slowly and pull over constantly.',dr:'East of Price UT on Nine Mile Canyon Rd — dirt road, passenger car ok in dry weather. Allow 3-4 hrs'},
    {id:'slc2',n:'Helper UT — Western Mining & Railroad Museum',tg:['ghost','history','art'],sq:false,d:'A beautifully preserved coal mining and railroad town in a canyon on US-6. The Western Mining & Railroad Museum is genuinely excellent and almost nobody stops here — mining equipment, company town history, labor history. The main street still has its original 1920s storefronts. One of Utah\'s most underrated towns.',dr:'On US-6 between Price and I-15 — right on the route north to SLC'},
    {id:'slc3',n:'Price UT — College of Eastern Utah Prehistoric Museum',tg:['history','art'],sq:true,d:'One of the best dinosaur and prehistoric museums in Utah — full-scale allosaurus and camptosaurus skeletons, extensive Fremont culture artifacts, and the context for all the petroglyphs you\'ve been seeing. Free admission. Completely overlooked.',dr:'Downtown Price UT — free, open daily'},
    {id:'slc4',n:'Gilgal Sculpture Garden — Salt Lake City',tg:['weird','art','star'],sq:false,d:'A completely bizarre free outdoor sculpture garden in a SLC neighborhood — a Mormon bishop spent 18 years carving giant sphinx heads onto boulders in a private garden, with Joseph Smith\'s face on the sphinx body. Sphinxes, totems, biblical scenes, all carved in the 1940s-50s. Wonderfully strange and completely free. The kiddo will have a lot of questions.',dr:'749 E. 500 S., Salt Lake City — free, open dawn to dusk'},
    {id:'slc5',n:'Great Salt Lake — float in it',tg:['star','swim','weird'],sq:false,d:'The lake is so salty you float effortlessly — it\'s genuinely hard to sink. Antelope Island State Park is the best access point, with bison roaming the island and the full scale of the lake visible. The water smells intensely of brine shrimp which is part of the experience. Grandpa\'s last big adventure before the airport.',dr:'Antelope Island State Park — 45 min from SLC downtown, $15/vehicle'},
    {id:'slc6',n:'Temple Square & Natural History Museum of Utah',tg:['history','art'],sq:true,d:'Temple Square is a remarkable piece of American religious architecture whatever your affiliation. The Natural History Museum of Utah is genuinely world-class — the dinosaur hall is extraordinary, the Native cultures galleries are excellent.',dr:'Downtown Salt Lake City'},
    {id:'slc7',n:'SLC — Grandpa flies home from Salt Lake City Airport',tg:['star'],sq:false,d:'SLC is a major hub with direct flights to most cities. Easy 20 minutes from downtown. Drop Grandpa at departures, have a proper goodbye, and then you and the kiddo point the car west toward California.',dr:'Salt Lake City International Airport — 20 min from downtown SLC'},
  ]},
  {id:'ca', ico:'🚗', t:'Kiddo & you — on to California', s:'After the SLC goodbye — Nevada, big trees, redwood coast, and Tahoe', stops:[
    {id:'ca1',n:'Bonneville Salt Flats',tg:['view','weird'],sq:true,d:'White salt flat where land speed records are set — completely flat horizon in every direction, nothing for miles. Surreal and very strange. Easy highway pull-off right on I-80 west of SLC.',dr:'~1.5 hrs west of SLC on I-80 — signed pull-off'},
    {id:'ca2',n:'Wendover UT/NV — state line town',tg:['weird'],sq:true,d:'The classic Nevada state line casino town — useful fuel and food stop after the salt flats. The drive across the salt desert from SLC to Wendover on I-80 is one of the most surreal stretches of highway in America.',dr:'On I-80 at the Utah/Nevada border'},
    {id:'ca3',n:'Great Basin NP — bristlecones & Lehman Caves',tg:['cave','nature','dark','star'],sq:true,d:'4,000-year-old bristlecone pine trees and gorgeous Lehman Caves guided tour. Almost nobody goes here. Wheeler Peak Glacier is the southernmost glacier in the US. International Dark Sky Park with extraordinary night skies. Worth the detour south from I-80.',dr:'On US-50 (the Loneliest Road) in eastern Nevada — nps.gov/grba'},
    {id:'ca4',n:'US-50 — the Loneliest Road in America',tg:['drive','view'],sq:true,d:'Life magazine called it "the loneliest road in America" in 1986 and the name stuck. 287 miles of Nevada desert with almost nothing between towns. Strange, beautiful, and very quiet. An alternative to I-80 if you want the slow road.',dr:'From Ely NV to Carson City NV — parallels I-80 to the south'},
    {id:'ca5',n:'Mono Lake — tufa towers',tg:['star','view','nature'],sq:false,d:'Ancient saline lake 760,000 years old with alien calcium carbonate tufa towers rising from the water. The light and reflections are extraordinary — photographers make pilgrimages here. Enormous numbers of migratory birds. US-395 near Lee Vining.',dr:'Eastern Sierra on US-395 near Lee Vining — south from US-50 via US-395'},
    {id:'ca6',n:'Sequoia NP — General Sherman Tree',tg:['star','nature'],sq:false,d:'The largest living thing on Earth by volume — 275 feet tall, 36 feet in diameter, approximately 2,200 years old. It was old when Rome fell. The scale is genuinely incomprehensible until you\'re standing right next to it.',dr:'~3 hrs from Mono Lake via US-395 south and CA-168 west'},
    {id:'ca7',n:'Kings Canyon — deepest canyon in North America',tg:['star','view','nature'],sq:true,d:'Deeper than the Grand Canyon. The scenic byway drops 2,600 feet to the canyon floor through switchbacks. The Zumwalt Meadow loop (2 miles, easy, beautiful) at the bottom is one of the best easy hikes in the Sierra.',dr:'Adjacent to Sequoia NP — Kings Canyon Scenic Byway, CA-180'},
    {id:'ca8',n:'Avenue of the Giants — coastal redwoods',tg:['star','nature'],sq:false,d:'32 miles of old-growth coastal redwood grove — trees 300+ feet tall and up to 1,500 years old. The canopy is so dense it feels like a cathedral. Founders Grove has the Dyerville Giant, one of the tallest trees ever recorded.',dr:'US-101 in Humboldt County — 3-4 hrs from Sequoia via CA-99/I-5 north'},
    {id:'ca9',n:'Lost Coast — Mattole Road',tg:['drive','view','nature'],sq:true,d:'24 miles of dirt road through the most remote stretch of the California coast — no services, black sand beaches, King Range mountains dropping straight to the sea. The most dramatic and isolated coastal drive in California. Not for the faint-hearted.',dr:'Off US-101 in Humboldt County — high clearance helpful, check road conditions'},
    {id:'ca10',n:'CA-1 — Pacific Coast Highway through Big Sur',tg:['star','drive','view'],sq:false,d:'The most dramatic coastal road in America. McWay Falls drops onto an inaccessible beach (which makes it more beautiful). Elephant seals lounging at San Simeon. Bixby Bridge. Pull over constantly. Go as slow as you can.',dr:'Central California coast between Carmel and San Luis Obispo'},
    {id:'ca11',n:'Lake Tahoe',tg:['star','nature','swim'],sq:false,d:'One of the most beautiful alpine lakes in the world — 22 miles long, 1,645 feet deep, water so clear you can see 70 feet down. A perfect final destination or waypoint into California. Reno airport is 45 min if you need to fly home from here.',dr:'Eastern Sierra — from SLC go west on I-80 through Reno then south on US-395, or south from SLC via US-50 and CA-89'},
  ]},
];

let ckd = new Set(), curF = 'all';

function initLegend() {
  const TYPES = [
    {k:'star',l:'⭐ Must-do'},{k:'eat',l:'🍔 Local eats'},{k:'bakery',l:'🥐 Bakery'},
    {k:'coffee',l:'☕ Coffee'},{k:'hot',l:'♨️ Hot spring'},{k:'swim',l:'🏊 Swim hole'},
    {k:'dark',l:'🌌 Dark sky'},{k:'view',l:'🏔️ Scenic pull-off'},{k:'rock',l:'🪨 Rockhound'},
    {k:'cave',l:'🔦 Cave'},{k:'ghost',l:'👻 Ghost town'},{k:'train',l:'🚂 Train'},
    {k:'art',l:'🎨 Art/museum'},{k:'alien',l:'🛸 UFO/Alien'},{k:'weird',l:'🤪 Weird Americana'},
    {k:'ranger',l:'🌲 Ranger program'},{k:'nature',l:'🌿 Nature'},{k:'history',l:'📜 History'},
    {k:'drive',l:'🛣️ Scenic drive'}
  ];
  const g = document.getElementById('legend-grid');
  TYPES.forEach(t => {
    const span = document.createElement('span');
    span.className = 'tg tg-'+t.k;
    span.style.fontSize = '0.68rem';
    span.style.padding = '2px 8px';
    span.textContent = t.l;
    g.appendChild(span);
  });
}

function initFilters() {
  const row = document.getElementById('frow');
  FTYPES.forEach(f => {
    const b = document.createElement('button');
    b.className = 'fb' + (f.k === 'all' ? ' on' : '');
    b.textContent = f.l;
    b.onclick = () => setF(f.k, b);
    row.appendChild(b);
  });
}

function buildAll() {
  const c = document.getElementById('legs');
  c.innerHTML = '';
  DATA.forEach(leg => {
    const div = document.createElement('div');
    div.className = 'leg';
    div.id = 'L' + leg.id;

    const hdr = document.createElement('div');
    hdr.className = 'leg-header';
    hdr.innerHTML = `<span class="leg-icon">${leg.ico}</span><div class="leg-text"><div class="leg-title">${leg.t}</div><div class="leg-sub">${leg.s}</div></div><span class="leg-badge empty" id="B${leg.id}">0 checked</span><span class="leg-chevron" id="C${leg.id}">▾</span>`;
    hdr.onclick = () => togLeg(leg.id);

    // Leg-level notes bar
    const legNoteKey = 'lnote_' + leg.id;
    const legNoteVal = localStorage.getItem(legNoteKey) || '';
    const legNoteBar = document.createElement('div');
    legNoteBar.className = 'leg-note-bar';
    legNoteBar.id = 'LNB' + leg.id;
    legNoteBar.innerHTML = `<span class="leg-note-label">📝 Leg notes</span><span class="leg-note-preview" id="LNBP${leg.id}">${legNoteVal ? legNoteVal.replace(/\n/g,' ').substring(0,80)+(legNoteVal.length>80?'…':'') : 'Click to add notes for this leg…'}</span>`;
    legNoteBar.onclick = (e) => { e.stopPropagation(); togLegNote(leg.id); };

    const legNoteArea = document.createElement('div');
    legNoteArea.className = 'leg-note-area';
    legNoteArea.id = 'LNA' + leg.id;
    const legNoteTa = document.createElement('textarea');
    legNoteTa.className = 'leg-note-ta';
    legNoteTa.placeholder = 'Notes for this leg — lodging ideas, timing, things to book in advance, packing reminders…';
    legNoteTa.value = legNoteVal;
    legNoteTa.onclick = e => e.stopPropagation();
    legNoteTa.oninput = () => {
      localStorage.setItem(legNoteKey, legNoteTa.value);
      const preview = document.getElementById('LNBP' + leg.id);
      if (preview) {
        const v = legNoteTa.value;
        preview.textContent = v ? v.replace(/\n/g,' ').substring(0,80)+(v.length>80?'…':'') : 'Click to add notes for this leg…';
      }
    };
    legNoteArea.appendChild(legNoteTa);

    const body = document.createElement('div');
    body.className = 'leg-body';
    body.id = 'BD' + leg.id;
    body.style.display = 'none';

    const main = leg.stops.filter(s => !s.sq);
    const side = leg.stops.filter(s => s.sq);

    if (main.length) {
      const l = document.createElement('div');
      l.className = 'slbl';
      l.textContent = 'Main stops';
      body.appendChild(l);
      const g = document.createElement('div');
      g.className = 'sg';
      main.forEach(s => g.appendChild(mkCard(s)));
      body.appendChild(g);
    }
    if (side.length) {
      const l = document.createElement('div');
      l.className = 'slbl';
      l.textContent = 'Side quests — take them or leave them';
      body.appendChild(l);
      const g = document.createElement('div');
      g.className = 'sg';
      side.forEach(s => g.appendChild(mkCard(s)));
      body.appendChild(g);
    }

    div.appendChild(hdr);
    div.appendChild(legNoteBar);
    div.appendChild(legNoteArea);
    div.appendChild(body);
    c.appendChild(div);
  });
  loadChecked();
  updStats();
  applyF();
  togLeg(DATA[0].id);
}

function togLegNote(id) {
  const area = document.getElementById('LNA' + id);
  if (!area) return;
  const isOpen = area.classList.contains('open');
  area.classList.toggle('open', !isOpen);
  if (!isOpen) area.querySelector('textarea').focus();
}

function mkCard(s) {
  const c = document.createElement('div');
  c.className = 'sc' + (s.sq ? ' sq' : '') + (ckd.has(s.id) ? ' ck' : '');
  c.id = 'SC' + s.id;
  c.setAttribute('data-tg', (s.tg || []).join(','));

  const chkEl = document.createElement('div');
  chkEl.className = 'chk';
  chkEl.innerHTML = ckd.has(s.id) ? '✓' : '';

  const info = document.createElement('div');
  info.className = 'si';

  const tgsHtml = (s.tg || []).map(t => `<span class="tg tg-${t}">${TL[t] || t}</span>`).join('');

  // Load saved note
  const noteKey = 'note_' + s.id;
  const noteVal = localStorage.getItem(noteKey) || '';
  const hasNote = noteVal.trim().length > 0;

  info.innerHTML = `
    <div class="stop-top"><span class="sn">${s.n}</span></div>
    <div class="tgs">${tgsHtml}</div>
    <div class="sdesc">${s.d}</div>
    <div class="sdrv">${s.dr}</div>
  `;

  // Notes toggle button
  const noteToggle = document.createElement('button');
  noteToggle.className = 'note-toggle' + (hasNote ? ' has-note' : '');
  noteToggle.id = 'NT' + s.id;
  noteToggle.innerHTML = `<span class="nt-icon">▶</span> ${hasNote ? '📝 Note added' : 'Add a note'}`;
  noteToggle.onclick = (e) => { e.stopPropagation(); togNote(s.id); };

  // Notes area
  const noteArea = document.createElement('div');
  noteArea.className = 'note-area';
  noteArea.id = 'NA' + s.id;

  const noteTa = document.createElement('textarea');
  noteTa.className = 'note-ta';
  noteTa.placeholder = 'Your notes — booking links, reminders, things Grandpa said he wants to do here, opening hours…';
  noteTa.value = noteVal;
  noteTa.setAttribute('data-has-note', hasNote ? 'true' : 'false');
  noteTa.onclick = e => e.stopPropagation();
  noteTa.oninput = () => {
    const v = noteTa.value;
    const has = v.trim().length > 0;
    noteTa.setAttribute('data-has-note', has ? 'true' : 'false');
    localStorage.setItem(noteKey, v);
    const tog = document.getElementById('NT' + s.id);
    if (tog) {
      tog.className = 'note-toggle' + (has ? ' has-note' : '');
      tog.innerHTML = `<span class="nt-icon open-icon">▶</span> ${has ? '📝 Note added' : 'Add a note'}`;
      if (document.getElementById('NA' + s.id).classList.contains('open')) {
        tog.classList.add('open');
        tog.querySelector('.nt-icon').style.transform = 'rotate(90deg)';
      }
    }
  };

  noteArea.appendChild(noteTa);
  info.appendChild(noteToggle);
  info.appendChild(noteArea);

  c.appendChild(chkEl);
  c.appendChild(info);
  c.onclick = (e) => {
    // Don't toggle stop if clicking notes
    if (e.target.closest('.note-toggle') || e.target.closest('.note-area')) return;
    togStop(s.id);
  };
  return c;
}

function togNote(id) {
  const area = document.getElementById('NA' + id);
  const tog = document.getElementById('NT' + id);
  if (!area || !tog) return;
  const isOpen = area.classList.contains('open');
  area.classList.toggle('open', !isOpen);
  tog.classList.toggle('open', !isOpen);
  if (!isOpen) {
    area.querySelector('textarea').focus();
  }
}

function saveChecked() {
  localStorage.setItem('ga_checked', JSON.stringify([...ckd]));
}

function loadChecked() {
  try {
    const saved = localStorage.getItem('ga_checked');
    if (saved) {
      const ids = JSON.parse(saved);
      ids.forEach(id => {
        ckd.add(id);
        const card = document.getElementById('SC' + id);
        if (card) {
          card.classList.add('ck');
          const ch = card.querySelector('.chk');
          if (ch) ch.innerHTML = '✓';
        }
      });
      updBadges();
    }
  } catch(e) {}
}

function togStop(id) {
  if (ckd.has(id)) ckd.delete(id);
  else ckd.add(id);
  const c = document.getElementById('SC' + id);
  if (!c) return;
  const chkEl = c.querySelector('.chk');
  if (ckd.has(id)) { c.classList.add('ck'); chkEl.innerHTML = '✓'; }
  else { c.classList.remove('ck'); chkEl.innerHTML = ''; }
  saveChecked();
  updStats();
  updBadges();
  updPreview();
}

function togLeg(id) {
  const body = document.getElementById('BD' + id);
  const chev = document.getElementById('C' + id);
  const isOpen = body.style.display !== 'none';
  body.style.display = isOpen ? 'none' : 'block';
  chev.classList.toggle('open', !isOpen);
}

function updStats() {
  const all = DATA.flatMap(l => l.stops);
  const stars = all.filter(s => (s.tg || []).includes('star'));
  const fTags = ['eat', 'bakery', 'coffee', 'diner'];
  const food = all.filter(s => (s.tg || []).some(t => fTags.includes(t)));
  document.getElementById('s-ck').textContent = ckd.size;
  document.getElementById('s-st').textContent = stars.filter(s => ckd.has(s.id)).length + ' / ' + stars.length;
  document.getElementById('s-fd').textContent = food.filter(s => ckd.has(s.id)).length;
  document.getElementById('s-tt').textContent = all.length;
}

function updBadges() {
  DATA.forEach(leg => {
    const n = leg.stops.filter(s => ckd.has(s.id)).length;
    const b = document.getElementById('B' + leg.id);
    if (b) {
      b.textContent = n === 0 ? '0 checked' : n + ' checked';
      b.className = 'leg-badge' + (n === 0 ? ' empty' : '');
    }
  });
}

function setF(k, btn) {
  curF = k;
  document.querySelectorAll('.fb').forEach(b => b.classList.remove('on'));
  btn.classList.add('on');
  applyF();
}

function applyF() {
  DATA.forEach(leg => leg.stops.forEach(s => {
    const c = document.getElementById('SC' + s.id);
    if (!c) return;
    c.style.display = (curF === 'all' || (s.tg || []).includes(curF)) ? '' : 'none';
  }));
}

function chkAll() {
  DATA.forEach(leg => leg.stops.forEach(s => {
    ckd.add(s.id);
    const c = document.getElementById('SC' + s.id);
    if (c) { c.classList.add('ck'); const ch = c.querySelector('.chk'); if (ch) ch.innerHTML = '✓'; }
  }));
  saveChecked(); updStats(); updBadges(); updPreview();
}

function clrAll() {
  ckd.clear();
  DATA.forEach(leg => leg.stops.forEach(s => {
    const c = document.getElementById('SC' + s.id);
    if (c) { c.classList.remove('ck'); const ch = c.querySelector('.chk'); if (ch) ch.innerHTML = ''; }
  }));
  saveChecked();
  updStats(); updBadges();
  document.getElementById('rp').style.display = 'none';
}

function chkCat(tags) {
  clrAll();
  DATA.forEach(leg => leg.stops.forEach(s => {
    if ((s.tg || []).some(t => tags.includes(t))) {
      ckd.add(s.id);
      const c = document.getElementById('SC' + s.id);
      if (c) { c.classList.add('ck'); const ch = c.querySelector('.chk'); if (ch) ch.innerHTML = '✓'; }
    }
  }));
  saveChecked(); updStats(); updBadges(); updPreview();
}

function chkStars() { chkCat(['star']); }
function chkFood() { chkCat(['eat', 'bakery', 'coffee', 'diner']); }
function chkHot() { chkCat(['hot', 'swim']); }
function chkDark() { chkCat(['dark']); }

function updPreview() {
  const rp = document.getElementById('rp');
  const stops = DATA.flatMap(l => l.stops).filter(s => ckd.has(s.id));
  if (!stops.length) { rp.style.display = 'none'; return; }
  rp.style.display = 'block';
  document.getElementById('rp-stops').innerHTML = stops.map(s => `<span class="act">${s.n}</span>`).join(' <span style="color:#aaa"> › </span> ');
}

// ══ TAB SWITCHING ══
function showTab(id, btn) {
  document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  document.getElementById('tab-' + id).classList.add('active');
  btn.classList.add('active');
}

// ══ GRANDPA LEG DATA ══
const GRANDPA_DAYS = [
  {
    id:'g_jul3', date:'3', month:'Jul', dow:'Thu', type:'slc',
    title:'Grandpa Arrives Denver!',
    sub:'Pick up from DIA, rest day, settle in',
    sections:[
      {type:'logistics',icon:'✈️',label:'Arrival',items:[
        {must:true,name:'Pick up Grandpa at Denver International Airport',desc:'DIA is about 45 min from most Denver neighborhoods. Grab the bags, get food on the way home, decompress from the flight.',note:'Confirm arrival terminal and flight number ahead of time — DIA has multiple concourses'},
        {must:true,name:'Rest day — no agenda',desc:'Grandpa just flew in. Light evening, good dinner, early bed. The trip starts properly on the 4th.',note:''},
      ]},
    ]
  },
  {
    id:'g_jul4', date:'4', month:'Jul', dow:'Fri', type:'slc',
    title:'July 4th in Denver',
    sub:'Rest day, local adventure, fireworks',
    sections:[
      {type:'evening',icon:'🎆',label:'July 4th — Full Family Local Day',items:[
        {must:true,name:'4th of July fireworks',desc:'Denver has several good fireworks shows. Civic Center Park downtown, Stapleton/Central Park, or drive up to Red Rocks for the view. Grandpa + fireworks = non-negotiable.',note:'Crowds are significant downtown — get there early and have a clear exit plan'},
        {must:false,name:'Red Rocks Amphitheater',desc:'The most iconic outdoor venue in America — 300-foot sandstone fins framing a natural stage. Beautiful hike or just the view. 30 min from Denver.',note:'Free to visit during the day outside of concert hours — check schedule'},
        {must:false,name:'City Park / Denver Zoo area',desc:'Great neighborhood for a relaxed afternoon, paddle boats on the lake, the Denver Museum of Nature and Science has a good dinosaur hall if the kiddo is interested.',note:''},
        {must:false,name:'Larimer Square or RiNo for dinner',desc:'Great Denver neighborhoods for food. Larimer Square is historic and lively on the 4th. RiNo has excellent food and brewery options.',note:''},
      ]},
    ]
  },
  {
    id:'g_jul5', date:'5', month:'Jul', dow:'Sat', type:'drive',
    title:'Hit the Road — Denver → Durango',
    sub:'South over Wolf Creek Pass through the San Juans, ~5.5 hrs',
    sections:[
      {type:'drive-section',icon:'🛣️',label:'Drive Log — ~5.5 hrs',items:[
        {must:true,name:'Denver → Pueblo → Walsenburg (I-25 south)',desc:'~2 hrs. Head south on I-25 through Colorado Springs and Pueblo. Flat and fast — good audiobook stretch. The Spanish Peaks appear on your left around Walsenburg.',note:''},
        {must:true,name:'Walsenburg → Alamosa → South Fork (US-160 west)',desc:'~1.5 hrs. Cross the San Luis Valley — the largest alpine valley in the world, flat as a table surrounded by 14,000-ft peaks. The Great Sand Dunes are visible to the east if you look for them.',note:'Worth the Drive Bakery in Monte Vista is 20 min off US-160 — Amish-run, famous cinnamon rolls, 4.9 stars'},
        {must:true,name:'Wolf Creek Pass (US-160) — 10,857 ft',desc:'The climb over the Continental Divide. Spectacular alpine scenery, switchbacks, snow-capped peaks in early July. One of the great Colorado mountain drives.',note:'Take it slow on the descent — steep grades, beautiful views'},
        {must:true,name:'Wolf Creek Pass → Pagosa Springs → Durango',desc:'~1.5 hrs. Drop into the San Juan River valley. Pagosa Springs has the world\'s deepest natural hot spring — quick stop at The Springs Resort to look at the sulfur pools if you want.',note:''},
      ]},
      {type:'evening',icon:'🌅',label:'Durango Evening',items:[
        {must:true,name:'Arrive Durango — Main Avenue',desc:'A beautifully preserved Victorian railroad town. Walk Main Avenue, look at the Durango & Silverton Narrow Gauge Railroad depot for tomorrow, good dinner.',note:'Book lodging ahead — July is peak season in Durango'},
        {must:false,name:'Dinner: Steamworks Brewing or Carver Brewing',desc:'Both excellent Durango institutions on Main Ave. Steamworks has great food beyond the beer. Carver has been there since 1988.',note:''},
        {must:false,name:'Durango & Silverton Railroad — check morning schedule',desc:'The D&SRG departs 8:45am for Silverton — if Grandpa wants to do the steam train it\'s today or never on this trip. Adds half a day but it\'s magnificent.',note:'Book at durangotrain.com — sells out, go tonight if interested'},
      ]},
    ]
  },
  {
    id:'g_jul6', date:'6', month:'Jul', dow:'Sun', type:'drive',
    title:'Durango → Aztec Ruins → Carlsbad Caverns',
    sub:'Ancient ruins in the morning, bats at sunset, ~5.5 hrs driving',
    sections:[
      {type:'drive-section',icon:'🛣️',label:'Drive Log — ~5.5 hrs plus stops',items:[
        {must:true,name:'Durango → Aztec Ruins NM (US-550 south)',desc:'~1 hr to Aztec NM near Farmington. Ship Rock is visible from the highway as you descend into New Mexico — the 1,583-ft volcanic needle rising from flat desert. Pull over.',note:''},
        {must:true,name:'Aztec Ruins National Monument — great kiva',desc:'The only fully reconstructed great kiva you can walk into anywhere. The 50-foot circular ceremonial chamber is surprisingly moving. 30-minute stop. Sets up everything you\'ll see in canyon country.',note:'$10/person — allow 45 min, worth every minute'},
        {must:true,name:'Aztec → Carlsbad Caverns (US-285 south)',desc:'~4 hrs through the New Mexico high desert. Long drive but beautiful open country. Cross the Guadalupe Mountains as you approach Carlsbad.',note:'Fuel in Artesia — limited services on this stretch'},
      ]},
      {type:'evening',icon:'🦇',label:'Carlsbad — The Main Event',items:[
        {must:true,name:'Carlsbad Caverns — Natural Entrance walk',desc:'Enter through the cave mouth and descend a mile into the earth on foot. The Big Room: 14 acres of cathedral space, 750 feet underground, stalactites the size of cars, cave pearls, the Bottomless Pit. One of the genuine wonders of North America.',note:'$15/person — allow 2-3 hrs. Elevator available if Natural Entrance is too much.'},
        {must:true,name:'BAT FLIGHT at sunset — do not miss this',desc:'Hundreds of thousands of Mexican free-tailed bats spiral out of the cave mouth at dusk in a column that can last 20 minutes. You sit in the outdoor amphitheater, a ranger narrates, and then it begins. Completely free, no reservation needed. One of the great wildlife spectacles in America.',note:'Check nps.gov/cave for the exact announced time for your date — show up 30 min early for a good seat'},
      ]},
    ]
  },
  {
    id:'g_jul7', date:'7', month:'Jul', dow:'Mon', type:'drive',
    title:'Carlsbad → White Sands',
    sub:'Short drive, full afternoon in the dunes, sunset is everything',
    sections:[
      {type:'drive-section',icon:'🛣️',label:'Drive — ~1.5 hrs',items:[
        {must:true,name:'Carlsbad → White Sands via US-285 and US-70',desc:'~1.5 hrs. Short and easy. This gives you the whole afternoon in the park.',note:'Guadalupe Mountains NP is on US-62/180 between Carlsbad and El Paso — 1 hr detour if you want to add it. Highest peak in Texas, striking scenery.'},
      ]},
      {type:'evening',icon:'🏜️',label:'White Sands — All Afternoon and Sunset',items:[
        {must:true,name:'White Sands National Park — arrive by 3pm',desc:'Pure white gypsum dunes stretching to the horizon. NASA tests Mars rovers here. The afternoon light builds toward something extraordinary by sunset.',note:'$25/vehicle — the Alkali Flat Trail (5 miles) goes deepest into the dunes. Interdune Boardwalk is easy and accessible.'},
        {must:true,name:'Rent sleds at the visitor center gift shop',desc:'Grandpa is sledding. This is not negotiable and non-optional. The kiddo especially will launch themselves down dunes for an hour straight.',note:'~$25 deposit, returnable'},
        {must:true,name:'Stay for sunset — the real reason',desc:'The light turns the white dunes pink, then orange, then deep rose. Every person in the park falls quiet. One of those moments that doesn\'t photograph as well as it looks in real life.',note:'Sunset varies — check time and plan to be deep in the dunes 30 min before'},
        {must:false,name:'Moonrise/dark sky',desc:'White Sands under a full moon is extraordinary — the dunes glow. Check moon phase for July 7. White Sands occasionally does full moon nights with extended hours.',note:'Check nps.gov/whsa for special evening programs'},
      ]},
    ]
  },
  {
    id:'g_jul8', date:'8', month:'Jul', dow:'Tue', type:'drive',
    title:'White Sands → West Across New Mexico → Overnight near Grand Canyon',
    sub:'Long drive day with great stops — ~6 hrs to Williams or Tusayan AZ',
    sections:[
      {type:'drive-section',icon:'🛣️',label:'Drive Log — ~6 hrs',items:[
        {must:true,name:'White Sands → I-10 west → I-25 north → I-40 west',desc:'Head northwest out of Las Cruces and pick up I-40 westbound at Albuquerque. The most efficient path to the Grand Canyon.',note:'Albuquerque is a good fuel and lunch stop — Old Town Albuquerque if you have 45 min'},
        {must:true,name:'Petrified Forest National Park — right on I-40',desc:'Drive-through the 28-mile park road. Ancient logs turned to crystal scattered across painted badlands — 225 million years old. The Painted Desert colors at any light are extraordinary. 2-hour detour from I-40.',note:'$25/vehicle — enter from I-40 at the north entrance, exit south or vice versa'},
        {must:false,name:'Winslow AZ — lunch stop',desc:'The Eagles corner ("standin\' on a corner in Winslow Arizona") is a fun 10-minute photo stop. La Posada Hotel is a beautifully restored 1930 Harvey House — excellent lunch and extraordinary architecture.',note:'~40 min west of Petrified Forest on I-40'},
        {must:true,name:'Williams or Tusayan AZ — overnight',desc:'Williams is the classic Route 66 town 60 miles south of the rim — good food, historic main street, more options. Tusayan is right outside the park south entrance — convenient for an early start but limited options.',note:'Book ahead — July is peak season'},
      ]},
    ]
  },
  {
    id:'g_jul9', date:'9', month:'Jul', dow:'Wed', type:'drive',
    title:'Grand Canyon South Rim — Full Day',
    sub:'Enter via Desert View east entrance, work west along the rim',
    sections:[
      {type:'drive-section',icon:'🗺️',label:'Grand Canyon Strategy',items:[
        {must:true,name:'Enter via Desert View — east entrance',desc:'Take US-64 east from Williams/Tusayan rather than going straight to the main south entrance. Desert View is the far east end of the rim — less crowded, better orientation, and the Watchtower is here.',note:'Desert View entry is included in the park pass — $35/vehicle for 7 days'},
        {must:true,name:'Desert View Watchtower — Mary Colter 1932',desc:'A masterpiece of Southwest architecture built to evoke ancestral Puebloan towers. Views stretch across the canyon and the Painted Desert. Start here, get oriented, let the scale sink in.',note:'Short staircase to the top — accessible otherwise'},
        {must:true,name:'Drive the rim west — stop at every overlook',desc:'Lipan Point, Navajo Point, Grandview Point, Moran Point, Yaki Point. Each one is a different perspective on the canyon. Take the free shuttle from the main visitor area for the western viewpoints.',note:''},
        {must:true,name:'Bright Angel Point and Village area',desc:'The historic core — El Tovar Hotel, Bright Angel Lodge (both Mary Colter), the trailheads, Yavapai Geology Museum right on the rim. The Colorado River is 4,500 feet below.',note:'Mather Point at sunrise the next morning if you\'re still here — genuinely transforms the canyon'},
        {must:false,name:'Hermit\'s Rest — west end of shuttle route',desc:'The last stop on the western shuttle — another Mary Colter building designed to look like a hermit\'s cave. The views from here are quieter and the stone fireplace inside is beautiful.',note:'Free shuttle from village — 30 min each way'},
        {must:false,name:'Rim Trail walk — any section',desc:'The paved rim trail is flat and accessible and lets you move between viewpoints at your own pace with the canyon right beside you. Grandpa sets the pace.',note:''},
      ]},
      {type:'evening',icon:'🌅',label:'Grand Canyon Evening',items:[
        {must:true,name:'Sunset on the rim',desc:'Position at Hopi Point or Mohave Point on the western shuttle route — these face west and give the full sunset color show on the canyon walls. The canyon turns every shade of red and gold.',note:'These spots fill up 30-40 min before sunset in July — get there early'},
        {must:false,name:'Dinner: El Tovar Dining Room',desc:'The grand dame of the rim — the 1905 El Tovar Hotel dining room has been feeding canyon visitors for 120 years. Excellent food, views of the rim, historic atmosphere. Worth the splurge.',note:'Reservations strongly recommended — book at xanterra.com well ahead'},
      ]},
    ]
  },
  {
    id:'g_jul10', date:'10', month:'Jul', dow:'Thu', type:'drive',
    title:'Grand Canyon → Monument Valley — Last Night on the Road',
    sub:'Exit via Desert View, north on US-89, arrive for afternoon light',
    sections:[
      {type:'drive-section',icon:'🛣️',label:'Drive Log — ~3 hrs',items:[
        {must:true,name:'Grand Canyon → Desert View → US-89 north',desc:'Exit the canyon the way you came in — via Desert View. Then head north on US-89 through one of the best highway stretches in the Southwest.',note:''},
        {must:true,name:'Vermilion Cliffs and Echo Cliffs — US-89',desc:'The road drops off the plateau and the Vermilion Cliffs appear — 3,000-foot walls of red and orange sandstone. California condors were reintroduced here and are often visible from the road. One of the great American highway drives.',note:'Pull off at the Navajo Bridge overlook — condors roost on the bridge itself'},
        {must:true,name:'Navajo Bridge — Marble Canyon',desc:'Two bridges side by side over the Colorado River at the entrance to Marble Canyon. Walk the old 1929 span (pedestrian only now). Look down 467 feet to the river. California condors nest under the bridge.',note:'Free — short walk from the parking area'},
        {must:true,name:'US-89 → US-160 east → Kayenta → Monument Valley',desc:'~1.5 hrs from Navajo Bridge. The landscape shifts to the iconic Navajo Nation red mesa country as you approach.',note:''},
      ]},
      {type:'evening',icon:'🏜️',label:'Monument Valley — The Finale',items:[
        {must:true,name:'Arrive Monument Valley — The View Hotel',desc:'Check in, walk to the viewing deck, and let the Mittens and Merrick Butte do their thing. The afternoon light on those spires is extraordinary. This is the image. This is the one.',note:'theviewhotel.com — (435) 727-5555. July 10 night. If not already booked, call immediately.'},
        {must:true,name:'Sunset from the hotel deck',desc:'Watch the Mittens turn red, then orange, then deep purple as the sun drops. Pour something worth drinking. Grandpa has earned this view.',note:''},
        {must:false,name:'Navajo jeep tour — book at the hotel',desc:'The valley floor requires a Navajo guide. Ancient ruins, the Wave formation, the Ear of the Wind — none visible from the road. If there\'s an evening tour available, take it.',note:'Book at The View Hotel front desk on arrival — 90 min to 3 hr options'},
        {must:false,name:'Star gazing after dark',desc:'Monument Valley is extremely dark. The night sky here, with the silhouette of the Mittens against the Milky Way, is one of the great sights of the American West.',note:''},
      ]},
    ]
  },
  {
    id:'g_jul11', date:'11', month:'Jul', dow:'Fri', type:'slc',
    title:'Sunrise at Monument Valley → SLC → Grandpa Flies Home',
    sub:'The best possible last morning, then north to the airport',
    sections:[
      {type:'evening',icon:'🌅',label:'The Last Morning',items:[
        {must:true,name:'SUNRISE from The View Hotel deck',desc:'Set an alarm. Get up. Walk to the deck. Watch the Mittens emerge from darkness as the sky turns pink and gold behind them. This is Grandpa\'s last morning of the trip and it is a very good one.',note:'Sunrise is around 6am in early July — check the exact time'},
        {must:true,name:'Breakfast and load the car',desc:'Good breakfast at The View Hotel restaurant, load up, take one more look at the valley, then point north.',note:''},
      ]},
      {type:'drive-section',icon:'🛣️',label:'Drive to SLC — ~5 hrs',items:[
        {must:true,name:'Monument Valley → US-163 north → US-191 north → I-70 → SLC',desc:'~5 hrs. Head north through Bluff, Moab area, up US-191 and connect to I-70 and then I-15 north to Salt Lake City.',note:'Monument Valley to SLC is exactly 5 hours — give yourself buffer for the airport'},
        {must:false,name:'Valley of the Gods — scenic detour',desc:'A free drivable mini Monument Valley on a dirt road just north of Mexican Hat — 17 miles of red mesas with no crowds. Adds 45 min.',note:'Off US-163 near Mexican Hat'},
        {must:false,name:'Moab lunch stop',desc:'Moab is right on the route — good food, Last stop before the highway north. Breakfast at Moab Garage Co. or lunch at Zax.',note:'~2.5 hrs from Monument Valley'},
      ]},
      {type:'logistics',icon:'✈️',label:'SLC Airport Sendoff',items:[
        {must:true,name:'Drop Grandpa at Salt Lake City International Airport',desc:'Mid-morning flight July 11. SLC is 20 min from downtown. Allow extra time for bags and security. Make it a proper goodbye.',note:'SLC airport is well laid out — drop-off is easy, clear signage'},
        {must:true,name:'Pick up partner — same airport',desc:'Coordinate the timing so partner arrives around the same time Grandpa departs. One stop, two missions.',note:''},
        {must:true,name:'Head west — the California leg begins',desc:'I-80 west out of SLC. The next chapter starts now.',note:''},
      ]},
    ]
  },
];

// ══ BUILD GRANDPA CALENDAR ══
function buildGrandpaCalendar() {
  const container = document.getElementById('grandpa-days');
  if (!container) return;
  container.innerHTML = '';
  GRANDPA_DAYS.forEach(day => buildCalDay(container, day, 'gp_'));
}

// ══ CALENDAR DATA ══
const CAL_DAYS = [
  {
    id:'jul10', date:'10', month:'Jul', dow:'Thu', type:'slc',
    title:'SLC — Last Night with Grandpa',
    sub:'Sendoff dinner, hot springs soak, get the airport plan sorted',
    sections:[
      {type:'logistics',icon:'✈️',label:'Logistics',items:[
        {must:true,name:'Confirm Grandpa\'s flight',desc:'July 10 or 11 — nail down the exact date and time. SLC airport is 20 min from downtown, easy drop-off. Delta and United have good connections from SLC.',note:'Book early — summer SLC flights fill up'},
        {must:true,name:'Pick up partner at SLC airport',desc:'Coordinate arrival time with Grandpa\'s departure so the handoff is clean. Partner flies in, Grandpa flies out, possibly same terminal.',note:''},
      ]},
      {type:'evening',icon:'🌅',label:'Full Family Evening',items:[
        {must:true,name:'Grandpa farewell dinner',desc:'Make it count. Downtown SLC has excellent food — Red Iguana (Mexican, legendary, cash only) or Market Street Grill (seafood, Salt Lake institution since 1983). Grandpa picks.',note:'Red Iguana often has a wait — call ahead or go early'},
        {must:false,name:'Antelope Island State Park — float the Great Salt Lake',desc:'If timing allows before dinner — drive out to Antelope Island (45 min), wade into the lake, float effortlessly in the brine. Bison roaming the island. The scale of the lake is genuinely staggering. Grandpa\'s last big adventure.',note:'$15/vehicle — closes at dusk, check sunset time'},
        {must:false,name:'Temple Square evening walk',desc:'The grounds are beautiful at night, beautifully lit, and free to walk. A good after-dinner stroll if everyone has energy.',note:''},
      ]},
    ]
  },
  {
    id:'jul11', date:'11', month:'Jul', dow:'Fri', type:'slc',
    title:'Grandpa Flies Home — Head West',
    sub:'Airport sendoff, hit I-80, overnight somewhere in Nevada',
    sections:[
      {type:'logistics',icon:'🚗',label:'Drive Plan',items:[
        {must:true,name:'SLC → Nevada — I-80 west',desc:'After the airport drop-off, head west on I-80 through the Bonneville Salt Flats and into Nevada. The salt flats are right on I-80 — pull over for 10 minutes and walk out on them. The flatness is disorienting in the best way.',note:''},
        {must:true,name:'Bonneville Salt Flats pull-off',desc:'Signed pull-off directly on I-80 about 100 miles west of SLC. Walk out onto the crust. Take the photo. It\'s genuinely surreal — completely flat horizon 360 degrees.',note:'Free, 10 min, totally worth it'},
        {must:false,name:'Wendover — Nevada state line',desc:'Classic casino border town. Useful for fuel, food, cheap overnight if you leave late. The drive across the salt desert from SLC to Wendover is one of the most alien stretches of highway in America.',note:''},
      ]},
      {type:'drive-section',icon:'🛣️',label:'Drive Log',items:[
        {must:true,name:'SLC → Elko NV via I-80',desc:'~3.5 hrs. Good overnight if leaving SLC by early afternoon. Elko has decent hotels, good Basque food (the Basque community in Elko is real and the food is excellent — try Star Hotel).',note:''},
        {must:false,name:'Or push to Winnemucca',desc:'~5.5 hrs from SLC. More of Nevada but puts you closer to Reno for the next morning.',note:''},
        {must:false,name:'Or push all the way to Reno',desc:'~7 hrs from SLC. Possible if leaving by noon. Reno has good food and casinos if you want a fun overnight.',note:''},
      ]},
    ]
  },
  {
    id:'jul12', date:'12', month:'Jul', dow:'Sat', type:'drive',
    title:'Drive to California — Arrive by Night',
    sub:'Cross into California, head north on US-101, arrive Jedediah Smith area',
    sections:[
      {type:'drive-section',icon:'🛣️',label:'Drive Log',items:[
        {must:true,name:'Nevada → Reno → Sacramento (I-80)',desc:'~2.5 hrs Reno to Sacramento. Cross the Sierra Nevada — beautiful mountain driving through Donner Pass, Truckee, and down the western slope.',note:'Check for any chain control requirements if traveling late in season'},
        {must:true,name:'Sacramento → Redding (I-5 north)',desc:'~2.5 hrs. The Central Valley is not glamorous but it\'s fast. Redding has good food options for a break.',note:''},
        {must:true,name:'Redding → Arcata → US-101 north → Crescent City',desc:'~3.5 hrs. The last stretch on US-101 enters the redwood zone around Arcata — trees start getting serious. By the time you hit Humboldt and Del Norte counties you\'re in the cathedral.',note:''},
      ]},
      {type:'logistics',icon:'📍',label:'Arrival Area',items:[
        {must:true,name:'Base: Crescent City / Jedediah Smith area',desc:'Crescent City is the practical base — hotels, groceries, restaurants. Jedediah Smith Redwoods State Park is 9 miles east on US-199. The park campground is extraordinary if camping, or stay in town and drive in each day.',note:'Book accommodation well ahead — limited options in this area in July'},
        {must:false,name:'Elk Valley Rancheria area — Howonquet Lodge',desc:'Tribal hotel near Crescent City, surprisingly good, supports the Tolowa Dee-ni\' Nation directly.',note:''},
      ]},
    ]
  },
  {
    id:'jul13', date:'13', month:'Jul', dow:'Sun', type:'redwood',
    title:'First Full Day — Jedediah Smith',
    sub:'Partner settles in, full family explores the grove together',
    sections:[
      {type:'evening',icon:'👨‍👩‍👦',label:'Full Family Day — Everyone Together',items:[
        {must:true,name:'Stout Grove — the great grove',desc:'0.6 miles, flat, right on the Smith River. The trees here are among the largest on Earth and the riverbank setting is unlike any other grove. Go in the morning when the mist is still in the canopy. Stand very still and listen.',note:'Free — trailhead off Howland Hill Rd, accessible in most vehicles'},
        {must:true,name:'Swim in the Smith River',desc:'The clearest river in California — gin-clear water over smooth boulders, cold, perfect swimming. Multiple access points near the campground and on US-199. The kiddo will want to stay all afternoon.',note:'Water is cold even in July — bring a towel and sun protection'},
        {must:false,name:'Howland Hill Road scenic drive',desc:'An unpaved road through the middle of Jedediah Smith — 10 miles of ancient redwood forest you drive through at walking speed. Passes the Stout Grove trailhead. The canopy closes completely overhead.',note:'Not suitable for large RVs; passenger cars fine in dry conditions'},
        {must:false,name:'Dinner: Good Harvest Café — Crescent City',desc:'Best breakfast and casual dinner in Crescent City — locally sourced, good vegetarian options, the kind of place a small town is lucky to have.',note:''},
      ]},
    ]
  },
  {
    id:'jul14', date:'14', month:'Jul', dow:'Mon', type:'redwood',
    title:'Monday — Partner Works, You + Kiddo Explore',
    sub:'Daytime adventure, evening full family',
    sections:[
      {type:'daytime',icon:'☀️',label:'Daytime — You + Kiddo',items:[
        {must:true,name:'Fern Canyon — Gold Bluffs Beach',desc:'Drive on the beach through Fern Canyon — 50-foot walls of five-finger ferns on both sides, a stream running through the middle. Used as a filming location in Jurassic Park 2 and The Mandalorian. Otherworldly. The kiddo will lose their mind.',note:'$12/vehicle — Davison Road from US-101. High clearance recommended, creek crossing. Check road conditions.'},
        {must:true,name:'Trees of Mystery — Klamath',desc:'A gondola through the redwood canopy, a giant Paul Bunyan and Babe the Blue Ox at the entrance (iconic photo), and inside — a genuinely excellent Native American museum. One of those roadside attractions that turns out to be legitimately great. The kiddo will love the gondola.',note:'~45 min south of Crescent City on US-101 — $25/adult, $18/child. Allow 2-3 hrs'},
        {must:false,name:'Klamath River overlook',desc:'Pull-off on US-101 above the Klamath River mouth — on a good day you can see harbor seals, sea lions, and if you\'re very lucky, a gray whale offshore.',note:'Free pull-off, 10 minutes'},
        {must:false,name:'Damnation Creek Trail',desc:'One of the best hikes in Redwood NP — 4 miles round trip dropping through old-growth forest to a secret rocky beach. Steep but not technical. Check tide tables before going to the beach section.',note:'Trailhead on US-101 at mile marker 16 — free'},
      ]},
      {type:'evening',icon:'🌅',label:'Evening — Full Family',items:[
        {must:true,name:'Golden hour in the grove',desc:'Drive into Jedediah Smith around 6pm when the angled light comes through the trees. The redwoods glow. Bring a blanket, sit on a log, do nothing for a while. This is the moment.',note:''},
        {must:false,name:'Dinner: SeaQuake Brewing — Crescent City',desc:'Local brewery right near the harbor. Good food, local beer, casual atmosphere, right on the waterfront. Good family spot.',note:''},
        {must:false,name:'Battery Point Lighthouse — sunset',desc:'Walk out on the causeway at low tide to the lighthouse on a small island. One of the last accessible lighthouses on the West Coast. Check tide tables — accessible only at low tide.',note:'Free to walk out — $5 for lighthouse tour if open'},
      ]},
    ]
  },
  {
    id:'jul15', date:'15', month:'Jul', dow:'Tue', type:'redwood',
    title:'Tuesday — Partner Works, Free Day',
    sub:'Slower pace, beach time, explore at will',
    sections:[
      {type:'daytime',icon:'☀️',label:'Daytime — You + Kiddo',items:[
        {must:true,name:'Enderts Beach — hidden coastal trail',desc:'A little-known gem at the south end of Crescent City — a short trail drops to a long wild beach with tide pools, driftwood, and no crowds. The sea stacks offshore are dramatic.',note:'End of Enderts Beach Rd off US-101 — free, easy 1-mile trail'},
        {must:false,name:'Redwood National Park Visitor Center — Crescent City',desc:'Well done visitor center with junior ranger program for the kiddo — they\'ll earn a badge for Redwood NP. Good orientation maps for the whole park complex.',note:'Free — the junior ranger program is genuinely fun and they\'re thorough'},
        {must:false,name:'Point St. George',desc:'Remote headland north of Crescent City — wild Pacific views, whale watching in season, a lighthouse visible offshore. Often has good bird activity.',note:'Free — follow Washington Blvd north from Crescent City'},
        {must:false,name:'Lake Earl Wildlife Area',desc:'A large coastal lagoon and wetland just north of Crescent City — great birding, possible river otter sightings, easy flat walking. The kiddo can wade in the shallow edges.',note:'Free — Lake Earl Drive off US-101'},
        {must:false,name:'Second Smith River swim',desc:'The kids will ask to go back. Go back. Different spot — try the swimming hole near the confluence on US-199.',note:''},
      ]},
      {type:'evening',icon:'🌅',label:'Evening — Full Family',items:[
        {must:true,name:'Crescent City harbor — watch the fishing boats come in',desc:'The commercial fleet returns in the late afternoon. Fresh Dungeness crab and salmon available right off the boats or at the adjacent docks. Get something for dinner from the source.',note:''},
        {must:false,name:'Dinner: harbor seafood',desc:'Crescent City doesn\'t have fancy restaurants but the seafood is extraordinary — caught that day, a few miles offshore. Fisherman\'s Restaurant or just cook what you bought at the dock.',note:''},
      ]},
    ]
  },
  {
    id:'jul16', date:'16', month:'Jul', dow:'Wed', type:'drive',
    title:'Wednesday Afternoon — Head South, Overnight Mendocino Coast',
    sub:'Morning in the redwoods, afternoon drive down US-101, overnight on the coast',
    sections:[
      {type:'daytime',icon:'☀️',label:'Morning — Last Redwood Hours',items:[
        {must:true,name:'Boy Scout Tree Trail — Jedediah Smith',desc:'The most secluded old-growth trail in the park — 2.8 miles each way through primeval forest to the Boy Scout Tree. Go early so you have time to linger before the drive.',note:'Trailhead on Howland Hill Rd — free, muddy in spots, worth every step'},
        {must:false,name:'Final Smith River swim',desc:'One last dip in the clearest river in California before you leave. Cold, perfect, the kiddo will not want to get out.',note:''},
        {must:true,name:'Pack up, fuel up, download offline maps',desc:'CA-1 south of Fort Bragg loses cell signal in places. Download offline maps before leaving Crescent City.',note:''},
      ]},
      {type:'drive-section',icon:'🛣️',label:'Afternoon Drive — ~3.5 hrs to Mendocino area',items:[
        {must:true,name:'US-101 south → Avenue of the Giants',desc:'Leave by 2-3pm. Avenue of the Giants starts near Garberville ~90 min south — exit off US-101 and drive all 32 miles of old-growth at a slow pace. Trees 300+ feet tall, canopy closes overhead.',note:'Exit signed from US-101 near Myers Flat — allow 1 hr at a gentle pace'},
        {must:true,name:'Leggett → CA-1 west → Fort Bragg → Mendocino',desc:'Turn west at Leggett. The road becomes immediately dramatic — sea cliffs, coastal bluffs, fishing villages. Arrive Fort Bragg or Mendocino for the night.',note:'CA-1 is slow and gorgeous — 1.5 hrs from Leggett to Mendocino'},
      ]},
      {type:'evening',icon:'🌅',label:'Overnight — Mendocino Coast',items:[
        {must:true,name:'Overnight: Little River Inn or MacCallum House',desc:'Little River Inn sits on the ocean bluff just south of Mendocino — excellent restaurant, beautiful rooms. MacCallum House is Victorian, in the village. Both book up fast in July.',note:'littleriverinn.com or maccallumhouse.com — book well ahead'},
        {must:true,name:'Dinner in Mendocino',desc:'Victorian headland village above the Pacific. Café Beaujolais is legendary (reserve ahead). The Mendocino Hotel dining room is good. Fort Bragg harbor has more casual fresh seafood options.',note:''},
        {must:false,name:'Mendocino Headlands walk at sunset',desc:'Free state park on the headlands above the bay — extraordinary views of sea stacks and blowhole at golden hour.',note:'Park at end of Main St in Mendocino village'},
      ]},
    ]
  },
  {
    id:'jul17', date:'17', month:'Jul', dow:'Thu', type:'tahoe',
    title:'Coastal Morning Drive → Tahoe — Rehearsal Day',
    sub:'Finish CA-1, arrive Tahoe early afternoon, river float + rehearsal dinner tonight',
    sections:[
      {type:'drive-section',icon:'🛣️',label:'Morning Drive — ~4 hrs to Tahoe',items:[
        {must:true,name:'Mendocino → CA-20 east → US-50 → South Lake Tahoe',desc:'~4 hrs. East on CA-20 through the mountains, Sacramento Valley, then US-50 east through Placerville and up into the Sierra Nevada to Tahoe. The last 30 min through the mountains is beautiful.',note:'Leave by 9am to arrive Tahoe early afternoon with time for the river float'},
        {must:false,name:'Placerville stop — Gold Rush country',desc:'Heart of the California Gold Rush — old Main Street, good coffee, El Dorado County Historical Museum. Natural halfway point on US-50.',note:'~2.5 hrs from Mendocino'},
      ]},
      {type:'evening',icon:'💒',label:'Wedding Eve — Rehearsal Day',items:[
        {must:true,name:'Arrive Lake Tahoe — early afternoon',desc:'Get settled, breathe, appreciate that you drove from the redwood coast to an alpine lake in one morning.',note:'July wedding weekend — book lodging immediately if not done'},
        {must:true,name:'Pre-wedding Truckee River float',desc:'The classic Tahoe pre-wedding event — float the Truckee River from Tahoe City downstream. Tubes or kayaks, cold clear water, giant pines on both sides, easy current. Perfect way to decompress from the road.',note:'Tahoe City is ~30 min from South Shore — Truckee River Raft Company for tube rentals'},
        {must:true,name:'Rehearsal dinner',desc:'The main event of the evening. Everyone is here. The trip has been leading to this.',note:''},
      ]},
    ]
  },
  {
    id:'jul18', date:'18', month:'Jul', dow:'Fri', type:'tahoe',
    title:'The Wedding Day 💍',
    sub:'Friday July 18th — the whole reason for the trip',
    sections:[
      {type:'evening',icon:'💍',label:'Wedding Day',items:[
        {must:true,name:'The Wedding',desc:'You drove from Denver through the desert, through the redwoods, up the coast, and across the Sierra Nevada to be here. Celebrate accordingly.',note:''},
        {must:false,name:'Morning — Emerald Bay',desc:'If the ceremony is afternoon, the morning at Emerald Bay is perfect. The most photographed spot in California — emerald cove, Vikingsholm Castle on the shore, kayaks available.',note:'Emerald Bay State Park — $10 parking, go early'},
        {must:false,name:'Sand Harbor swim — Nevada side',desc:'White granite boulders, water so clear you can see 70 feet down. Perfect pre-ceremony morning swim.',note:'Sand Harbor Nevada State Park — $12/vehicle'},
      ]},
    ]
  },
  {
    id:'jul19', date:'19', month:'Jul', dow:'Sat', type:'tahoe',
    title:'Post-Wedding Day — Lake Tahoe',
    sub:'Saturday — decompress, explore, enjoy the lake before the drive home',
    sections:[
      {type:'evening',icon:'🏔️',label:'Full Day at the Lake',items:[
        {must:true,name:'Tahoe Rim Trail — any section',desc:'The trail circles the entire lake at elevation. Tahoe Meadows near Incline Village is easy and spectacular. A perfect way to clear the head the morning after the wedding.',note:'Free — many trailheads around the lake'},
        {must:false,name:'Vikingsholm Castle tour',desc:'The 1929 Scandinavian castle inside Emerald Bay — accessible by steep 1-mile trail or kayak. Tours in summer.',note:'$12/adult — steep trail down'},
        {must:false,name:'D.L. Bliss State Park beach',desc:'One of the most beautiful beaches on the lake — white granite sand, crystal water, West Shore between Emerald Bay and Meeks Bay.',note:'$12/vehicle — fills early in July'},
        {must:false,name:'Lake Tahoe boat cruise',desc:'Several operators on the South Shore do scenic cruises — a good way to see the lake scale from the water.',note:'Book ahead — $50-80/person'},
        {must:true,name:'Last dinner on the lake',desc:'Sunset over the Sierra Nevada. Tomorrow you start driving home. Make this one count.',note:'Edgewood Restaurant has the best lake view — reserve ahead'},
      ]},
    ]
  },
  {
    id:'jul20', date:'20', month:'Jul', dow:'Sun', type:'home',
    title:'Drive Home — Day One',
    sub:'Tahoe → Utah — the long run east, ~10-11 hrs driving',
    sections:[
      {type:'drive-section',icon:'🛣️',label:'Drive Plan',items:[
        {must:true,name:'Tahoe → Reno (US-395 / I-80)',desc:'~1 hr. Quick and beautiful over the Sierra crest. Reno is a good fuel and breakfast stop.',note:''},
        {must:true,name:'Reno → Salt Lake City (I-80 east)',desc:'~5.5 hrs. Cross the Nevada desert and Utah salt flats on I-80. Not glamorous but fast. The Bonneville Salt Flats are right on I-80 — easy 10-minute stop if you haven\'t done it.',note:'Long open stretch with limited services — fuel in Winnemucca and Elko'},
        {must:false,name:'Wendover to SLC — salt flat pull-off',desc:'The Bonneville Salt Flats overlook is signed right off I-80, about 100 miles west of SLC. 10 minutes, completely surreal, easy stop.',note:'Free pull-off'},
        {must:true,name:'Salt Lake City — fuel, food, stretch',desc:'Good lunch stop or early dinner depending on timing. The Great Salt Lake float at Antelope Island if you haven\'t done it — 45 min detour but it\'s extraordinary.',note:''},
        {must:true,name:'SLC → Green River UT (I-15 south then I-70 east)',desc:'~2.5 hrs. Head south on I-15 past Provo, then join I-70 east into canyon country. The landscape changes dramatically as you enter the Colorado Plateau — red rock walls, canyon country, the Colorado River.',note:''},
      ]},
      {type:'logistics',icon:'🏨',label:'Overnight Options',items:[
        {must:false,name:'Green River, UT — overnight option',desc:'A tiny town on the Colorado River at the junction of I-70 and US-191. Famous for cantaloupes and honeydew melons — the Melon Days Festival is in September but the melon stands run all summer. Crystal Geyser (a cold CO2 geyser) is 10 min south of town on the river.',note:'Basic motels — Comfort Inn or Holiday Inn Express are the reliable options'},
        {must:false,name:'Moab, UT — overnight option',desc:'45 min south of Green River on US-191 — better food, more character, and you wake up in canyon country. If you\'ve already done Moab/Arches this trip it may feel redundant, but it\'s a better overnight than Green River.',note:'July in Moab is hot and popular — book ahead'},
        {must:false,name:'Or push to Grand Junction, CO',desc:'~2 hrs further east on I-70. Puts you 4 hrs from Denver the next morning. Good food options, Colorado wines from the Grand Valley.',note:''},
      ]},
    ]
  },
  {
    id:'jul21', date:'21', month:'Jul', dow:'Mon', type:'home',
    title:'Drive Home — Day Two (or Day One finish)',
    sub:'Utah/Colorado → Denver — the final stretch',
    sections:[
      {type:'drive-section',icon:'🛣️',label:'Drive Plan — From Green River to Denver',items:[
        {must:true,name:'Green River → Grand Junction (I-70 east)',desc:'~2 hrs. I-70 through the Colorado River canyon — the road drops into a slot canyon at one point and walls close in on both sides. One of the great American highway moments. Don\'t be in the left lane.',note:''},
        {must:true,name:'Grand Junction → Glenwood Canyon (I-70 east)',desc:'~1 hr. Glenwood Canyon is 12 miles of I-70 carved into sheer 2,000-foot canyon walls — one of the most expensive highway miles ever built. Slow down.',note:'Check CDOT for any closures — this section closes occasionally for rockfall'},
        {must:false,name:'Glenwood Springs — quick stop',desc:'Natural hot springs pool right in town, the Hotel Colorado (Teddy Roosevelt\'s favorite), and good coffee. 30-minute break if you want it.',note:''},
        {must:true,name:'Glenwood Springs → Vail Pass → Denver (I-70 east)',desc:'~2.5 hrs. Over Vail Pass, through the Eisenhower Tunnel (11,013 ft), down into the Front Range. Denver skyline appears. You\'re home.',note:''},
      ]},
      {type:'logistics',icon:'🏁',label:'Worth-It Stops (If Needed)',items:[
        {must:false,name:'Melon stand — Green River UT',desc:'The cantaloupe from the Green River valley is genuinely extraordinary — grown in the sandy soil with the right minerals and temperature swings. Stop at one of the roadside stands on I-70 or US-191. Buy a whole one. Eat it immediately.',note:'Stands run July–September'},
        {must:false,name:'Palisade Peach Stand — Palisade CO',desc:'Just east of Grand Junction on I-70 — the Palisade peaches are Colorado\'s greatest agricultural achievement. Pull off at any of the farm stands. The peaches in July are obscenely good.',note:'Exit 42 off I-70 — 10 minute detour'},
        {must:false,name:'Hanging Lake trail — Glenwood Canyon',desc:'Only if you have several hours to spare — a stunning 3-mile round-trip to a turquoise hanging lake above the canyon. Requires advance permit reservation. Worth it if you planned ahead.',note:'Permit required at recreation.gov — book months ahead in summer'},
      ]},
      {type:'notes-section',icon:'🎉',label:'You Made It',items:[
        {must:true,name:'Denver — home',desc:'Drop partner, unload the car, do the laundry, sleep for 10 hours. The trip is over. It was a great one.',note:''},
      ]},
    ]
  },
];

// ══ BUILD CALENDAR (shared) ══
function buildCalDay(container, day, prefix) {
  prefix = prefix || '';
  const dayEl = document.createElement('div');
  dayEl.className = 'cal-day ' + day.type;
  dayEl.id = 'CD' + prefix + day.id;

  const hdr = document.createElement('div');
  hdr.className = 'cal-day-header';
  hdr.onclick = () => togCalDay(prefix + day.id);

  const dateBlock = document.createElement('div');
  dateBlock.className = 'cal-date-block';
  dateBlock.innerHTML = `<span class="cal-month">${day.month}</span><span class="cal-day-num">${day.date}</span><span class="cal-dow">${day.dow}</span>`;

  const titleBlock = document.createElement('div');
  titleBlock.className = 'cal-day-title-block';
  titleBlock.innerHTML = `<div><div class="cal-day-title">${day.title}</div><div class="cal-day-sub">${day.sub}</div></div><span class="cal-chevron" id="CC${prefix}${day.id}">▾</span>`;

  hdr.appendChild(dateBlock);
  hdr.appendChild(titleBlock);

  const body = document.createElement('div');
  body.className = 'cal-day-body';
  body.id = 'CB' + prefix + day.id;

  day.sections.forEach(sec => {
    const secEl = document.createElement('div');
    secEl.className = 'cal-section ' + sec.type + '-section';
    const secLbl = document.createElement('div');
    secLbl.className = 'cal-section-label';
    secLbl.innerHTML = `<span class="sl-icon">${sec.icon}</span><span>${sec.label}</span>`;
    secEl.appendChild(secLbl);
    const itemsEl = document.createElement('div');
    itemsEl.className = 'cal-items';
    sec.items.forEach(item => {
      const itemEl = document.createElement('div');
      itemEl.className = 'cal-item ' + (item.must ? 'must' : 'opt');
      itemEl.innerHTML = `
        <div class="cal-item-name">${item.name}${!item.must ? '<span class="opt-badge">optional</span>' : ''}</div>
        <div class="cal-item-desc">${item.desc}</div>
        ${item.note ? `<div class="cal-item-note">💡 ${item.note}</div>` : ''}
      `;
      itemsEl.appendChild(itemEl);
    });
    secEl.appendChild(itemsEl);
    body.appendChild(secEl);
  });

  const noteKey = 'calnote_' + prefix + day.id;
  const noteVal = localStorage.getItem(noteKey) || '';
  const noteBar = document.createElement('div');
  noteBar.className = 'cal-note-bar';
  noteBar.onclick = (e) => { e.stopPropagation(); togCalNote(prefix + day.id); };
  noteBar.innerHTML = `<span class="cal-note-label">📝 Notes</span><span class="cal-note-preview" id="CNP${prefix}${day.id}">${noteVal ? noteVal.replace(/\n/g,' ').substring(0,70)+(noteVal.length>70?'…':'') : 'Add notes for this day…'}</span>`;

  const noteArea = document.createElement('div');
  noteArea.className = 'cal-note-area';
  noteArea.id = 'CNA' + prefix + day.id;
  const noteTa = document.createElement('textarea');
  noteTa.className = 'cal-note-ta';
  noteTa.placeholder = 'Notes — booking links, timing details, things to remember…';
  noteTa.value = noteVal;
  noteTa.oninput = () => {
    localStorage.setItem(noteKey, noteTa.value);
    const prev = document.getElementById('CNP' + prefix + day.id);
    if (prev) {
      const v = noteTa.value;
      prev.textContent = v ? v.replace(/\n/g,' ').substring(0,70)+(v.length>70?'…':'') : 'Add notes for this day…';
    }
  };
  noteArea.appendChild(noteTa);

  dayEl.appendChild(hdr);
  dayEl.appendChild(body);
  dayEl.appendChild(noteBar);
  dayEl.appendChild(noteArea);
  container.appendChild(dayEl);
}

function buildCalendar() {
  const container = document.getElementById('cal-days');
  if (!container) return;
  container.innerHTML = '';
  CAL_DAYS.forEach(day => buildCalDay(container, day, ''));
}

function togCalDay(id) {
  const body = document.getElementById('CB' + id);
  const chev = document.getElementById('CC' + id);
  if (!body) return;
  const isOpen = body.classList.contains('open');
  body.classList.toggle('open', !isOpen);
  if (chev) chev.classList.toggle('open', !isOpen);
}

function togCalNote(id) {
  const area = document.getElementById('CNA' + id);
  if (!area) return;
  area.classList.toggle('open');
  if (area.classList.contains('open')) area.querySelector('textarea').focus();
}

initLegend();
initFilters();
buildAll();
buildGrandpaCalendar();
buildCalendar();
</script>
</body>
</html>
