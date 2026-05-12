import { useState, useEffect, useRef } from "react";

const questions = [
  {
    id: 1,
    text: "What do you most fear others would discover about you if they could see past the version of you that you present to the world — and why would that feel dangerous?",
    hint: "If your first answer feels too clean, go one layer deeper.",
    targets: ["enneagram: core fear / shame structure"],
  },
  {
    id: 2,
    text: "Describe a moment when you felt completely alive and like yourself. What were you doing, who were you with, and what specifically made it feel that way?",
    hint: "A real, specific moment — not a general category of experience.",
    targets: ["enneagram: core desire", "mbti: dominant function"],
  },
  {
    id: 3,
    text: "Think of a period in your life when you were under sustained, serious pressure — not a bad day, but weeks or months of it. How did you change? What did you do that you're not proud of, and what did you need that you couldn't find?",
    hint: "If your first answer feels too clean, go one layer deeper.",
    targets: ["enneagram: disintegration", "neuroticism (Big Five)"],
  },
  {
    id: 4,
    text: "Imagine you're in a group working on something that matters. What role do you gravitate toward without thinking about it — and what role, if no one fills it, quietly drives you mad? What does that tell you about yourself?",
    hint: "Both parts of the question matter equally.",
    targets: ["mbti: E/I, J/P", "enneagram: social style"],
  },
  {
    id: 5,
    text: "Walk me through a significant decision you've made — one that cost you something. How did you actually arrive at it, and how did you know it was right? What voices did you listen to, and which did you override?",
    hint: "Process matters more than outcome here.",
    targets: ["mbti: T/F, J/P", "conscientiousness (Big Five)"],
  },
  {
    id: 6,
    text: "What do you most need from the people close to you that you almost never ask for directly — and what stops you from asking? Where do you think that comes from?",
    hint: "The thing you hope someone will notice without you saying it.",
    targets: ["enneagram: attachment style", "agreeableness (Big Five)"],
  },
  {
    id: 7,
    text: "Looking across your whole life — not just now — what kinds of questions, ideas, or fields have pulled you in repeatedly? Is there a thread connecting them, and if so, what does that thread say about what you're actually looking for?",
    hint: "Patterns across years, not just current interests.",
    targets: ["mbti: S/N", "openness (Big Five)"],
  },
  {
    id: 8,
    text: "When you imagine a life that feels genuinely well lived — yours, not anyone else's — what does it contain? And just as importantly, what has it refused? What are the things you would consider a betrayal of yourself?",
    hint: "The refusals often say more than the desires.",
    targets: ["enneagram: core motivation", "values structure"],
  },
];

const minLength = 30;

export default function PersonalityTest() {
  const [stage, setStage] = useState("intro");
  const [answers, setAnswers] = useState({});
  const [currentQ, setCurrentQ] = useState(0);
  const [results, setResults] = useState(null);
  const [error, setError] = useState(null);
  const [charCounts, setCharCounts] = useState({});
  const textareaRef = useRef(null);

  useEffect(() => {
    if (stage === "test" && textareaRef.current) {
      textareaRef.current.focus();
    }
  }, [currentQ, stage]);

  const q = questions[currentQ];
  const currentAnswer = answers[currentQ + 1] || "";
  const currentValid = currentAnswer.trim().length >= minLength;
  const answeredCount = Object.values(answers).filter(a => a.trim().length >= minLength).length;
  const allAnswered = answeredCount === questions.length;

  const handleChange = (val) => {
    setAnswers(prev => ({ ...prev, [q.id]: val }));
    setCharCounts(prev => ({ ...prev, [q.id]: val.length }));
  };

  const next = () => {
    if (currentQ < questions.length - 1) setCurrentQ(c => c + 1);
  };
  const prev = () => {
    if (currentQ > 0) setCurrentQ(c => c - 1);
  };

  const buildPrompt = () => {
    const pairs = questions.map(q => `QUESTION: ${q.text}\nANSWER: ${answers[q.id] || "(no answer)"}`).join("\n\n");
    return `You are an expert psychologist trained in Enneagram typology, MBTI/Jungian cognitive functions, and Big Five personality research. Analyse the following open-ended responses and produce a personality profile.

${pairs}

Return ONLY a valid JSON object — no markdown fences, no preamble. Use this exact structure:

{
  "mbti": {
    "type": "e.g. INFJ",
    "confidence": "High | Medium | Low",
    "tagline": "a 6-10 word evocative description of this type",
    "what_it_means": "2-3 sentences explaining what this type actually means in lived experience — not a textbook definition",
    "insight": "1-2 sentences of specific insight drawn from THIS person's answers, not generic type description",
    "explore": "One specific MBTI resource or direction to explore further (book, concept, or question to sit with)"
  },
  "enneagram": {
    "type": "e.g. Type 4",
    "wing": "e.g. 4w5 or 4w3",
    "confidence": "High | Medium | Low",
    "tagline": "a 6-10 word evocative description",
    "core_fear": "One precise sentence",
    "core_desire": "One precise sentence",
    "what_it_means": "2-3 sentences on lived experience of this type",
    "insight": "1-2 sentences specific to this person's answers",
    "explore": "One direction to explore — a book, a concept, or a reflective question"
  },
  "bigFive": {
    "openness": {
      "score": 0-100,
      "label": "Very High | High | Moderate | Low | Very Low",
      "what_it_means": "1-2 sentences on what this score means in practice",
      "insight": "One sentence specific to this person"
    },
    "conscientiousness": {
      "score": 0-100,
      "label": "Very High | High | Moderate | Low | Very Low",
      "what_it_means": "1-2 sentences",
      "insight": "One sentence specific to this person"
    },
    "extraversion": {
      "score": 0-100,
      "label": "Very High | High | Moderate | Low | Very Low",
      "what_it_means": "1-2 sentences",
      "insight": "One sentence specific to this person"
    },
    "agreeableness": {
      "score": 0-100,
      "label": "Very High | High | Moderate | Low | Very Low",
      "what_it_means": "1-2 sentences",
      "insight": "One sentence specific to this person"
    },
    "neuroticism": {
      "score": 0-100,
      "label": "Very High | High | Moderate | Low | Very Low",
      "what_it_means": "1-2 sentences",
      "insight": "One sentence specific to this person"
    }
  },
  "synthesis": {
    "headline": "A single evocative sentence that captures the whole person",
    "convergence": "2-3 sentences on where all three frameworks agree and what that convergence reveals",
    "tension": "1-2 sentences on where the frameworks diverge or create productive tension",
    "one_question": "The single most important question this person should sit with, based on everything above"
  }
}`;
  };

  const submit = async () => {
    setStage("loading");
    setError(null);
    try {
      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 1000,
          messages: [{ role: "user", content: buildPrompt() }],
        }),
      });
      const data = await res.json();
      const text = data.content?.map(b => b.text || "").join("") || "";
      const clean = text.replace(/```json|```/g, "").trim();
      const parsed = JSON.parse(clean);
      setResults(parsed);
      setStage("results");
    } catch (e) {
      setError("Analysis failed. Please try again.");
      setStage("test");
    }
  };

  const restart = () => {
    setAnswers({});
    setResults(null);
    setError(null);
    setCurrentQ(0);
    setCharCounts({});
    setStage("intro");
  };

  const progress = (answeredCount / questions.length) * 100;

  return (
    <div style={s.root}>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400;1,600&family=Lora:ital,wght@0,400;0,500;1,400&display=swap');
        * { box-sizing: border-box; }
        ::selection { background: #c8a96e33; }
        textarea { resize: none; }
        textarea::placeholder { color: #4a4a4a; }
        ::-webkit-scrollbar { width: 4px; }
        ::-webkit-scrollbar-track { background: #0a0a0a; }
        ::-webkit-scrollbar-thumb { background: #2a2a2a; }
        @keyframes fadeUp {
          from { opacity: 0; transform: translateY(16px); }
          to { opacity: 1; transform: translateY(0); }
        }
        @keyframes spin { to { transform: rotate(360deg); } }
        @keyframes pulse { 0%,100% { opacity:0.4; } 50% { opacity:1; } }
        .fadeup { animation: fadeUp 0.6s ease both; }
        .bar-fill { transition: width 1s cubic-bezier(0.4,0,0.2,1); }
      `}</style>

      {/* Background texture */}
      <div style={s.bg} />

      {/* INTRO */}
      {stage === "intro" && (
        <div className="fadeup" style={s.introWrap}>
          <div style={s.introEyebrow}>A SELF-INQUIRY</div>
          <h1 style={s.introTitle}>Know<br /><em>Thyself</em></h1>
          <div style={s.introDivider} />
          <p style={s.introBody}>
            Eight open questions. Honest answers.<br />
            Your profile across Enneagram, MBTI, and Big Five.
          </p>
          <p style={s.introMeta}>
            Write freely — longer answers yield sharper insight.<br />
            No right or wrong. Only true or not quite true.
          </p>
          <div style={s.introFrameworks}>
            {["Enneagram", "MBTI", "Big Five"].map(f => (
              <span key={f} style={s.frameworkTag}>{f}</span>
            ))}
          </div>
          <button style={s.btnGold} onClick={() => setStage("test")}>
            Begin the inquiry →
          </button>
        </div>
      )}

      {/* TEST */}
      {stage === "test" && (
        <div style={s.testWrap}>
          {/* Progress */}
          <div style={s.progressArea}>
            <div style={s.progressTrack}>
              <div className="bar-fill" style={{ ...s.progressFill, width: `${progress}%` }} />
            </div>
            <div style={s.progressMeta}>
              <span style={s.progressLabel}>Question {currentQ + 1} of {questions.length}</span>
              <span style={s.progressLabel}>{answeredCount} answered</span>
            </div>
          </div>

          {/* Question card */}
          <div className="fadeup" key={currentQ} style={s.qCard}>
            <div style={s.qNumber}>0{currentQ + 1}</div>
            <p style={s.qText}>{q.text}</p>
            <p style={s.qHint}>{q.hint}</p>

            <textarea
              ref={textareaRef}
              value={currentAnswer}
              onChange={e => handleChange(e.target.value)}
              placeholder="Write your answer here..."
              style={s.textarea}
              rows={6}
            />

            <div style={s.charRow}>
              <span style={{ ...s.charCount, color: currentValid ? "#c8a96e" : "#444" }}>
                {currentValid ? "✓ enough to analyse" : `${Math.max(0, minLength - currentAnswer.trim().length)} more characters`}
              </span>
            </div>
          </div>

          {/* Navigation */}
          <div style={s.navRow}>
            <button style={s.btnGhost} onClick={prev} disabled={currentQ === 0}>
              ← Previous
            </button>
            {currentQ < questions.length - 1 ? (
              <button
                style={{ ...s.btnGold, opacity: currentValid ? 1 : 0.4 }}
                onClick={next}
                disabled={!currentValid}
              >
                Next →
              </button>
            ) : null}
          </div>

          {/* Submit */}
          {allAnswered && (
            <div style={{ textAlign: "center", marginTop: "1rem" }}>
              <button style={s.btnGold} onClick={submit}>
                Analyse my profile →
              </button>
            </div>
          )}

          {/* Dot nav */}
          <div style={s.dotNav}>
            {questions.map((_, i) => {
              const ans = answers[i + 1] || "";
              const done = ans.trim().length >= minLength;
              return (
                <button
                  key={i}
                  onClick={() => setCurrentQ(i)}
                  style={{
                    ...s.dot,
                    background: i === currentQ ? "#c8a96e" : done ? "#5a4a2a" : "#222",
                    border: i === currentQ ? "1px solid #c8a96e" : "1px solid #2a2a2a",
                  }}
                  title={`Question ${i + 1}`}
                />
              );
            })}
          </div>

          {error && <p style={s.error}>{error}</p>}
        </div>
      )}

      {/* LOADING */}
      {stage === "loading" && (
        <div className="fadeup" style={s.loadingWrap}>
          <div style={s.loadingOrb} />
          <p style={s.loadingTitle}>Reading between the lines</p>
          <p style={s.loadingBody}>Cross-referencing your answers across<br />three frameworks of self-understanding…</p>
        </div>
      )}

      {/* RESULTS */}
      {stage === "results" && results && (
        <div style={s.resultsWrap}>
          {/* Synthesis headline */}
          <div className="fadeup" style={s.synthesisHero}>
            <div style={s.introEyebrow}>YOUR PROFILE</div>
            <p style={s.synthesisHeadline}>"{results.synthesis.headline}"</p>
          </div>

          {/* MBTI */}
          <ResultCard
            color="#c8a96e"
            framework="MBTI"
            type={results.mbti.type}
            wing={null}
            confidence={results.mbti.confidence}
            tagline={results.mbti.tagline}
            sections={[
              { label: "What this means", text: results.mbti.what_it_means },
              { label: "From your answers", text: results.mbti.insight },
              { label: "Explore further", text: results.mbti.explore },
            ]}
          />

          {/* Enneagram */}
          <ResultCard
            color="#7eb8a4"
            framework="ENNEAGRAM"
            type={results.enneagram.type}
            wing={results.enneagram.wing}
            confidence={results.enneagram.confidence}
            tagline={results.enneagram.tagline}
            sections={[
              { label: "Core fear", text: results.enneagram.core_fear },
              { label: "Core desire", text: results.enneagram.core_desire },
              { label: "What this means", text: results.enneagram.what_it_means },
              { label: "From your answers", text: results.enneagram.insight },
              { label: "Explore further", text: results.enneagram.explore },
            ]}
          />

          {/* Big Five */}
          <div style={{ ...s.card, borderColor: "#7a7af7" }}>
            <div style={{ ...s.cardFramework, color: "#7a7af7" }}>BIG FIVE · OCEAN</div>
            {Object.entries(results.bigFive).map(([trait, data]) => (
              <div key={trait} style={s.traitBlock}>
                <div style={s.traitHeader}>
                  <span style={s.traitName}>{trait.charAt(0).toUpperCase() + trait.slice(1)}</span>
                  <span style={{ ...s.traitLabel, color: "#7a7af7" }}>{data.label} · {data.score}/100</span>
                </div>
                <div style={s.barTrack}>
                  <div className="bar-fill" style={{ ...s.barFill, width: `${data.score}%`, background: "#7a7af7" }} />
                </div>
                <p style={s.traitMeaning}>{data.what_it_means}</p>
                <p style={s.traitInsight}>↳ {data.insight}</p>
              </div>
            ))}
          </div>

          {/* Synthesis */}
          <div style={{ ...s.card, borderColor: "#444", background: "#0c0c0c" }}>
            <div style={s.cardFramework}>SYNTHESIS</div>
            <div style={s.synthSection}>
              <div style={s.synthLabel}>Where the frameworks converge</div>
              <p style={s.synthText}>{results.synthesis.convergence}</p>
            </div>
            <div style={s.synthSection}>
              <div style={s.synthLabel}>Where they create tension</div>
              <p style={s.synthText}>{results.synthesis.tension}</p>
            </div>
            <div style={{ ...s.synthSection, borderTop: "1px solid #222", paddingTop: "1.5rem", marginTop: "0.5rem" }}>
              <div style={s.synthLabel}>The question to sit with</div>
              <p style={{ ...s.synthText, fontStyle: "italic", fontSize: "1.05rem", color: "#c8a96e", lineHeight: 1.8 }}>
                "{results.synthesis.one_question}"
              </p>
            </div>
          </div>

          <div style={{ textAlign: "center", paddingBottom: "3rem" }}>
            <p style={{ color: "#444", fontSize: "0.75rem", marginBottom: "1.5rem", letterSpacing: "0.05em" }}>
              These results are directional, not diagnostic.<br />
              Use them as a starting point for deeper inquiry.
            </p>
            <button style={s.btnGhost} onClick={restart}>↩ Start over</button>
          </div>
        </div>
      )}
    </div>
  );
}

function ResultCard({ color, framework, type, wing, confidence, tagline, sections }) {
  return (
    <div className="fadeup" style={{ ...s.card, borderColor: color }}>
      <div style={{ ...s.cardFramework, color }}>{framework}</div>
      <div style={s.cardTypeRow}>
        <span style={{ ...s.cardType, color }}>{wing || type}</span>
        <span style={s.cardConfidence}>confidence: {confidence}</span>
      </div>
      <p style={s.cardTagline}>"{tagline}"</p>
      <div style={s.cardDivider} />
      {sections.map((sec, i) => (
        <div key={i} style={s.cardSection}>
          <div style={{ ...s.cardSectionLabel, color }}>{sec.label}</div>
          <p style={s.cardSectionText}>{sec.text}</p>
        </div>
      ))}
    </div>
  );
}

const s = {
  root: {
    minHeight: "100vh",
    background: "#080808",
    color: "#d4cfc7",
    fontFamily: "'Lora', Georgia, serif",
    display: "flex",
    flexDirection: "column",
    alignItems: "center",
    padding: "3rem 1.25rem",
    position: "relative",
  },
  bg: {
    position: "fixed",
    inset: 0,
    background: "radial-gradient(ellipse 80% 60% at 50% 0%, #1a1408 0%, #080808 70%)",
    pointerEvents: "none",
    zIndex: 0,
  },
  introWrap: {
    position: "relative",
    zIndex: 1,
    maxWidth: 520,
    width: "100%",
    display: "flex",
    flexDirection: "column",
    alignItems: "center",
    gap: "1.25rem",
    textAlign: "center",
    paddingTop: "4rem",
  },
  introEyebrow: {
    fontSize: "0.6rem",
    letterSpacing: "0.3em",
    color: "#c8a96e",
    fontFamily: "'Lora', serif",
    fontStyle: "normal",
  },
  introTitle: {
    fontFamily: "'Playfair Display', Georgia, serif",
    fontSize: "clamp(3.5rem, 12vw, 6rem)",
    fontWeight: 400,
    lineHeight: 1.0,
    margin: 0,
    color: "#e8e0d0",
  },
  introDivider: {
    width: 40,
    height: 1,
    background: "#c8a96e",
    opacity: 0.5,
  },
  introBody: {
    fontSize: "1.05rem",
    color: "#a09880",
    lineHeight: 1.8,
    margin: 0,
  },
  introMeta: {
    fontSize: "0.8rem",
    color: "#504840",
    lineHeight: 1.7,
    margin: 0,
  },
  introFrameworks: {
    display: "flex",
    gap: "0.75rem",
    flexWrap: "wrap",
    justifyContent: "center",
  },
  frameworkTag: {
    fontSize: "0.65rem",
    letterSpacing: "0.15em",
    color: "#806040",
    border: "1px solid #2a2010",
    padding: "0.3rem 0.8rem",
  },
  btnGold: {
    background: "#c8a96e",
    color: "#080808",
    border: "none",
    padding: "0.85rem 2.5rem",
    fontSize: "0.85rem",
    letterSpacing: "0.1em",
    cursor: "pointer",
    fontFamily: "'Lora', serif",
    fontWeight: 500,
    marginTop: "0.5rem",
  },
  btnGhost: {
    background: "transparent",
    color: "#605040",
    border: "1px solid #2a2010",
    padding: "0.65rem 1.75rem",
    fontSize: "0.8rem",
    cursor: "pointer",
    fontFamily: "'Lora', serif",
    letterSpacing: "0.05em",
  },
  testWrap: {
    position: "relative",
    zIndex: 1,
    maxWidth: 620,
    width: "100%",
    display: "flex",
    flexDirection: "column",
    gap: "1.5rem",
    paddingTop: "1rem",
  },
  progressArea: {
    display: "flex",
    flexDirection: "column",
    gap: "0.5rem",
  },
  progressTrack: {
    height: "1px",
    background: "#1a1a1a",
    width: "100%",
  },
  progressFill: {
    height: "100%",
    background: "#c8a96e",
  },
  progressMeta: {
    display: "flex",
    justifyContent: "space-between",
  },
  progressLabel: {
    fontSize: "0.65rem",
    color: "#444",
    letterSpacing: "0.1em",
  },
  qCard: {
    background: "#0e0e0e",
    border: "1px solid #1a1a1a",
    padding: "2.5rem",
    display: "flex",
    flexDirection: "column",
    gap: "1rem",
  },
  qNumber: {
    fontSize: "0.6rem",
    letterSpacing: "0.25em",
    color: "#c8a96e",
    opacity: 0.7,
  },
  qText: {
    fontFamily: "'Playfair Display', serif",
    fontSize: "1.25rem",
    fontWeight: 400,
    lineHeight: 1.6,
    margin: 0,
    color: "#e0d8cc",
  },
  qHint: {
    fontSize: "0.78rem",
    color: "#484038",
    fontStyle: "italic",
    margin: 0,
    lineHeight: 1.6,
  },
  textarea: {
    width: "100%",
    background: "#080808",
    border: "1px solid #1e1e1e",
    color: "#c8c0b4",
    fontFamily: "'Lora', serif",
    fontSize: "0.9rem",
    lineHeight: 1.8,
    padding: "1rem 1.25rem",
    outline: "none",
    marginTop: "0.5rem",
  },
  charRow: {
    display: "flex",
    justifyContent: "flex-end",
  },
  charCount: {
    fontSize: "0.7rem",
    letterSpacing: "0.05em",
    transition: "color 0.3s",
  },
  navRow: {
    display: "flex",
    justifyContent: "space-between",
    alignItems: "center",
  },
  dotNav: {
    display: "flex",
    gap: "0.5rem",
    justifyContent: "center",
    flexWrap: "wrap",
  },
  dot: {
    width: 8,
    height: 8,
    borderRadius: "50%",
    cursor: "pointer",
    transition: "all 0.2s",
    padding: 0,
  },
  error: {
    color: "#c87060",
    fontSize: "0.8rem",
    textAlign: "center",
  },
  loadingWrap: {
    position: "relative",
    zIndex: 1,
    display: "flex",
    flexDirection: "column",
    alignItems: "center",
    gap: "2rem",
    paddingTop: "6rem",
    textAlign: "center",
  },
  loadingOrb: {
    width: 48,
    height: 48,
    border: "1px solid #1a1a1a",
    borderTop: "1px solid #c8a96e",
    borderRadius: "50%",
    animation: "spin 2s linear infinite",
  },
  loadingTitle: {
    fontFamily: "'Playfair Display', serif",
    fontSize: "1.5rem",
    fontStyle: "italic",
    color: "#c8c0b4",
    margin: 0,
  },
  loadingBody: {
    fontSize: "0.85rem",
    color: "#484038",
    lineHeight: 1.8,
    margin: 0,
  },
  resultsWrap: {
    position: "relative",
    zIndex: 1,
    maxWidth: 640,
    width: "100%",
    display: "flex",
    flexDirection: "column",
    gap: "1.5rem",
    paddingTop: "1rem",
  },
  synthesisHero: {
    textAlign: "center",
    padding: "2rem 0",
    display: "flex",
    flexDirection: "column",
    gap: "1.25rem",
    alignItems: "center",
  },
  synthesisHeadline: {
    fontFamily: "'Playfair Display', serif",
    fontSize: "clamp(1.1rem, 3vw, 1.5rem)",
    fontStyle: "italic",
    color: "#e0d8cc",
    lineHeight: 1.6,
    margin: 0,
    maxWidth: 500,
  },
  card: {
    background: "#0c0c0c",
    border: "1px solid #1a1a1a",
    borderLeft: "2px solid",
    padding: "2rem",
    display: "flex",
    flexDirection: "column",
    gap: "1rem",
  },
  cardFramework: {
    fontSize: "0.55rem",
    letterSpacing: "0.25em",
    color: "#555",
  },
  cardTypeRow: {
    display: "flex",
    alignItems: "baseline",
    gap: "1rem",
    flexWrap: "wrap",
  },
  cardType: {
    fontFamily: "'Playfair Display', serif",
    fontSize: "2.25rem",
    fontWeight: 400,
    lineHeight: 1,
  },
  cardConfidence: {
    fontSize: "0.65rem",
    color: "#444",
    letterSpacing: "0.1em",
  },
  cardTagline: {
    fontStyle: "italic",
    color: "#887060",
    fontSize: "0.9rem",
    margin: 0,
    lineHeight: 1.6,
  },
  cardDivider: {
    height: 1,
    background: "#1a1a1a",
  },
  cardSection: {
    display: "flex",
    flexDirection: "column",
    gap: "0.35rem",
  },
  cardSectionLabel: {
    fontSize: "0.6rem",
    letterSpacing: "0.2em",
    textTransform: "uppercase",
  },
  cardSectionText: {
    fontSize: "0.88rem",
    color: "#a09080",
    lineHeight: 1.75,
    margin: 0,
  },
  traitBlock: {
    display: "flex",
    flexDirection: "column",
    gap: "0.4rem",
    paddingBottom: "1.25rem",
    borderBottom: "1px solid #131313",
    marginBottom: "0.25rem",
  },
  traitHeader: {
    display: "flex",
    justifyContent: "space-between",
    alignItems: "baseline",
    flexWrap: "wrap",
    gap: "0.5rem",
  },
  traitName: {
    fontSize: "0.8rem",
    color: "#c8c0b4",
    letterSpacing: "0.05em",
  },
  traitLabel: {
    fontSize: "0.65rem",
    letterSpacing: "0.08em",
  },
  barTrack: {
    height: "2px",
    background: "#1a1a1a",
    width: "100%",
  },
  barFill: {
    height: "100%",
  },
  traitMeaning: {
    fontSize: "0.83rem",
    color: "#807060",
    lineHeight: 1.7,
    margin: 0,
  },
  traitInsight: {
    fontSize: "0.8rem",
    color: "#504840",
    lineHeight: 1.6,
    margin: 0,
    fontStyle: "italic",
  },
  synthSection: {
    display: "flex",
    flexDirection: "column",
    gap: "0.5rem",
  },
  synthLabel: {
    fontSize: "0.6rem",
    letterSpacing: "0.2em",
    color: "#444",
    textTransform: "uppercase",
  },
  synthText: {
    fontSize: "0.9rem",
    color: "#908070",
    lineHeight: 1.8,
    margin: 0,
  },
};
