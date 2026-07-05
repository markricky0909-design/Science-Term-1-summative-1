<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Newton's Laws of Motion - Study Companion</title>
  <style>
    /* Premium Modern Dark & Slate-Gray Theme */
    :root {
      --bg-gradient: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
      --card-bg: #1e293b;
      --card-border: #334155;
      --accent-color: #3b82f6;
      --accent-glow: rgba(59, 130, 246, 0.5);
      --text-primary: #f8fafc;
      --text-secondary: #94a3b8;
      --text-muted: #64748b;
      --success-color: #10b981;
      --success-bg: rgba(16, 185, 129, 0.1);
      --error-color: #ef4444;
      --error-bg: rgba(239, 68, 68, 0.1);
      --font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background: var(--bg-gradient);
      color: var(--text-primary);
      font-family: var(--font-family);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 1rem;
      overflow-x: hidden;
    }

    /* Container holding everything safely */
    .app-container {
      width: 100%;
      max-width: 800px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
    }

    /* Main Premium Header Banner */
    header {
      background: rgba(30, 41, 59, 0.8);
      backdrop-filter: blur(12px);
      border: 1px solid var(--card-border);
      border-radius: 16px;
      padding: 1.5rem;
      text-align: center;
      box-shadow: 0 4px 30px rgba(0, 0, 0, 0.3);
    }

    header h1 {
      font-size: 1.75rem;
      font-weight: 800;
      letter-spacing: -0.025em;
      margin-bottom: 0.5rem;
      background: linear-gradient(to right, #3b82f6, #60a5fa, #a5f3fc);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    header p {
      font-size: 0.95rem;
      color: var(--text-secondary);
    }

    /* Tab Navigation System */
    .navigation-tabs {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0.5rem;
      background: rgba(15, 23, 42, 0.6);
      padding: 0.4rem;
      border-radius: 12px;
      border: 1px solid var(--card-border);
    }

    .tab-button {
      background: transparent;
      border: none;
      color: var(--text-secondary);
      font-size: 0.9rem;
      font-weight: 600;
      padding: 0.75rem 0.5rem;
      border-radius: 8px;
      cursor: pointer;
      transition: all 0.25s ease;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.5rem;
    }

    .tab-button:hover {
      color: var(--text-primary);
      background: rgba(255, 255, 255, 0.05);
    }

    .tab-button.active {
      background: var(--accent-color);
      color: #ffffff;
      box-shadow: 0 4px 12px var(--accent-glow);
    }

    /* Modes Display Wrapper */
    .mode-content {
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      border-radius: 16px;
      padding: 1.5rem;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
      min-height: 420px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      position: relative;
    }

    /* General Utility Elements */
    .progress-bar-container {
      width: 100%;
      height: 6px;
      background: rgba(255, 255, 255, 0.1);
      border-radius: 10px;
      margin-bottom: 1.25rem;
      overflow: hidden;
    }

    .progress-bar-fill {
      height: 100%;
      background: var(--accent-color);
      width: 0%;
      transition: width 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .mode-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 1.5rem;
      font-size: 0.85rem;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      color: var(--text-secondary);
      font-weight: 700;
    }

    .score-badge {
      background: rgba(59, 130, 246, 0.15);
      border: 1px solid var(--accent-color);
      color: #93c5fd;
      padding: 0.25rem 0.75rem;
      border-radius: 9999px;
      font-size: 0.8rem;
    }

    /* --- FLASHCARDS STYLES --- */
    .flashcard-stage {
      flex-grow: 1;
      perspective: 1200px;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 1.5rem 0;
      min-height: 250px;
    }

    .flashcard {
      width: 100%;
      height: 250px;
      position: relative;
      transform-style: preserve-3d;
      transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
      cursor: pointer;
    }

    .flashcard.flipped {
      transform: rotateY(180deg);
    }

    .card-face {
      position: absolute;
      width: 100%;
      height: 100%;
      backface-visibility: hidden;
      border-radius: 14px;
      padding: 1.75rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.15);
    }

    .card-front {
      background: radial-gradient(circle at top left, #1e293b, #0f172a);
      border: 2px solid var(--accent-color);
      color: var(--text-primary);
    }

    .card-front h3 {
      font-size: 1.5rem;
      font-weight: 700;
      line-height: 1.4;
      margin-bottom: 0.5rem;
    }

    .card-front span {
      font-size: 0.75rem;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.1em;
      margin-top: 1rem;
      border: 1px dashed var(--text-muted);
      padding: 0.25rem 0.6rem;
      border-radius: 4px;
    }

    .card-back {
      background: radial-gradient(circle at bottom right, #1e293b, #111827);
      border: 2px solid var(--card-border);
      color: var(--text-primary);
      transform: rotateY(180deg);
      overflow-y: auto;
    }

    .card-back p {
      font-size: 1.1rem;
      line-height: 1.6;
      font-weight: 500;
    }

    .card-back span {
      font-size: 0.75rem;
      color: var(--accent-color);
      text-transform: uppercase;
      letter-spacing: 0.1em;
      margin-top: 1rem;
      font-weight: bold;
    }

    .controls-row {
      display: flex;
      justify-content: space-between;
      gap: 0.75rem;
      margin-top: 1rem;
    }

    .btn {
      background: #334155;
      border: 1px solid var(--card-border);
      color: var(--text-primary);
      padding: 0.65rem 1.25rem;
      border-radius: 10px;
      font-weight: 600;
      font-size: 0.9rem;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.5rem;
      transition: all 0.2s ease;
      flex-grow: 1;
    }

    .btn:hover {
      background: #475569;
      border-color: #64748b;
    }

    .btn:active {
      transform: scale(0.97);
    }

    .btn-accent {
      background: var(--accent-color);
      border-color: var(--accent-color);
    }

    .btn-accent:hover {
      background: #2563eb;
      box-shadow: 0 4px 10px rgba(37, 99, 235, 0.4);
    }

    /* --- MULTIPLE CHOICE STYLES --- */
    .question-box {
      margin: 1.5rem 0;
      flex-grow: 1;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .question-text {
      font-size: 1.2rem;
      font-weight: 600;
      line-height: 1.5;
      color: var(--text-primary);
      margin-bottom: 1.5rem;
    }

    .choices-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 0.75rem;
    }

    .choice-btn {
      background: #0f172a;
      border: 1px solid var(--card-border);
      border-radius: 10px;
      color: var(--text-secondary);
      padding: 1rem;
      text-align: left;
      font-size: 0.95rem;
      font-weight: 500;
      cursor: pointer;
      transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
      display: flex;
      align-items: center;
      gap: 0.75rem;
      position: relative;
    }

    .choice-btn:hover {
      background: #1e293b;
      border-color: var(--text-muted);
      color: var(--text-primary);
    }

    .choice-badge {
      display: inline-flex;
      width: 24px;
      height: 24px;
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid var(--card-border);
      border-radius: 6px;
      justify-content: center;
      align-items: center;
      font-weight: 700;
      font-size: 0.8rem;
      color: var(--text-secondary);
      flex-shrink: 0;
    }

    .choice-btn.correct {
      background: var(--success-bg) !important;
      border-color: var(--success-color) !important;
      color: var(--success-color) !important;
    }
    
    .choice-btn.correct .choice-badge {
      background: var(--success-color);
      border-color: var(--success-color);
      color: #ffffff;
    }

    .choice-btn.incorrect {
      background: var(--error-bg) !important;
      border-color: var(--error-color) !important;
      color: var(--error-color) !important;
    }

    .choice-btn.incorrect .choice-badge {
      background: var(--error-color);
      border-color: var(--error-color);
      color: #ffffff;
    }

    .choices-grid.disabled .choice-btn {
      pointer-events: none;
      opacity: 0.6;
    }

    .choices-grid.disabled .choice-btn.correct,
    .choices-grid.disabled .choice-btn.incorrect {
      opacity: 1;
    }

    /* --- IDENTIFICATION MODE STYLES --- */
    .identification-stage {
      margin: 1.5rem 0;
      flex-grow: 1;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .definition-box {
      font-size: 1.15rem;
      line-height: 1.6;
      color: var(--text-primary);
      margin-bottom: 1.5rem;
      padding: 1.25rem;
      background: rgba(15, 23, 42, 0.4);
      border-radius: 12px;
      border-left: 4px solid var(--accent-color);
    }

    .input-container {
      position: relative;
      margin-bottom: 1.25rem;
    }

    .id-input {
      width: 100%;
      background: #0f172a;
      border: 2px solid var(--card-border);
      border-radius: 10px;
      color: var(--text-primary);
      padding: 0.9rem 1rem;
      font-size: 1rem;
      outline: none;
      transition: all 0.25s ease;
    }

    .id-input:focus {
      border-color: var(--accent-color);
      box-shadow: 0 0 0 3px var(--accent-glow);
    }

    .feedback-message {
      padding: 1rem;
      border-radius: 10px;
      font-weight: 600;
      font-size: 0.95rem;
      margin-bottom: 1.25rem;
      display: none;
      animation: fadeIn 0.3s ease;
    }

    .feedback-message.success {
      background: var(--success-bg);
      border: 1px solid var(--success-color);
      color: var(--success-color);
      display: block;
    }

    .feedback-message.error {
      background: var(--error-bg);
      border: 1px solid var(--error-color);
      color: var(--error-color);
      display: block;
    }

    /* Quick stats dashboard at the bottom */
    .stats-dashboard {
      background: rgba(30, 41, 59, 0.5);
      border: 1px solid var(--card-border);
      border-radius: 16px;
      padding: 1.25rem;
    }

    .stats-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0.75rem;
      text-align: center;
    }

    .stat-card {
      background: #0f172a;
      border: 1px solid var(--card-border);
      border-radius: 10px;
      padding: 0.75rem;
    }

    .stat-val {
      font-size: 1.25rem;
      font-weight: 700;
      color: var(--text-primary);
    }

    .stat-label {
      font-size: 0.75rem;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.05em;
      margin-top: 0.2rem;
    }

    footer {
      text-align: center;
      font-size: 0.8rem;
      color: var(--text-muted);
      margin-top: 1rem;
      margin-bottom: 2rem;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(5px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @media (max-width: 600px) {
      header h1 {
        font-size: 1.4rem;
      }
      .tab-button {
        font-size: 0.8rem;
        padding: 0.6rem 0.3rem;
      }
      .card-front h3 {
        font-size: 1.25rem;
      }
      .card-back p {
        font-size: 0.95rem;
      }
      .mode-content {
        padding: 1rem;
        min-height: auto;
      }
      .stats-grid {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>

  <div class="app-container">
    
    <header>
      <h1>Science 9 Companion</h1>
      <p>Newton's Laws of Motion: Inertia, Acceleration, & Interaction</p>
    </header>

    <nav class="navigation-tabs" role="tablist">
      <button class="tab-button active" onclick="switchMode('flashcard')" id="tab-flashcard" role="tab" aria-selected="true">
        <span>🎴</span> Flashcards
      </button>
      <button class="tab-button" onclick="switchMode('test')" id="tab-test" role="tab" aria-selected="false">
        <span>📝</span> MC Test
      </button>
      <button class="tab-button" onclick="switchMode('id')" id="tab-id" role="tab" aria-selected="false">
        <span>🧠</span> ID Quiz
      </button>
    </nav>

    <main class="mode-content" id="workspace">
      </main>

    <section class="stats-dashboard">
      <div class="stats-grid">
        <div class="stat-card">
          <div class="stat-val" id="global-lessons-count">0</div>
          <div class="stat-label">Total Notes</div>
        </div>
        <div class="stat-card">
          <div class="stat-val" id="global-completed-count">0%</div>
          <div class="stat-label">MC Test High</div>
        </div>
        <div class="stat-card">
          <div class="stat-val" id="global-accuracy-count">0%</div>
          <div class="stat-label">ID Quiz High</div>
        </div>
      </div>
    </section>

    <footer>
      Science 9 Summative Exam Preparation Application &bull; Purely Client-Side Design
    </footer>

  </div>

  <script>
    /**
     * ==========================================
     * Summative Dataset: Science 9 Newton's Laws
     * ==========================================
     * Feel free to insert/paste your custom objects or override this list.
     * Structured as:
     * - term: Displayed on Front of Flashcard, and must be entered EXACTLY in ID Mode.
     * - definition: Displayed on Back of Flashcard, and acts as the Question Prompt in Tests.
     */
    const studyData = [
      {
        term: "Law of Inertia",
        definition: "Newton's First Law of Motion. It states that an object at rest stays at rest, and an object in motion stays in motion at a constant speed and in a straight line, unless acted upon by an unbalanced force."
      },
      {
        term: "Inertia",
        definition: "The physical property of an object to resist changes in its state of motion. It is directly determined by the object's mass."
      },
      {
        term: "Mass",
        definition: "The measurement of the quantity of matter within an object. It represents the numerical measure of its inertia (more of this means more resistance)."
      },
      {
        term: "Unbalanced Force",
        definition: "A net force that is not equal to zero. This force is required to change an object's velocity, cause an acceleration, or modify its direction."
      },
      {
        term: "Friction",
        definition: "An external unbalanced force that acts against an object's motion, causing a sliding marble or rolling vehicle to eventually slow down and stop."
      },
      {
        term: "Law of Acceleration",
        definition: "Newton's Second Law of Motion. It states that an object accelerates when a net force acts on it, modeled by the formula: Acceleration = Net Force / Mass."
      },
      {
        term: "Acceleration",
        definition: "The physical rate of change in an object's velocity, which can represent a change in speed, a change in direction, or both."
      },
      {
        term: "Directly Proportional",
        definition: "The relationship between Force and Acceleration. When the net force acting upon a constant mass increases, the acceleration increases at the same rate."
      },
      {
        term: "Inversely Proportional",
        definition: "The relationship between Mass and Acceleration. When the mass of an object increases, the acceleration produced by a constant net force decreases."
      },
      {
        term: "Newton",
        definition: "The standard metric unit of force, equivalent to 1 kilogram meter per second squared (1 kg·m/s²)."
      },
      {
        term: "Law of Interaction",
        definition: "Newton's Third Law of Motion. It states that for every action force, there is an equal and opposite reaction force."
      },
      {
        term: "Action Force",
        definition: "The initial force exerted by one object onto another. It is equal in size and opposite in direction to its paired response."
      },
      {
        term: "Reaction Force",
        definition: "The simultaneous force exerted back by the second object onto the first, matching the magnitude but directed in reverse."
      },
      {
        term: "Different Objects",
        definition: "The reason action-reaction force pairs never cancel each other out. They always act simultaneously on separate targets rather than a single body."
      },
      {
        term: "Equal and Opposite",
        definition: "The description of paired forces under Newton's Third Law. They contain exactly matching numerical values of magnitude but project in reverse vectors."
      }
    ];

    // State Variables
    let currentMode = 'flashcard'; 
    let deck = [...studyData];
    let flashcardIndex = 0;
    
    let mcQuestions = [];
    let mcIndex = 0;
    let mcScore = 0;
    let mcSelected = false;

    let idQuestions = [];
    let idIndex = 0;
    let idScore = 0;
    let idAnswered = false;

    let mcHighScore = 0;
    let idHighScore = 0;

    // Load initial counts
    document.getElementById('global-lessons-count').innerText = studyData.length;

    // Switch Tabs Navigation
    function switchMode(mode) {
      currentMode = mode;
      
      document.querySelectorAll('.tab-button').forEach(btn => {
        btn.classList.remove('active');
        btn.setAttribute('aria-selected', 'false');
      });
      document.getElementById(`tab-${mode}`).classList.add('active');
      document.getElementById(`tab-${mode}`).setAttribute('aria-selected', 'true');

      if (mode === 'flashcard') {
        initFlashcardMode();
      } else if (mode === 'test') {
        initTestMode();
      } else if (mode === 'id') {
        initIdQuizMode();
      }
    }

    function shuffleArray(arr) {
      for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
      }
      return arr;
    }

    // --- MODE 1: FLASHCARDS BUSINESS LOGIC ---
    function initFlashcardMode() {
      if (deck.length === 0 && studyData.length > 0) {
        deck = [...studyData];
      }
      if (flashcardIndex >= deck.length) {
        flashcardIndex = 0;
      }
      renderFlashcard();
    }

    function renderFlashcard() {
      const workspace = document.getElementById('workspace');
      if (deck.length === 0) {
        workspace.innerHTML = `<div class="question-text">Your dataset is empty. Insert items into studyData.</div>`;
        return;
      }

      const activeItem = deck[flashcardIndex];
      const progressPercent = ((flashcardIndex + 1) / deck.length) * 100;

      workspace.innerHTML = `
        <div>
          <div class="progress-bar-container">
            <div class="progress-bar-fill" style="width: ${progressPercent}%"></div>
          </div>
          <div class="mode-header">
            <span>Flashcard Review</span>
            <span>Card ${flashcardIndex + 1} of ${deck.length}</span>
          </d
