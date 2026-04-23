<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>The Logic Inside Neurons: A McCulloch–Pitts Machine</title>
<style>
  :root {
    color-scheme: dark;
    font-family: Inter, system-ui, sans-serif;
    --bg: #07080f;
    --panel: rgba(10, 14, 28, 0.92);
    --panel-soft: rgba(16, 22, 38, 0.95);
    --text: #e8f1ff;
    --muted: #8da3c7;
    --accent: #5fe8ff;
    --accent2: #6bf58c;
    --danger: #ff5b7a;
    --border: rgba(130, 163, 213, 0.18);
    --shadow: 0 30px 120px rgba(0, 0, 0, 0.35);
  }

  * {
    box-sizing: border-box;
  }

  body {
    margin: 0;
    min-height: 100vh;
    background: radial-gradient(circle at top, rgba(30, 80, 160, 0.14), transparent 20%),
      radial-gradient(circle at bottom right, rgba(40, 255, 180, 0.06), transparent 18%),
      linear-gradient(180deg, #05070d 0%, #090d16 35%, #05060a 100%);
    color: var(--text);
    overflow-x: hidden;
  }

  .page {
    display: grid;
    grid-template-columns: minmax(320px, 380px) 1fr;
    gap: 24px;
    padding: 24px;
    min-height: 100vh;
  }

  .hero {
    grid-column: 1 / -1;
    padding: 24px 28px;
    border-radius: 26px;
    background: rgba(9, 13, 23, 0.92);
    box-shadow: var(--shadow);
    border: 1px solid rgba(120, 180, 255, 0.08);
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: "";
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at 20% 40%, rgba(95, 232, 255, 0.12), transparent 26%),
      radial-gradient(circle at 80% 20%, rgba(107, 245, 140, 0.08), transparent 20%);
    pointer-events: none;
  }

  .hero-content {
    position: relative;
    z-index: 1;
  }

  h1 {
    font-size: clamp(2.2rem, 3.3vw, 3.6rem);
    margin: 0;
    line-height: 1.05;
  }

  p.lead {
    margin: 18px 0 0;
    max-width: 760px;
    color: var(--muted);
    font-size: 1rem;
    line-height: 1.8;
  }

  .cards {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 14px;
    margin-top: 22px;
  }

  .card {
    padding: 18px;
    border-radius: 20px;
    background: rgba(12, 17, 30, 0.85);
    border: 1px solid rgba(120, 180, 255, 0.08);
    backdrop-filter: blur(12px);
  }

  .card strong {
    display: block;
    font-size: 0.94rem;
    margin-bottom: 10px;
    color: #c1d6ff;
  }

  .page > section {
    display: flex;
    flex-direction: column;
    gap: 18px;
  }

  .panel {
    border-radius: 26px;
    background: var(--panel);
    box-shadow: var(--shadow);
    border: 1px solid rgba(255, 255, 255, 0.06);
    overflow: hidden;
  }

  .panel-header {
    padding: 18px 22px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 10px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.06);
  }

  .panel-header h2 {
    margin: 0;
    font-size: 1.05rem;
  }

  .panel-body {
    padding: 20px;
    display: grid;
    gap: 18px;
  }

  .controls,
  .insights,
  .logic-view,
  .build-buttons {
    display: grid;
    gap: 14px;
  }

  .button-group {
    display: grid;
    gap: 10px;
  }

  button,
  .toggle-button,
  input[type="range"] {
    font: inherit;
  }

  button,
  .toggle-button {
    border: none;
    cursor: pointer;
    border-radius: 16px;
    padding: 14px 16px;
    background: rgba(14, 19, 34, 0.95);
    color: var(--text);
    transition: transform 0.18s ease, background 0.18s ease, box-shadow 0.18s ease;
    box-shadow: inset 0 0 0 1px rgba(255,255,255,0.05), 0 18px 45px rgba(0,0,0,0.18);
  }

  button:hover,
  .toggle-button:hover {
    transform: translateY(-1px);
    background: rgba(28, 39, 68, 0.98);
  }

  button.active,
  .toggle-button.active {
    background: linear-gradient(135deg, rgba(95, 232, 255, 0.2), rgba(107, 245, 140, 0.18));
    box-shadow: 0 0 0 1px rgba(95, 232, 255, 0.16), 0 20px 40px rgba(12, 19, 34, 0.4);
  }

  .row {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
  }

  .row > * {
    flex: 1 1 150px;
    min-width: 120px;
  }

  .status-bar {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
    align-items: center;
  }

  .status-pill {
    padding: 10px 14px;
    border-radius: 999px;
    background: rgba(255,255,255,0.05);
    color: var(--muted);
    font-size: 0.92rem;
  }

  .status-pill strong {
    color: var(--text);
  }

  .toggle-control {
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .toggle-switch {
    width: 46px;
    height: 24px;
    border-radius: 999px;
    background: rgba(255,255,255,0.12);
    position: relative;
    transition: background 0.2s ease;
  }

  .toggle-switch::after {
    content: "";
    position: absolute;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background: var(--text);
    top: 2px;
    left: 3px;
    transition: transform 0.2s ease;
  }

  .toggle-switch.active {
    background: linear-gradient(135deg, #5fe8ff, #6bf58c);
  }

  .toggle-switch.active::after {
    transform: translateX(22px);
    background: #071021;
  }

  .insights p,
  .logic-view p,
  .logic-view pre {
    margin: 0;
    line-height: 1.6;
  }

  .insights {
    padding: 18px;
    border-radius: 22px;
    background: rgba(3, 8, 18, 0.9);
    border: 1px solid rgba(95, 232, 255, 0.08);
  }

  .insights p {
    font-size: 0.95rem;
    color: var(--text);
  }

  .build-buttons {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .build-buttons button {
    min-height: 52px;
  }

  .canvas-panel {
    position: relative;
    min-height: 740px;
    border-radius: 32px;
    overflow: hidden;
    background: radial-gradient(circle at center, rgba(10, 30, 70, 0.16), transparent 35%),
      linear-gradient(180deg, rgba(12, 18, 35, 0.9), rgba(3, 6, 14, 0.72));
    border: 1px solid rgba(255,255,255,0.06);
    box-shadow: var(--shadow);
  }

  canvas {
    width: 100%;
    height: 100%;
    display: block;
  }

  .hint {
    color: var(--muted);
    font-size: 0.92rem;
  }

  .small-label {
    color: #9ab0d8;
    font-size: 0.88rem;
  }

  .selected-neuron {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 16px;
    padding: 16px;
    border-radius: 20px;
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
  }

  .selected-neuron span {
    font-size: 0.96rem;
    color: var(--muted);
  }

  .selected-neuron strong {
    color: #fff;
  }

  .slider-row {
    display: grid;
    gap: 10px;
  }

  input[type="range"] {
    width: 100%;
    accent-color: #5fe8ff;
  }

  .footer-note {
    margin-top: 30px;
    color: rgba(255,255,255,0.56);
    font-size: 0.92rem;
  }

  .node-label {
    font-size: 0.8rem;
    letter-spacing: 0.04em;
    text-transform: uppercase;
    color: #9ab0d8;
  }

  @media (max-width: 1140px) {
    .page {
      grid-template-columns: 1fr;
    }
  }

  @media (max-width: 760px) {
    .hero,
    .panel {
      border-radius: 22px;
    }

    .canvas-panel {
      min-height: 620px;
    }
  }
</style>
</head>
<body>
<div class="page">
  <section class="hero">
    <div class="hero-content">
      <div class="node-label">Interactive visualization</div>
      <h1>The Logic Inside Neurons: A McCulloch–Pitts Machine</h1>
      <p class="lead">Explore how simple binary units connected by excitation and inhibition produce rigid logic. Click inputs, step through time, and build surprising circuits that reveal how inhibition overrides excitation and how structure matters more than biology.</p>
      <div class="cards">
        <div class="card"><strong>Core rule</strong> Firing occurs when excitatory inputs meet threshold and no inhibitory input is active.</div>
        <div class="card"><strong>Modes</strong> Switch between strict logical dynamics and a smoother biological activation view.</div>
        <div class="card"><strong>Prebuilt networks</strong> AND, OR, NOT, XOR, memory loop, paradox circuit.</div>
        <div class="card"><strong>Live logic</strong> Select any neuron to see its evolving expression.</div>
      </div>
    </div>
  </section>

  <section class="panel controls">
    <div class="panel-header">
      <div>
        <h2>Simulation controls</h2>
        <div class="small-label">Step through logic, run continuously, or reset circuits.</div>
      </div>
      <div class="status-pill"><strong>Tick:</strong> <span id="stepCounter">0</span></div>
    </div>
    <div class="panel-body">
      <div class="row">
        <button id="stepButton">Step</button>
        <button id="resetButton">Reset</button>
      </div>
      <div class="toggle-control">
        <span>Auto-run</span>
        <div id="runToggle" class="toggle-switch"></div>
      </div>
      <div class="toggle-control">
        <span>Biological vs Logical Mode</span>
        <div id="modeToggle" class="toggle-switch"></div>
      </div>
      <div class="build-buttons">
        <button data-build="and">AND Gate</button>
        <button data-build="or">OR Gate</button>
        <button data-build="not">NOT Gate</button>
        <button data-build="xor">XOR Circuit</button>
        <button data-build="memory">Memory Loop</button>
        <button data-build="paradox">Paradox Circuit</button>
      </div>
      <div class="build-buttons" style="grid-template-columns: repeat(3, minmax(0, 1fr));">
        <button id="addNeuronButton">Add Neuron</button>
        <button id="addInputButton">Add Input</button>
        <button id="removeNeuronButton">Remove Selected</button>
      </div>
      <div class="row" style="align-items: center; gap: 10px;">
        <span class="small-label">Connection type:</span>
        <select id="connectionType" style="flex: 1; min-width: 150px; padding: 12px 14px; border-radius: 14px; border: 1px solid rgba(255,255,255,0.12); background: rgba(10, 16, 28, 0.95); color: var(--text);">
          <option value="exc">Excitatory</option>
          <option value="inh">Inhibitory</option>
        </select>
        <button id="connectButton">Connect Selection</button>
      </div>
      <div class="hint" id="constructionHint">Click input nodes in the canvas to toggle ON/OFF. Turn on construction mode to drag nodes and connect them.</div>
    </div>
  </section>

  <section class="panel insights">
    <div class="panel-header">
      <h2>Key insights</h2>
    </div>
    <div class="panel-body">
      <p id="insightText">This network behaves like a logical gate. Inhibition dominates: one OFF signal cancels all.</p>
    </div>
  </section>

  <section class="panel logic-view">
    <div class="panel-header">
      <h2>Live logic view</h2>
      <span class="small-label">Selected neuron</span>
    </div>
    <div class="panel-body">
      <div class="selected-neuron">
        <div>
          <span>Neuron ID:</span>
          <strong id="selectedId">None</strong>
        </div>
        <div>
          <span>State:</span>
          <strong id="selectedState">—</strong>
        </div>
      </div>
      <div>
        <p id="liveExpression">Select a neuron to inspect its logic expression.</p>
      </div>
      <div class="slider-row">
        <label class="small-label" for="thresholdSlider">Threshold: <span id="thresholdValue">2</span></label>
        <input id="thresholdSlider" type="range" min="1" max="5" value="2" />
      </div>
      <div class="toggle-control">
        <label class="small-label"><input id="constructionMode" type="checkbox" /> Construction mode</label>
      </div>
    </div>
  </section>

  <section class="canvas-panel">
    <canvas id="networkCanvas"></canvas>
  </section>

  <div class="footer-note">Try the paradox circuit to see why one inhibitory signal can silence an entire chain.</div>
</div>

<script>
const canvas = document.getElementById('networkCanvas');
const ctx = canvas.getContext('2d');
const stepButton = document.getElementById('stepButton');
const resetButton = document.getElementById('resetButton');
const runToggle = document.getElementById('runToggle');
const modeToggle = document.getElementById('modeToggle');
const insightText = document.getElementById('insightText');
const stepCounter = document.getElementById('stepCounter');
const selectedId = document.getElementById('selectedId');
const selectedState = document.getElementById('selectedState');
const liveExpression = document.getElementById('liveExpression');
const thresholdSlider = document.getElementById('thresholdSlider');
const thresholdValue = document.getElementById('thresholdValue');
const constructionMode = document.getElementById('constructionMode');
const buildButtons = document.querySelectorAll('[data-build]');
const addNeuronButton = document.getElementById('addNeuronButton');
const addInputButton = document.getElementById('addInputButton');
const removeNeuronButton = document.getElementById('removeNeuronButton');
const connectButton = document.getElementById('connectButton');
const connectionType = document.getElementById('connectionType');
const constructionHint = document.getElementById('constructionHint');

let width = 0;
let height = 0;
let animationFrame = null;
let autoRun = false;
let mode = 'logical';
let step = 0;
let selectedNeuron = null;
let selectedSource = null;
let construction = false;
let dragging = null;
let dragOffset = { x: 0, y: 0 };
let buildHint = '';
let neuronIdCounter = 1;

const defaultExpression = 'Select a neuron to inspect its logic expression.';
const insights = [
  'This network behaves like a logical AND gate.',
  'Inhibition dominates: one OFF signal cancels all.',
  'Complex behavior emerges from rigid rules.',
  'You are not simulating a brain—you are simulating logic.',
  'A single inhibitory signal overrides all excitation.',
  'Binary neurons are simple, but their connections are not.',
];

const state = {
  neurons: [],
  edges: [],
};

const colors = {
  off: '#4d5465',
  on: '#5fe8ff',
  on2: '#78ff96',
  excitatory: '#5fe8ff',
  inhibitory: '#ff5b7a',
  edgeGlow: 'rgba(95, 232, 255, 0.16)',
};

function resizeCanvas() {
  width = canvas.clientWidth * window.devicePixelRatio;
  height = canvas.clientHeight * window.devicePixelRatio;
  canvas.width = width;
  canvas.height = height;
  drawNetwork();
}

function freshNeuron(x, y, label = '') {
  return {
    id: 'N' + neuronIdCounter++,
    x,
    y,
    radius: 24,
    label,
    threshold: 2,
    lastState: 0,
    state: 0,
    nextState: 0,
    input: label === 'Input' ? 0 : null,
  };
}

function createNetwork(config) {
  state.neurons = [];
  state.edges = [];
  neuronIdCounter = 1;
  selectNeuron(null);
  if (config === 'and') {
    const a = freshNeuron(190, 180, 'Input');
    const b = freshNeuron(190, 380, 'Input');
    const out = freshNeuron(540, 280, 'Output');
    out.threshold = 2;
    state.neurons.push(a, b, out);
    state.edges.push({ from: a.id, to: out.id, type: 'exc' });
    state.edges.push({ from: b.id, to: out.id, type: 'exc' });
    insightText.textContent = 'This network behaves like a logical AND gate.';
  } else if (config === 'or') {
    const a = freshNeuron(190, 170, 'Input');
    const b = freshNeuron(190, 390, 'Input');
    const out = freshNeuron(540, 280, 'Output');
    out.threshold = 1;
    state.neurons.push(a, b, out);
    state.edges.push({ from: a.id, to: out.id, type: 'exc' });
    state.edges.push({ from: b.id, to: out.id, type: 'exc' });
    insightText.textContent = 'This network behaves like a logical OR gate.';
  } else if (config === 'not') {
    const a = freshNeuron(190, 280, 'Input');
    const inv = freshNeuron(540, 280, 'Output');
    inv.threshold = 1;
    state.neurons.push(a, inv);
    state.edges.push({ from: a.id, to: inv.id, type: 'inh' });
    insightText.textContent = 'Inhibition creates logical negation: a single OFF signal cancels the output.';
  } else if (config === 'xor') {
    const a = freshNeuron(140, 160, 'Input');
    const b = freshNeuron(140, 400, 'Input');
    const n1 = freshNeuron(360, 160, '');
    const n2 = freshNeuron(360, 400, '');
    const out = freshNeuron(620, 280, 'Output');
    n1.threshold = 1;
    n2.threshold = 1;
    out.threshold = 1;
    state.neurons.push(a, b, n1, n2, out);
    state.edges.push({ from: a.id, to: n1.id, type: 'exc' });
    state.edges.push({ from: b.id, to: n1.id, type: 'inh' });
    state.edges.push({ from: b.id, to: n2.id, type: 'exc' });
    state.edges.push({ from: a.id, to: n2.id, type: 'inh' });
    state.edges.push({ from: n1.id, to: out.id, type: 'exc' });
    state.edges.push({ from: n2.id, to: out.id, type: 'exc' });
    insightText.textContent = 'XOR uses inhibition and excitation together to produce surprising logic.';
  } else if (config === 'memory') {
    const input = freshNeuron(180, 280, 'Input');
    const loop = freshNeuron(520, 280, 'Memory');
    loop.threshold = 1;
    state.neurons.push(input, loop);
    state.edges.push({ from: input.id, to: loop.id, type: 'exc' });
    state.edges.push({ from: loop.id, to: loop.id, type: 'exc' });
    loop.input = null;
    insightText.textContent = 'A recurrent excitatory loop creates a simple memory unit.';
  } else if (config === 'paradox') {
    const a = freshNeuron(160, 200, 'Input');
    const b = freshNeuron(160, 360, 'Input');
    const mid = freshNeuron(420, 280, '');
    const out = freshNeuron(700, 280, 'Output');
    const inhibitor = freshNeuron(420, 120, 'Input');
    mid.threshold = 1;
    out.threshold = 1;
    state.neurons.push(a, b, inhibitor, mid, out);
    state.edges.push({ from: a.id, to: mid.id, type: 'exc' });
    state.edges.push({ from: b.id, to: mid.id, type: 'exc' });
    state.edges.push({ from: mid.id, to: out.id, type: 'exc' });
    state.edges.push({ from: inhibitor.id, to: out.id, type: 'inh' });
    insightText.textContent = 'A single inhibitory signal overrides all excitation. Logic is not intuitive—it is absolute.';
  }

  state.neurons.forEach((n) => {
    if (n.input === 0) n.state = 0;
    n.lastState = n.state;
    n.nextState = n.state;
  });
  step = 0;
  selectedSource = null;
  updateStepCounter();
  drawNetwork();
}

function updateStepCounter() {
  stepCounter.textContent = step;
}

function toggleRun(active) {
  autoRun = active;
  runToggle.classList.toggle('active', active);
  if (autoRun) runLoop();
}

function toggleMode(active) {
  mode = active ? 'biological' : 'logical';
  modeToggle.classList.toggle('active', active);
  insightText.textContent = active ? 'Biological mode softens the threshold and shows smoother activation.' : 'Logical mode enforces strict McCulloch–Pitts behavior.';
  drawNetwork();
}

function runLoop() {
  if (!autoRun) return;
  stepNetwork();
  setTimeout(runLoop, 500);
}

function getNeuronById(id) {
  return state.neurons.find((node) => node.id === id);
}

function stepNetwork() {
  state.neurons.forEach((neuron) => {
    if (neuron.input !== null) {
      neuron.nextState = neuron.input;
      return;
    }
    const incoming = state.edges.filter((edge) => edge.to === neuron.id);
    const inhibitionActive = incoming.some((edge) => edge.type === 'inh' && getNeuronById(edge.from).state === 1);
    const excitatorySum = incoming.filter((edge) => edge.type === 'exc').reduce((sum, edge) => sum + (getNeuronById(edge.from).state === 1 ? 1 : 0), 0);
    if (mode === 'logical') {
      neuron.nextState = inhibitionActive ? 0 : (excitatorySum >= neuron.threshold ? 1 : 0);
    } else {
      const output = inhibitionActive ? 0 : Math.min(1, excitatorySum / Math.max(1, neuron.threshold));
      neuron.nextState = output >= 0.5 ? 1 : 0;
    }
  });
  state.neurons.forEach((neuron) => {
    neuron.lastState = neuron.state;
    neuron.state = neuron.nextState;
  });
  step += 1;
  updateStepCounter();
  refreshSelectedLogic();
  updateInsight();
  drawNetwork();
}

function updateInsight() {
  const activeInputs = state.neurons.filter((n) => n.label === 'Input' && n.state === 1).length;
  if (state.edges.some((edge) => edge.type === 'inh')) {
    insightText.textContent = 'Inhibition can dominate: if any inhibitory input is active, output can be completely silenced.';
    return;
  }
  if (activeInputs === 0) {
    insightText.textContent = 'No inputs are active; the network remains quiet until a trigger appears.';
    return;
  }
  if (activeInputs === 1) {
    insightText.textContent = 'A single active input can still be enough if thresholds and excitation align.';
    return;
  }
  insightText.textContent = insights[step % insights.length];
}

function drawNetwork() {
  ctx.clearRect(0, 0, width, height);
  ctx.save();
  ctx.scale(window.devicePixelRatio, window.devicePixelRatio);
  ctx.translate(0.5, 0.5);

  state.edges.forEach((edge) => {
    const from = getNeuronById(edge.from);
    const to = getNeuronById(edge.to);
    if (!from || !to) return;
    const isActive = getNeuronById(edge.from).state === 1;
    ctx.strokeStyle = edge.type === 'exc' ? `rgba(95, 232, 255, ${isActive ? 0.95 : 0.3})` : `rgba(255, 91, 122, ${isActive ? 0.95 : 0.25})`;
    ctx.lineWidth = edge.type === 'exc' ? 4 : 3;
    ctx.setLineDash(edge.type === 'inh' ? [8, 10] : []);
    ctx.beginPath();
    ctx.moveTo(from.x, from.y);
    const midX = (from.x + to.x) / 2;
    const ctrlY = from.y < to.y ? from.y - 10 : from.y + 10;
    ctx.quadraticCurveTo(midX, ctrlY, to.x, to.y);
    ctx.stroke();
    if (isActive) {
      ctx.fillStyle = edge.type === 'exc' ? colors.excitatory : colors.inhibitory;
      const pulseX = from.x + (to.x - from.x) * 0.55 + Math.sin(Date.now()/300) * 6;
      const pulseY = from.y + (to.y - from.y) * 0.55 + Math.cos(Date.now()/300) * 6;
      ctx.beginPath();
      ctx.arc(pulseX, pulseY, 4, 0, Math.PI * 2);
      ctx.fill();
    }
  });

  state.neurons.forEach((neuron) => {
    const glow = neuron.state === 1 ? 'rgba(95, 232, 255, 0.24)' : 'rgba(100, 115, 160, 0.1)';
    ctx.fillStyle = neuron.state === 1 ? colors.on : colors.off;
    ctx.shadowColor = glow;
    ctx.shadowBlur = neuron.state === 1 ? 26 : 12;
    ctx.beginPath();
    ctx.arc(neuron.x, neuron.y, neuron.radius, 0, Math.PI * 2);
    ctx.fill();
    ctx.shadowBlur = 0;
    if (selectedSource === neuron) {
      ctx.strokeStyle = '#6bf58c';
      ctx.lineWidth = 5;
    } else {
      ctx.strokeStyle = selectedNeuron === neuron ? '#5fe8ff' : 'rgba(255,255,255,0.12)';
      ctx.lineWidth = selectedNeuron === neuron ? 4 : 1.8;
    }
    ctx.stroke();
    ctx.fillStyle = '#e8f1ff';
    ctx.font = '600 14px Inter, system-ui, sans-serif';
    ctx.textAlign = 'center';
    ctx.textBaseline = 'middle';
    ctx.fillText(neuron.label || neuron.id, neuron.x, neuron.y);
    if (neuron.label === 'Input') {
      ctx.font = '500 11px Inter, system-ui, sans-serif';
      ctx.fillText(neuron.state === 1 ? 'ON' : 'OFF', neuron.x, neuron.y + 22);
    }
  });

  ctx.restore();
}

function findNeuronAt(x, y) {
  return state.neurons.find((neuron) => {
    const dx = neuron.x - x;
    const dy = neuron.y - y;
    return Math.sqrt(dx * dx + dy * dy) <= neuron.radius + 6;
  });
}

function addNeuron(label = '') {
  state.neurons.push(freshNeuron(220 + Math.random() * 420, 160 + Math.random() * 380, label));
  drawNetwork();
}

function removeSelectedNeuron() {
  if (!selectedNeuron) return;
  const id = selectedNeuron.id;
  state.neurons = state.neurons.filter((neuron) => neuron.id !== id);
  state.edges = state.edges.filter((edge) => edge.from !== id && edge.to !== id);
  selectNeuron(null);
  drawNetwork();
}

function setConnectTarget(neuron) {
  if (!selectedSource) {
    selectedSource = neuron;
    constructionHint.textContent = `Source selected: ${neuron.id}. Now click a target node to connect.`;
    return;
  }
  if (selectedSource === neuron) {
    selectedSource = null;
    constructionHint.textContent = 'Connection canceled. Select a source neuron again.';
    drawNetwork();
    return;
  }
  state.edges.push({ from: selectedSource.id, to: neuron.id, type: connectionType.value });
  constructionHint.textContent = `${connectionType.value === 'exc' ? 'Excitatory' : 'Inhibitory'} connection created from ${selectedSource.id} to ${neuron.id}.`;
  selectedSource = null;
  drawNetwork();
}

function resetConnectionSelection() {
  selectedSource = null;
  constructionHint.textContent = 'Construction mode active: drag nodes and connect them.';
}

addNeuronButton.addEventListener('click', () => addNeuron());
addInputButton.addEventListener('click', () => addNeuron('Input'));
removeNeuronButton.addEventListener('click', removeSelectedNeuron);
connectButton.addEventListener('click', () => {
  if (!selectedSource || !selectedNeuron || selectedSource === selectedNeuron) {
    constructionHint.textContent = 'Select two different neurons before connecting them.';
    return;
  }
  state.edges.push({ from: selectedSource.id, to: selectedNeuron.id, type: connectionType.value });
  constructionHint.textContent = `${connectionType.value === 'exc' ? 'Excitatory' : 'Inhibitory'} connection created from ${selectedSource.id} to ${selectedNeuron.id}.`;
  selectedSource = null;
  drawNetwork();
});

function toCanvasCoordinates(event) {
  const rect = canvas.getBoundingClientRect();
  return {
    x: (event.clientX - rect.left),
    y: (event.clientY - rect.top),
  };
}

canvas.addEventListener('pointerdown', (event) => {
  const pos = toCanvasCoordinates(event);
  const neuron = findNeuronAt(pos.x, pos.y);
  if (!neuron) return;
  if (construction) {
    if (selectedSource && selectedSource !== neuron) {
      setConnectTarget(neuron);
      return;
    }
    if (!selectedSource) {
      selectedSource = neuron;
      constructionHint.textContent = `Source selected: ${neuron.id}. Now click a target node to connect.`;
    }
    dragging = neuron;
    dragOffset.x = neuron.x - pos.x;
    dragOffset.y = neuron.y - pos.y;
    return;
  }
  if (neuron.label === 'Input') {
    neuron.input = neuron.input === 1 ? 0 : 1;
    neuron.state = neuron.input;
    drawNetwork();
    refreshSelectedLogic();
    return;
  }
  selectNeuron(neuron);
});

canvas.addEventListener('pointermove', (event) => {
  if (!dragging) return;
  const pos = toCanvasCoordinates(event);
  dragging.x = pos.x + dragOffset.x;
  dragging.y = pos.y + dragOffset.y;
  drawNetwork();
});

canvas.addEventListener('pointerup', () => {
  dragging = null;
});

function selectNeuron(neuron) {
  selectedNeuron = neuron;
  if (!neuron) {
    selectedId.textContent = 'None';
    selectedState.textContent = '—';
    liveExpression.textContent = defaultExpression;
    return;
  }
  selectedId.textContent = neuron.id;
  selectedState.textContent = neuron.state === 1 ? 'ON' : 'OFF';
  thresholdSlider.value = neuron.threshold;
  thresholdValue.textContent = neuron.threshold;
  refreshSelectedLogic();
}

function refreshSelectedLogic() {
  if (!selectedNeuron) return;
  selectedState.textContent = selectedNeuron.state === 1 ? 'ON' : 'OFF';
  const expression = buildExpression(selectedNeuron);
  liveExpression.textContent = expression;
}

function buildExpression(neuron) {
  const incoming = state.edges.filter((edge) => edge.to === neuron.id);
  if (incoming.length === 0) return 'No inputs. Static node.';
  const excitations = incoming.filter((edge) => edge.type === 'exc').map((edge) => getNeuronById(edge.from).id);
  const inhibitions = incoming.filter((edge) => edge.type === 'inh').map((edge) => getNeuronById(edge.from).id);
  const excText = excitations.length ? excitations.join(' AND ') : '0';
  const inhText = inhibitions.length ? 'NOT(' + inhibitions.join(' OR ') + ')' : '';
  const thresholdText = neuron.threshold > 1 ? ` threshold ≥ ${neuron.threshold}` : '';
  if (inhText) {
    return `Fires if: (${excText}) AND ${inhText}${thresholdText}`;
  }
  return `Fires if: (${excText})${thresholdText}`;
}

thresholdSlider.addEventListener('input', () => {
  thresholdValue.textContent = thresholdSlider.value;
  if (selectedNeuron) {
    selectedNeuron.threshold = Number(thresholdSlider.value);
    refreshSelectedLogic();
    drawNetwork();
  }
});

stepButton.addEventListener('click', () => stepNetwork());
resetButton.addEventListener('click', () => createNetwork(currentConfig));
runToggle.addEventListener('click', () => toggleRun(!autoRun));
modeToggle.addEventListener('click', () => toggleMode(mode === 'logical'));
constructionMode.addEventListener('change', () => {
  construction = constructionMode.checked;
  selectedSource = null;
  dragging = null;
  constructionHint.textContent = construction ? 'Construction mode active: drag nodes and connect them.' : 'Click input nodes in the canvas to toggle ON/OFF. Turn on construction mode to drag nodes and connect them.';
});

let currentConfig = 'and';

buildButtons.forEach((button) => {
  button.addEventListener('click', () => {
    currentConfig = button.dataset.build;
    createNetwork(currentConfig);
  });
});

window.addEventListener('resize', resizeCanvas);

function init() {
  resizeCanvas();
  createNetwork('and');
  animate();
}

function animate() {
  drawNetwork();
  animationFrame = requestAnimationFrame(animate);
}

init();
</script>
</body>
</html>
