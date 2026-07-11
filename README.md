import React, { useState } from "react";
import {
  Eye,
  Users,
  Star,
  GraduationCap,
  Code2,
  Sparkles,
  Zap,
  Target,
  Github,
  Linkedin,
  Mail,
  MessageCircle,
  ExternalLink,
  Moon,
} from "lucide-react";

/* ---------- design tokens ----------
  bg gradient   : #030712 -> #0a0f24
  neon blue     : #22d3ee
  neon magenta  : #d946ef
  neon violet   : #7c3aed
  text          : #f5f6fb
  muted text    : #93a0c2
  card surface  : rgba(255,255,255,0.04)
  card border   : rgba(148,163,255,0.18)
------------------------------------- */

const glowCard = {
  background: "rgba(255,255,255,0.035)",
  border: "1px solid rgba(148,163,255,0.16)",
  backdropFilter: "blur(14px)",
  WebkitBackdropFilter: "blur(14px)",
  boxShadow: "0 0 0 1px rgba(255,255,255,0.02), 0 20px 60px -25px rgba(124,58,237,0.35)",
};

function Card({ children, className = "", style = {}, hover = true, ...rest }) {
  return (
    <div
      className={
        "rounded-2xl transition-all duration-300 " +
        (hover ? "hover:-translate-y-1 hover:shadow-2xl " : "") +
        className
      }
      style={{ ...glowCard, ...style }}
      {...rest}
    >
      {children}
    </div>
  );
}

function Tag({ children }) {
  return (
    <span
      className="text-xs px-2.5 py-1 rounded-full font-medium"
      style={{
        color: "#c4b5fd",
        background: "rgba(124,58,237,0.12)",
        border: "1px solid rgba(124,58,237,0.35)",
      }}
    >
      {children}
    </span>
  );
}

function SectionHeading({ eyebrow, title }) {
  return (
    <div className="mb-10 text-center">
      <div
        className="inline-flex items-center gap-2 text-xs tracking-[0.3em] uppercase mb-3 font-semibold"
        style={{ color: "#22d3ee" }}
      >
        <span
          className="h-px w-8"
          style={{ background: "linear-gradient(90deg, transparent, #22d3ee)" }}
        />
        {eyebrow}
        <span
          className="h-px w-8"
          style={{ background: "linear-gradient(90deg, #22d3ee, transparent)" }}
        />
      </div>
      <h2
        className="text-3xl md:text-4xl font-bold"
        style={{
          color: "#f5f6fb",
          textShadow: "0 0 30px rgba(217,70,239,0.25)",
        }}
      >
        {title}
      </h2>
    </div>
  );
}

const stats = [
  { label: "Profile Views", value: "—", icon: Eye, color: "#22d3ee" },
  { label: "Followers", value: "—", icon: Users, color: "#d946ef" },
  { label: "Total Stars", value: "—", icon: Star, color: "#facc15" },
];

const techGroups = [
  { title: "Languages", items: ["Java", "Python", "JavaScript"], glow: "#22d3ee" },
  { title: "Frontend", items: ["HTML", "CSS", "React", "Bootstrap"], glow: "#d946ef" },
  { title: "Backend", items: ["Spring Boot", "Node.js"], glow: "#7c3aed" },
  { title: "Database", items: ["MySQL", "SQLite"], glow: "#22d3ee" },
  { title: "Tools", items: ["Git", "GitHub", "VS Code", "Eclipse"], glow: "#d946ef" },
  { title: "Cloud", items: ["AWS"], glow: "#7c3aed" },
];

const projects = [
  {
    title: "Web-Based Emotion Detection",
    desc: "Real-time facial emotion analysis using deep learning, TensorFlow & DeepFace, with a Flask backend, SQLite database and PDF report generation.",
    tags: ["Python", "TensorFlow", "OpenCV", "Flask"],
    repo: "https://github.com/Dnyaneshwar0302/Web-Based-Emotion-Detection-",
    hue: "linear-gradient(135deg, #22d3ee33, #7c3aed33)",
    ring: "#22d3ee",
  },
  {
    title: "Online Examination System",
    desc: "Full-stack exam platform with a React frontend, Spring Boot backend, MySQL database, secure authentication and AI-based evaluation features.",
    tags: ["React", "Spring Boot", "MySQL"],
    repo: "https://github.com/Dnyaneshwar0302",
    hue: "linear-gradient(135deg, #d946ef33, #22d3ee33)",
    ring: "#d946ef",
  },
  {
    title: "TaskBuddy React",
    desc: "A modern, responsive task manager built with React — full CRUD, dark/light mode, Framer Motion animations & dynamic progress tracking.",
    tags: ["React", "Framer Motion", "JavaScript"],
    repo: "https://github.com/Dnyaneshwar0302/TaskBuddy-React",
    hue: "linear-gradient(135deg, #7c3aed33, #d946ef33)",
    ring: "#7c3aed",
  },
  {
    title: "Cafe Management System",
    desc: "A Python-based cafe management system with order handling and billing features for smooth day-to-day cafe operations.",
    tags: ["Python"],
    repo: "https://github.com/Dnyaneshwar0302/Cafe-Management-System-",
    hue: "linear-gradient(135deg, #22d3ee33, #d946ef33)",
    ring: "#22d3ee",
  },
  {
    title: "Simple Bank Account System",
    desc: "A Java project demonstrating object-oriented principles, especially encapsulation, through a simple bank account system.",
    tags: ["Java"],
    repo: "https://github.com/Dnyaneshwar0302/Simple-Bank-Account-System",
    hue: "linear-gradient(135deg, #d946ef33, #7c3aed33)",
    ring: "#d946ef",
  },
  {
    title: "Front-End Code",
    desc: "My very first hosted HTML page — the starting point of my frontend development journey.",
    tags: ["HTML5"],
    repo: "https://github.com/Dnyaneshwar0302/Front-End-Code",
    hue: "linear-gradient(135deg, #7c3aed33, #22d3ee33)",
    ring: "#7c3aed",
  },
];

const GH_USER = "Dnyaneshwar0302";

const statWidgets = [
  {
    title: "GitHub Overview",
    accent: "#22d3ee",
    img: `https://github-readme-stats.vercel.app/api?username=${GH_USER}&show_icons=true&theme=radical&hide_border=true&bg_color=00000000&title_color=22d3ee&icon_color=d946ef&text_color=dfe4f5`,
  },
  {
    title: "Top Languages",
    accent: "#d946ef",
    img: `https://github-readme-stats.vercel.app/api/top-langs/?username=${GH_USER}&layout=compact&theme=radical&hide_border=true&bg_color=00000000&title_color=22d3ee&text_color=dfe4f5`,
  },
  {
    title: "Streak Stats",
    accent: "#facc15",
    img: `https://streak-stats.demolab.com/?user=${GH_USER}&theme=radical&hide_border=true&background=00000000&stroke=22d3ee&ring=d946ef&fire=facc15&currStreakLabel=22d3ee`,
  },
  {
    title: "Contribution Snake",
    accent: "#7c3aed",
    img: `https://raw.githubusercontent.com/${GH_USER}/${GH_USER}/output/github-snake-dark.svg`,
  },
  {
    title: "Activity Graph",
    accent: "#22d3ee",
    img: `https://github-readme-activity-graph.vercel.app/graph?username=${GH_USER}&theme=react-dark&hide_border=true&bg_color=00000000&color=22d3ee&line=d946ef&point=facc15`,
  },
  {
    title: "GitHub Trophies",
    accent: "#d946ef",
    img: `https://github-profile-trophy.vercel.app/?username=${GH_USER}&theme=radical&no-frame=true&no-bg=true&margin-w=10&row=1`,
  },
];

const connects = [
  {
    label: "LinkedIn",
    sub: "/in/dnyaneshwar-sawale-b2a619309",
    href: "https://www.linkedin.com/in/dnyaneshwar-sawale-b2a619309",
    icon: Linkedin,
    accent: "#22d3ee",
  },
  {
    label: "GitHub",
    sub: "/Dnyaneshwar0302",
    href: "https://github.com/Dnyaneshwar0302",
    icon: Github,
    accent: "#d946ef",
  },
  {
    label: "Email",
    sub: "dnyaneshwarsawale997@gmail.com",
    href: "mailto:dnyaneshwarsawale997@gmail.com",
    icon: Mail,
    accent: "#7c3aed",
  },
  {
    label: "WhatsApp",
    sub: "+91 6361873025",
    href: "https://wa.me/916361873025",
    icon: MessageCircle,
    accent: "#facc15",
  },
];

const aboutPoints = [
  { icon: GraduationCap, text: "BE in Artificial Intelligence & Data Science" },
  { icon: Code2, text: "Passionate Java Full Stack Developer" },
  { icon: Sparkles, text: "Currently learning Spring Boot" },
  { icon: Zap, text: "Love solving DSA & building real-world projects" },
  { icon: Target, text: "Goal: Java Full Stack Developer & AI/Data Science Professional" },
];

function Stars({ count = 60 }) {
  const dots = Array.from({ length: count });
  return (
    <div className="absolute inset-0 overflow-hidden pointer-events-none">
      {dots.map((_, i) => {
        const size = Math.random() < 0.85 ? 1 : 2;
        return (
          <span
            key={i}
            className="absolute rounded-full"
            style={{
              top: `${Math.random() * 100}%`,
              left: `${Math.random() * 100}%`,
              width: size,
              height: size,
              background: "#e6ecff",
              opacity: Math.random() * 0.6 + 0.2,
              boxShadow: size === 2 ? "0 0 4px rgba(230,236,255,0.8)" : "none",
            }}
          />
        );
      })}
    </div>
  );
}

export default function DevPortfolio() {
  const [hoveredProject, setHoveredProject] = useState(null);

  return (
    <div
      className="min-h-screen w-full relative"
      style={{
        background: "linear-gradient(180deg, #030712 0%, #0a0f24 55%, #050814 100%)",
        fontFamily:
          "'Inter', ui-sans-serif, system-ui, -apple-system, 'Segoe UI', sans-serif",
        color: "#f5f6fb",
      }}
    >
      <Stars count={90} />

      {/* ambient glow blobs */}
      <div
        className="absolute -top-40 -left-40 w-96 h-96 rounded-full pointer-events-none"
        style={{ background: "#7c3aed", opacity: 0.18, filter: "blur(120px)" }}
      />
      <div
        className="absolute top-20 -right-32 w-96 h-96 rounded-full pointer-events-none"
        style={{ background: "#22d3ee", opacity: 0.14, filter: "blur(140px)" }}
      />
      <div
        className="absolute bottom-0 left-1/3 w-96 h-96 rounded-full pointer-events-none"
        style={{ background: "#d946ef", opacity: 0.1, filter: "blur(140px)" }}
      />

      <div className="relative max-w-6xl mx-auto px-6 py-16 md:py-24">
        {/* ---------------- HEADER ---------------- */}
        <header className="grid lg:grid-cols-[1fr_300px] gap-10 items-start mb-28">
          <div className="flex flex-col md:flex-row gap-8 items-center md:items-start">
            {/* avatar */}
            <div className="relative shrink-0">
              <div
                className="absolute inset-0 rounded-full"
                style={{
                  background: "conic-gradient(from 90deg, #22d3ee, #d946ef, #7c3aed, #22d3ee)",
                  filter: "blur(18px)",
                  opacity: 0.75,
                }}
              />
              <div
                className="relative w-36 h-36 md:w-40 md:h-40 rounded-full p-[3px]"
                style={{
                  background: "conic-gradient(from 90deg, #22d3ee, #d946ef, #7c3aed, #22d3ee)",
                }}
              >
                <div
                  className="w-full h-full rounded-full flex items-center justify-center"
                  style={{ background: "#0a0f24" }}
                >
                  <Moon size={44} style={{ color: "#c4b5fd" }} strokeWidth={1.5} />
                </div>
              </div>
            </div>

            <div className="text-center md:text-left">
              <div className="flex items-center justify-center md:justify-start gap-2 mb-2">
                <span style={{ color: "#facc15" }}>👋</span>
                <span className="text-sm" style={{ color: "#93a0c2" }}>
                  Hi there!
                </span>
              </div>
              <h1 className="text-4xl md:text-5xl font-extrabold leading-tight mb-4">
                I'm{" "}
                <span
                  style={{
                    background: "linear-gradient(90deg, #22d3ee, #d946ef)",
                    WebkitBackgroundClip: "text",
                    WebkitTextFillColor: "transparent",
                    textShadow: "0 0 40px rgba(217,70,239,0.25)",
                  }}
                >
                  Dnyaneshwar Sawale
                </span>
              </h1>

              <div className="flex flex-wrap gap-2 justify-center md:justify-start mb-4">
                <Tag>Frontend Developer</Tag>
                <Tag>AI &amp; Data Science Engineer</Tag>
              </div>

              <p
                className="max-w-md text-sm md:text-base leading-relaxed"
                style={{ color: "#93a0c2" }}
              >
                BE student in Artificial Intelligence &amp; Data Science, building
                real-world applications with Java, React and Spring Boot.
              </p>
            </div>
          </div>

          {/* floating stat cards */}
          <div className="flex flex-row lg:flex-col gap-4">
            {stats.map(({ label, value, icon: Icon, color }) => (
              <Card key={label} className="flex-1 px-5 py-4 flex items-center gap-4">
                <div
                  className="w-10 h-10 rounded-xl flex items-center justify-center shrink-0"
                  style={{
                    background: `${color}1a`,
                    border: `1px solid ${color}55`,
                  }}
                >
                  <Icon size={18} style={{ color }} />
                </div>
                <div>
                  <div className="text-lg font-bold" style={{ color: "#f5f6fb" }}>
                    {value}
                  </div>
                  <div className="text-xs" style={{ color: "#93a0c2" }}>
                    {label}
                  </div>
                </div>
              </Card>
            ))}
          </div>
        </header>

        {/* ---------------- ABOUT ---------------- */}
        <section className="mb-28">
          <SectionHeading eyebrow="Get to know me" title="🌙 About Me" />
          <div className="grid md:grid-cols-2 gap-8 items-stretch">
            <Card className="p-8">
              <ul className="space-y-5">
                {aboutPoints.map(({ icon: Icon, text }, i) => (
                  <li key={i} className="flex items-start gap-4">
                    <div
                      className="w-9 h-9 rounded-lg flex items-center justify-center shrink-0 mt-0.5"
                      style={{
                        background: "rgba(34,211,238,0.1)",
                        border: "1px solid rgba(34,211,238,0.35)",
                      }}
                    >
                      <Icon size={16} style={{ color: "#22d3ee" }} />
                    </div>
                    <span className="text-sm md:text-base pt-1.5" style={{ color: "#dfe4f5" }}>
                      {text}
                    </span>
                  </li>
                ))}
              </ul>
            </Card>

            {/* illustrated moonlit room card, built with layered CSS gradients */}
            <Card className="relative overflow-hidden min-h-[280px]" hover={false}>
              <div
                className="absolute inset-0"
                style={{
                  background:
                    "linear-gradient(180deg, #0b1230 0%, #141b3e 55%, #1c2450 100%)",
                }}
              />
              <Stars count={40} />
              {/* moon */}
              <div
                className="absolute rounded-full"
                style={{
                  top: 28,
                  right: 40,
                  width: 64,
                  height: 64,
                  background: "radial-gradient(circle at 35% 35%, #fff, #d6e6ff 60%, #9db4e8 100%)",
                  boxShadow: "0 0 50px 12px rgba(214,230,255,0.55)",
                }}
              />
              {/* mountains */}
              <svg
                className="absolute bottom-0 left-0 w-full"
                viewBox="0 0 400 120"
                preserveAspectRatio="none"
                height="120"
              >
                <polygon points="0,120 0,70 60,30 130,80 200,20 280,75 340,45 400,90 400,120" fill="#141a3a" />
                <polygon points="0,120 0,95 90,55 180,95 260,60 340,100 400,80 400,120" fill="#0d1230" />
              </svg>
              <div className="absolute bottom-4 left-4 right-4 text-center">
                <span
                  className="text-xs tracking-widest uppercase"
                  style={{ color: "#93a0c2" }}
                >
                  night sessions, calm focus, steady progress
                </span>
              </div>
            </Card>
          </div>
        </section>

        {/* ---------------- TECH STACK ---------------- */}
        <section className="mb-28">
          <SectionHeading eyebrow="What I work with" title="🛠️ Tech Stack" />
          <div className="grid grid-cols-2 md:grid-cols-3 gap-5">
            {techGroups.map((g) => (
              <Card key={g.title} className="p-5" style={{}}>
                <div
                  className="text-xs font-semibold tracking-wider uppercase mb-4 flex items-center gap-2"
                  style={{ color: g.glow }}
                >
                  <span
                    className="w-1.5 h-1.5 rounded-full"
                    style={{ background: g.glow, boxShadow: `0 0 8px ${g.glow}` }}
                  />
                  {g.title}
                </div>
                <div className="flex flex-wrap gap-2">
                  {g.items.map((item) => (
                    <span
                      key={item}
                      className="flex items-center gap-1.5 text-xs font-medium px-3 py-1.5 rounded-lg"
                      style={{
                        background: `${g.glow}14`,
                        border: `1px solid ${g.glow}45`,
                        color: "#eef1ff",
                      }}
                    >
                      <Code2 size={12} style={{ color: g.glow }} />
                      {item}
                    </span>
                  ))}
                </div>
              </Card>
            ))}
          </div>
        </section>

        {/* ---------------- PROJECTS ---------------- */}
        <section className="mb-28">
          <SectionHeading eyebrow="What I've built" title="🚀 My Projects" />
          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
            {projects.map((p) => (
              <Card
                key={p.title}
                className="overflow-hidden flex flex-col"
                onMouseEnter={() => setHoveredProject(p.title)}
                onMouseLeave={() => setHoveredProject(null)}
                style={{
                  ...glowCard,
                  boxShadow:
                    hoveredProject === p.title
                      ? `0 0 0 1px ${p.ring}55, 0 25px 60px -20px ${p.ring}66`
                      : glowCard.boxShadow,
                }}
              >
                <div
                  className="h-28 flex items-center justify-center relative"
                  style={{ background: p.hue }}
                >
                  <Code2 size={28} style={{ color: p.ring, opacity: 0.9 }} />
                  <div
                    className="absolute inset-0"
                    style={{
                      background:
                        "linear-gradient(180deg, transparent 40%, rgba(3,7,18,0.6) 100%)",
                    }}
                  />
                </div>
                <div className="p-5 flex flex-col flex-1">
                  <h3 className="font-semibold text-base mb-2" style={{ color: "#f5f6fb" }}>
                    {p.title}
                  </h3>
                  <p className="text-xs leading-relaxed mb-4 flex-1" style={{ color: "#93a0c2" }}>
                    {p.desc}
                  </p>
                  <div className="flex flex-wrap gap-2 mb-5">
                    {p.tags.map((t) => (
                      <Tag key={t}>{t}</Tag>
                    ))}
                  </div>
                  <a
                    href={p.repo}
                    target="_blank"
                    rel="noreferrer"
                    className="inline-flex items-center justify-center gap-2 text-xs font-semibold py-2.5 rounded-xl transition-all duration-200 hover:brightness-125"
                    style={{
                      background: `linear-gradient(90deg, ${p.ring}, #7c3aed)`,
                      color: "#030712",
                    }}
                  >
                    <Github size={14} /> View on GitHub
                  </a>
                </div>
              </Card>
            ))}
          </div>
        </section>

        {/* ---------------- GITHUB STATS ---------------- */}
        <section className="mb-28">
          <SectionHeading eyebrow="Live from GitHub" title="📊 GitHub Stats" />
          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-5">
            {statWidgets.map((w) => (
              <Card key={w.title} className="p-5">
                <div className="flex items-center gap-2 mb-4">
                  <span
                    className="w-2 h-2 rounded-full"
                    style={{ background: w.accent, boxShadow: `0 0 8px ${w.accent}` }}
                  />
                  <span className="text-xs font-semibold tracking-wide" style={{ color: "#dfe4f5" }}>
                    {w.title}
                  </span>
                </div>
                <div
                  className="rounded-lg flex items-center justify-center overflow-hidden p-2 min-h-[110px]"
                  style={{
                    background: "rgba(255,255,255,0.02)",
                    border: `1px solid ${w.accent}33`,
                  }}
                >
                  <img
                    src={w.img}
                    alt={w.title}
                    className="max-w-full"
                    style={{ filter: `drop-shadow(0 0 12px ${w.accent}33)` }}
                    onError={(e) => {
                      e.currentTarget.style.display = "none";
                      e.currentTarget.nextSibling.style.display = "block";
                    }}
                  />
                  <span
                    className="hidden text-[10px] tracking-wider uppercase text-center"
                    style={{ color: "#5b6690" }}
                  >
                    loads live from GitHub once published
                  </span>
                </div>
              </Card>
            ))}
          </div>
        </section>

        {/* ---------------- CONNECT ---------------- */}
        <section className="mb-16">
          <SectionHeading eyebrow="Let's talk" title="📫 Connect With Me" />
          <div className="grid sm:grid-cols-2 lg:grid-cols-4 gap-5">
            {connects.map(({ label, sub, href, icon: Icon, accent }) => (
              <a
                key={label}
                href={href}
                target="_blank"
                rel="noopener noreferrer"
                onClick={(e) => {
                  e.preventDefault();
                  if (href.startsWith("mailto:")) {
                    window.location.href = href;
                  } else {
                    window.open(href, "_blank", "noopener,noreferrer");
                  }
                }}
                className="block cursor-pointer"
              >
                <Card
                  className="p-5 flex flex-col items-center text-center gap-3 h-full hover:scale-[1.03]"
                  style={{ cursor: "pointer" }}
                >
                  <div
                    className="w-12 h-12 rounded-xl flex items-center justify-center"
                    style={{ background: `${accent}1a`, border: `1px solid ${accent}55` }}
                  >
                    <Icon size={20} style={{ color: accent }} />
                  </div>
                  <div>
                    <div className="text-sm font-semibold" style={{ color: "#f5f6fb" }}>
                      {label}
                    </div>
                    <div className="text-[11px] break-all mt-1" style={{ color: "#7783a8" }}>
                      {sub}
                    </div>
                  </div>
                </Card>
              </a>
            ))}
          </div>
        </section>

        {/* ---------------- FOOTER ---------------- */}
        <footer className="text-center pt-10" style={{ borderTop: "1px solid rgba(148,163,255,0.12)" }}>
          <p
            className="italic text-sm md:text-base mb-3"
            style={{ color: "#c4b5fd" }}
          >
            "Code. Learn. Build. Repeat."
          </p>
          <p className="text-xs" style={{ color: "#5b6690" }}>
            © {new Date().getFullYear()} Dnyaneshwar Sawale — built with <ExternalLink size={10} className="inline" /> late nights and lots of coffee
          </p>
        </footer>
      </div>
    </div>
  );
}
