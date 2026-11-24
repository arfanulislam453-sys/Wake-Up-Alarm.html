# Wake-Up-Alarm.html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <meta name="theme-color" content="#0f172a" />
  <title>Push-up & Plank Alarm</title>
  <style>
    :root {
      --bg: #0f172a;
      --card: #1e293b;
      --accent: #22d3ee;
      --accent2: #a78bfa;
      --success: #4ade80;
      --danger: #f87171;
      --text: #f1f5f9;
      --muted: #94a3b8;
    }
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      background: var(--bg);
      color: var(--text);
      min-height: 100dvh;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 16px;
      overflow-x: hidden;
    }
    h1 {
      font-size: 1.6rem;
      margin: 12px 0 4px;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      text-align: center;
    }
    .subtitle { color: var(--muted); font-size: 0.9rem; margin-bottom: 20px; text-align: center; }
    .card {
      background: var(--card);
      border-radius: 16px;
      padding: 20px;
      width: 100%;
      max-width: 420px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.4);
    }
    .time-display {
      font-size: 3.2rem;
      font-weight: 700;
      text-align: center;
      letter-spacing: 2px;
      margin: 8px 0 16px;
      font-variant-numeric: tabular-nums;
    }
    label { display: block; font-size: 0.85rem; color: var(--muted); margin-bottom: 6px; }
    input[type="time"] {
      width: 100%;
      padding: 12px;
      font-size: 1.3rem;
      border-radius: 10px;
      border: 2px solid #334155;
      background: #0f172a;
      color: var(--text);
      text-align: center;
    }
    .btn-row { display: flex; gap: 10px; margin-top: 16px; }
    button {
      flex: 1;
      padding: 14px;
      border: none;
      border-radius: 12px;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: transform 0.15s, opacity 0.15s;
    }
    button:active { transform: scale(0.97); }
    .btn-primary { background: linear-gradient(135deg, var(--accent), #06b6d4); color: #0f172a; }
    .btn-danger { background: var(--danger); color: #fff; }
    .btn-success { background: var(--success); color: #0f172a; }
    .btn-secondary { background: #334155; color: var(--text); }
    .status {
      text-align: center;
      margin-top: 14px;
      font-size: 0.95rem;
      min-height: 1.4em;
    }
    .status.active { color: var(--accent); }
    .status.alarm { color: var(--danger); font-weight: 700; animation: pulse 1s infinite; }
    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.5; }
    }

    /* Challenge screen */
    #challenge {
      display: none;
      flex-direction: column;
      align-items: center;
      width: 100%;
      max-width: 480px;
      gap: 12px;
    }
    #challenge.active { display: flex; }
    #setup { display: block; }
    #setup.hidden { display: none; }

    .video-wrap {
      position: relative;
      width: 100%;
      aspect-ratio: 3/4;
      max-height: 55vh;
      background: #000;
      border-radius: 16px;
      overflow: hidden;
      border: 3px solid var(--accent);
    }
    video, canvas {
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      object-fit: cover;
      transform: scaleX(-1); /* mirror for natural feel */
    }
    canvas { pointer-events: none; }

    .progress-card {
      background: var(--card);
      border-radius: 14px;
      padding: 16px;
      width: 100%;
      text-align: center;
    }
    .phase-title {
      font-size: 1.1rem;
      font-weight: 600;
      margin-bottom: 8px;
      color: var(--accent);
    }
    .big-number {
      font-size: 2.8rem;
      font-weight: 800;
      line-height: 1;
    }
    .hint { color: var(--muted); font-size: 0.85rem; margin-top: 6px; }
    .bar 
...
